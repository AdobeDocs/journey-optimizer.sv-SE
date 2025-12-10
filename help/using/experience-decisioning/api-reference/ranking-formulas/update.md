---
title: Uppdatera rankningsformler
description: Med rankningsformler kan du definiera funktionerna för poängsättning, som används för att rangordna artiklar.
feature: API, Collections, Decisioning
topic: Integrations
role: Developer
level: Experienced
exl-id: 4ef1bfc2-e74f-4b44-b3b5-8a4f2fbd6438
version: Journey Orchestration
source-git-commit: 1735324b5fd330ecfc9261a54d0317b71d57ff4f
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 1%

---

# Uppdatera en rankningsformel {#update-ranking-formula}

Du kan ändra eller uppdatera en rankningsformel genom att göra en PUT-förfrågan till Offer Library API.

Mer information om JSON PUT, inklusive tillgängliga åtgärder, finns i den officiella [JSON PUT-dokumentationen](http://jsonpatch.com/).

**Godkänn och Content-Type-rubriker**

I följande tabell visas giltiga värden som omfattar fälten Content-Type i begärandehuvudet:

| Rubriknamn | Värde |
| --------- | ----------- |
| Content-Type | `application/json` |

**API-format**

```http
PUT /{ENDPOINT_PATH}/ranking-formulas/{ID}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |
| `{ID}` | ID:t för den entitet som du vill uppdatera. | `rankingFormula1234` |

**Begäran**

```shell
curl -X PATCH 'https://platform.adobe.io/data/core/dps/ranking-formulas/rankingFormula1234' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer  {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-d '{
    "name": "[UPDATED] Test Ranking Function DPS",
    "description": "Ranking  function description",
    "isPure": true,
    "exdFunction": true,
    "returnType": {
        "type": "integer"
    },
    "expression": {
        "type": "PQL",
        "format": "pql/text",
        "value": "if(offer.rank.priority.isNotNull(), offer.rank.priority, 0) * if(offer.tags.intersects(boosted.tags), 2, 1)"
    },
    "definedOn": {
        "offer": {
            "schema": {
                "altId": "_experience.offer-management.personalized-offer",
                "version": "0"
            }
        },
        "boosted": {
            "schema": {
                "altId": "_xdm.context.foo",
                "version": "0"
            }
        }
    }
}'
```

| Parameter | Beskrivning |
| --------- | ----------- |
| `value` | Det nya värdet som du vill uppdatera parametern med. |
| `path` | Sökvägen till den parameter som ska uppdateras. |
| `op` | Åtgärdsanropet som används för att definiera den åtgärd som krävs för att uppdatera anslutningen. Åtgärderna är: `add`, `replace`, `remove`, `copy` och `test`. |

**Svar**

Ett godkänt svar returnerar uppdaterade detaljer för rangordningsformeln, inklusive ID:t.

```json
{
    "etag": 2,
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
