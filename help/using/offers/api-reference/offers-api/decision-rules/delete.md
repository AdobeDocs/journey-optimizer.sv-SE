---
title: Radera beslutsregler
description: Beslutsregler läggs till i ett personaliserat erbjudande och tillämpas på en profil för att avgöra vem som är berättigad.
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 52f4803b-9e9a-4ad0-ae24-de652006763d
source-git-commit: 3568e86015ee7b2ec59a7fa95e042449fb5a0693
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 5%

---

# Ta bort en beslutsregel {#delete-decision-rule}

Ibland kan det vara nödvändigt att ta bort (DELETE) en beslutsregel. Detta görs genom att en DELETE-begäran görs till [!DNL Offer Library] API med `id` av den beslutsregel som du vill ta bort.

**API-format**

```http
DELETE /{ENDPOINT_PATH}/offer-rules/{ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | ID:t för enheten som du vill ta bort. | `offerRule1234` |

**Begäran**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/offer-rules/offerRule1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett lyckat svar returnerar HTTP-status 200 och en tom brödtext.

Du kan bekräfta borttagningen genom att försöka med en sökbegäran (GET) till beslutsregeln och få HTTP-statusen 404 (Hittades inte) eftersom beslutsregeln har tagits bort.
