---
title: Skapa en urvalsstrategi
description: Urvalsstrategier består av samlingar som är kopplade till begränsningar och rangordningsmetoder för att fastställa erbjudanden.
feature: Decision Management, API, Collections
topic: Integrations
role: Developer
level: Experienced
exl-id: 0e35c77b-6741-4c32-b012-36fc3a8b6d7a
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 1%

---

# Skapa en urvalsstrategi {#create-selection-strategy}

Du kan skapa en urvalsstrategi genom att göra en POST-begäran till erbjudandebiblioteks-API:t.

**API-format**

```http
POST /{ENDPOINT_PATH}/selection-strategies 
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |

**Begäran**

```shell
curl -X POST 'https://platform.adobe.io/data/core/dps/selection-strategies' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '{    
    "name": "Selection Strategy One",
    "description": "Selection Strategy",
    "rank": {
        "priority": 1,
        "order": {
            "orderEvaluationType": "static"
        }
    },
    "profileConstraint": {
        "profileConstraintType": "eligibilityRule",
        "eligibilityRule": "offerRule1234"
    },
    "optionSelection": {
        "filter": "itemCollection1234",
    }
}'
```

**Svar**

Ett lyckat svar returnerar information om den nyligen skapade urvalsstrategin, inklusive ID:t. Du kan använda id:t i senare steg för att uppdatera eller ta bort din urvalsstrategi.

```json
{
    "etag": 1,
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
