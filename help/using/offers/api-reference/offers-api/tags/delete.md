---
title: Ta bort samlingskvalificerare
description: Med en samling kvalificerare kan ni ordna och sortera genom era erbjudanden på ett bättre sätt.
feature: Decision Management, API
topic: Integrations
role: Developer
level: Experienced
exl-id: 335c1b80-f1f0-4fd0-add8-84b8cc5e2e00
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 0%

---


# Ta bort en samlingskvalificerare {#delete-tag}

Ibland kan det vara nödvändigt att ta bort (DELETE) en samlingskvalificerare (tidigare kallad &quot;tagg&quot;). Detta gör du genom att utföra en DELETE-begäran till API:t för erbjudandebiblioteket med ID:t för den samlingskvalificerare som du vill ta bort.

**API-format**

```http
DELETE /{ENDPOINT_PATH}/tags/{ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | ID:t för enheten som du vill ta bort. | `tag1234` |

**Begäran**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/tags/tag1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett lyckat svar returnerar HTTP-status 200 och en tom brödtext.

Du kan bekräfta borttagningen genom att försöka utföra en uppslagsbegäran (GET) till samlingskvalificeraren. Du bör få HTTP-status 404 (Hittades inte) eftersom samlingskvalificeraren har tagits bort.