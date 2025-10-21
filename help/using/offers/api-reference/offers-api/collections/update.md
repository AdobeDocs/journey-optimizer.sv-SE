---
title: Uppdatera samlingar
description: Samlingar är delmängder av erbjudanden som baseras på fördefinierade villkor som definieras av en marknadsförare, t.ex. erbjudandets kategori.
feature: Decision Management, API, Collections
topic: Integrations
role: Developer
level: Experienced
exl-id: 7d766f0a-4fcb-434a-bbfd-e18ade71ae56
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 3%

---

# Uppdatera en samling {#update-collection}

Du kan ändra eller uppdatera en samling genom att göra en PATCH-begäran till API:t [!DNL Offer Library]

Mer information om JSON Patch, inklusive tillgängliga åtgärder, finns i den officiella [JSON Patch-dokumentationen](https://jsonpatch.com/).

## Sidhuvuden för acceptera och innehållstyp {#accept-and-content-type-headers}

I följande tabell visas giltiga värden som utgör fältet *Content-Type* i begärandehuvudet:

| Rubriknamn | Värde |
| ----------- | ----- |
| Content-Type | `application/json` |

**API-format**

```http
PATCH /{ENDPOINT_PATH}/offer-collections/{ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | ID:t för enheten som du vill uppdatera. | `offerCollection1234` |

**Begäran**

```shell
curl -X PATCH 'https://platform.adobe.io/data/core/dps/offer-collections/offerCollection1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '[
    {
        "op": "replace",
        "path": "/name",
        "value": "Updated offer collection"
    },
    {
        "op": "replace",
        "path": "/description",
        "value": "Updated offer collection description"
    }
]'
```

| Parameter | Beskrivning |
| --------- | ----------- |
| `op` | Åtgärdsanropet som används för att definiera den åtgärd som krävs för att uppdatera anslutningen. Åtgärderna är: `add`, `replace`, `remove`, `copy` och `test`. |
| `path` | Sökvägen till den parameter som ska uppdateras. |
| `value` | Det nya värdet som du vill uppdatera parametern med. |

**Svar**

Ett lyckat svar returnerar den uppdaterade informationen om samlingen, inklusive dess unika samling `id`.

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
