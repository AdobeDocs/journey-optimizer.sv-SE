---
title: Skapa en berättiganderegel
description: Behörighetsregler gör att ni kan definiera de berättigade kandidaterna baserat på vad ni vill rikta, t.ex. profilattribut och målgrupper.
feature: Decision Management, API, Collections
topic: Integrations
role: Developer
level: Experienced
exl-id: 39c6e82e-c1b1-4dda-a941-3db6324cef37
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 1%

---

# Skapa en berättiganderegel {#create-eligibility-rule}

Du kan skapa en berättiganderegel genom att göra en POST-begäran till erbjudandebiblioteks-API:t.

**API-format**

```http
POST /{ENDPOINT_PATH}/eligibility-rules 
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |

**Begäran**

```shell
curl -X POST 'https://platform.adobe.io/data/core/dps/offer-rules' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '
{
    "name": "test dule",
    "description": "xxxxxx",
    "exdRule": true,
    "condition": {
        "type": "PQL",
        "format": "pql/text",
        "value": "inSegment(\"849807b6-0a76-4895-96d9-89996477f23b\") and billingAddress.city.equals(\"san jose\", false)"
    }
}'
```

**Svar**

Ett godkänt svar returnerar information om den nyligen skapade berättiganderegeln inklusive ID:t. Du kan använda ID:t i senare steg för att uppdatera eller ta bort din berättiganderegel.

```json
{
    "etag": 1,
    "createdBy": "{CREATED_BY}",
    "lastModifiedBy": "{MODIFIED_BY}",
    "id": "{ID}",
    "sandboxId": "{SANDBOX_ID}",
    "createdDate": "2023-05-31T15:09:11.771Z",
    "lastModifiedDate": "2023-05-31T15:09:11.771Z",
    "createdByClientId": "{CREATED_CLIENT_ID}",
    "lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```
