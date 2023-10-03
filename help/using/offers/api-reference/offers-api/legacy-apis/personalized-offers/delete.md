---
title: Ta bort personaliserade erbjudanden
description: Ett personaliserat erbjudande är ett anpassningsbart marknadsföringsmeddelande som baseras på regler och begränsningar för behörighet.
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 52a5053d-3b94-47fd-a064-a20f9a595150
source-git-commit: 5315c0878db9ddf1806f4f7d22fdd9f5a037fd59
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 4%

---


# Ta bort ett personaliserat erbjudande {#delete-personalized-offer}

Ibland kan det vara nödvändigt att ta bort (DELETE) ett personaliserat erbjudande. Endast personliga erbjudanden som du skapar i innehavarbehållaren kan tas bort. Detta görs genom att en DELETE-begäran görs till [!DNL Offer Library] API som använder $id för det anpassade erbjudande som du vill ta bort.

**API-format**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för databas-API:er. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | Behållaren där personaliserade erbjudanden finns. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

**Begäran**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/0f4bc230-13df-11eb-bc55-c11be7252432' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett lyckat svar returnerar HTTP-status 202 (inget innehåll) och en tom brödtext.

Du kan bekräfta borttagningen genom att försöka göra en sökbegäran (GET) till det anpassade erbjudandet. Du måste inkludera en Accept-rubrik i begäran, men du bör få HTTP-status 404 (Hittades inte) eftersom det anpassade erbjudandet har tagits bort från behållaren.