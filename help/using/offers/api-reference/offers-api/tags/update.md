---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: Uppdatera samlingskvalificerare
description: Med en samling kvalificerare kan ni ordna och sortera genom era erbjudanden på ett bättre sätt.
feature: Decision Management, API
badge: label="Äldre" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: 918927e1-ad7a-4937-b652-2a0932e9efa1
version: Journey Orchestration
source-git-commit: 8732a73118b807eaa7f57cfdad60355b535282ff
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 2%

---


# Uppdatera en samlingskvalificerare {#update-collection-qualifier}

>[!TIP]
>
>Beslutsfattandet, [!DNL Adobe Journey Optimizer]s nya beslutsfunktion, är nu tillgängligt via den kodbaserade upplevelsen och e-postkanalerna! [Läs mer](../../experience-decisioning/gs-experience-decisioning.md)


Du kan ändra eller uppdatera en samlingskvalificerare (som tidigare kallades &quot;tagg&quot;) genom att göra en PATCH-begäran i Offer Library API.

Mer information om JSON Patch, inklusive tillgängliga åtgärder, finns i den officiella [JSON Patch-dokumentationen](https://jsonpatch.com/).

## Sidhuvuden för acceptera och innehållstyp {#accept-and-content-type-headers}

I följande tabell visas giltiga värden som utgör fältet *Content-Type* i begärandehuvudet:

| Rubriknamn | Värde |
| ----------- | ----- |
| Content-Type | `application/json` |

**API-format**

```http
PATCH /{ENDPOINT_PATH}/tags/{ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | ID:t för enheten som du vill uppdatera. | `tag1234` |

**Begäran**

```shell
curl -X PATCH 'https://platform.adobe.io/data/core/dps/tags/tag1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '[
    {
        "op": "replace",
        "path": "/name",
        "value": "Updated tag"
    },
    {
        "op": "replace",
        "path": "/description",
        "value": "Updated tag description"
    }
]'
```

**Svar**

Ett lyckat svar returnerar den uppdaterade informationen om samlingskvalificeraren, inklusive dess unika `id`.

```json
{
    "id": "{ID}",
    "sandboxId": "{SANDBOX_ID}",
    "etag": 2,
    "createdDate": "2023-09-07T12:36:26.602Z",
    "lastModifiedDate": "2023-09-07T12:36:26.602Z",
    "createdBy": "{CREATED_BY}",
    "lastModifiedBy": "{MODIFIED_BY}",
    "createdByClientId": "{CREATED_CLIENT_ID}",
    "lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```
