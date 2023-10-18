---
title: Ta bort en samling
description: Samlingar är delmängder av erbjudanden som baseras på fördefinierade villkor som definieras av en marknadsförare, t.ex. erbjudandets kategori.
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 2eaa0092-2436-4679-83f1-7530ab4a858f
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 6%

---

# Ta bort en samling {#delete-collection}

Ibland kan det vara nödvändigt att ta bort (DELETE) en samling. Detta görs genom att en DELETE-begäran görs till [!DNL Offer Library] API med `id` för den samling som du vill ta bort.

**API-format**

```http
DELETE /{ENDPOINT_PATH}/offer-collections/{ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | ID:t för enheten som du vill ta bort. | `offerCollection1234` |

**Begäran**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/tags/tag1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett lyckat svar returnerar HTTP-status 200 och en tom brödtext.

Du kan bekräfta borttagningen genom att försöka utföra en sökning (GET) i samlingen. Du bör få HTTP-status 404 (Hittades inte) eftersom samlingen har tagits bort.
