---
title: API för beslutsmigrering
description: Lär dig hur du använder API:t för beslutsmigreringstjänsten för att migrera beslutshanteringsobjekt mellan sandlådor med automatisk beroendeupplösning och återställningsstöd.
feature: Decisioning
topic: Integrations
role: Developer
level: Experienced
exl-id: 3ec084ca-af9e-4b5e-b66f-ec390328a9d6
source-git-commit: aca4e62faa7aa09a60eef661c0732a8b0b1fa36e
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 0%

---

# API för beslutsmigrering {#decisioning-migration-api}

Med API:t för migreringstjänsten för beslut kan du migrera beslutshanteringsobjekt från en sandlåda till en annan. Migreringsprocessen körs som asynkrona arbetsflöden som innehåller beroendeanalys, körning och valfria återställningsfunktioner.

Med detta API kan du smidigt övergå ditt beslutsinnehåll mellan miljöer <!--(e.g., from development to staging, or staging to production) --> samtidigt som dataintegritet och relationer bevaras.

Om du vill veta mer om fördelarna och möjligheterna med att fatta beslut jämfört med att hantera beslut kan du läsa [den här sidan](migrate-to-decisioning.md).

## Funktioner {#capabilities}

API:t för beslutsmigreringstjänsten innehåller följande funktioner:

* **Beroendeanalys** - Identifiera alla nödvändiga beroenden mellan käll- och målsandlådor, inklusive attribut, segment och datauppsättningskrav.
* **Flexibelt migreringsomfång** - Kör migreringar på sandlåda, erbjudande eller beslutsnivå baserat på dina behov.
* **Återställningsstöd** - Återställ en slutförd migrering om problem upptäcks under valideringen.

## Förhandskrav {#prerequisites}

### Nödvändiga behörigheter {#permissions}

Om du vill använda migrerings-API:t måste du ha rätt behörigheter i både käll- och målsandlådan:

**Source-sandlåda** - Läsåtkomst till beslutshanteringsobjekt

**Målsandlåda** - Skapa och redigera åtkomst till beslutsobjekt

Vanliga behörigheter är:

* Hantera/visa beslut
* Hantera/visa beslut
* Hantera erbjudanden
* Hantera rankningsstrategier
* Hantera kampanjer (om du migrerar kampanjrelaterade artefakter)
* Hantera/visa datastreams (om du skapar ett datastream)
* Hantera/visa scheman

>[!NOTE]
>
>Lär dig hur du tilldelar beslutsbehörigheter i [det här avsnittet](gs-experience-decisioning.md#steps). En fullständig lista över behörigheter finns på sidan [Inbyggda behörigheter](../administration/ootb-permissions.md#ootb-permissions).

### Förbered målsandlådan {#target-sandbox-preparation}

Kontrollera att målsandlådan är korrekt konfigurerad innan du kör en migrering:

* **Attribut** - Verifiera att nödvändiga profilattribut och kontextattribut finns i målsandlådan, eller förbered mappningar för dem.
* **Segment** - Kontrollera att nödvändiga segment finns i målsandlådan, eller planera för att mappa dem med namnutrymme och ID.
* **Datauppsättning** - Identifiera ett datauppsättningsnamn som ska användas för migreringen (`dependency.datasetName`).
* **Datastream** - Bestäm om migreringen ska skapa ett datastream (`createDataStream`).

Mer information om sandlådehantering finns i [Använda och tilldela sandlådor](../administration/sandboxes.md).

## Grunderna i API {#api-basics}

### Bas-URL {#base-url}

Använd följande bas-URL:

* **Produktion**: `https://decisioning-migration.adobe.io`
  <!--* **Staging**: `https://decisioning-migration-stage.adobe.io`-->

### Autentisering {#authentication}

Alla API-begäranden kräver följande rubriker:

* `Authorization: Bearer <IMS_ACCESS_TOKEN>`
* `x-gw-ims-org-id: <IMS_ORG_ID>`
* `Content-Type: application/json`

Detaljerade instruktioner om hur du konfigurerar autentisering finns i [Journey Optimizer-autentiseringsguiden](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"}.

### Arbetsflödesmodell {#workflow-model}

Varje API-anrop skapar eller hämtar en arbetsflödesresurs. Arbetsflöden är asynkrona åtgärder som spårar förloppet och resultaten av migreringsåtgärder.

Ett arbetsflöde har följande egenskaper:

* `id` - Unik identifierare för arbetsflöde (UUID)
* `status` - Aktuell arbetsflödesstatus: `New`, `Running`, `Completed` eller `Failed`
* `result` - Arbetsflödets utdata när det är klart (inkluderar migreringsresultat och varningar)
* `errors` - Strukturerad felinformation vid fel
* `_links.self` - Arbetsflödes-URL för att hämta status
  <!--* `_etag` - Version identifier used for delete operations (service users only)-->

## Arbetsflöde för migrering {#migration-workflow}

Migreringsprocessen består av två huvudsteg: analysera beroenden och köra migreringen. Följ de här stegen för att säkerställa en lyckad migrering.

### Steg 1: Analysera beroenden {#analyze-dependencies}

Innan du migrerar använder du beroendearbetsflödet för att identifiera vad som behöver mappas från Beslutshantering till Beslutsfattning i målsandlådan. Den här analysen hjälper dig att förstå relationerna mellan objekt och förbereda nödvändiga mappningar.

#### Skapa ett beroendearbetsflöde {#create-dependency-workflow}

Använd följande API-anrop för att skapa ett arbetsflöde för beroendeanalys.

**API-format**

```http
POST /workflows/generate-dependencies
```

**Beroende på sandlådenivå (rekommenderas först)**

Börja med en analys på sandlådenivå för att få en fullständig bild av alla beroenden:

```shell
curl --request POST \
  --url "https://decisioning-migration.adobe.io/workflows/generate-dependencies" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>" \
  --header "Content-Type: application/json" \
  --data '{
    "imsOrgId": "<IMS_ORG_ID>",
    "sourceSandboxDetails": { "sandboxName": "<SOURCE_SANDBOX_NAME>" },
    "targetSandboxDetails": { "sandboxName": "<TARGET_SANDBOX_NAME>" },
    "requestLevel": "sandbox"
  }'
```

**Beroende på erbjudandenivå**

Om du bara vill analysera beroenden för specifika erbjudanden anger du `requestLevel: "offer"` och tillhandahåller en `offersList`-matris med de erbjudande-ID som du vill analysera.

**Beroende på beslutsnivå**

Om du bara vill analysera beroenden för specifika beslut anger du `requestLevel: "decision"` och tillhandahåller en `decisionsList`-matris med de beslut-ID som du vill analysera.

#### Kontrollera arbetsflödesstatus för beroende {#poll-dependency-status}

Avsök beroendearbetsflödet för att kontrollera när analysen är klar.

**API-format**

```http
GET /workflows/generate-dependencies/{id}
```

**Begäran**

```shell
curl --request GET \
  --url "https://decisioning-migration.adobe.io/workflows/generate-dependencies/<WORKFLOW_ID>" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>"
```

När fältet `status` visar `Completed` är beroendeanalysen klar. Använd arbetsflödets utdata för att skapa dina migreringsberoendemappningar:

* **profileAttributes** - Mappar källprofilattribut till målprofilattribut
* **contextAttributes** - Mappar källkontextattribut till målkontextattribut
* **segment** - Mappar källsegmentnycklar till målsegmentidentifierare (`{namespace, id}`)
* **datasetName** - Anger måldatamängdens namn för migreringen

### Steg 2: Utför migreringen {#execute-migration}

När du har analyserat beroendena och förberett mappningarna kan du utföra migreringen.

#### Skapa ett migreringsarbetsflöde {#create-migration-workflow}

Använd beroendemappningarna från steg 1 för att konfigurera och köra din migrering.

**API-format**

```http
POST /workflows/migration
```

**Migrering på sandlådenivå**

Så här migrerar du alla beslutsobjekt från en sandlåda till en annan:

```shell
curl --request POST \
  --url "https://decisioning-migration.adobe.io/workflows/migration" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>" \
  --header "Content-Type: application/json" \
  --data '{
    "imsOrgId": "<IMS_ORG_ID>",
    "sourceSandboxDetails": { "sandboxName": "<SOURCE_SANDBOX_NAME>" },
    "targetSandboxDetails": { "sandboxName": "<TARGET_SANDBOX_NAME>" },
    "createDataStream": true,
    "dependency": {
      "profileAttributes": {
        "sourceAttr1": "targetAttr1"
      },
      "segments": {
        "sourceSegmentKey1": {
          "namespace": "<TARGET_SEGMENT_NAMESPACE>",
          "id": "<TARGET_SEGMENT_ID>"
        }
      },
      "contextAttributes": {
        "sourceCtx1": "targetCtx1"
      },
      "datasetName": "<TARGET_DATASET_NAME>"
    },
    "requestLevel": "sandbox"
  }'
```

**Migrering på erbjudandenivå**

Om du bara vill migrera specifika erbjudanden använder du `requestLevel: "offer"` och lägger till en `offersList`-array:

```json
"offersList": ["offer-id-1", "offer-id-2"]
```

**Migrering på beslutsnivå**

Om du bara vill migrera specifika beslut använder du `requestLevel: "decision"` och lägger till en `decisionsList`-array:

```json
"decisionsList": ["decision-id-1", "decision-id-2"]
```

#### Övervaka migreringsstatus {#poll-migration-status}

Avfråga migreringsarbetsflödet för att spåra dess förlopp.

**API-format**

```http
GET /workflows/migration/{id}
```

**Begäran**

```shell
curl --request GET \
  --url "https://decisioning-migration.adobe.io/workflows/migration/<WORKFLOW_ID>" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>"
```

**Migreringsresultat**

Migreringen lyckades när fältet `status` visar `Completed`. Arbetsflödet `result` innehåller:
* Mappningar av migrerade objekt
* Varningar påträffades under migreringen

När fältet `status` visar `Failed` granskar du arrayen `errors[]` och fältet `result.error` för att få information om vad som gick fel.

## Validera din migrering {#validate-migration}

När migreringen har slutförts kontrollerar du att alla objekt migrerades korrekt.

### Checklista för validering {#validation-checklist}

1. **Segment** - Verifiera att alla refererade segment tolkas korrekt i målsandlådan enligt dina mappningar.
2. **Attribut** - Bekräfta att alla profilattribut och kontextattribut finns i målsandlådan och är korrekt mappade.
3. **Objekten bestäms** - Granska migrerade objekt i Journey Optimizer-användargränssnittet:
   * Erbjudanden (beslutsunderlag)
   * Villkor för deltagande
   * Rankningsformler
   * Urvalsstrategier
   * Beslutspolitik
4. **Datastream-testning** - Om ett datastream skapades testar du körtidsleveransen med Edge Interact API.

### Exempel {#test-runtime-delivery}

Om din migrering har skapat en datastream kan du testa leveransen av erbjudanden med följande exempel:

```shell
curl --request POST \
  --url "https://edge.adobedc.net/ee/or2/v1/interact?configId=<DATASTREAM_ID>" \
  --header "Content-Type: application/json" \
  --header "x-request-id: <uuid>" \
  --data '{ "events": [ ... ] }'
```

## Återställa en migrering {#rollback}

Om du upptäcker problem under valideringen kan du återställa en slutförd migrering och återställa målsandlådan till dess tidigare läge.

### Skapa ett återställningsarbetsflöde {#create-rollback-workflow}

Starta en återställning genom att skapa ett återställningsarbetsflöde som refererar till den migrering du vill återställa.

**API-format**

```http
POST /workflows/rollback
```

**Begäran**

```shell
curl --request POST \
  --url "https://decisioning-migration.adobe.io/workflows/rollback" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>" \
  --header "Content-Type: application/json" \
  --data '{ "rollbackWorkflowId": "<MIGRATION_WORKFLOW_ID>" }'
```

Ersätt `<MIGRATION_WORKFLOW_ID>` med ID:t för det migreringsarbetsflöde som du vill återställa.

### Status för skärmåterställning {#poll-rollback-status}

Avsök återställningsarbetsflödet för att spåra dess förlopp.

**API-format**

```http
GET /workflows/rollback/{rollbackWorkflowId}
```

**Begäran**

```shell
curl --request GET \
  --url "https://decisioning-migration.adobe.io/workflows/rollback/<ROLLBACK_WORKFLOW_ID>" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>"
```

## Hantera samtidiga arbetsflöden {#handle-concurrency}

Migrerings-API:t tillåter bara ett arbetsflöde åt gången per organisation. Om du försöker skapa ett nytt arbetsflöde medan ett annat pågår får du felsvaret **409 i konflikt** (&quot;Ett arbetsflöde pågår redan..&quot;).

I det här fallet väntar du tills arbetsflödet har slutförts eller hämtar arbetsflödes-ID:t och kontrollerar statusen. När det aktuella arbetsflödet är klart kan du skapa ett nytt.

## Referens för enhetsmappning {#entity-mapping}

När enheter migreras från beslutshantering till beslut mappas de på följande sätt:

| Beslutshantering | Beslut |
|-------------------|-------------|
| Erbjudande | Beslutsobjekt |
| Erbjudandesamling | Artikelsamling |
| Kvalifikationsregel | Kvalifikationsregel |
| Rankningsformel | Rankningsformel |
| Beslut | Urvalsstrategi + beslutspolitik |
| Campaign | Kampanj *(endast grundläggande innehåll)* |
| Placement | Konfiguration av yta + kanal |
| Tagg | Enhetlig tagg |

## Rensa arbetsflöde {#cleanup}

<!--Workflow resources can be deleted by service users only. Delete operations require an `If-Match` header with the workflow's `_etag` value.

**Available delete operations:**

* `DELETE /workflows/generate-dependencies/{id}`
* `DELETE /workflows/migration/{id}`
* `DELETE /workflows/rollback/{id}`-->

Det går inte att ta bort arbetsflöden offentligt. Kontakta systemadministratören om du behöver ta bort en arbetsflödesresurs.

## Relaterade ämnen {#related-topics}

* [Migrera från beslutshantering till beslut](migrate-to-decisioning.md) - Förstå fördelarna och möjligheterna med att migrera till beslut
* [Kom igång med beslutsfattande](gs-experience-decisioning.md)
* [Beslut om skyddsräcken och begränsningar](decisioning-guardrails.md)
* [Kom igång med besluts-API:er](api-reference/getting-started.md)
