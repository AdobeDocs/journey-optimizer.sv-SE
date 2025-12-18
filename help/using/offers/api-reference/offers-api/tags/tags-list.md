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
exl-id: 8cee44ed-5569-416c-b463-e75fb20d4c9c
version: Journey Orchestration
source-git-commit: 8732a73118b807eaa7f57cfdad60355b535282ff
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 1%

---


# Kvalificerare för listsamling {#list-tags}

>[!TIP]
>
>Beslutsfattandet, [!DNL Adobe Journey Optimizer]s nya beslutsfunktion, är nu tillgängligt via den kodbaserade upplevelsen och e-postkanalerna! [Läs mer](../../experience-decisioning/gs-experience-decisioning.md)


Med samlingskvalificerare (som tidigare kallades&quot;taggar&quot;) kan du bättre ordna och sortera dina erbjudanden. Du kan till exempel märka dina erbjudanden på Black Friday med&quot;Black Friday&quot;-samlingskvalificeraren. Du kan sedan använda sökfunktionen i erbjudandebiblioteket för att enkelt hitta alla erbjudanden med den samlingskvalificeraren.

Samlingskvalificerare kan också användas för att gruppera erbjudanden i samlingar.

Du kan visa en lista över alla samlingskvalificerare i en behållare genom att utföra en enda GET-begäran till Offer Library API.

**API-format**

```http
GET /{ENDPOINT_PATH}/tags?{QUERY_PARAMS}
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för beständiga API:er. | `https://platform.adobe.io/data/core/dps` |
| `{QUERY_PARAMS}` | Valfria frågeparametrar för att filtrera resultat efter. | `limit=2` |

## Sidindelning {#paging}

De vanligaste frågeparametrarna för sidindelning är:

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `property` | En valfri egenskap: <ul><li>Egenskaperna grupperas efter AND-åtgärd.</li><li>Parametrar kan upprepas så här: property={PROPERTY_EXPR}[&amp;property={PROPERTY_EXPR2}..] eller property={PROPERTY_EXPR1}[,{PROPERTY_EXPR2}..]</li><li>Egenskapsuttryck har formatet `[ !]field[op]value`, med `op` i `[==,!=,<=,>=,<,>,~]`, som stöder reguljära uttryck.</li></ul> | `property=name!=abc&property=id~.*1234.*&property=description equivalent with property=name!=abc,id~.*1234.*,description.` |
| `orderBy` | Sortera resultat efter en specifik egenskap. Om du lägger till ett - före namn (orderBy=-name) sorteras objekten efter namn i fallande ordning (Z-A). Banuttryck är i form av punktavgränsade banor. Den här parametern kan upprepas så här: `orderby=field1[,-fields2,field3,...]` | `orderby=id`,`-name` |
| `limit` | Begränsa antalet returnerade placeringar. | `limit=5` |

**Begäran**

```shell
curl -X GET 'https://platform.adobe.io/data/core/dps/tags?limit=2' \
-H 'Accept: *,application/json' \
-H 'Authorization: Bearer {ACCESS_TOKEN}' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett godkänt svar returnerar en lista med samlingskvalificerare som finns i den behållare som du har åtkomst till.

```json
{
    "results": [
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
