---
title: Ta bort ett beslutsobjekt
description: Beslutsobjekt är marknadsföringserbjudanden som du kan skapa och ordna i samlingar och kataloger.
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: c555e6a6d88f43d7c29e27060d464b8fd21aed96
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 0%

---


# Ta bort ett beslutsobjekt {#delete-decision-item}

Ibland kan det vara nödvändigt att ta bort (DELETE) en beslutspost. Detta gör du genom att utföra en DELETE-begäran till offertbiblioteks-API med ID:t för det beslutsobjekt som du vill ta bort.

**API-format**

```http
DELETE /{ENDPOINT_PATH}/offer-items/{ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | ID:t för enheten som du vill ta bort. | `offerItem1234` |

**Begäran**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/offer-items/offerItem1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-H 'x-schema-id: {SCHEMA_ID}'
```

**Svar**

Ett lyckat svar returnerar HTTP-status 200 och en tom brödtext.

Du kan bekräfta borttagningen genom att försöka utföra en sökning (GET) på beslutsobjektet. Du bör få HTTP-status 404 (Hittades inte) eftersom beslutsobjektet har tagits bort.
