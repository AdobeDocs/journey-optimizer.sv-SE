---
title: Ta bort beslut
description: Ett beslut innehåller den logik som ligger till grund för valet av ett erbjudande.
feature: Decision Management, API
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 36a87d98-fd61-416e-83a1-e267a7b4d455
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 3%

---

# Ta bort ett beslut {#delete-decision}

Ibland kan det vara nödvändigt att ta bort (DELETE) ett beslut. Endast beslut som du skapar i innehavarbehållaren kan tas bort. Detta görs genom att en DELETE-begäran görs till [!DNL Offer Library] API som använder $id för det reserverbjudande som du vill ta bort.

**API-format**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för databas-API:er. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | Behållaren där besluten finns. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | Instans-ID för beslutet. | `f88c9be0-1245-11eb-8622-b77b60702882` |

**Begäran**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/f88c9be0-1245-11eb-8622-b77b60702882' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett lyckat svar returnerar HTTP-status 202 (inget innehåll) och en tom brödtext.

Du kan bekräfta borttagningen genom att försöka utföra en sökning (GET) på beslutet. Du måste inkludera en Accept-rubrik i begäran, men du bör få HTTP-statusen 404 (Hittades inte) eftersom beslutet har tagits bort från behållaren.
