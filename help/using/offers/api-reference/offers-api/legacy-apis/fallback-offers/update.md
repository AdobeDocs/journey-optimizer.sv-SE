---
title: Uppdatera ett reserverbjudande
description: Ett reserverbjudande skickas till kunderna om de inte är berättigade till andra erbjudanden
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 7ff69887-620f-4bc0-b8ff-5144ff30696c
source-git-commit: 54b92b19f2e3a6afa6557ffeff0d971a4c411510
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 6%

---


# Uppdatera ett reserverbjudande {#update-fallback-offer}

Du kan ändra eller uppdatera ett reserverbjudande i din behållare genom att göra en PATCH-förfrågan till [!DNL Offer Library] API.

Mer information om JSON Patch, inklusive tillgängliga åtgärder, finns i [JSON Patch-dokumentation](https://jsonpatch.com/).

## Sidhuvuden för acceptera och innehållstyp {#accept-and-content-type-headers}

I följande tabell visas giltiga värden som utgör *Content-Type* och *Acceptera* fält i begärandehuvudet:

| Rubriknamn | Värde |
| ----------- | ----- |
| Content-Type | `application/json` |

**API-format**

```http
PATCH /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för databas-API:er. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | Behållaren där reserverbjudandena finns. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | Instans-ID för reserverbjudandet. | `b3966680-13ec-11eb-9c20-8323709cfc65` |

**Begäran**

    @@ -58,7 +57,7 @@ bol -X PATCH &#39;https://platform.adobe.io/data/core/dps/offers/fallbackOffer1234?

| Parameter | Beskrivning |
| --------- | ----------- |
| `op` | Åtgärdsanropet som används för att definiera den åtgärd som krävs för att uppdatera anslutningen. Åtgärderna omfattar: `add`, `replace`och `remove`. |
| `path` | Sökvägen till den parameter som ska uppdateras. |
| `value` | Det nya värdet som du vill uppdatera parametern med. |
ens35577 markerade den här konversationen som löst.
Visa lösta

**Svar**
Ett lyckat svar returnerar den uppdaterade informationen om reserverbjudandet, inklusive dess unika instans `id`.

```json
{
    "id": "{ID}",
    "datasetId": "{DATASET_ID}",
    "sandboxId": "{SANDBOX_ID}",
    "etag": 2,
    "createdDate": "2023-09-07T12:47:43.012Z",
    "lastModifiedDate": "2023-09-07T12:47:43.012Z",
    "createdBy": "{CREATED_BY}",
    "lastModifiedBy": "{MODIFIED_BY}",
    "createdByClientId": "{CREATED_CLIENT_ID}",
    "lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```
