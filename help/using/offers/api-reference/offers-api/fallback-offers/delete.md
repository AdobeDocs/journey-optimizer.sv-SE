---
title: Ta bort ett reserverbjudande
description: Ett reserverbjudande skickas till kunderna om de inte är berättigade till andra erbjudanden
feature: Erbjudanden
topic: Integreringar
role: Data Engineer
level: Experienced
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 7%

---

# Ta bort ett reserverbjudande

Ibland kan det vara nödvändigt att ta bort (DELETE) ett reserverbjudande. Endast reserverbjudanden som du skapar i innehavarbehållaren kan tas bort. Detta görs genom att utföra en DELETE-begäran till [!DNL Offer Library]-API:t med $id för det reserverbjudande som du vill ta bort.

**API-format**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för databas-API:er. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | Behållaren där reserverbjudandena finns. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | Instans-ID för reserverbjudandet. | `b3966680-13ec-11eb-9c20-8323709cfc65` |

**Begäran**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/b3966680-13ec-11eb-9c20-8323709cfc65' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett lyckat svar returnerar HTTP-status 202 (inget innehåll) och en tom brödtext.

Du kan bekräfta borttagningen genom att försöka utföra en uppslagsbegäran (GET) till reserverbjudandet. Du måste inkludera en Accept-rubrik i begäran, men du bör få HTTP-status 404 (Hittades inte) eftersom reserverbjudandet har tagits bort från behållaren.
