---
title: Kvalificerare för listsamling
description: Med en samling kvalificerare kan ni ordna och sortera genom era erbjudanden på ett bättre sätt.
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 8cee44ed-5569-416c-b463-e75fb20d4c9c
source-git-commit: 805f7bdc921c53f63367041afbb6198d0ec05ad8
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 1%

---

# Kvalificerare för listsamling {#list-tags}

Med samlingskvalificerare (som tidigare kallades&quot;taggar&quot;) kan du bättre ordna och sortera dina erbjudanden. Du kan till exempel märka dina erbjudanden på Black Friday med&quot;Black Friday&quot;-samlingskvalificeraren. Du kan sedan använda sökfunktionen i erbjudandebiblioteket för att enkelt hitta alla erbjudanden med den samlingskvalificeraren.

Samlingskvalificerare kan också användas för att gruppera erbjudanden i samlingar. Mer information finns i självstudiekursen om [skapa samlingar](../../../offer-library/creating-collections.md).

Du kan visa en lista över alla samlingskvalificerare genom att utföra en enda GET-förfrågan till [!DNL Offer Library] API.

**API-format**

```http
GET /{ENDPOINT_PATH}/tags?{QUERY_PARAMS}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |

**Begäran**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/tags?limit=2' \
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

Ett lyckat svar returnerar en lista med samlingskvalificerare som finns.

```json
{
                "created": "2022-09-16T19:00:02.070+00:00",
            "modified": "2022-09-16T19:00:02.070+00:00",
            "etag": 1,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/tag;version=0.1"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "tag1234",
            "name": "Sneakers"
        },
        {
            "created": "2022-09-16T19:55:02.168+00:00",
            "modified": "2022-09-16T19:55:02.168+00:00",
            "etag": 1,
            "schemas": [
                "https://ns.adobe.com/experience/offer-management/tag;version=0.1"
            ],
            "createdBy": "{CREATED_BY}",
            "lastModifiedBy": "{MODIFIED_BY}",
            "id": "tag5678",
            "name": "Black Friday"
        }
    ],
    "count": 2,
    "total": 5,
    "_links": {
        "self": {
            "href": "/tags?href={SELF_HREF}&limit=2",
            "type": "application/json"
        },
        "next": {
            "href": "/tags?href={NEXT_HREF}&limit=2",
            "type": "application/json"
        }
    }
}
```
