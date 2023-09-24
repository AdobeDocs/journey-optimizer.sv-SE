---
title: Förutsättningar för webbkanaler
description: Följ kraven på den här sidan för att kunna komma åt och skapa webbsidor i Journey Optimizer användargränssnitt
feature: Web Channel
topic: Content Management
role: User
level: Beginner
exl-id: 6cb4f8ab-77ad-44a2-b2bf-a97f87b8f1db
source-git-commit: ec071392cec9933bb73ae9ab20618292b6089061
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 1%

---

# Förutsättningar och skyddsräcken {#web-prerequisites}

För att kunna komma åt och skriva webbsidor i [!DNL Journey Optimizer] följer du kraven nedan:

* Om du vill lägga till ändringar på webbplatsen måste du ha en specifik implementering. [Läs mer](#implementation-prerequisites)

* Så här öppnar du [!DNL Journey Optimizer] webbdesignern måste ha ett specifikt webbläsartillägg för Google Chrome installerat. [Läs mer](#visual-authoring-prerequesites)

* För att webbupplevelsen ska fungera på rätt sätt måste du definiera Adobe Experience Platform-inställningarna [här](#delivery-prerequisites).

## Observera varningar {#caution-notes-web}

* Ingår [!DNL Journey Optimizer] kan du bara skapa webbupplevelser i **kampanjer**. [Läs mer](../campaigns/create-campaign.md#configure)

* [!DNL Journey Optimizer] webbkampanjer riktar sig till nya profiler som inte har varit engagerade tidigare i andra kanaler. Detta ökar det totala antalet profiler du kan göra gällande, vilket kan ha kostnadskonsekvenser om det avtalsenliga antalet profiler du har köpt överskrids. Licensvärden för varje paket visas på sidan [Journey Optimizer produktbeskrivning](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer.html) sida.


>[!AVAILABILITY]
>
>För närvarande är webbkanalen inte tillgänglig för organisationer som har köpt tillägget Adobe Healthcare Shield.
>

## Krav för implementering {#implementation-prerequisites}

För närvarande stöds två typer av implementeringar för att möjliggöra utveckling och leverans av webbkanalskampanjer på dina webbegenskaper:

* Endast på klientsidan - Om du vill lägga till ändringar på webbplatsen måste du implementera [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html){target="_blank"} på er webbplats.

  >[!NOTE]
  >
  >Kontrollera att AEP Web SDK-versionen är 2.16 eller senare.

* Hybridläge - Du kan använda [API för AEP Edge Network Server](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html){target="_blank"} to request for personalization server-side; the response is provided to the Adobe Experience Platform Web SDK to render the modifications client-side. Learn more in the Adobe Experience Platform [Edge Network Server API documentation](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html){target="_blank"}. You can find out more about the hybrid mode and check some implementation samples in [this blog post](https://blog.developer.adobe.com/hybrid-personalization-in-the-adobe-experience-platform-web-sdk-6a1bb674bf41){target="_blank"}.

>[!NOTE]
>
>Implementeringen av enbart serversidan stöds inte för närvarande.

<!--If the Adobe Experience Platform Web SDK is not yet implemented on the website, a message displays in the web designer suggesting that you install the Visual Editing Helper browser extension and implement the [Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html){target="_blank"}.-->

## Krav för visuell redigering {#visual-authoring-prerequisites}

<!--In order to rapidly author and preview your web experiences, the Adobe Experience Cloud Visual Editing Helper browser extension for Google Chrome lets you load websites reliably within the Adobe [!DNL Journey Optimizer] web designer.-->

Om du vill kunna öppna, redigera och förhandsgranska dina webbsidor på ett tillförlitligt sätt i [!DNL Journey Optimizer] webbdesigner måste ha [Adobe Experience Cloud Visual Editing Helper](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target="_blank"} webbläsartillägg som är installerat i webbläsaren.

>[!CAUTION]
>
>Google Chrome och Microsoft Edge är för närvarande de enda webbläsare som har stöd för att skapa webbsidor i [!DNL Journey Optimizer].

### Installera tillägget Hjälp för visuell redigering {#install-visual-editing-helper}

Följ stegen nedan om du vill hämta och installera tillägget för hjälpen för visuell redigering.

1. Öppna en ny flik i webbläsaren (Google Chrome eller Microsoft Edge).

1. Gå till [Google Chrome Web Store](https://chrome.google.com/webstore/category/extensions){target="_blank"}.

1. Om du använder Microsoft Edge väljer du **[!UICONTROL Allow extensions from other stores]** på den översta banderollen. På så sätt kan du lägga till tillägg från Chrome Web Store till Microsoft Edge.

1. Sök och navigera till [Adobe Experience Cloud Visual Editing Helper](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target="_blank"} webbläsartillägg.

1. Klicka på **[!UICONTROL Add to Chrome]** > **[!UICONTROL Add Extension]**.

   >[!NOTE]
   >
   >Om du använder Microsoft Edge läggs tillägget till i Edge även om knappen har en etikett **[!UICONTROL Add to Chrome]**.

1. Kontrollera att webbläsartillägget Visuell redigeringshjälp är korrekt aktiverat i webbläsarens verktygsfält.

   ![](assets/web-visual-editing-extension-edge.png)

Adobe Experience Cloud Visual Editing Helper aktiveras nu automatiskt när en webbplats öppnas i [!DNL Journey Optimizer] [webbdesigner](edit-web-content.md#work-with-web-designer) till kraftfull redigering.

Tillägget har inga villkorsinställningar och hanterar automatiskt alla inställningar, inklusive cookies för SameSite.

>[!NOTE]
>
>Vissa webbplatser kanske inte öppnas som de ska i [!DNL Journey Optimizer] webbdesignern på grund av någon av följande orsaker:
>
> * Webbplatsen har strikta säkerhetsprinciper.
> * Webbplatsen ligger i en iframe.
> * Kundens QA- eller stage-sajt är inte tillgänglig för omvärlden (webbplatsen är intern).

### Felsök webbplatsen som inte läses in {#troubleshooting}

När du använder Adobe [!DNL Journey Optimizer] webbdesigner, om du försöker läsa in en webbplats som inte kan läsas in, visas ett meddelande om att du har installerat [Webbläsartillägg för hjälp för visuell redigering](#install-visual-editing-helper).

1. Kontrollera att webbläsartillägget för hjälpen för visuell redigering är korrekt installerat.

1. Om webbplatsen fortfarande uppför sig oväntat bör du kontrollera att cookies från tredje part tillåts i webbläsaren, annars kan webbsidan inte läsas in i [!DNL Journey Optimizer] webbdesigner.

För sidor som autentiseras, om inloggningssidan inte kan läsas in eller om du fortfarande inte är inloggad efter att ha försökt logga in:

1. Försök logga in först på en ny flik i webbläsaren och navigera till önskad sida, kopiera sedan URL:en och försök öppna den i dialogrutan [!DNL Journey Optimizer] webbdesigner.

2. Om du fortfarande inte kan läsa in webbplatsen i [!DNL Journey Optimizer] webbdesigner, kontakta Adobe kundtjänst för att rapportera problemet och se till att du anger den felaktiga URL:en.

## Leveransvillkor {#delivery-prerequisites}

För att webbupplevelsen ska kunna levereras på rätt sätt måste följande inställningar definieras:

* I [Adobe Experience Platform Data Collection](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html){target="_blank"}kontrollerar du att du har en datastream definierad, till exempel under **[!UICONTROL Adobe Experience Platform]** den tjänst du har **[!UICONTROL Adobe Journey Optimizer]** aktiverat alternativ.

  Detta säkerställer att Journey Optimizer inkommande händelser hanteras korrekt av Adobe Experience Platform Edge. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html){target="_blank"}

  ![](assets/web-aep-datastream-ajo.png)

* I [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv){target="_blank"}, make sure you have one merge policy with the **[!UICONTROL Active-On-Edge Merge Policy]** option enabled. To do this, select a policy under the **[!UICONTROL Customer]** > **[!UICONTROL Profiles]** > **[!UICONTROL Merge Policies]** Experience Platform menu. [Learn more](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html#configure){target="_blank"}

  Den här sammanfogningsprincipen används av [!DNL Journey Optimizer] inkommande kanaler för att korrekt aktivera och publicera inkommande kampanjer. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html){target="_blank"}

  ![](assets/web-aep-merge-policy.png)

## Förutsättningar för innehållsexperiment {#experiment-prerequisites}

Om du vill aktivera innehållsexperiment för webbkanalen måste du se till att [datauppsättning](../data/get-started-datasets.md) används i din webbimplementering [datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html){target="_blank"} ingår även i din rapportkonfiguration.

Om du lägger till en datauppsättning som inte finns i webbdataströmmen när du konfigurerar experimentrapporter, kommer webbdata alltså inte att visas i innehållsexperimentrapporter.

Lär dig hur du lägger till datauppsättningar för att experimentera med innehåll i [det här avsnittet](../campaigns/reporting-configuration.md#add-datasets).

>[!NOTE]
>
>Datauppsättningen används skrivskyddat av [!DNL Journey Optimizer] rapporteringssystem och påverkar inte datainsamling eller datainmatning.

Om du **not** med följande fördefinierade [fältgrupper](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#field-group){target="_blank"} for your dataset schema: `AEP Web SDK ExperienceEvent` and `Consumer Experience Event` (as defined in [this page](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/initial-configuration/configure-schemas.html#add-field-groups){target="_blank"}) måste du lägga till följande fältgrupper: `Experience Event - Proposition Interactions`, `Application Details`, `Commerce Details`och `Web Details`. Dessa behövs av [!DNL Journey Optimizer] Experimentera med rapporter om vilka experiment och behandlingar respektive profil deltar i.

>[!NOTE]
>
>När du lägger till dessa fältgrupper påverkas inte den normala datainsamlingen. Den är bara additiv för de sidor där ett experiment pågår, och lämnar all annan spårning orörd.

## Varumärkesdomäner för resurser {#branded-domains-for-assets}

Om du lägger till innehåll från [Adobe Experience Manager Assets Essentials](../content-management/assets-essentials.md) måste du konfigurera den underdomän som ska användas för att publicera innehållet. [Läs mer](web-delegated-subdomains.md)
