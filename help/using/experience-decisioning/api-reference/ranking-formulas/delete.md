---
title: Ta bort en rankningsformel
description: Med rankningsformler kan du definiera funktionerna för poängsättning, som används för att rangordna artiklar.
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: 8fa34ebb7c853f9af5b3f58574374a3acb641dd9
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 0%

---

# Ta bort en rankningsformel {#delete-selection-strategy}

Ibland kan det vara nödvändigt att ta bort (DELETE) en rankningsformel. Detta görs genom att en DELETE-begäran till erbjudandebiblioteks-API görs med ID:t för den rangordningsformel som du vill ta bort.

**API-format**

```http
DELETE /{ENDPOINT_PATH}/ranking-formulas/{ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | ID:t för den entitet som du vill ta bort. | `rankingFormula1234` |

**Begäran**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/ranking-formulas/rankingFormula1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett lyckat svar returnerar HTTP-status 200 och en tom brödtext.

Du kan bekräfta borttagningen genom att försöka utföra en sökning (GET) på rankningsformeln. Du bör få HTTP-status 404 (Hittades inte) eftersom rankningsformeln har tagits bort.

