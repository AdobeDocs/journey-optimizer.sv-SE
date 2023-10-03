---
title: API för gruppbeslut
description: Lär dig hur du använder API:t för gruppbeslut för att välja de bästa erbjudandena för målgruppsprofiler inom ett fördefinierat beslutsområde.
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 1ed01a6b-5e42-47c8-a436-bdb388f50b4e
source-git-commit: be372f8f80d304067748d539fb8e210df6280721
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 1%

---


# Leverera erbjudanden med [!DNL Batch Decisioning] API {#deliver-offers-batch}

The [!DNL Batch Decisioning] Med API kan organisationer använda beslutsfunktioner för alla profiler i en viss målgrupp i ett enda anrop. Erbjudandeinnehållet för varje profil i målgruppen placeras i en Adobe Experience Platform-datauppsättning där det är tillgängligt för anpassade grupparbetsflöden.

Med [!DNL Batch Decisioning] API kan ni fylla i en datauppsättning med de bästa erbjudandena för alla profiler i en Adobe Experience Platform-målgrupp för beslutsomfattningar. En organisation kanske vill köra [!DNL Batch Decisioning] så att de kan skicka erbjudanden till en meddelandeleverantör. Erbjudandena används sedan som innehåll som skickas ut för batchmeddelandeleverans till samma målgrupp.

För att göra detta skulle organisationen:

* Kör [!DNL Batch Decisioning] API, som innehåller två begäranden:

   1. A **Begäran om batchvis POST** för att starta en arbetsbelastning för att batchbearbeta erbjudandeval.

   2. A **Batchbegäran om GET** för att hämta batcharbetsbelastningsstatus.

* Exportera datauppsättningen till meddelandeleverantörens API.

<!-- (Refer to the [export jobs endpoint documentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html) to learn more about exporting audiences.) -->

>[!NOTE]
>
>Gruppbeslut kan också utföras med Journey Optimizer gränssnitt. Mer information finns i [det här avsnittet](../../batch-delivery.md), som innehåller information om globala krav och begränsningar som ska beaktas vid gruppbeslut.

* **Antalet batchjobb som körs per datamängd**: Upp till fem batchjobb kan köras åt gången, per datauppsättning. Alla andra gruppförfrågningar med samma utdatamängd läggs till i kön. Ett jobb i kö plockas upp för bearbetning när det föregående jobbet har slutförts.
* **Frekvensbegränsning**: En batch körs bort från den profilögonblicksbild som inträffar en gång om dagen. The [!DNL Batch Decisioning] API kapslar frekvensen och läser alltid in profiler från den senaste ögonblicksbilden.

## Komma igång {#getting-started}

Innan du använder detta API måste du utföra följande steg.

### Förbered beslutet {#prepare-decision}

Om du vill förbereda ett eller flera beslut måste du skapa en datauppsättning, en målgrupp och ett beslut. Dessa förutsättningar beskrivs närmare i [det här avsnittet](../../batch-delivery.md).

### API-krav {#api-requirements}

Alla [!DNL Batch Decisioning] kräver följande rubriker förutom de som anges i [Utvecklarhandbok för API för beslutshantering](../getting-started.md):

* `Content-Type`: `application/json`
* `x-request-id`: En unik sträng som identifierar begäran.
* `x-sandbox-name`: Namn på sandlådan.
* `x-sandbox-id`: Sandbox-ID.

## Starta en gruppbearbetning {#start-a-batch-process}

Om du vill starta en arbetsbelastning för att gruppbearbeta beslut, skickar du en POST till `/workloads/decisions` slutpunkt.

>[!NOTE]
>
>Detaljerad information om bearbetningstiden för batchjobb finns i [det här avsnittet](../../batch-delivery.md).

**API-format**

```https
POST {ENDPOINT_PATH}/{CONTAINER_ID}/workloads/decisions
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för databas-API:er. | `https://platform.adobe.io/data/core/ode` |
| `{CONTAINER_ID}` | Behållaren där besluten finns. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

**Begäran**

```shell
curl -X POST 'https://platform.adobe.io/data/core/ode/0948b1c5-fff8-3b76-ba17-909c6b93b5a2/workloads/decisions' \
-H 'x-request-id: f671a589-eb7b-432f-b6b9-23d5b796b4dc' \
-H 'Content-Type: application/json' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-H 'x-sandbox-id: {SANDBOX_ID}' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-d '{
  "xdm:segmentIds": [
    "609028e4-e66c-4776-b0d9-c782887e2273"
  ],
  "xdm:dataSetId": "6196b4a1a63bd118dafe093c",
  "xdm:propositionRequests": [
        {
            "xdm:activityId": "xcore:offer-activity:1410cdcda196707b",
            "xdm:placementId": "xcore:offer-placement:1410c4117306488a",
            "xdm:itemCount": 1
        }
  ],
  "xdm:includeContent": false
}'
```

| Egenskap | Beskrivning | Exempel |
| -------- | ----------- | ------- |
| `xdm:segmentIds` | Värdet är en array som innehåller målgruppens unika identifierare. Den får bara innehålla ett värde. | `609028e4-e66c-4776-b0d9-c782887e2273` |
| `xdm:dataSetId` | DataSet-utdata som beslutshändelser kan skrivas till. | `6196b4a1a63bd118dafe093c` |
| `xdm:propositionRequests` | En wrapper som innehåller `placementId` och `activityId` |  |
| `xdm:activityId` | Beslutets unika identifierare. | `xcore:offer-activity:1410cdcda196707b` |
| `xdm:placementId` | Den unika placeringsidentifieraren. | `xcore:offer-placement:1410c4117306488a` |
| `xdm:itemCount` | Det här är ett valfritt fält som visar antalet objekt, t.ex. alternativ som begärts för beslutsomfånget. Som standard returnerar API ett alternativ per omfång, men du kan uttryckligen be om fler alternativ genom att ange det här fältet. Minst 1 och högst 30 alternativ kan begäras per scope. | `1` |
| `xdm:includeContent` | Detta är ett valfritt fält och är `false` som standard. If `true`, ingår erbjudandeinnehållet i beslutshändelserna för datauppsättningen. | `false` |

Se [Beslutsledningens dokumentation](../../get-started/starting-offer-decisioning.md) om du vill ha en översikt över de viktigaste begreppen och egenskaperna.

**Svar**

```json
{
    "@id": "47efef25-4bcf-404f-96e2-67c4f784a1f5",
    "xdm:imsOrgId": "9GTO98D5F@AdobeOrg",
    "xdm:containerId": "0948b1c5-fff8-3b76-ba17-909c6b93b5a2",
    "ode:createDate": 1648078924834,
    "ode:status": "QUEUED"
}
```

| Egenskap | Beskrivning | Exempel |
| -------- | ----------- | ------- |
| `@id` | UUID som genereras av beslutshantering som identifierar en enskild arbetsbelastning. | `5d0ffb5e-dfc6-4280-99b6-0bf3131cb8b8` |
| `xdm:imsOrgId` | Organisations-ID. | `9GTO98D5F@AdobeOrg` |
| `xdm:containerId` | Behållar-ID. | `0948b1c5-fff8-3b76-ba17-909c6b93b5a2` |
| `ode:createDate` | Den tid då begäran om beslutsarbetsbelastning skapades. | `1648078924834` |
| `ode:status` | Status för arbetsbelastningen. | `ode:status: "QUEUED"` |

## Hämta information om ett batchbeslut {#retrieve-information-on-a-batch-decision}

Om du vill hämta information om ett visst beslut skickar du en GET-förfrågan till `/workloads/decisions` slutpunkt när du anger motsvarande ID-värde för arbetsbelastning för ditt beslut.

**API-format**

```https
GET  {ENDPOINT_PATH}/{CONTAINER_ID}/workloads/decisions/{WORKLOAD_ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för databas-API:er. | `https://platform.adobe.io/data/core/ode` |
| `{CONTAINER_ID}` | Behållaren där besluten finns. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{WORKLOAD_ID}` | UUID som genereras av beslutshantering som identifierar en enskild arbetsbelastning. | `47efef25-4bcf-404f-96e2-67c4f784a1f5` |

**Begäran**

```shell
curl -X GET 'https://platform.adobe.io/data/core/ode/0948b1c5-fff8-3b76-ba17-909c6b93b5a2/workloads/decisions/f395ab1f-dfaf-48d4-84c9-199ad6354591' \
-H 'x-request-id: 7832a42a-d4e5-413b-98e8-e49bef056436' \
-H 'Content-Type: application/json' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-H'x-sandbox-id: {SANDBOX_ID}' \
-H 'Authorization: Bearer {ACCESS_TOKEN}'
```

**Svar**

```json
{
    "@id": "f395ab1f-dfaf-48d4-84c9-199ad6354591",
    "xdm:imsOrgId": "{IMS_ORG}",
    "xdm:containerId": "0948b1c5-fff8-3b76-ba17-909c6b93b5a2",
    "ode:createDate": 1648076994405,
    "ode:status": "COMPLETED"
}
```

| Egenskap | Beskrivning | Exempel |
| -------- | ----------- | ------- |
| `@id` | UUID som genereras av beslutshantering som identifierar en enskild arbetsbelastning. | `5d0ffb5e-dfc6-4280-99b6-0bf3131cb8b8` |
| `xdm:imsOrgId` | Organisations-ID | `9GTO98D5F@AdobeOrg` |
| `xdm:containerId` | Behållar-ID | `0948b1c5-fff8-3b76-ba17-909c6b93b5a2` |
| `ode:createDate` | Den tid då begäran om beslutsarbetsbelastning skapades. | `1648076994405` |
| `ode:status` | Arbetsbelastningens status börjar med &quot;QUEUED&quot; och ändras till &quot;PROCESSING&quot;, &quot;INGESTING&quot;, &quot;COMPLETED&quot; eller &quot;ERROR&quot;. | `ode:status: "COMPLETED"` |
| `ode:statusDetail` | Detta visar mer information, till exempel sparkJobId och batchID, om statusen är &quot;PROCESSING&quot; eller &quot;INGESTING&quot;. Felinformationen visas om statusen är FEL. |  |

## Nästa steg {#next-steps}

Genom att följa den här API-guiden har du kontrollerat arbetsbelastningsstatus och levererade erbjudanden med hjälp av [!DNL [!DNL Batch Decisioning]] API. Mer information finns i [Översikt över beslutsfattandet](../../get-started/starting-offer-decisioning.md).
