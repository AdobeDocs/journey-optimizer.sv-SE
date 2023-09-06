---
title: Komma igång
description: Lär dig hur du börjar använda Offer Library API för att utföra nyckelåtgärder med hjälp av beslutsmotorn.
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 773bee50-849f-4b07-9423-67de5279ad28
source-git-commit: ccc3ad2b186a64b9859a5cc529fe0aefa736fc00
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 3%

---

# Utvecklarhandbok för API för beslutshantering {#decision-management-api-developer-guide}

Den här utvecklarhandboken innehåller steg som hjälper dig att börja använda [!DNL Offer Library] API. Handboken innehåller sedan exempel på API-anrop för att utföra nyckelåtgärder med beslutsmotorn.

➡️ [Läs mer om komponenterna i Beslutshantering i den här videon](#video)

## Förutsättningar {#prerequisites}

Handboken kräver en fungerande förståelse av följande komponenter i Adobe Experience Platform:

* [[!DNL Experience Data Model (XDM) System]](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target="_blank"}: Det standardiserade ramverk som [!DNL Experience Platform] organiserar kundupplevelsedata.
   * [Grunderna för schemakomposition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html){target="_blank"}: Lär dig mer om grundläggande byggstenar i XDM-scheman.
* [Beslutshantering](../../../using/offers/get-started/starting-offer-decisioning.md): Beskriver de begrepp och komponenter som används för Experience Decision i allmänhet och i synnerhet för beslutshantering. Illustrerar de strategier som används för att välja det bästa alternativet att presentera under en kunds upplevelse.
* [[!DNL Profile Query Language (PQL)]](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html){target="_blank"}: PQL är ett kraftfullt språk för att skriva uttryck över XDM-instanser. PQL används för att definiera beslutsregler.

## Läser exempel-API-anrop {#reading-sample-api-calls}

Den här guiden innehåller exempel på API-anrop som visar hur du formaterar dina begäranden. Det kan vara sökvägar, obligatoriska rubriker och korrekt formaterade begärandenyttolaster. Ett exempel på JSON som returneras i API-svar finns också. Information om konventionerna som används i dokumentationen för exempel-API-anrop finns i avsnittet om [läsa exempel-API-anrop](https://experienceleague.adobe.com/docs/experience-platform/landing/troubleshooting.html#how-do-i-format-an-api-request){target="_blank"} i [!DNL Experience Platform] felsökningsguide.

## Samla in värden för obligatoriska rubriker {#gather-values-for-required-headers}

För att ringa [!DNL Adobe Experience Platform] API:er måste du först slutföra [självstudiekurs om autentisering](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html){target="_blank"}. När du är klar med självstudiekursen för autentisering visas värdena för var och en av de obligatoriska rubrikerna i alla [!DNL Experience Platform] API-anrop enligt nedan:

* `Authorization: Bearer {ACCESS_TOKEN}`
* `x-api-key: {API_KEY}`
* `x-gw-ims-org-id: {IMS_ORG}`

Alla begäranden som innehåller en nyttolast (POST, PUT, PATCH) kräver ytterligare en rubrik:

* `Content-Type: application/json`

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

## Nästa steg {#next-steps}

Det här dokumentet innehöll de nödvändiga kunskaperna som krävs för att ringa till [!DNL Offer Library] API, inklusive att hämta ditt behållar-ID. Du kan nu gå vidare till exempelsamtalen i den här utvecklarhandboken och följa med i instruktionerna för dessa.
<!--
>[!NOTE]
>
> The In-app messaging channel in Adobe Journey Optimizer uses decision management objects. If your organization uses the in-app messaging channel, then API list requests for objects will include objects created by the in-app messaging service and can be ignored for decision management use cases. Objects created for in-app messages will have `createdBy = “Mobile_Sheliak”`.
-->

## Instruktionsvideo {#video}

Följande video är avsedd att ge stöd för din förståelse av komponenterna i Beslutshantering.

>[!VIDEO](https://video.tv.adobe.com/v/329919?quality=12)

