---
title: Ta bort beslut
description: Ett beslut innehåller den logik som ligger till grund för valet av ett erbjudande.
feature: Erbjudanden
topic: Integreringar
role: Data Engineer
level: Experienced
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 4%

---

# Ta bort ett beslut

Ibland kan det vara nödvändigt att ta bort (DELETE) ett beslut (tidigare kallat erbjudandeaktivitet). Endast beslut som du skapar i innehavarbehållaren kan tas bort. Detta görs genom att utföra en DELETE-begäran till [!DNL Offer Library]-API:t med $id för det reserverbjudande som du vill ta bort.

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
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett lyckat svar returnerar HTTP-status 202 (inget innehåll) och en tom brödtext.

Du kan bekräfta borttagningen genom att försöka utföra en sökning (GET) på beslutet. Du måste inkludera en Accept-rubrik i begäran, men du bör få HTTP-statusen 404 (Hittades inte) eftersom beslutet har tagits bort från behållaren.
