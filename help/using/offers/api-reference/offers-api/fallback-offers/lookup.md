---
title: erbjudanden för sökning efter reserverbjudanden
description: Ett reserverbjudande skickas till kunderna om de inte är berättigade till andra erbjudanden
feature: Decision Management, API
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 8f1fa116-30d2-4732-8973-bbce0dc66dec
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 2%

---

# Slå upp reserverbjudanden {#look-up-fallback-offers}

Du kan slå upp specifika reserverbjudanden genom att göra en GET-förfrågan till [!DNL Offer Library] API som innehåller ID för reserverbjudande i sökvägen för begäran.

**API-format**

```http
GET /{ENDPOINT_PATH}/offers/{ID}?offer-type=fallback
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | ID:t för enheten som du vill söka efter. | `fallbackOffer1234` |

**Begäran**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/offers/fallbackOffer1234?offer-type=fallback' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett lyckat svar returnerar detaljerna om reserverbjudandet, inklusive information om ditt reserverbjudande och ett unikt reserverbjudande-ID.

```json
{
    "created": "2023-06-08T14:04:41.011+00:00",
    "modified": "2023-06-08T14:04:41.011+00:00",
    "etag": 1,
    "schemas": [
        "https://ns.adobe.com/experience/offer-management/fallback-offer;version=0.8"
    ],
    "createdBy": "{CREATED_BY}",
    "lastModifiedBy": "{MODIFIED_BY}",
    "id": "fallbackOffer1234",
    "name": "Fallback Offer Web",
    "description": "Fallback Offer Web Description",
    "status": "draft",
    "representations": [
        {
            "channel": "https://ns.adobe.com/xdm/channel-types/web",
            "placement": "offerPlacement1234",
            "components": [
                {
                    "type": "imagelink",
                    "format": "image/png",
                    "deliveryURL": "https://mysite.com"
                }
            ]
        }
    ]
}
```
