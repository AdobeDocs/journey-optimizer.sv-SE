---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: Kvalificerare för listsamling
description: Med en samling kvalificerare kan ni ordna och sortera genom era erbjudanden på ett bättre sätt.
feature: Decision Management, API
badge: label="Äldre" type="Informative"
topic: Integrations
role: Developer
level: Experienced
exl-id: cc577989-198c-4e21-80e7-32ebb7a60606
version: Journey Orchestration
source-git-commit: 0b6d41fad9715985ec6418cdda27760f977bbc47
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 1%

---

# Kvalificerare för listsamling {#list-tags}

>[!TIP]
>
>Beslutsfattandet, [!DNL Adobe Journey Optimizer]s nya beslutsfunktion, är nu tillgängligt via den kodbaserade upplevelsen och e-postkanalerna! [Läs mer](../../../../../experience-decisioning/gs-experience-decisioning.md)


Med samlingskvalificerare (som tidigare kallades&quot;taggar&quot;) kan du bättre ordna och sortera dina erbjudanden. Du kan till exempel märka dina erbjudanden på Black Friday med&quot;Black Friday&quot;-samlingskvalificeraren. Du kan sedan använda sökfunktionen i erbjudandebiblioteket för att enkelt hitta alla erbjudanden med den samlingskvalificeraren.

Samlingskvalificerare kan också användas för att gruppera erbjudanden i samlingar. Mer information finns i självstudiekursen om att [skapa samlingar](../../../../offer-library/creating-collections.md).

Du kan visa en lista över alla samlingskvalificerare genom att utföra en enda GET-begäran till API:t [!DNL Offer Library].

**API-format**

```http
GET /{ENDPOINT_PATH}/{CONTAINER_ID}/queries/core/search?schema={SCHEMA_TAG}&{QUERY_PARAMS}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för databas-API:er. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | Behållaren där samlingskvalificerarna finns. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{SCHEMA_TAG}` | Definierar det schema som är associerat med samlingskvalificerare. | `https://ns.adobe.com/experience/offer-management/tag;version=0.1` |
| `{QUERY_PARAMS}` | Valfria frågeparametrar för att filtrera resultat efter. | `limit=2` |

**Begäran**

```shell
curl -X GET \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?schema=https://ns.adobe.com/experience/offer-management/tag;version=0.1&limit=2' \
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
| `property` | En valfri egenskap: <ul><li>Egenskaperna grupperas efter AND-åtgärd.</li><li>Parametrar kan upprepas så här: property={PROPERTY_EXPR}[&amp;property={PROPERTY_EXPR2}..] eller property={PROPERTY_EXPR1}[,{PROPERTY_EXPR2}..]</li><li>Egenskapsuttryck har formatet `[ !]field[op]value`, med `op` i `[==,!=,<=,>=,<,>,~]`, som stöder reguljära uttryck.</li></ul> | `property=name!=abc&property=id~.*1234.*&property=description equivalent with property=name!=abc,id~.*1234.*,description.` |
| `orderBy` | Sortera resultat efter en specifik egenskap. Om du lägger till ett - före namn (orderBy=-name) sorteras objekten efter namn i fallande ordning (Z-A). Banuttryck är i form av punktavgränsade banor. Den här parametern kan upprepas så här: `orderby=field1[,-fields2,field3,...]` | `orderby=id`,`-name` |
| `limit` | Begränsa antalet enheter som returneras. | `limit=5` |

**Svar**

Ett godkänt svar returnerar en lista med samlingskvalificerare som finns i den behållare som du har åtkomst till.

```json
{
    "containerId": "e0bd8463-0913-4ca1-bd84-6309134ca1f6",
    "schemaNs": "https://ns.adobe.com/experience/offer-management/tag;version=0.1",
    "requestTime": "2023-10-21T20:28:21.521267Z",
    "_embedded": {
        "results": [
            {
                "instanceId": "0adf2ef0-0f6e-11eb-b3be-9b775f952952",
                "schemas": [
                    "https://ns.adobe.com/experience/offer-management/tag;version=0.1"
                ],
                "productContexts": [
                    "acp"
                ],
                "repo:etag": 2,
                "repo:createdDate": "2023-10-16T05:11:26.815213Z",
                "repo:lastModifiedDate": "2023-10-16T22:20:20.190006Z",
                "repo:createdBy": "{CREATED_BY}",
                "repo:lastModifiedBy": "{MODIFIED_BY}",
                "repo:createdByClientId": "{CREATED_CLIENT_ID}",
                "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}",
                "_instance": {
                    "xdm:name": "Sneakers",
                    "@id": "xcore:tag:1246d138ec8cca1f"
                },
                "_links": {
                    "self": {
                        "name": "https://ns.adobe.com/experience/offer-management/tag;version=0.1#0adf2ef0-0f6e-11eb-b3be-9b775f952952",
                        "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/0adf2ef0-0f6e-11eb-b3be-9b775f952952",
                        "@type": "https://ns.adobe.com/experience/offer-management/tag;version=0.1"
                    }
                }
            },
            {
                "instanceId": "149e0de0-ff5f-11ea-b017-f98866426d43",
                "schemas": [
                    "https://ns.adobe.com/experience/offer-management/tag;version=0.1"
                ],
                "productContexts": [
                    "acp"
                ],
                "repo:etag": 1,
                "repo:createdDate": "2023-09-25T18:44:02.109748Z",
                "repo:lastModifiedDate": "2023-09-25T18:44:02.109748Z",
                "repo:createdBy": "{CREATED_BY}",
                "repo:lastModifiedBy": "{MODIFIED_BY}",
                "repo:createdByClientId": "{CREATED_CLIENT_ID}",
                "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}",
                "_instance": {
                    "xdm:name": "retirement",
                    "@id": "xcore:tag:122c81d2804e69e3"
                },
                "_links": {
                    "self": {
                        "name": "https://ns.adobe.com/experience/offer-management/tag;version=0.1#149e0de0-ff5f-11ea-b017-f98866426d43",
                        "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/149e0de0-ff5f-11ea-b017-f98866426d43",
                        "@type": "https://ns.adobe.com/experience/offer-management/tag;version=0.1"
                    }
                },
                "sandboxName": "ode-prod-va7-edge-testing"
            }
        ],
        "total": 11,
        "count": 2
    },
    "_links": {
        "self": {
            "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?schema=https://ns.adobe.com/experience/offer-management/tag;version=0.1&limit=2",
            "@type": "https://ns.adobe.com/experience/xcore/hal/results"
        },
        "next": {
            "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?start=149e0de0-ff5f-11ea-b017-f98866426d43&orderby=instanceId&schema=https://ns.adobe.com/experience/offer-management/tag;version=0.1&limit=2",
            "@type": "https://ns.adobe.com/experience/xcore/hal/results"
        }
    }
}
```
