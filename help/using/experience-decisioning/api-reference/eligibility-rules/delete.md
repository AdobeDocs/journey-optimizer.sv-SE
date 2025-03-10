---
title: Ta bort en berättiganderegel
description: Behörighetsregler gör att ni kan definiera de berättigade kandidaterna baserat på vad ni vill rikta, t.ex. profilattribut och målgrupper.
feature: Decision Management, API, Collections
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: 8fa34ebb7c853f9af5b3f58574374a3acb641dd9
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 0%

---

# Ta bort en berättiganderegel {#delete-eligibility-rule}

Ibland kan det vara nödvändigt att ta bort (DELETE) en regel för behörighet. Detta gör du genom att göra en DELETE-förfrågan till Offer Library API med ID:t för den behörighetsregel som du vill ta bort.

**API-format**

```http
DELETE /{ENDPOINT_PATH}/eligibility-rules/{ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | ID:t för enheten som du vill ta bort. | `rule1234` |

**Begäran**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/offer-rules/rule1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett lyckat svar returnerar HTTP-status 200 och en tom brödtext.

Du kan bekräfta borttagningen genom att försöka utföra en uppslagsbegäran (GET) för regeln. Du bör få HTTP-status 404 (Hittades inte) eftersom regeln har tagits bort.
