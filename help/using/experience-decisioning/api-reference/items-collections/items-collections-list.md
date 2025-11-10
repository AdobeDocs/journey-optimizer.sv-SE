---
title: Visa artikelsamlingar
description: Med samlingar kan du kategorisera och gruppera beslutsobjekt enligt dina önskemål.
feature: Decision Management, API, Collections
topic: Integrations
role: Developer
level: Experienced
exl-id: cc9f0d7a-6166-4736-8cb7-1989816708ad
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Visa artikelsamlingar {#list-decision-items}

Med samlingar, som också kallas objektsamlingar, kan du kategorisera och gruppera dina beslutsobjekt efter dina önskemål. Dessa kategorier skapas genom att regler som utnyttjar attributen för beslutsposter skapas.

Du kan visa en lista över alla objektsamlingar genom att utföra en enda GET-begäran till Offer Library API.

**API-format**

```http
GET /{ENDPOINT_PATH}/item-collections?{QUERY_PARAMS}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |
| `{QUERY_PARAMS}` | Valfria frågeparametrar för att filtrera resultat efter. | `limit=2` |

## Använda frågeparametrar {#using-query-parameters}

Du kan använda frågeparametrar för att sidgranska och filtrera resultat när du visar resurser.

### Sidindelning {#paging}

De vanligaste frågeparametrarna för sidindelning är:

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `property` | En valfri egenskap: <ul><li>Egenskaperna grupperas efter AND-åtgärd.</li><li>Parametrar kan upprepas så här: property={PROPERTY_EXPR}[&amp;property={PROPERTY_EXPR2}..] eller property={PROPERTY_EXPR1}[,{PROPERTY_EXPR2}..]</li><li>Egenskapsuttryck har formatet `[ !]field[op]value`, med `op` i `[==,!=,<=,>=,<,>,~]`, som stöder reguljära uttryck.</li></ul> | `property=name!=abc&property=id~.*1234.*&property=description equivalent with property=name!=abc,id~.*1234.*,description.` |
| `orderBy` | Sortera resultat efter en specifik egenskap. Om du lägger till ett - före namn (orderBy=-name) sorteras objekten efter namn i fallande ordning (Z-A). Banuttryck är i form av punktavgränsade banor. Den här parametern kan upprepas så här: `orderby=field1[,-fields2,field3,...]` | `orderby=id`,`-name` |
| `limit` | Begränsa antalet enheter som returneras. | `limit=5` |

**Begäran**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/item-collections?limit=2' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett godkänt svar returnerar en lista med objektsamlingar som du har tillgång till.

```json
{
    "results": [
        {
            "created": "2024-01-31T18:28:52.888Z",
            "modified": "2024-06-28T19:44:13.112Z",
            "etag": 7,
            "schemas": [
                "https://ns.adobe.com/experience/decisioning/item-collection;version=1.2"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "itemCollection1234",
            "name": "Item collection One",
            "description": "Item collection",
            "constraints": [
                {
                    "itemCatalogId": "itemCatalog1234",
                    "uiModel": "{\"operator\":\"equals\",\"value\":{\"left\":\"_experience.decisioning.decisionitem.itemName\",\"right\":\"Some offer item\"}}"
                }
            ],
            "tags": []
        },
        {
            "created": "2024-06-10T16:02:57.878Z",
            "modified": "2024-06-10T16:02:57.878Z",
            "etag": 1,
            "schemas": [
                "https://ns.adobe.com/experience/decisioning/item-collection;version=1.2"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "itemCollection5678",
            "name": "Item collection One",
            "description": "Item collection",
            "constraints": [
                {
                    "itemCatalogId": "itemCatalog1234",
                    "uiModel": "{\"operator\":\"greater than\",\"value\":{\"left\":\"_<imsOrg>.some_integer\",\"right\":100}}"
                }
            ],
            "tags": []
        }
    ],
    "count": 2,
    "total": 166,
    "_links": {
        "self": {
            "href": "/item-collections?orderby=-modified&limit=2",
            "type": "application/json"
        },
        "next": {
            "href": "/item-collections?orderby=-modified&limit=2&start=2024-06-04T23:37:33.980Z",
            "type": "application/json"
        }
    }
}
```
