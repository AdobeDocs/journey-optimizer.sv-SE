---
title: Skapa en samlingskvalificerare
description: Med en samling kvalificerare kan ni ordna och sortera genom era erbjudanden på ett bättre sätt.
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: f3f7cccb-0173-409e-8b76-8b6e136a22ac
source-git-commit: 54b92b19f2e3a6afa6557ffeff0d971a4c411510
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 2%

---

# Skapa en samlingskvalificerare {#create-tag}

Du kan skapa en samlingskvalificerare (som tidigare kallades &quot;tagg&quot;) genom att göra en POST-förfrågan till [!DNL Offer Library] API.

## Sidhuvuden för acceptera och innehållstyp {#accept-and-content-type-headers}

I följande tabell visas giltiga värden som utgör *Content-Type* fält i begärandehuvudet:

| Rubriknamn | Värde |
| ----------- | ----- |
| Content-Type | `application/json` |

**API-format**

```http
POST /{ENDPOINT_PATH}/tags
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps/` |

**Begäran**

```shell
curl -X POST 'https://platform.adobe.io/data/core/dps/tags' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '{        
    "name": "Black Friday",
    "description": "Tag for black friday"
}'
```

**Svar**

Ett godkänt svar returnerar information om den nyligen skapade samlingskvalificeraren, inklusive dess `id`. Du kan använda den i senare steg för att uppdatera eller ta bort samlingskvalificeraren. Du kan använda din unika samlingskvalificerare `id` i senare självstudiekurser för att skapa samlingar och personaliserade erbjudanden.

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
