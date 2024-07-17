---
title: Radera beslutsregler
description: Beslutsregler läggs till i ett personaliserat erbjudande och tillämpas på en profil för att avgöra vem som är berättigad.
feature: Decision Management, API
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 7c02041c-b022-4027-b932-294b207add80
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 3%

---

# Ta bort en beslutsregel {#delete-decision-rule}

Ibland kan det vara nödvändigt att ta bort (DELETE) en beslutsregel. Endast beslutsregler som du skapar i innehavarbehållaren kan tas bort. Detta görs genom att utföra en DELETE-begäran till [!DNL Offer Library]-API:t med instans-ID:t för den beslutsregel som du vill ta bort.

**API-format**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för databas-API:er. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | Behållaren där beslutsreglerna finns. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | Instans-ID för den beslutsregel som du vill uppdatera. | `eaa5af90-13d9-11eb-9472-194dee6dc381` |

**Begäran**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/eaa5af90-13d9-11eb-9472-194dee6dc381' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett lyckat svar returnerar HTTP-status 202 (inget innehåll) och en tom brödtext.

Du kan bekräfta borttagningen genom att försöka med en sökbegäran (GET) till beslutsregeln. Du måste inkludera en Accept-rubrik i begäran, men du bör få HTTP-statusen 404 (Hittades inte) eftersom beslutsregeln har tagits bort från behållaren.
