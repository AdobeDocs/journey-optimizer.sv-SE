---
title: ta bort placeringar
description: Placeringar är behållare som används för att visa upp dina erbjudanden.
feature: Decision Management, API
topic: Integrations
role: Developer
level: Experienced
exl-id: 944efb12-6745-4bb2-be52-293e23925350
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 2%

---

# Ta bort en placering {#delete-placement}

Ibland kan det vara nödvändigt att ta bort (DELETE) en placering. Endast placeringar som du skapar i innehavarbehållaren kan tas bort. Detta görs genom att utföra en DELETE-begäran till [!DNL Offer Library]-API:t med instans-ID:t för den placering som du vill ta bort.

**API-format**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för databas-API:er. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | Behållaren där placeringarna finns. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | Instans-ID för placeringen som du vill uppdatera. | `9aa58fd0-13d7-11eb-928b-576735ea4db8` |

**Begäran**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/9aa58fd0-13d7-11eb-928b-576735ea4db8' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett lyckat svar returnerar HTTP-status 202 (inget innehåll) och en tom brödtext.

Du kan bekräfta borttagningen genom att försöka utföra en sökning (GET) på placeringen. Du måste inkludera en Accept-rubrik i begäran, men du bör få HTTP-statusen 404 (Hittades inte) eftersom placeringen har tagits bort från behållaren.
