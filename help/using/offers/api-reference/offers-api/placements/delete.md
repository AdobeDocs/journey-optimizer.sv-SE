---
title: ta bort placeringar
description: Placeringar är behållare som används för att visa upp dina erbjudanden.
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: ca7af3b0-62cd-44ac-8856-b3d1ec15f284
source-git-commit: 805f7bdc921c53f63367041afbb6198d0ec05ad8
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 4%

---

# Ta bort en placering {#delete-placement}

Ibland kan det vara nödvändigt att ta bort (DELETE) en placering. Detta görs genom att en DELETE-begäran görs till [!DNL Offer Library] API som använder ID:t för placeringen som du vill ta bort.

**API-format**

```http
DELETE /{ENDPOINT_PATH}/placements/{ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps/` |
| `{ID}` | Instans-ID för placeringen som du vill uppdatera. | `offerPlacement1234` |

**Begäran**

```shell
curl -X DELETE 'https://platform.adobe.io/data/core/dps/placements/offerPlacement1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett lyckat svar returnerar HTTP-status 200 och en tom brödtext.

Du kan bekräfta borttagningen genom att försöka utföra en sökning (GET) på placeringen och få HTTP-statusen 404 (Hittades inte) eftersom placeringen har tagits bort.
