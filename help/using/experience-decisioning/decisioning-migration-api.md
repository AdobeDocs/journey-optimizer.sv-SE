---
title: API för beslutsmigrering
description: Lär dig hur du använder API:t för beslutsmigreringstjänsten för att migrera beslutshanteringsobjekt mellan sandlådor med automatisk beroendeupplösning och återställningsstöd.
feature: Decisioning
topic: Integrations
role: Developer
level: Experienced
source-git-commit: 398d4c2ab3a2312a0af5b8ac835f7d1f49a61b5b
workflow-type: tm+mt
source-wordcount: '1154'
ht-degree: 0%

---


# API för beslutsmigrering {#decisioning-migration-api}

Med API:t för migreringstjänsten för beslut kan du migrera beslutshanteringsobjekt från en sandlåda till en annan. Migreringsprocessen körs som asynkrona arbetsflöden som innehåller beroendeanalys, körning och valfria återställningsfunktioner.

Med detta API kan du smidigt överföra ditt beslutsinnehåll mellan miljöer (t.ex. från utveckling till staging eller från mellanlagring till produktion) samtidigt som dataintegritet och relationer upprätthålls.

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

### Bas-URL {#base-urls}

Använd följande bas-URL:er beroende på din miljö:

* **Produktion**: `https://platform.adobe.io`
* **Förproduktion**: `https://platform-stage.adobe.io`

### Autentisering {#authentication}

Alla API-begäranden kräver följande rubriker:

* `Authorization: Bearer <IMS_ACCESS_TOKEN>`
* `x-gw-ims-org-id: <IMS_ORG_ID>`
* `x-api-key: <CLIENT_API_KEY>`
* `Content-Type: application/json`

Detaljerade instruktioner om hur du konfigurerar autentisering finns i [Journey Optimizer-autentiseringsguiden](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"}.

### Arbetsflödesmodell {#workflow-model}

Varje API-anrop skapar eller hämtar en arbetsflödesresurs. Arbetsflöden är asynkrona åtgärder som spårar förloppet och resultaten av migreringsåtgärder.

Ett arbetsflöde har följande egenskaper:

* `id` - Unik identifierare för arbetsflöde (UUID)
* `status` - Aktuell arbetsflödesstatus: `New`, `Running`, `Completed`, `Failed` eller `Cancelled`
* `result` - Arbetsflödets utdata när det är klart (inkluderar migreringsresultat och varningar)
* `errors` - Strukturerad felinformation vid fel
* `_etag` - Versionsidentifierare används för borttagningsåtgärder (endast tjänstanvändare)
* `_links.self` - Arbetsflödes-URL för att hämta status

## Arbetsflöde för migrering {#migration-workflow}

Migreringsprocessen består av två huvudsteg: analysera beroenden och köra migreringen. Följ de här stegen för att säkerställa en lyckad migrering.

### Steg 1: Analysera beroenden {#analyze-dependencies}

Innan du migrerar använder du beroendearbetsflödet för att identifiera vad som behöver mappas från Beslutshantering till Beslutsfattning i målsandlådan. Den här analysen hjälper dig att förstå relationerna mellan objekt och förbereda nödvändiga mappningar.

#### Skapa ett beroendearbetsflöde {#create-dependency-workflow}

Använd följande API-anrop för att skapa ett arbetsflöde för beroendeanalys.

**API-format**

```http
POST /migration/service/dependency
```

**Beroende på sandlådenivå (rekommenderas först)**

Börja med en analys på sandlådenivå för att få en fullständig bild av alla beroenden:

```shell
curl --request POST \
  --url "https://platform.adobe.io/migration/service/dependency" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>" \
  --header "x-api-key: <CLIENT_API_KEY>" \
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
GET /migration/service/dependency/{id}
```

**Begäran**

```shell
curl --request GET \
  --url "https://platform.adobe.io/migration/service/dependency/<WORKFLOW_ID>" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>" \
  --header "x-api-key: <CLIENT_API_KEY>"
```

När fältet `status` visar `Completed` är beroendeanalysen klar. Använd arbetsflödets utdata för att skapa dina migreringsberoendemappningar:

* **profileAttributeDependency** - Mappar källprofilattribut till målprofilattribut
* **contextAttributeDependency** - Mappar källkontextattribut till målkontextattribut
* **segmentsDependency** - Mappar källsegmentnycklar till målsegmentidentifierare (`{segmentNamespace, segmentId}`)
* **datasetName** - Anger måldatamängdens namn för migreringen

### Steg 2: Utför migreringen {#execute-migration}

När du har analyserat beroendena och förberett mappningarna kan du utföra migreringen.

#### Skapa ett migreringsarbetsflöde {#create-migration-workflow}

Använd beroendemappningarna från steg 1 för att konfigurera och köra din migrering.

**API-format**

```http
POST /migration/service/migrations
```

**Migrering på sandlådenivå**

Så här migrerar du alla beslutsobjekt från en sandlåda till en annan:

```shell
curl --request POST \
  --url "https://platform.adobe.io/migration/service/migrations" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>" \
  --header "x-api-key: <CLIENT_API_KEY>" \
  --header "Content-Type: application/json" \
  --data '{
    "imsOrgId": "<IMS_ORG_ID>",
    "sourceSandboxDetails": { "sandboxName": "<SOURCE_SANDBOX_NAME>" },
    "targetSandboxDetails": { "sandboxName": "<TARGET_SANDBOX_NAME>" },
    "createDataStream": true,
    "dependency": {
      "profileAttributeDependency": {
        "sourceAttr1": "targetAttr1"
      },
      "segmentsDependency": {
        "sourceSegmentKey1": {
          "segmentNamespace": "<TARGET_SEGMENT_NAMESPACE>",
          "segmentId": "<TARGET_SEGMENT_ID>"
        }
      },
      "contextAttributeDependency": {
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
GET /migration/service/migrations/{id}
```

**Begäran**

```shell
curl --request GET \
  --url "https://platform.adobe.io/migration/service/migrations/<WORKFLOW_ID>" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>" \
  --header "x-api-key: <CLIENT_API_KEY>"
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
POST /migration/service/rollbacks/{migrationWorkflowId}
```

Ersätt `{migrationWorkflowId}` med ID:t för det migreringsarbetsflöde som du vill återställa.

**Begäran**

```shell
curl --request POST \
  --url "https://platform.adobe.io/migration/service/rollbacks/<MIGRATION_WORKFLOW_ID>" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>" \
  --header "x-api-key: <CLIENT_API_KEY>"
```

### Status för skärmåterställning {#poll-rollback-status}

Avsök återställningsarbetsflödet för att spåra dess förlopp.

**API-format**

```http
GET /migration/service/rollbacks/{rollbackWorkflowId}
```

**Begäran**

```shell
curl --request GET \
  --url "https://platform.adobe.io/migration/service/rollbacks/<ROLLBACK_WORKFLOW_ID>" \
  --header "Authorization: Bearer <IMS_ACCESS_TOKEN>" \
  --header "x-gw-ims-org-id: <IMS_ORG_ID>" \
  --header "x-api-key: <CLIENT_API_KEY>"
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

Arbetsflödesresurser kan bara tas bort av tjänstanvändare. Borttagningsåtgärder kräver ett `If-Match`-huvud med arbetsflödets `_etag`-värde.

**Tillgängliga borttagningsåtgärder:**

* `DELETE /migration/service/dependency/{id}`
* `DELETE /migration/service/migrations/{id}`
* `DELETE /migration/service/rollbacks/{id}`

>[!NOTE]
>
>Borttagning av arbetsflöden är bara tillgängligt för tjänstkonton med rätt behörighet. Kontakta systemadministratören om du behöver ta bort en arbetsflödesresurs.

## Relaterade ämnen {#related-topics}

* [Migrera från beslutshantering till beslut](migrate-to-decisioning.md) - Förstå fördelarna och möjligheterna med att migrera till beslut
* [Kom igång med beslutsfattande](gs-experience-decisioning.md)
* [Beslut om skyddsräcken och begränsningar](decisioning-guardrails.md)
* [Kom igång med besluts-API:er](api-reference/getting-started.md)
