---
title: Kom igång med erbjudandeleverans-API:er
description: Läs mer om de API:er som finns för att leverera personaliserade erbjudanden.
feature: Decision Management, API
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 7bc1a4ec-113c-4af7-b549-ee17b843b818
source-git-commit: 91f52af0c2e42556c4456be9b6b0cb84378c2a23
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 0%

---

# Kom igång med erbjudandeleverans-API:er {#about-decisioning-apis}

Du kan leverera erbjudanden med **Beslut** eller **Edge Decisionering** API. Dessutom kan du **Gruppbeslut** Med API kan ni leverera erbjudanden till alla profiler i en viss målgrupp i ett enda samtal. Erbjudandeinnehållet för varje profil i målgruppen placeras i en Adobe Experience Platform-datauppsättning där det är tillgängligt för anpassade grupparbetsflöden.

På den här sidan hittar du information om specifika funktioner som är tillgängliga med **Beslut** och **Edge Decisionering** API. Vi rekommenderar att du använder **Edge Decisionering** API när det är möjligt för inkommande användning och för att säkerställa bättre latens och genomströmning på din plattform.

Mer information om hur du arbetar med API:erna finns i följande avsnitt:
* [Besluts-API](decisioning-api.md)
* [API för Edge Decisioning](edge-decisioning-api.md)
* [API för gruppbeslut](batch-decisioning-api.md)

## Hantera åtkomst till en behållare {#manage-access-to-container}

En behållare är en isoleringsmekanism för att hålla olika bekymmer isär. Behållar-ID är det första sökvägselementet för alla databas-API:er. Alla beslutsobjekt finns i en behållare.

En administratör kan gruppera liknande principer, resurser och åtkomstbehörigheter i profiler. Detta minskar handläggningsbördan och stöds av [Adobe Admin Console](https://adminconsole.adobe.com/). Du måste vara produktadministratör för Adobe Experience Platform i din organisation för att kunna skapa profiler och tilldela användare till dem. Det räcker med att skapa produktprofiler som matchar vissa behörigheter i ett enda steg och sedan lägga till användare i dessa profiler. Profiler fungerar som grupper som har beviljats behörigheter och alla verkliga användare eller tekniska användare i gruppen ärver dessa behörigheter.

Administratörsbehörighet kan du ge eller återkalla behörigheter till användare via [Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"}. For more information, see the [Access control overview](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html){target="_blank"}.

### Visa behållare som är tillgängliga för användare och integreringar {#list-containers-accessible-to-users-and-integrations}

**API-format**

```http
GET /{ENDPOINT_PATH}?product={PRODUCT_CONTEXT}&property={PROPERTY}==decisioning
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för databas-API:er. | `https://platform.adobe.io/data/core/xcore/` |
| `{PRODUCT_CONTEXT}` | Filtrerar listan med behållare efter deras koppling till produktkontexter. | `acp` |
| `{PROPERTY}` | Filtrerar den typ av behållare som returneras. | `_instance.containerType==decisioning` |

**Begäran**

```shell
curl -X GET \
  'https://platform.adobe.io/data/core/xcore/?product=acp&property=_instance.containerType==decisioning' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Svar**

Ett lyckat svar returnerar information om beslutsbehållare. Detta inkluderar `instanceId` -attribut, vars värde är ditt behållar-ID.

```json
{
    "_embedded": {
        "https://ns.adobe.com/experience/xcore/container": [
            {
                "instanceId": "{INSTANCE_ID}",
                "schemas": [
                    "https://ns.adobe.com/experience/xcore/container;version=0.5"
                ],
                "productContexts": [
                    "acp"
                ],
                "repo:etag": 2,
                "repo:createdDate": "2020-09-16T07:54:28.319959Z",
                "repo:lastModifiedDate": "2020-09-16T07:54:32.098139Z",
                "repo:createdBy": "{CREATED_BY}",
                "repo:lastModifiedBy": "{MODIFIED_BY}",
                "repo:createdByClientId": "{CREATED_CLIENT_ID}",
                "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}",
                "_instance": {
                    "containerType": "decisioning",
                    "repo:name": "{REPO_NAME}",
                    "dataCenter": "{DATA_CENTER}",
                    "parentName": "{PARENT_NAME}",
                    "parentId": "{PARENT_ID}"
                },
                "_links": {
                    "self": {
                        "href": "/containers/{INSTANCE_ID}"
                    }
                }
            }
        ]
    },
    "_links": {
        "self": {
            "href": "/?product=acp&property=_instance.containerType==decisioning",
            "@type": "https://ns.adobe.com/experience/xcore/hal/home"
        }
    }
}
```

## API-funktioner för Edge Decision {#edge}

**Unik begäran om upplevelsehändelser och beslutsbegäranden**

Med Edge Decisioning API kan du i en enda begäran skicka upplevelsehändelsen tillsammans med beslutsbegäran, i stället för att ha två olika förfrågningar.

Om en kund t.ex. besöker din webbplats kommer förfrågan att innehålla upplevelsehändelsen (kundens besök på sidan) och ett erbjudande skickas tillbaka för att fylla i den besökta sidan.

**Lagring av kontextdata i Adobe Experience Platform**

Kontextdata avser data som du bara känner till när du vill ha tillbaka ett erbjudande. Till exempel färgen på den köpta artikeln, vädret vid köptillfället osv.

När kontextdata skickas med en begäran från Edge Decisioning API, lagras data i Adobe Experience Platform-profilen så att de kan återanvändas i framtiden.

>[!NOTE]
>
>För att kontextdata ska kunna lagras måste du ha ett dedikerat XDM-schema konfigurerat.

## API-funktioner för beslut {#decisioning}

De funktioner som anges nedan är endast tillgängliga med besluts-API:t. Om du behöver utnyttja någon av dem för att uppfylla dina krav använder du API:t för beslut. I annat fall rekommenderar vi att du använder API:erna för Edge Decision.

* **Erbjud innehåll och egenskaper**: du kan välja att inte returnera innehållet och egenskaperna för ett erbjudande med ett dedikerat alternativ.
* **Erbjud metadata**: aktivera ett alternativ för att returnera metadata för ett erbjudande.
* **Kopplingsprincip**: använd i din begäran en annan sammanfogningsprincip än den som är kopplad till din sandlåda.
* **Beslutshändelser och frekvensbegränsning**: blockbeslutshändelser räknas inte av någon frekvensbegränsning som inträffar.
* **Duplicera förslag**: aktivera ett alternativ för att inte deduplicera anbud.
