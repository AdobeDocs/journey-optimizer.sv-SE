---
title: Uppdatera personaliserade erbjudanden
description: Ett personaliserat erbjudande är ett anpassningsbart marknadsföringsmeddelande som baseras på regler och begränsningar för behörighet.
feature: Decision Management, API
topic: Integrations
role: Developer
level: Experienced
exl-id: 9d8f2df6-aa04-4e66-8555-d51c2e409063
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 4%

---

# Uppdatera ett personaliserat erbjudande {#update-personalized-offer}

Du kan ändra eller uppdatera ett anpassat erbjudande genom att göra en PATCH-begäran till API:t [!DNL Offer Library]

Mer information om JSON Patch, inklusive tillgängliga åtgärder, finns i den officiella [JSON Patch-dokumentationen](https://jsonpatch.com/).

## Sidhuvuden för acceptera och innehållstyp {#accept-and-content-type-headers}

I följande tabell visas giltiga värden som utgör fältet *Content-Type* i begärandehuvudet:

| Rubriknamn | Värde |
| ----------- | ----- |
| Content-Type | `application/json` |

**API-format**

```http
PATCH /{ENDPOINT_PATH}/offers/{ID}?offer-type=personalized
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | ID:t för enheten som du vill uppdatera. | `personalizedOffer1234` |

**Begäran**

```shell
curl -X PATCH 'https://platform.adobe.io/data/core/dps/offers/personalizedOffer1234?offer-type=personalized' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '[
    {
        "op": "replace",
        "path": "/name",
        "value": "Updated personalized offer"
    },
    {
        "op": "replace",
        "path": "/description",
        "value": "Updated personalized offer description"
    }
]'
```

| Parameter | Beskrivning |
| --------- | ----------- |
| `op` | Åtgärdsanropet som används för att definiera den åtgärd som krävs för att uppdatera anslutningen. Åtgärderna är: `add`, `replace`, `remove`, `copy` och `test`. |
| `path` | Sökvägen till den parameter som ska uppdateras. |
| `value` | Det nya värdet som du vill uppdatera parametern med. |

**Svar**

Ett godkänt svar returnerar de uppdaterade detaljerna om placeringen, inklusive placerings-ID.

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
