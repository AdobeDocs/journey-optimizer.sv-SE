---
title: Uppdatera en objektsamling
description: Samlingar är delmängder av erbjudanden som baseras på fördefinierade villkor som definieras av en marknadsförare, t.ex. erbjudandets kategori.
feature: Decision Management, API, Collections
topic: Integrations
role: Developer
level: Experienced
exl-id: a2b7779d-8c2e-4ff9-8cc3-90846f100c98
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 1%

---

# Uppdatera en objektsamling {#update-item-collection}

Du kan ändra eller uppdatera en objektsamling genom att göra en PATCH-begäran till Offer Library API.

Mer information om JSON Patch, inklusive tillgängliga åtgärder, finns i den officiella [JSON Patch-dokumentationen](https://jsonpatch.com/).

**API-format**

```http
PATCH /{ENDPOINT_PATH}/item-collections/{ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | ID:t för enheten som du vill uppdatera. | `itemCollections1234` |

**Begäran**

```shell
curl -X PATCH 'https://platform.adobe.io/data/core/dps/item-collections/itemCollections1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '[
    {
        "op": "replace",
        "path": "/name",
        "value": "Updated item collection"
    },
    {
        "op": "replace",
        "path": "/description",
        "value": "Updated item collection description"
    }
]'
```

| Parameter | Beskrivning |
| --------- | ----------- |
| `value` | Det nya värdet som du vill uppdatera parametern med. |
| `path` | Sökvägen till den parameter som ska uppdateras. |
| `op` | Åtgärdsanropet som används för att definiera den åtgärd som krävs för att uppdatera anslutningen. Åtgärderna är: `add`, `replace`, `remove`, `copy` och `test`. |

**Svar**

Ett godkänt svar returnerar den uppdaterade informationen i objektsamlingen, inklusive `id`.

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
