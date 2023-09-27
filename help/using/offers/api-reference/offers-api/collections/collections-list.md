---
title: Lista samlingar
description: Samlingar är delmängder av erbjudanden som baseras på fördefinierade villkor som definieras av en marknadsförare, t.ex. erbjudandets kategori.
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: f27ffbe0-a61a-428a-bc37-db6b56e38a83
source-git-commit: 805f7bdc921c53f63367041afbb6198d0ec05ad8
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 3%

---

# Lista samlingar {#list-collections}

Samlingar är delmängder av erbjudanden som baseras på fördefinierade villkor som definieras av en marknadsförare, t.ex. erbjudandets kategori.

Du kan visa en lista över alla samlingar genom att utföra en enda GET-förfrågan till [!DNL Offer Library] API.

**API-format**

```http
GET /{ENDPOINT_PATH}/offer-collections?{QUERY_PARAMS}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |
| `{QUERY_PARAMS}` | Valfria frågeparametrar för att filtrera resultat efter. | `limit=2` |

**Begäran**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/offer-collections?limit=2' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

## Använda frågeparametrar {#using-query-parameters}

Du kan använda frågeparametrar för att sidgranska och filtrera resultat när du visar resurser.

### Sidindelning {#paging}

De vanligaste frågeparametrarna för sidindelning är:

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `property` | En valfri egenskap: <br> <ul> - Egenskaperna grupperas efter AND-åtgärd. <br><br> - Parametrar kan upprepas så här: property=<property-expr>[&amp;property=<property-expr2>...] eller property=<property-expr1>[,<property-expr2>...] <br><br> - Egenskapsuttryck är i format [!]fält[op]värde, med början in [==,!=,&lt;=,>=,&lt;,>,~], stöd för reguljära uttryck | `property=name!=abc&property=id~.*1234.*&property=description equivalent with property=name!=abc,id~.*1234.*,description.` |
| `orderBy` | Sortera resultat efter en specifik egenskap. Om du lägger till ett - före namn (orderBy=-name) sorteras objekten efter namn i fallande ordning (Z-A). Banuttryck är i form av punktavgränsade banor. Den här parametern kan upprepas så här: `orderby=field1[,-fields2,field3,...]` | `orderby=id`,`-name` |
| `limit` | Begränsa antalet enheter som returneras. | `limit=5` |

**Svar**

Ett godkänt svar returnerar en lista med samlingar som finns i den behållare som du har åtkomst till.

```json
{
        "results": [
        {
            "created": "2022-09-16T18:59:23.063+00:00",
            "modified": "2022-09-16T18:59:23.063+00:00",
            "etag": 1,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/offer-filter;version=0.4"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "offerCollection1234",
            "name": "Test Collection with tags",
            "filterType": "any-tags",
            "ids": [
                "tag1234"
            ],
            "labels": [
                "core/C5",
                "custom/myLabel"
            ]
        },
        {
            "created": "2023-05-15T12:50:49.887+00:00",
            "modified": "2023-05-15T12:50:49.887+00:00",
            "etag": 1,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/offer-filter;version=0.4"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "offerCollection5678",
            "name": "Test Collection with offers",
            "filterType": "offers",
            "ids": [
                "personalizedOffer1234",
                "personalizedOffer5678"
            ]
        }
    ],
    "count": 2,
    "total": 9,
    "_links": {
        "self": {
            "href": "/offer-collections?href={SELF_HREF}&limit=2",
            "type": "application/json"
        },
        "next": {
            "href": "/offer-collections?href={NEXT_HREF}&limit=2",
            "type": "application/json"
        }
    }
}
```
