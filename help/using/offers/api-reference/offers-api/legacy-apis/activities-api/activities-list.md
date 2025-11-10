---
title: Lista beslut
description: Ett beslut innehåller den logik som ligger till grund för valet av ett erbjudande.
feature: Decision Management, API
topic: Integrations
role: Developer
level: Experienced
exl-id: e9bd7602-8945-4768-8a56-dc13ade32a0b
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 2%

---

# Lista beslut {#list-decisions}

Ett beslut innehåller den logik som ligger till grund för valet av ett erbjudande.

Du kan visa en lista över alla beslut i en behållare genom att utföra en enda GET-begäran till API:t [!DNL Offer Library].

**API-format**

```http
GET /{ENDPOINT_PATH}/{CONTAINER_ID}/queries/core/search?schema={SCHEMA_ACTIVITIES}&{QUERY_PARAMS}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för databas-API:er. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | Behållaren där besluten finns. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{SCHEMA_ACTIVITIES}` | Definierar det schema som är associerat med beslut. | `https://ns.adobe.com/experience/offer-management/offer-activity;version=0.5` |
| `{QUERY_PARAMS}` | Valfria frågeparametrar för att filtrera resultat efter. | `limit=2` |

**Begäran**

```shell
curl -X GET \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?schema=https://ns.adobe.com/experience/offer-management/offer-activity;version=0.5&limit=2' \
  -H 'Accept: *,application/vnd.adobe.platform.xcore.hal+json; schema="https://ns.adobe.com/experience/xcore/hal/results"' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `q` | En valfri frågesträng att söka efter i markerade fält. Frågesträngen ska vara i gemener och kan omges av citattecken för att förhindra att den tokeniseras och för att undvika specialtecken. Tecknen `+ - = && \|\| > < ! ( ) { } [ ] ^ \" ~ * ? : \ /` har en speciell innebörd och bör föregås av ett omvänt snedstreck när de visas i frågesträngen. | `default` |
| `qop` | Använder AND- eller OR-operatorn på värden i q-frågesträngsparam. | `AND` / `OR` |
| `field` | Valfri lista med fält som sökningen ska begränsas till. Den här parametern kan upprepas så här: field=field1[, field=field2,..] och (sökvägsuttryck är i form av punktavgränsade sökvägar som _instance.xdm:name) | `_instance.xdm:name` |
| `orderBy` | Sortera resultat efter en specifik egenskap. Om du lägger till en `-` före-titel (`orderby=-title`) sorteras objekt efter titel i fallande ordning (Z-A). | `-repo:createdDate` |
| `limit` | Begränsa antalet beslut som returneras. | `limit=5` |

**Svar**

Ett godkänt svar returnerar en lista med beslut som finns i den behållare som du har åtkomst till.

```json
{
    "results": [
        {
            "created": "2022-07-05T09:02:02.835+00:00",
            "modified": "2022-08-16T21:40:58.573+00:00",
            "etag": 12,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/offer-activity;version=0.8"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "offerDecision1234",
            "name": "Test Decision One",
            "status": "live",
            "startDate": "2022-05-18T00:09:57.706+00:00",
            "endDate": "2032-08-13T21:40:58.235+00:00",
            "fallback": "fallbackOffer1234",
            "criteria": [
                {
                    "placements": [
                        "offerPlacement1234",
                        "offerPlacement5678"
                    ],
                    "rank": {
                        "priority": 0,
                        "order": {
                            "orderEvaluationType": "ranking-strategy",
                            "rankingStrategy": "123456789123"
                        }
                    },
                    "profileConstraint": {
                        "profileConstraintType": "none"
                    },
                    "optionSelection": {
                        "filter": "offerCollection1234"
                    }
                }
            ]
        },
        {
            "created": "2022-09-05T14:12:13.773+00:00",
            "modified": "2022-09-05T14:12:13.773+00:00",
            "etag": 1,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/offer-activity;version=0.8"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "offerDecision5678",
            "name": "Test Decision Two",
            "status": "live",
            "startDate": "2022-08-31T21:00:00.000+00:00",
            "endDate": "2023-02-03T22:00:00.000+00:00",
            "fallback": "fallbackOffer5678",
            "criteria": [
                {
                    "placements": [
                        "offerPlacement1234"
                    ],
                    "rank": {
                        "priority": 2
                    },
                    "optionSelection": {
                        "filter": "offerCollection5678"
                    }
                },
                {
                    "placements": [
                        "offerPlacement5678"
                    ],
                    "rank": {
                        "priority": 1
                    },
                    "optionSelection": {
                        "filter": "offerCollection1234"
                    }
                }          
            ]
        }
    ],
    "count": 2,
    "total": 21,
    "_links": {
        "self": {
            "href": "/offer-decisions?href={SELF_HREF}&limit=2",
            "type": "application/json"
        },
        "next": {
            "href": "/offer-decisions?href={NEXT_HREF}&limit=2",
            "type": "application/json"
        }
    }
}
```
