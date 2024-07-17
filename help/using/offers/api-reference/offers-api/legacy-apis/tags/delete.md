---
title: Ta bort samlingskvalificerare
description: Med en samling kvalificerare kan ni ordna och sortera genom era erbjudanden på ett bättre sätt.
feature: Decision Management, API
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: cc67519e-7a80-49c7-8c8b-c777be633026
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 0%

---

# Ta bort en samlingskvalificerare {#delete-tag}

Ibland kan det vara nödvändigt att ta bort (DELETE) en samlingskvalificerare (tidigare kallad &quot;tagg&quot;). Endast samlingskvalificerare som du skapar i innehavarbehållaren kan tas bort. Detta görs genom att utföra en DELETE-begäran till [!DNL Offer Library]-API:t med $id för den samlingskvalificerare som du vill ta bort.

**API-format**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för databas-API:er. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | Behållaren där samlingskvalificerarna finns. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | Instans-ID för den samlingskvalificerare som du vill uppdatera. | `d48fd160-13dc-11eb-bc55-c11be7252432` |

**Begäran**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/d48fd160-13dc-11eb-bc55-c11be7252432' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett lyckat svar returnerar HTTP-status 202 (inget innehåll) och en tom brödtext.

Du kan bekräfta borttagningen genom att försöka med en sökbegäran (GET) till samlingskvalificeraren. Du måste inkludera en Accept-rubrik i begäran, men du bör få HTTP-status 404 (Hittades inte) eftersom samlingskvalificeraren har tagits bort från behållaren.
