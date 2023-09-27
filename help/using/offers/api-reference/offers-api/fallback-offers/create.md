---
title: Skapa ett reserverbjudande
description: Ett reserverbjudande skickas till kunderna om de inte är berättigade till andra erbjudanden
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 156d6c71-d8fd-4631-ae0c-44452d664dde
source-git-commit: 805f7bdc921c53f63367041afbb6198d0ec05ad8
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 9%

---

# Skapa ett reserverbjudande {#create-fallback-offer}

Du kan skapa ett reserverbjudande genom att göra en POST till [!DNL Offer Library] API.

## Sidhuvuden för acceptera och innehållstyp {#accept-and-content-type-headers}

I följande tabell visas giltiga värden som utgör *Content-Type* fält i begärandehuvudet:

| Rubriknamn | Värde |
| ----------- | ----- |
| Content-Type | `application/json` |

**API-format**

```http
POST /{ENDPOINT_PATH}/offers/{ID}?offer-type=fallback
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | ID:t för enheten som du vill uppdatera. | `fallbackOffer1234` |

**Begäran**

```shell
curl -X PATCH 'https://platform.adobe.io/data/core/dps/offers/fallbackOffer1234?offer-type=fallback' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '[
    {
        "op": "replace",
        "path": "/name",
        "value": "Updated fallback offer"
    },
    {
        "op": "replace",
        "path": "/description",
        "value": "Updated fallback offer description"
    }
]'
```

**Svar**

Ett lyckat svar returnerar information om det nya reserverbjudandet, inklusive det unika reserverbjudandet `id`. Du kan använda `id` i senare steg för att uppdatera eller ta bort ditt reserverbjudande eller för att skapa ett beslut i en senare självstudiekurs.


```json
{
    "etag": 2,
    "createdBy": "{CREATED_BY}",
    "lastModifiedBy": "{MODIFIED_BY}",
    "id": "{ID}",
    "sandboxId": "{SANDBOX_ID}",
    "createdDate": "2023-05-31T15:09:11.771Z",
    "lastModifiedDate": "2023-05-31T15:09:11.771Z",
    "createdByClientId": "{CREATED_CLIENT_ID}",
    "lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```
