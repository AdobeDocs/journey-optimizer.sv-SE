---
title: uppdatera en placering
description: Placeringar är behållare som används för att visa upp dina erbjudanden.
feature: Decision Management, API
topic: Integrations
role: Developer
level: Experienced
exl-id: 6990918c-e736-4f28-9ac6-9ac3101b069f
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 4%

---

# Uppdatera en placering {#update-placement}

Du kan ändra eller uppdatera en placering genom att göra en PATCH-förfrågan till API:t [!DNL Offer Library].

Mer information om JSON Patch, inklusive tillgängliga åtgärder, finns i den officiella [JSON Patch-dokumentationen](https://jsonpatch.com/).

## Sidhuvuden för acceptera och innehållstyp {#accept-and-content-type-headers}

I följande tabell visas giltiga värden som utgör fältet *Content-Type* i begärandehuvudet:

| Rubriknamn | Värde |
| ----------- | ----- |
| Content-Type | `application/json` |

**API-format**

```http
PATCH /{ENDPOINT_PATH}/placements/{ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | ID:t för enheten som du vill uppdatera. | `offerPlacement1234` |

**Begäran**

```shell
curl -X PATCH 'https://platform.adobe.io/data/core/dps/placements/offerPlacement1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '[
    {
        "op": "replace",
        "path": "/name",
        "value": "Updated placement"
    },
    {
        "op": "replace",
        "path": "/description",
        "value": "Updated placement description"
    }
]'
```

| Parameter | Beskrivning |
| --------- | ----------- |
| `op` | Åtgärdsanropet som används för att definiera den åtgärd som krävs för att uppdatera anslutningen. Åtgärderna är: `add`, `replace`, `remove`, `copy` och `test`. |
| `path` | Sökvägen till den parameter som ska uppdateras. |
| `value` | Det nya värdet som du vill uppdatera parametern med. |

**Svar**

Ett godkänt svar returnerar de uppdaterade detaljerna för placeringen, inklusive den unika placeringen `id`.

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
