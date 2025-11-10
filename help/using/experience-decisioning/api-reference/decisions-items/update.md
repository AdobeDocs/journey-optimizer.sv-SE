---
title: Uppdatera ett beslutsobjekt
description: Beslutsobjekt är marknadsföringserbjudanden som du kan skapa och ordna i samlingar och kataloger.
feature: Decision Management, API, Collections
topic: Integrations
role: Developer
level: Experienced
exl-id: b924b7d0-bbed-409e-8173-0685fc41d7de
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 1%

---

# Uppdatera ett beslutsobjekt {#update-decision-items}

Du kan ändra eller uppdatera ett beslutsobjekt genom att göra en PATCH-begäran till Offer Library API.

Mer information om JSON Patch, inklusive tillgängliga åtgärder, finns i den officiella [JSON Patch-dokumentationen](https://jsonpatch.com/).

**API-format**

```http
PATCH /{ENDPOINT_PATH}/offer-items/{ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | ID:t för enheten som du vill uppdatera. | `offerItem1234` |

**Begäran**

```shell
curl -X PATCH 'https://platform.adobe.io/data/core/dps/offer-items/offerItem1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-H 'x-schema-id: {SCHEMA_ID}' \
-d '[
    {
        "op": "replace",
        "path": "/_experience/decisioning/decisionitem/itemName",
        "value": "Updated offer item"
    },
    {
        "op": "replace",
        "path": "/_experience/decisioning/decisionitem/itemDescription",
        "value": "Updated offer item description"
    }
]'
```

| Parameter | Beskrivning |
| --------- | ----------- |
| `value` | Det nya värdet som du vill uppdatera parametern med. |
| `path` | Sökvägen till den parameter som ska uppdateras. |
| `op` | Den typ av åtgärd som ska utföras. Åtgärderna är: `add`, `replace`, `remove`, `copy` och `test`. |

**Svar**

Ett godkänt svar returnerar information om det uppdaterade objektet, inklusive ID:t. Du kan använda ID:t i senare steg för att uppdatera eller ta bort beslutsobjektet.

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
