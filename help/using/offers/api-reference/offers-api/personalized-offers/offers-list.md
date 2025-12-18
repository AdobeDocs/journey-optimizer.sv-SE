---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: Lista personaliserade erbjudanden
description: Ett personaliserat erbjudande är ett anpassningsbart marknadsföringsmeddelande som baseras på regler och begränsningar för behörighet.
feature: Decision Management, API
badge: label="Äldre" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: 45d51918-1106-4b6b-b383-8ab4d9a4f7af
version: Journey Orchestration
source-git-commit: 8732a73118b807eaa7f57cfdad60355b535282ff
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 3%

---


# Lista personaliserade erbjudanden {#list-personalized-offers}

>[!TIP]
>
>Beslutsfattandet, [!DNL Adobe Journey Optimizer]s nya beslutsfunktion, är nu tillgängligt via den kodbaserade upplevelsen och e-postkanalerna! [Läs mer](../../experience-decisioning/gs-experience-decisioning.md)


Ett personaliserat erbjudande är ett anpassningsbart marknadsföringsmeddelande som baseras på regler och begränsningar för behörighet.

Du kan visa en lista över alla personaliserade erbjudanden genom att utföra en enda GET-begäran till API:t [!DNL Offer Library].

**API-format**

```http
GET /{ENDPOINT_PATH}/offers?offer-type=personalized&{QUERY_PARAMS}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |
| `{QUERY_PARAMS}` | Valfria frågeparametrar för att filtrera resultat efter. | `limit=2` |

**Begäran**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/offers?offer-type=personalized&limit=2' \
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
| `property` | En valfri egenskap: <ul><li>Egenskaperna grupperas efter AND-åtgärd.</li><li>Parametrar kan upprepas så här: property={PROPERTY_EXPR}[&amp;property={PROPERTY_EXPR2}..] eller property={PROPERTY_EXPR1}[,{PROPERTY_EXPR2}..]</li><li>Egenskapsuttryck har formatet `[ !]field[op]value`, med `op` i `[==,!=,<=,>=,<,>,~]`, som stöder reguljära uttryck.</li></ul> | `property=name!=abc&property=id~.*1234.*&property=description equivalent with property=name!=abc,id~.*1234.*,description.` |
| `orderBy` | Sortera resultat efter en specifik egenskap. Om du lägger till ett - före namn (orderBy=-name) sorteras objekten efter namn i fallande ordning (Z-A). Banuttryck är i form av punktavgränsade banor. Den här parametern kan upprepas så här: `orderby=field1[,-fields2,field3,...]` | `orderby=id`,`-name` |
| `limit` | Begränsa antalet returnerade placeringar. | `limit=5` |

**Svar**

Ett lyckat svar returnerar en lista med personaliserade erbjudanden som finns tillsammans med de som du har tillgång till.

```json
{
    "results": [
        {
            "created": "2023-05-15T14:35:16.781+00:00",
            "modified": "2023-05-15T14:38:26.691+00:00",
            "etag": 2,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/personalized-offer;version=0.15"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "personalizedOffer1234",
            "name": "Test personalized offer with frequency constraint",
            "status": "draft",
            "representations": [
                {
                    "channel": "https://ns.adobe.com/xdm/channel-types/web",
                    "placement": "offerPlacement1234",
                    "components": [
                        {
                            "type": "html",
                            "format": "text/html",
                            "language": [
                                "en-us"
                            ],
                            "content": "Hello You qualify for our Discount of 60%"
                        }
                    ]
                }
            ],
            "selectionConstraint": {
                "startDate": "2022-07-27T05:00:00.000+00:00",
                "endDate": "2023-07-29T05:00:00.000+00:00",
                "profileConstraintType": "none"
            },
            "rank": {
                "priority": 0
            },
            "cappingConstraint": {},
            "frequencyCappingConstraints": [
                {
                    "enabled": false,
                    "limit": 1,
                    "startDate": "2023-05-15T14:25:49.622+00:00",
                    "endDate": "2023-05-25T14:25:49.622+00:00",
                    "scope": "global",
                    "entity": "offer",
                    "repeat": {
                        "enabled": false,
                        "unit": "month",
                        "unitCount": 1
                    }
                }
            ]
        }
    ],
    "count": 1,
    "total": 1,
    "_links": {
        "self": {
            "href": "/offers?offer-type=personalized&href={SELF_HREF}",
            "type": "application/json"
        }
    }
}
```

Utför sidnumrering om flera personaliserade erbjudanden saknas i svaret.

**Svar**

```json
{
    "results": [...],
    "count": 2,
    "total": 43,
    "_links": {
        "self": {
        "href": "/offers?orderby=-modified&limit=2&offer-type=PERSONALIZED",
        "type": "application/json"
        },
        "next": {
        "href": "/offers?orderby=-modified&limit=2&start={TIMESTAMP}&offer-type=PERSONALIZED",
        "type": "application/json"
        }
    }
    }
```

| Mått | Beskrivning |
|---------|-------------|
| `total` | Antalet personaliserade erbjudanden. |
| `count` | Antalet erbjudanden som returneras i det här svaret. |

Hämta slutpunkten från `_links.next.href`, till exempel `/offers?orderby=-modified&limit=2&start={TIMESTAMP}&offer-type=PERSONALIZED`, och lägg till den i API:t.

**API-format**

```http
GET /{ENDPOINT_PATH}/offers?orderby=-modified&limit=2&start={TIMESTAMP}&offer-type=PERSONALIZED
```

```json
{
    "results": [...],
    "count": 2,
    "total": 43,
    "_links": {
        "self": {...},
        "next": {
        "href": "/offers?orderby=-modified&limit=2&start={TIMESTAMP}&offer-type=PERSONALIZED",
        "type": "application/json"
        }
    }
}
```

Om du inte är på den första sidan och behöver hämta föregående sida med personaliserade erbjudanden använder du värdet `href` från `_links.prev`. Gör en begäran till URL:en om att hämta föregående resultatuppsättning, vilket visas i exemplet nedan.

**Svar**

```json
{
    "results": [...],
    "count": 2,
    "total": 43,
    "_links": {
        "self": {...},
        "next": {...},
        "prev": {
        "href": "/offers?orderby=-modified&limit=2&start={TIMESTAMP}&offer-type=PERSONALIZED",
        "type": "application/json"
        }
    }
}
```
