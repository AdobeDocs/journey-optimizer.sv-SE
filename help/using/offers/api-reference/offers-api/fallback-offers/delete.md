---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: Ta bort ett reserverbjudande
description: Ett reserverbjudande skickas till kunderna om de inte är berättigade till andra erbjudanden
feature: Decision Management, API
topic: Integrations
role: Developer
level: Experienced
exl-id: 5c94842a-021c-4a3a-ad9c-ccc2af2c1526
version: Journey Orchestration
source-git-commit: d6a9a8a392f0492aa6e4f059198ce77b6b2cd962
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 7%

---


# Ta bort ett reserverbjudande {#delete-fallback-offer}

Ibland kan det vara nödvändigt att ta bort (DELETE) ett reserverbjudande. Detta görs genom att utföra en DELETE-begäran till [!DNL Offer Library]-API:t med ID:t för det reserverbjudande som du vill ta bort.

**API-format**

```http
DELETE /{ENDPOINT_PATH}/offers/{ID}?offer-type=fallback
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | ID:t för enheten som du vill ta bort. | `fallbackOffer1234` |

**Begäran**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/offers/fallbackOffer1234?offer-type=fallback' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett lyckat svar returnerar HTTP-status 200 och en tom brödtext.

Du kan bekräfta borttagningen genom att försöka skicka en sökning (GET) till erbjudandet och få HTTP-statusen 404 (Hittades inte) eftersom reserverbjudandet har tagits bort.
