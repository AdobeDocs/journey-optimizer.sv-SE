---
title: Ta bort samlingskvalificerare
description: Med en samling kvalificerare kan ni ordna och sortera genom era erbjudanden på ett bättre sätt.
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 335c1b80-f1f0-4fd0-add8-84b8cc5e2e00
source-git-commit: 805f7bdc921c53f63367041afbb6198d0ec05ad8
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 1%

---

# Ta bort en samlingskvalificerare {#delete-tag}

Ibland kan det vara nödvändigt att ta bort (DELETE) en samlingskvalificerare (tidigare kallad &quot;tagg&quot;). Detta görs genom att en DELETE-begäran görs till [!DNL Offer Library] API som använder ID:t för den samlingskvalificerare som du vill ta bort.

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

Du kan bekräfta borttagningen genom att försöka med en sökbegäran (GET) till samlingskvalificeraren och få HTTP-statusen 404 (Hittades inte) eftersom den har tagits bort.