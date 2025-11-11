---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: Lista personaliserade erbjudanden
description: Ett personaliserat erbjudande är ett anpassningsbart marknadsföringsmeddelande som baseras på regler och begränsningar för behörighet.
feature: Decision Management, API
topic: Integrations
role: Developer
level: Experienced
exl-id: 50f4119f-c730-4883-867e-eac83793dced
version: Journey Orchestration
source-git-commit: d6a9a8a392f0492aa6e4f059198ce77b6b2cd962
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 3%

---

# Lista personaliserade erbjudanden {#list-personalized-offers}

Ett personaliserat erbjudande är ett anpassningsbart marknadsföringsmeddelande som baseras på regler och begränsningar för behörighet.

Du kan visa en lista över alla anpassade erbjudanden i en behållare genom att utföra en enda GET-begäran till API:t [!DNL Offer Library].

**API-format**

```http
GET /{ENDPOINT_PATH}/{CONTAINER_ID}/queries/core/search?schema={SCHEMA_PERSONALIZED_OFFER}&{QUERY_PARAMS}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för databas-API:er. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | Behållaren där personaliserade erbjudanden finns. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{SCHEMA_PERSONALIZED_OFFER}` | Definierar det schema som är associerat med personaliserade erbjudanden. | `https://ns.adobe.com/experience/offer-management/personalized-offer;version=0.5` |
| `{QUERY_PARAMS}` | Valfria frågeparametrar för att filtrera resultat efter. | `limit=1` |

**Begäran**

```shell
curl -X GET \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?schema=https://ns.adobe.com/experience/offer-management/personalized-offer;version=0.5&limit=1' \
  -H 'Accept: *,application/vnd.adobe.platform.xcore.hal+json; schema="https://ns.adobe.com/experience/xcore/hal/results"' \
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
| `q` | En valfri frågesträng att söka efter i markerade fält. Frågesträngen ska vara i gemener och kan omges av citattecken för att förhindra att den tokeniseras och för att undvika specialtecken. Tecknen `+ - = && \|\| > < ! ( ) { } [ ] ^ \" ~ * ? : \ /` har en speciell innebörd och bör föregås av ett omvänt snedstreck när de visas i frågesträngen. | `discounted offers` |
| `qop` | Använder AND- eller OR-operatorn på värden i q-frågesträngsparam. | `AND` / `OR` |
| `field` | Valfri lista med fält som sökningen ska begränsas till. Den här parametern kan upprepas så här: field=field1[, field=field2,..] och (sökvägsuttryck är i form av punktavgränsade sökvägar som _instance.xdm:name) | `_instance.xdm:name` |
| `orderBy` | Sortera resultat efter en specifik egenskap. Om du lägger till en `-` före-titel (`orderby=-title`) sorteras objekt efter titel i fallande ordning (Z-A). | `-repo:createdDate` |
| `limit` | Begränsa antalet returnerade personaliserade erbjudanden. | `limit=5` |

**Svar**

Ett godkänt svar returnerar en lista med personliga erbjudanden som finns i den behållare du har tillgång till.

```json
{
    "containerId": "e0bd8463-0913-4ca1-bd84-6309134ca1f6",
    "schemaNs": "https://ns.adobe.com/experience/offer-management/personalized-offer;version=0.5",
    "requestTime": "2023-10-22T20:36:50.408105Z",
    "_embedded": {
    "results": [
        {
                "instanceId": "2cdb4d10-149e-11eb-b1a9-a779d2fe8690",
            "schemas": [
                    "https://ns.adobe.com/experience/offer-management/personalized-offer;version=0.5"
            ],
                "productContexts": [
                    "acp"
                ],
                "repo:etag": 2,
                "repo:createdDate": "2023-10-22T19:38:35.489354Z",
                "repo:lastModifiedDate": "2023-10-22T19:45:43.839088Z",
                "repo:createdBy": "{CREATED_BY}",
                "repo:lastModifiedBy": "{MODIFIED_BY}",
                "repo:createdByClientId": "{CREATED_CLIENT_ID}",
                "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}",
                "_instance": {
                    "xdm:name": "Checking Advanced",
                    "xdm:representations": [
                        {
                            "xdm:components": [
                                {
                                    "dc:format": "image/png",
                                    "repo:id": "urn:aaid:sc:US:7db21be9-89ee-472a-b2c9-91f7a39ada51",
                                    "repo:resolveURL": "https://platform-cs-va6.adobe.io/content/storage/id/urn:aaid:sc:US:7db21be9-89ee-472a-b2c9-91f7a39ada51/:rendition;size=300",
                                    "repo:name": "mobile-check-deposit.png",
                                    "dc:language": [
                                        "en-us"
                                    ],
                                    "@type": "https://ns.adobe.com/experience/offer-management/content-component-imagelink",
                                    "xdm:deliveryURL": ""
                                }
                            ],
                            "xdm:channel": "https://ns.adobe.com/xdm/channel-types/offline",
                            "xdm:placement": "xcore:offer-placement:124f4e33724bb15f"
                        },
                {
                            "xdm:components": [
                        {
                                    "dc:format": "text/html",
                                    "repo:name": "my content",
                                    "dc:language": [
                                "en-us"
                            ],
                                    "xdm:content": "{\n\"foo\": \"bar\"\n}",
                                    "@type": "https://ns.adobe.com/experience/offer-management/content-component-html"
                        }
                            ],
                            "xdm:channel": "https://ns.adobe.com/xdm/channel-types/web",
                            "xdm:placement": "xcore:offer-placement:124e0be5699743d3"
                }
            ],
                    "xdm:rank": {
                        "xdm:priority": 10
                    },
                    "xdm:characteristics": {
                        "PROD": "checking",
                        "offer_code": "CHECK200",
                        "region": "NA"
            },
                    "xdm:selectionConstraint": {
                        "xdm:startDate": "2023-10-22T07:00:00.000Z",
                        "xdm:endDate": "2023-12-31T08:00:00.000Z",
                        "xdm:eligibilityRule": "xcore:eligibility-rule:124f4f57259caba5"
            },
                    "xdm:status": "draft",
                    "xdm:cappingConstraint": {
                        "xdm:globalCap": 1000
                    },
                    "xdm:tags": [
                        "xcore:tag:124f4e5c8a00cd92",
                        "xcore:tag:1229cf47455177b1"
                    ],
                    "@id": "xcore:personalized-offer:124f513c290bb16e"
                },
                "_links": {
                    "self": {
                        "name": "https://ns.adobe.com/experience/offer-management/personalized-offer;version=0.5#2cdb4d10-149e-11eb-b1a9-a779d2fe8690",
                        "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/2cdb4d10-149e-11eb-b1a9-a779d2fe8690",
                        "@type": "https://ns.adobe.com/experience/offer-management/personalized-offer;version=0.5"
                    }
                },
                "sandboxName": "ode-prod-va7-edge-testing"
        }
    ],
        "total": 15,
        "count": 1
    },
    "_links": {
        "self": {
            "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?schema=https://ns.adobe.com/experience/offer-management/personalized-offer;version=0.5&orderby=-repo:createdDate&limit=1",
            "@type": "https://ns.adobe.com/experience/xcore/hal/results"
        },
        "next": {
            "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?start=1603395515489%2C2cdb4d10-149e-11eb-b1a9-a779d2fe8690&schema=https://ns.adobe.com/experience/offer-management/personalized-offer;version=0.5&orderby=-repo%3AcreatedDate%2CinstanceId&limit=1",
            "@type": "https://ns.adobe.com/experience/xcore/hal/results"
        }
    }
}
```
