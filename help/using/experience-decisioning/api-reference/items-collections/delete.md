---
title: Ta bort en objektsamling
description: Lär dig hur du kategoriserar gruppbeslut i samlingar.
feature: Decision Management, API, Collections
topic: Integrations
role: Developer
level: Experienced
exl-id: 7290c857-cbc7-4197-ae13-430adcf1649b
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 0%

---

# Ta bort en objektsamling {#delete-decision-item}

Ibland kan det vara nödvändigt att ta bort (DELETE) en objektsamling. Detta gör du genom att utföra en DELETE-begäran till offertbiblioteks-API:t med ID:t för den objektsamling som du vill ta bort.

**API-format**

```http
DELETE /{ENDPOINT_PATH}/item-collections/{ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | ID:t för enheten som du vill ta bort. | `itemCollections1234` |

**Begäran**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/item-collections/itemCollections1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett lyckat svar returnerar HTTP-status 200 och en tom brödtext.

Du kan bekräfta borttagningen genom att försöka utföra en sökning (GET) på objektsamlingen. Du bör få HTTP-status 404 (Hittades inte) eftersom objektsamlingen har tagits bort.
