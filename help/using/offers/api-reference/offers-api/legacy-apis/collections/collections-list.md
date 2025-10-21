---
title: Lista samlingar
description: Samlingar är delmängder av erbjudanden som baseras på fördefinierade villkor som definieras av en marknadsförare, t.ex. erbjudandets kategori.
feature: Decision Management, API, Collections
topic: Integrations
role: Developer
level: Experienced
exl-id: ce39d77d-6d81-48d7-9e73-e1d537874018
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 2%

---

# Lista samlingar {#list-collections}

Samlingar är delmängder av erbjudanden som baseras på fördefinierade villkor som definieras av en marknadsförare, t.ex. erbjudandets kategori.

Du kan visa en lista över alla samlingar i en behållare genom att utföra en enda GET-begäran till API:t [!DNL Offer Library].

**API-format**

```http
GET /{ENDPOINT_PATH}/{CONTAINER_ID}/queries/core/search?schema={SCHEMA_FILTER}&{QUERY_PARAMS}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för databas-API:er. | `https://platform.adobe.io/data/core/xcore/` |
| `{QUERY_PARAMS}` | Valfria frågeparametrar för att filtrera resultat efter. | `limit=2` |
| `{CONTAINER_ID}` | Behållaren där samlingarna finns. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{SCHEMA_FILTER}` | Definierar det schema som är associerat med samlingar. <https://ns.adobe.com/experience/offer-management/offer-filter;version=0.1> |  |
| `{QUERY_PARAMS}` | Valfria frågeparametrar för att filtrera resultat efter. | `limit=1` |

**Begäran**

```shell
curl -X GET \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?schema=https://ns.adobe.com/experience/offer-management/offer-filter;version=0.1&limit=2' \
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
| `q` | En valfri frågesträng att söka efter i markerade fält. Frågesträngen ska vara i gemener och kan omges av citattecken för att förhindra att den tokeniseras och för att undvika specialtecken. Tecknen `+ - = && \|\| > < ! ( ) { } [ ] ^ \" ~ * ? : \ /` har en speciell innebörd och bör föregås av ett omvänt snedstreck när de visas i frågesträngen. | `demo collection` |
| `qop` | Använder AND- eller OR-operatorn på värden i q-frågesträngsparam. | `AND` / `OR` |
| `field` | Valfri lista med fält som sökningen ska begränsas till. Den här parametern kan upprepas så här: field=field1[, field=field2,..] och (sökvägsuttryck är i form av punktavgränsade sökvägar som _instance.xdm:name) | `_instance.xdm:name` |
| `orderBy` | Sortera resultat efter en specifik egenskap. Om du lägger till en `-` före-titel (`orderby=-title`) sorteras objekt efter titel i fallande ordning (Z-A). | `-repo:createdDate` |
| `limit` | Begränsa antalet returnerade samlingar. | `limit=5` |

**Svar**

Ett godkänt svar returnerar en lista med samlingar som finns i den behållare som du har åtkomst till.

```json
{
    "containerId": "e0bd8463-0913-4ca1-bd84-6309134ca1f6",
    "schemaNs": "https://ns.adobe.com/experience/offer-management/offer-filter;version=0.1",
    "requestTime": "2023-10-21T21:14:19.282175Z",
    "_embedded": {
        "results": [
            {
                "instanceId": "27c92e00-127d-11eb-b9fe-5bcfb5d7ef36",
                "schemas": [
                    "https://ns.adobe.com/experience/offer-management/offer-filter;version=0.3"
                ],
                "productContexts": [
                    "acp"
                ],
                "repo:etag": 1,
                "repo:createdDate": "2023-10-20T02:37:11.263718Z",
                "repo:lastModifiedDate": "2023-10-20T02:37:11.263718Z",
                "repo:createdBy": "{CREATED_BY}",
                "repo:lastModifiedBy": "{MODIFIED_BY}",
                "repo:createdByClientId": "{CREATED_CLIENT_ID}",
                "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}",
                "_instance": {
                    "xdm:ids": [
                        "xcore:tag:124bd3de7f598dd8"
                    ],
                    "xdm:name": "Mobile Demo",
                    "xdm:filterType": "anyTags",
                    "@id": "xcore:offer-filter:124bd44648f17ec1"
                },
                "_links": {
                    "self": {
                        "name": "https://ns.adobe.com/experience/offer-management/offer-filter;version=0.3#27c92e00-127d-11eb-b9fe-5bcfb5d7ef36",
                        "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/27c92e00-127d-11eb-b9fe-5bcfb5d7ef36",
                        "@type": "https://ns.adobe.com/experience/offer-management/offer-filter;version=0.3"
                    }
                },
                "sandboxName": "ode-prod-va7-edge-testing"
            },
            {
                "instanceId": "2c54fc90-f8f3-11ea-ad6e-775ad2c9b1a1",
                "schemas": [
                    "https://ns.adobe.com/experience/offer-management/offer-filter;version=0.3"
                ],
                "productContexts": [
                    "acp"
                ],
                "repo:etag": 1,
                "repo:createdDate": "2023-09-17T14:36:29.272451Z",
                "repo:lastModifiedDate": "2023-09-17T14:36:29.272451Z",
                "repo:createdBy": "{CREATED_BY}",
                "repo:lastModifiedBy": "{MODIFIED_BY}",
                "repo:createdByClientId": "{CREATED_CLIENT_ID}",
                "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}",
                "_instance": {
                    "xdm:ids": [
                        "xcore:personalized-offer:1221fbedfa4d98b0"
                    ],
                    "xdm:name": "demo collection",
                    "xdm:filterType": "offers",
                    "@id": "xcore:offer-filter:1221fc71c74d98b4"
                },
                "_links": {
                    "self": {
                        "name": "https://ns.adobe.com/experience/offer-management/offer-filter;version=0.3#2c54fc90-f8f3-11ea-ad6e-775ad2c9b1a1",
                        "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/2c54fc90-f8f3-11ea-ad6e-775ad2c9b1a1",
                        "@type": "https://ns.adobe.com/experience/offer-management/offer-filter;version=0.3"
                    }
                },
                "sandboxName": "ode-prod-va7-edge-testing"
            }
        ],
        "total": 8,
        "count": 2
    },
    "_links": {
        "self": {
            "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?schema=https://ns.adobe.com/experience/offer-management/offer-filter;version=0.1&limit=2",
            "@type": "https://ns.adobe.com/experience/xcore/hal/results"
        },
        "next": {
            "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?start=2c54fc90-f8f3-11ea-ad6e-775ad2c9b1a1&orderby=instanceId&schema=https://ns.adobe.com/experience/offer-management/offer-filter;version=0.1&limit=2",
            "@type": "https://ns.adobe.com/experience/xcore/hal/results"
        }
    }
}
```
