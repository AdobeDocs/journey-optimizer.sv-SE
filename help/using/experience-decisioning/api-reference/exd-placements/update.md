---
title: Uppdatera utökad placering
description: Expanderingen består av samlingar som är kopplade till begränsningar och rankningsmetoder för att bestämma erbjudanden.
feature: Decision Management, API, Collections
topic: Integrations
role: Developer
level: Experienced
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 2%

---

# Uppdatera en extern placering {#update-exd-placement}

Du kan ändra eller uppdatera en placering genom att göra en PUT-förfrågan till Offer Library API.

Mer information om JSON PUT, inklusive tillgängliga åtgärder, finns i den officiella JSON PUT-dokumentationen.

**Godkänn och Content-Type-rubriker**

I följande tabell visas giltiga värden som omfattar fälten Content-Type i begärandehuvudet:

| Parameter | Beskrivning |
| --------- | ----------- |
| Content-Type | `application/json` |

**API-format**

```http
PUT /{ENDPOINT_PATH}/exd-placements/{ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | ID:t för enheten som du vill uppdatera. | `placement1234` |

**Begäran**

```shell
curl --location --request PUT 'https://platform-stage.adobe.io/data/core/dps/exd-placements/dps:exd-placement:19aca09b0a456e57' \
--H 'Content-Type: application/json' \
--H 'x-gw-ims-org-id: {IMS_ORG}' \
--H 'x-sandbox-name: {SANDBOX_NAME}' \
--H 'x-api-key: {API_KEY}' \
--H 'Authorization: Bearer {ACCESS_TOKEN}' \
--X '{
  "id":"dps:exd-placement:19aca09b0a456e57",
  "description": "Keyboard application",
  "status":"archived"
}'
```

| Parameter | Beskrivning |
| --------- | ----------- |
| `value` | Det nya värdet som du vill uppdatera parametern med. |
| `path` | Sökvägen till den parameter som ska uppdateras. |
| `op` | Åtgärdsanropet som används för att definiera den åtgärd som krävs för att uppdatera anslutningen. Åtgärderna är: `add`, `replace`, `remove`, `copy` och `test`. |

**Svar**

Ett godkänt svar returnerar den uppdaterade informationen om den utökade placeringen, inklusive ID:t.

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
