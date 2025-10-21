---
title: Ta bort en urvalsstrategi
description: Urvalsstrategier består av samlingar som är kopplade till begränsningar och rangordningsmetoder för att fastställa erbjudanden.
feature: Decision Management, API, Collections
topic: Integrations
role: Developer
level: Experienced
exl-id: 774f3773-bc39-46c4-b32c-143abbd45696
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 0%

---

# Ta bort en urvalsstrategi {#delete-selection-strategy}

Ibland kan det vara nödvändigt att ta bort (DELETE) en urvalsstrategi. Detta görs genom att en DELETE-begäran till Offer Library API görs med ID:t för den urvalsstrategi som du vill ta bort.

**API-format**

```http
DELETE /{ENDPOINT_PATH}/selection-strategies/{ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | ID:t för enheten som du vill ta bort. | `selectionStrategy1234` |

**Begäran**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/selection-strategies/selectionStrategy1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett lyckat svar returnerar HTTP-status 200 och en tom brödtext.

Du kan bekräfta borttagningen genom att försöka utföra en sökning (GET)-begäran i urvalsstrategin. Du bör få HTTP-status 404 (Hittades inte) eftersom urvalsstrategin har tagits bort.
