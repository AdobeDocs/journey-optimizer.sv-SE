---
title: Visa berättiganderegler
description: Behörighetsregler gör att ni kan definiera de berättigade kandidaterna baserat på vad ni vill rikta, t.ex. profilattribut och målgrupper.
feature: API, Collections, Decisioning
topic: Integrations
role: Developer
level: Experienced
exl-id: c8f88954-a721-4d18-9137-035ee9dc1bcf
version: Journey Orchestration
source-git-commit: 1735324b5fd330ecfc9261a54d0317b71d57ff4f
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 1%

---

# Visa berättiganderegler {#list-eligibilit-rules}

En berättiganderegel består av ett PQL-regeluttryck som definierar hur behörigheten ska definieras.

Du kan visa en lista över alla regler för behörighet genom att utföra en enda GET-begäran till Offer Library API.

**API-format**

```http
GET /{ENDPOINT_PATH}/offer-rules?{QUERY_PARAMS}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |
| `{QUERY_PARAMS}` | exdRule. | `property=exdRule%3D%3Dtrue` |

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
curl -X GET 'https://platform.adobe.io/data/core/dps/offer-rules?property=exdRule%3D%3Dtrue&limit=2' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett godkänt svar returnerar en lista med berättiganderegler som du har tillgång till.

```json
{
    "results": [
        {
            "created": "2024-10-28T01:18:08.506Z",
            "modified": "2024-10-28T01:18:08.506Z",
            "etag": 1,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/eligibility-rule"
            ],
            "createdBy": "3254197F65569E890A49422F@658557135fa10b860a494019",
            "lastModifiedBy": "3254197F65569E890A49422F@658557135fa10b860a494019",
            "id": "dps:eligibility-rule:19af09a9ae45a8d3",
            "name": "dasdsa",
            "description": "",
            "exdRule": true,
            "condition": {
                "type": "PQL",
                "format": "pql/text",
                "value": "personalEmail.address.equals(\"youz@adobe.com\", false)"
            },
            "segmentModel": {
                "lifecycleState": "published",
                "expression": {
                    "isValid": true,
                    "logicalOperator": "and",
                    "profileAttributesContainer": {
                        "exclude": false,
                        "items": [
                            {
                                "comparisonType": "equals",
                                "component": {
                                    "id": "profile.personalEmail.address",
                                    "__entity__": true,
                                    "type": "Sz"
                                },
                                "isCaseSensitive": false,
                                "isPlaceholder": false,
                                "originalLocation": [],
                                "value": [
                                    "youz@adobe.com"
                                ],
                                "itemType": "segmentRule"
                            }
                        ],
                        "logicalOperator": "and",
                        "itemType": "segmentContainer"
                    },
                    "xEventAttributesContainer": {
                        "exclude": false,
                        "items": [],
                        "logicalOperator": "then",
                        "itemType": "eventTypeCardContainer"
                    },
                    "itemType": "segmentDefinition"
                },
                "isMissingAnsibleModel": false,
                "relationalExpression": false,
                "deprecated": {
                    "status": false,
                    "reason": ""
                },
                "description": "",
                "evaluationInfo": {
                    "batch": {
                        "enabled": true
                    },
                    "continuous": {
                        "enabled": false
                    },
                    "synchronous": {
                        "enabled": false
                    }
                },
                "labels": [],
                "tags": [],
                "canHaveFolder": true,
                "mergePolicyId": "24526dbe-d615-4d41-9ebb-fd7f2b3dcdc2",
                "name": "dasdsa",
                "namespace": "ups"
            }
        },
        {
            "created": "2024-10-27T04:01:29.343Z",
            "modified": "2024-10-27T04:33:44.781Z",
            "etag": 2,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/eligibility-rule"
            ],
            "createdBy": "3254197F65569E890A49422F@658557135fa10b860a494019",
            "lastModifiedBy": "3254197F65569E890A49422F@658557135fa10b860a494019",
            "id": "dps:eligibility-rule:19ade575cf95e584",
            "name": "nick test pes",
            "description": "dasdsad",
            "exdRule": true,
            "condition": {
                "type": "PQL",
                "format": "pql/text",
                "value": "personalEmail.address.equals(\"youz@adobe.com\", false)"
            },
            "segmentModel": {
                "lifecycleState": "published",
                "expression": {
                    "isValid": true,
                    "logicalOperator": "and",
                    "profileAttributesContainer": {
                        "exclude": false,
                        "items": [
                            {
                                "comparisonType": "equals",
                                "component": {
                                    "id": "profile.personalEmail.address",
                                    "__entity__": true,
                                    "type": "Sz"
                                },
                                "isCaseSensitive": false,
                                "isPlaceholder": false,
                                "originalLocation": [],
                                "value": [
                                    "youz@adobe.com"
                                ],
                                "itemType": "segmentRule"
                            }
                        ],
                        "logicalOperator": "and",
                        "itemType": "segmentContainer"
                    },
                    "xEventAttributesContainer": {
                        "exclude": false,
                        "items": [],
                        "logicalOperator": "then",
                        "itemType": "eventTypeCardContainer"
                    },
                    "itemType": "segmentDefinition"
                },
                "isMissingAnsibleModel": false,
                "relationalExpression": false,
                "deprecated": {
                    "status": false,
                    "reason": ""
                },
                "description": "dasdsad",
                "evaluationInfo": {
                    "batch": {
                        "enabled": true
                    },
                    "continuous": {
                        "enabled": false
                    },
                    "synchronous": {
                        "enabled": false
                    }
                },
                "labels": [],
                "tags": [],
                "canHaveFolder": true,
                "mergePolicyId": "24526dbe-d615-4d41-9ebb-fd7f2b3dcdc2",
                "name": "nick test pes",
                "namespace": "ups",
                "estimates": [
                    {
                        "previewId": "MDpTQU1QTEVfUkVJTklUOmJiNjI0MmZkLWUyOGQtNDY0Ni05ZWJjLTc1YmU5NGQ0YjY1Nzow",
                        "addressabilityText": "Of total",
                        "color": "#12805c",
                        "estimateData": {
                            "previewId": "MDpTQU1QTEVfUkVJTklUOmJiNjI0MmZkLWUyOGQtNDY0Ni05ZWJjLTc1YmU5NGQ0YjY1Nzow",
                            "estimatedSize": 0,
                            "totalRows": 62088,
                            "percent": 0,
                            "standardError": 0,
                            "confidenceInterval": "95%",
                            "state": "RESULT_READY",
                            "profilesReadSoFar": 62088,
                            "numRowsToRead": 62088
                        },
                        "state": "RESULT_READY"
                    }
                ]
            }
        }
    ],
    "count": 2,
    "total": 229,
    "_links": {
        "self": {
            "href": "/offer-rules?orderby=-modified&limit=2",
            "type": "application/json"
        },
        "next": {
            "href": "/offer-rules?orderby=-modified&limit=2&start=2024-10-27T01:24:51.785Z",
            "type": "application/json"
        }
    }
}
```
