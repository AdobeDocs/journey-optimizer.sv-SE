---
title: Komma igång
description: Lär dig hur du börjar använda Offer Library API för att utföra nyckelåtgärder med hjälp av beslutsmotorn.
feature: Decision Management, API
topic: Integrations
role: Developer
level: Experienced
exl-id: 773bee50-849f-4b07-9423-67de5279ad28
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 1%

---

# Utvecklarhandbok för API för beslutshantering {#decision-management-api-developer-guide}

>[!CONTEXTUALHELP]
>id="od_api_support"
>title="Nya API:er för beslutshantering"
>abstract="Nu finns nya API:er för att skapa och hantera beslutshanteringsobjekt. Det äldre API:t stöds till och med 2024-03-27."

>[!CONTEXTUALHELP]
>id="ajo_decisioning_api_support"
>title="Nya API:er för beslutshantering"
>abstract="Nu finns nya API:er för att skapa och hantera beslutshanteringsobjekt. Det äldre API:t stöds till och med 2024-03-27."

Den här utvecklarhandboken innehåller steg som hjälper dig att börja använda API:t för [!DNL Offer Library]. Handboken innehåller sedan exempel på API-anrop för att utföra nyckelåtgärder med beslutsmotorn.

➡️ [Läs mer om komponenterna i Beslutshantering i den här videon](#video)

## Förhandskrav {#prerequisites}

Handboken kräver en fungerande förståelse av följande komponenter i Adobe Experience Platform:

* [[!DNL Experience Data Model (XDM) System]](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target="_blank"}: Det standardiserade ramverk som [!DNL Experience Platform] organiserar kundupplevelsedata med.
   * [Grunderna i schemakomposition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html){target="_blank"}: Lär dig mer om grundläggande byggstenar i XDM-scheman.
* [Beslutshantering](../../../using/offers/get-started/starting-offer-decisioning.md): Beskriver de koncept och komponenter som används för beslut i allmänhet och för beslutshantering i synnerhet. Illustrerar de strategier som används för att välja det bästa alternativet att presentera under en kunds upplevelse.
* [[!DNL Profile Query Language (PQL)]](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html){target="_blank"}: PQL är ett kraftfullt språk för att skriva uttryck över XDM-instanser. PQL används för att definiera beslutsregler.

## Läser exempel-API-anrop {#reading-sample-api-calls}

Den här guiden innehåller exempel på API-anrop som visar hur du formaterar dina begäranden. Det kan vara sökvägar, obligatoriska rubriker och korrekt formaterade begärandenyttolaster. Ett exempel på JSON som returneras i API-svar finns också. Information om de konventioner som används i dokumentationen för exempel-API-anrop finns i avsnittet [Så här läser du exempel-API-anrop](https://experienceleague.adobe.com/docs/experience-platform/landing/troubleshooting.html#how-do-i-format-an-api-request){target="_blank"} i felsökningsguiden för [!DNL Experience Platform].

## Samla in värden för obligatoriska rubriker {#gather-values-for-required-headers}

För att kunna anropa [!DNL Adobe Experience Platform] API:er måste du först slutföra [autentiseringssjälvstudiekursen](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html){target="_blank"}. När du slutför självstudiekursen för autentisering visas värdena för var och en av de obligatoriska rubrikerna i alla [!DNL Experience Platform] API-anrop, vilket visas nedan:

* `Authorization: Bearer {ACCESS_TOKEN}`
* `x-api-key: {API_KEY}`
* `x-gw-ims-org-id: {IMS_ORG}`
* `x-sandbox-name: {SANDBOX_NAME}`

Alla begäranden som innehåller en nyttolast (POST, PUT, PATCH) kräver ytterligare ett huvud:

* `Content-Type: application/json`

>[!NOTE]
>
>Behörighetskontroller genomförs enligt de tilldelade produktprofilerna. Det är bara behörigheterna i den associerade produktprofilen som avgör vilka resurser som kan nås eller hanteras via API:t.

## Nästa steg {#next-steps}

Det här dokumentet innehöll den nödvändiga kunskapen som krävs för att anropa API:t [!DNL Offer Library]. Du kan nu gå vidare till exempelsamtalen i den här utvecklarhandboken och följa med i instruktionerna för dessa.
<!--
>[!NOTE]
>
> The In-app messaging channel in Adobe Journey Optimizer uses decision management objects. If your organization uses the in-app messaging channel, then API list requests for objects will include objects created by the in-app messaging service and can be ignored for decision management use cases. Objects created for in-app messages will have `createdBy = "Mobile_Sheliak"`.
-->

<!-- ## How-to video {#video}

The following video is intended to support your understanding of the components of Decision Management.

>[!VIDEO](https://video.tv.adobe.com/v/329919?quality=12) -->

