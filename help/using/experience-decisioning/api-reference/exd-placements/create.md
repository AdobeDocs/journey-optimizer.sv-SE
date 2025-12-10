---
title: Skapa en utökad placering
description: Externa strategier består av samlingar som är kopplade till begränsningar och rankningsmetoder för att fastställa erbjudanden.
feature: API, Collections, Decisioning
topic: Integrations
role: Developer
level: Experienced
version: Journey Orchestration
source-git-commit: 1735324b5fd330ecfc9261a54d0317b71d57ff4f
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 1%

---

# Skapa en utökad placering {#create-exd-placement}

Du kan skapa en utökad ersättning genom att göra en POST-begäran till erbjudandebiblioteks-API:t.

**Godkänn och Content-Type-rubriker**

I följande tabell visas giltiga värden som omfattar fälten Content-Type i begärandehuvudet:

| Parameter | Beskrivning |
| --------- | ----------- |
| Content-Type | `application/json` |

**API-format**

```http
POST /{ENDPOINT_PATH}/exd-placements
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |

**Begäran**

```shell
curl --location 'https://platform-stage.adobe.io/data/core/dps/exd-placements' \
--header 'Content-Type: application/json' \
--header 'x-gw-ims-org-id: {IMS_ORG}' \
--header 'x-sandbox-name: {SANDBOX_NAME}' \
--header 'x-api-key: {API_KEY}' \
--header 'Authorization: Bearer {ACCESS_TOKEN}' \
--data '{
  "name": "Test Exd Placement1 Pants",
  "channel": "https://ns.adobe.com/xdm/channel-types/email",
  "tags":["3d75b849-b344-402b-9d9e-5d750bd46884"],
  "channelConfiguration":"530b76f9-dcd6-4fd5-8c52-38e29b04a60a",
  "description": "compressing alarm",
  "status":"active"
}'
```

**Svar**

Ett godkänt svar returnerar information om den nya expanderingen inklusive ID:t. Du kan använda ID:t i senare steg för att uppdatera eller ta bort din utökade placering.

```json
{
    "id": "dps:exd-placement:19cb038eca47bead",
    "sandboxId": "068abf40-575e-11ea-8512-9b1bfdb82603",
    "etag": 2,
    "createdDate": "2024-11-18T18:48:56.298Z",
    "lastModifiedDate": "2024-11-18T18:57:27.457Z",
    "createdBy": "71486D7B5F4011980A494030@AdobeID",
    "lastModifiedBy": "71486D7B5F4011980A494030@AdobeID",
    "lastModifiedByClientId": "CJMTestClientACP"
}
```
