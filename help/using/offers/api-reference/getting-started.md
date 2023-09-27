---
title: Komma igång
description: Lär dig hur du börjar använda Offer Library API för att utföra nyckelåtgärder med hjälp av beslutsmotorn.
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 773bee50-849f-4b07-9423-67de5279ad28
source-git-commit: 805f7bdc921c53f63367041afbb6198d0ec05ad8
workflow-type: tm+mt
source-wordcount: '349'
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
* `x-sandbox-name: {SANDBOX_NAME}`

Alla begäranden som innehåller en nyttolast (POST, PUT, PATCH) kräver ytterligare en rubrik:

* `Content-Type: application/json`

## Nästa steg {#next-steps}

Det här dokumentet innehöll de nödvändiga kunskaperna som krävs för att ringa till [!DNL Offer Library] API. Du kan nu gå vidare till exempelsamtalen i den här utvecklarhandboken och följa med i instruktionerna för dessa.
<!--
>[!NOTE]
>
> The In-app messaging channel in Adobe Journey Optimizer uses decision management objects. If your organization uses the in-app messaging channel, then API list requests for objects will include objects created by the in-app messaging service and can be ignored for decision management use cases. Objects created for in-app messages will have `createdBy = “Mobile_Sheliak”`.
-->

## Instruktionsvideo {#video}

Följande video är avsedd att ge stöd för din förståelse av komponenterna i Beslutshantering.

>[!VIDEO](https://video.tv.adobe.com/v/329919?quality=12)

