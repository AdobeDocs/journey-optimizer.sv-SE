---
title: Komma igång
description: Lär dig hur du börjar använda Offer Library API för att utföra nyckelåtgärder med hjälp av beslutsmotorn.
source-git-commit: 741fe2b614e3ded57c4a7ecd9b7333bdd99ab359
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 2%

---

# Utvecklarhandbok för API för beslutshantering

Den här utvecklarhandboken innehåller steg som hjälper dig att börja använda API:t [!DNL Offer Library]. Handboken innehåller sedan exempel på API-anrop för att utföra nyckelåtgärder med hjälp av beslutsmotorn.

![](../../assets/do-not-localize/how-to-video.png) [Upptäck den här funktionen i en video](#video)

## Förutsättningar

Handboken kräver en fungerande förståelse av följande komponenter i Adobe Experience Platform:

* [[!DNL Experience Data Model (XDM) System]](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en): Det standardiserade ramverket som  [!DNL Experience Platform] organiserar kundupplevelsedata.
   * [Grundläggande om schemakomposition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html): Lär dig mer om grundstenarna i XDM-scheman.
* [Beslutshantering](../../../using/offers/get-started/starting-offer-decisioning.md): Beskriver de begrepp och komponenter som används för Experience Decision i allmänhet och Offer decisioning i synnerhet. Illustrerar de strategier som används för att välja det bästa alternativet att presentera under en kunds upplevelse.
* [[!DNL Profile Query Language (PQL)]](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html): PQL är ett kraftfullt språk för att skriva uttryck över XDM-instanser. PQL används för att definiera beslutsregler.

## Läser exempel-API-anrop

Den här guiden innehåller exempel på API-anrop som visar hur du formaterar dina begäranden. Det kan vara sökvägar, obligatoriska rubriker och korrekt formaterade begärandenyttolaster. Ett exempel på JSON som returneras i API-svar finns också. Information om de konventioner som används i dokumentationen för exempel-API-anrop finns i avsnittet [hur du läser exempel-API-anrop](https://experienceleague.adobe.com/docs/experience-platform/landing/troubleshooting.html#how-do-i-format-an-api-request) i felsökningsguiden för [!DNL Experience Platform].

## Samla in värden för obligatoriska rubriker

För att kunna anropa [!DNL Platform] API:er måste du först slutföra [självstudiekursen](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html) för autentisering. När du är klar med självstudiekursen för autentisering visas värdena för var och en av de obligatoriska rubrikerna i alla [!DNL Experience Platform] API-anrop enligt nedan:

* `Authorization: Bearer {ACCESS_TOKEN}`
* `x-api-key: {API_KEY}`
* `x-gw-ims-org-id: {IMS_ORG}`

Alla begäranden som innehåller en nyttolast (POST, PUT, PATCH) kräver ytterligare en rubrik:

* `Content-Type: application/json`

## Hantera åtkomst till en behållare

En behållare är en isoleringsmekanism för att hålla olika bekymmer isär. Behållar-ID är det första sökvägselementet för alla databas-API:er. Alla beslutsobjekt finns i en behållare.

En administratör kan gruppera liknande principer, resurser och åtkomstbehörigheter i profiler. Detta minskar hanteringsbördan och stöds av [Adobe Admin Console](https://adminconsole.adobe.com/). Du måste vara produktadministratör för Adobe Experience Platform i din organisation för att kunna skapa profiler och tilldela användare till dem. Det räcker med att skapa produktprofiler som matchar vissa behörigheter i ett enda steg och sedan lägga till användare i dessa profiler. Profiler fungerar som grupper som har beviljats behörigheter och alla verkliga användare eller tekniska användare i gruppen ärver dessa behörigheter.

Med administratörsbehörighet kan du bevilja eller återkalla behörigheter till användare via [Adobe Admin Console](https://adminconsole.adobe.com/). Mer information finns i [Översikt över åtkomstkontroll](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html).

### Visa behållare som är tillgängliga för användare och integreringar

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

Ett lyckat svar returnerar information om beslutsbehållare. Detta inkluderar ett `instanceId`-attribut, vars värde är ditt behållar-ID.

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

## Nästa steg

Det här dokumentet innehöll den nödvändiga kunskapen för att ringa anrop till API:t [!DNL Offer Library], inklusive att hämta ditt behållar-ID. Du kan nu gå vidare till exempelsamtalen i den här utvecklarhandboken och följa med i instruktionerna för dessa.

## Videokurs {#video}

Följande video är avsedd att ge stöd för din förståelse av komponenterna i Beslutshantering.

>[!NOTE]
>
>Den här videon gäller för Offera decisioningens programtjänst som är byggd på Adobe Experience Platform. Det ger dock allmän vägledning om hur man använder Erbjudandet inom ramen för Journey Optimizer.

>[!VIDEO](https://video.tv.adobe.com/v/329919?quality=12)
