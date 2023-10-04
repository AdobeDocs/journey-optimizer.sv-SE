---
title: Slå upp en placering
description: Placeringar är behållare som används för att visa upp dina erbjudanden.
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: f5372ee271851ffb5aa1f5ff281282c8c474dc2a
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 1%

---


# Slå upp en placering {#look-up-placement}

Du kan söka efter specifika placeringar genom att göra en GET-förfrågan till [!DNL Offer Library] API som innehåller antingen placeringen `@id` eller namnet på placeringen i begärandesökvägen.

**API-format**

```http
GET /{ENDPOINT_PATH}/{CONTAINER_ID}/queries/core/search?schema={SCHEMA_PLACEMENT}&{QUERY_PARAMS}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för databas-API:er. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | Behållaren där placeringarna finns. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `SCHEMA_PLACEMENT}` | Definierar schemat som är associerat med placeringar. | `https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4` |
| `id` | En sträng som matchar `@id` enheternas egenskap. Strängen matchas exakt. Parametrarna `id` och `name` kan inte användas tillsammans. | `xcore:offer-placement:124541309805b7e8` |
| `name` | En sträng som används för att matcha egenskapen xdm:name för entiteterna. Strängen matchas exakt med versaler, men jokertecken kan användas. Parametrarna `id` och `name` kan inte användas tillsammans | `Sales and Promotions Placement` |

```shell
curl -X GET \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances?schema=https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4&name=Sales%20and%20Promotions%20Placement' \
  -H 'Accept: *,application/vnd.adobe.platform.xcore.hal+json; schema='\''https://ns.adobe.com/experience/xcore/hal/results'\''' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett godkänt svar returnerar information om placeringen inklusive information om ditt behållar-ID, instans-ID och unik placering `@id`.

```json
{
    "containerId": "e0bd8463-0913-4ca1-bd84-6309134ca1f6",
    "schemaNs": "https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4",
    "requestTime": "2020-10-21T20:04:53.656503Z",
    "_embedded": {
        "results": [
            {
                "instanceId": "9aa58fd0-13d7-11eb-928b-576735ea4db8",
    "schemas": [
                    "https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4"
                ],
                "productContexts": [
                    "acp"
    ],
                "repo:etag": 2,
                "repo:createdDate": "2020-10-21T19:57:09.837456Z",
                "repo:lastModifiedDate": "2020-10-21T19:59:10.700149Z",
                "repo:createdBy": "{CREATED_BY}",
                "repo:lastModifiedBy": "{MODIFIED_BY}",
                "repo:createdByClientId": "{CREATED_CLIENT_ID}",
                "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}",
                "_score": 0,
                "_instance": {
                    "xdm:name": "Sales and Promotions Placement",
                    "xdm:componentType": "https://ns.adobe.com/experience/offer-management/content-component-html",
                    "xdm:channel": "https://ns.adobe.com/xdm/channel-types/web",
                    "xdm:description": "A test placement to contain offers of sales and discounts",
                    "@id": "xcore:offer-placement:124e0be5699743d3"
                },
                "_links": {
                    "self": {
                        "name": "https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4#9aa58fd0-13d7-11eb-928b-576735ea4db8",
                        "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/9aa58fd0-13d7-11eb-928b-576735ea4db8",
                        "@type": "https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4"
                    }
                }
            }
        ],
        "total": 1,
        "count": 1
    },
    "_links": {
        "self": {
            "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances?schema=https://ns.adobe.com/experience/offer-management/offer-placement;version=0.4&name=Sales%20and%20Promotions%20Placement",
            "@type": "https://ns.adobe.com/experience/xcore/hal/results"
        }
    }
}
```
