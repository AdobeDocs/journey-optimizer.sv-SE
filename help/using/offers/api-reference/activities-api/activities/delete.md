---
title: Ta bort beslut
description: Ett beslut innehåller den logik som ligger till grund för valet av ett erbjudande.
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 1eb19ff1-b210-4891-ab41-5488e2635527
source-git-commit: 3568e86015ee7b2ec59a7fa95e042449fb5a0693
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 4%

---

# Ta bort ett beslut {#delete-decision}

Ibland kan det vara nödvändigt att ta bort (DELETE) ett beslut. Detta görs genom att en DELETE-begäran görs till [!DNL Offer Library] API med `id` av det beslut du vill ta bort.

**API-format**

```http
DELETE /{ENDPOINT_PATH}/offer-decisions/{ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | ID:t för enheten som du vill ta bort. | `offerDecision1234` |

**Begäran**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/offer-decisions/offerDecision1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett lyckat svar returnerar HTTP-status 200 och en tom brödtext.

Du kan bekräfta borttagningen genom att försöka utföra en sökning (GET) på beslutet. Du bör få HTTP-status 404 (Hittades inte) eftersom beslutet har tagits bort.