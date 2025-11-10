---
title: Söka efter en samlingskvalificerare
description: Med en samling kvalificerare kan ni ordna och sortera genom era erbjudanden på ett bättre sätt.
feature: Decision Management, API
topic: Integrations
role: Developer
level: Experienced
exl-id: f31e6a17-c99a-4db9-a301-426a1f0bcc92
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 1%

---

# Söka efter en samlingskvalificerare {#look-up-tag}

Du kan söka efter specifika samlingskvalificerare (som tidigare kallades &quot;taggar&quot;) genom att göra en GET-begäran till [!DNL Offer Library]-API:t som innehåller samlingskvalificeraren `id` i sökvägen för begäran.

**API-format**

```http
GET /{ENDPOINT_PATH}/tags/{ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för databas-API:er. | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | ID:t för enheten som du vill söka efter. | `tag1234` |

**Begäran**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/tags/tag1234' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett lyckat svar returnerar information om samlingskvalificeraren, inklusive information om din unika samlingskvalificerare `id`.

```json
{
       "created": "2022-09-16T19:00:02.070+00:00",
    "modified": "2022-09-16T19:00:02.070+00:00",
    "etag": 1,
    "schemas": [
        "https://ns.adobe.com/experience/offer-management/tag;version=0.1"
    ],
    "createdBy": "{CREATED_BY}",
    "lastModifiedBy": "{MODIFIED_BY}",
    "id": "tag1234",
    "name": "Sneakers"
}
```
