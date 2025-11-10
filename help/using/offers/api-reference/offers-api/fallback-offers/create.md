---
title: Skapa ett reserverbjudande
description: Ett reserverbjudande skickas till kunderna om de inte är berättigade till andra erbjudanden
feature: Decision Management, API
topic: Integrations
role: Developer
level: Experienced
exl-id: 156d6c71-d8fd-4631-ae0c-44452d664dde
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 8%

---

# Skapa ett reserverbjudande {#create-fallback-offer}

Du kan skapa ett reserverbjudande genom att göra en POST-begäran till API:t [!DNL Offer Library].

## Sidhuvuden för acceptera och innehållstyp {#accept-and-content-type-headers}

I följande tabell visas giltiga värden som utgör fältet *Content-Type* i begärandehuvudet:

| Rubriknamn | Värde |
| ----------- | ----- |
| Content-Type | `application/json` |

**API-format**

```http
POST /{ENDPOINT_PATH}/offers?offer-type=fallback
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps/` |

**Begäran**

```shell
curl -X POST 'https://platform.adobe.io/data/core/dps/offers?offer-type=fallback' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '{
    "name": "Test Fallback Offer DPS",
    "description": "Fallback Offer description",
    "status": "approved",
    "selectionConstraint": {
        "startDate": "2022-06-10T00:30:00.000+00:00",
        "endDate": "2032-06-06T23:29:21.402+00:00",
        "profileConstraintType": "none"
    },
    "representations": [
        {
            "components": [
                {
                    "deliveryURL": "https://mysite.com",
                    "type": "imagelink",
                    "format": "image/png"
                }
            ],
            "channel": "https://ns.adobe.com/xdm/channel-types/web",
            "placement": "offerPlacement1234"
        }
    ],
    "rank": {
        "priority": 1
    }
}'
```

**Svar**

Ett lyckat svar returnerar information om det nya reserverbjudandet, inklusive det unika reserverbjudandet `id`. Du kan använda `id` i senare steg för att uppdatera eller ta bort ditt reserverbjudande eller för att skapa ett beslut i en senare självstudie.


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
