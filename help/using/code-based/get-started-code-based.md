---
title: Kom igång med kodbaserade upplevelser
description: Läs om kodbaserade upplevelser i Journey Optimizer
feature: Code-based Experiences
topic: Content Management
role: User, Developer, Admin
level: Experienced
exl-id: 987de2bf-cebe-4753-98b4-01eb3fded492
source-git-commit: efb943e5a6f27becc6e8b6128b776e46d6141823
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 1%

---

# Kom igång med kodbaserad kanal {#get-started-code-based}

Med [!DNL Journey Optimizer] kan du personalisera och testa de upplevelser du vill leverera till dina kunder via alla dina kontaktytor, som webbappar, mobilappar, datorprogram, videokonsoler, tv-anslutna enheter, smarta TV-apparater, kioskdatorer, ATM-enheter, röstassistenter, IoT-enheter osv.

Med funktionen **kodbaserad upplevelse** kan du definiera inkommande upplevelser med en enkel och intuitiv icke-visuell redigerare. Det gör att du kan infoga och redigera specifika element på enskilda och mer detaljerade platser i dina program eller webbsidor, oavsett vilken typ av program du har - i stället för att ändra ett helt innehåll.

<!--[!DNL Journey Optimizer] allows you to compose and deliver content on any inbound device in a developer-focused workflow. You can leverage all the personalization capabilities, and preview what will be published. The content can be static (images, text, JSON, HTML) or dynamic (offers, decisions, recommendations). You can also insert custom content actions in your omni-channel journeys.-->

>[!IMPORTANT]
>
>Specifika rekommendationer för kodbaserade upplevelser finns på [den här sidan](code-based-prerequisites.md).


<!--Discover the detailed steps to create a code-based campaign in this video.-->

<!--[Learn how to create a code-based campaign in this video](#video)-->

➡️ Ett heltäckande användningsexempel som visar hur du använder innehållsexperiment för att jämföra beslut med den kodbaserade upplevelsekanalen visas i [det här avsnittet](../experience-decisioning/experience-decisioning-uc.md).

## När kodbaserade jämfört med andra kanaler ska användas {#code-based-vs-other-channels}

### Kodbaserade jämfört med andra kanaler

När ska den kodbaserade kanalen användas i stället för de andra [!DNL Journey Optimizer] kanalerna?

* Du kan använda kodbaserade upplevelser när som helst när din digitala egenskap inte nås via en webbläsare eller en mobilapp - situationer där du troligen bättre kan använda [!DNL Journey Optimizer] [webbkanalen](../web/get-started-web.md){target="_blank"} eller [!DNL Journey Optimizer] [meddelandekanalen i appen](../../rp_landing_pages/in-app-landing-page.md){target="_blank"}.

<!--* You can use the code-based channel as an alternative to the [!DNL Journey Optimizer] web channel if your website cannot be loaded into the [web designer](../web/web-visual-editor.md){target="_blank"} visual editor or if you cannot use the [browser extension](../web/web-prerequisites.md#visual-authoring-prerequisites){target="_blank"} that powers visual authoring for web channel.-->

* Du kan använda den kodbaserade kanalen som ett alternativ till webbkanalen [!DNL Journey Optimizer] eller i appen om du har en API-baserad, headless- eller serversidesimplementering.

* Du kan också utnyttja den kodbaserade kanalen i inbyggda mobilprogram som ett alternativ till kanalen i appen om du vill ändra innehållet i din inbyggda app i stället för att visa modaler, popup-fönster eller övertäckningar.

### Kodbaserad kontra webbkanal {#code-based-vs-web}

Om du vill köra webbanvändningsfall kan du använda antingen webbkanalen eller den kodbaserade upplevelsen, men beroende på ditt sammanhang kan ett alternativ vara mer lämpligt än det andra. De viktigaste skillnaderna listas nedan så att du kan fatta ett välgrundat beslut om vad som ska användas och när.

**Webb**

* Redigera ditt innehåll med den visuella [webbdesignern](../web/web-visual-editor.md){target="_blank"} eller den icke-visuella [webbredigeraren](../web/web-non-visual-editor.md).
* Du behöver [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html){target="_blank"} - en implementering på klientsidan.
  <!--* You need the [Adobe Experience Cloud Visual Editing Helper](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target="_blank"} extension installed on your web browser. [Learn more](../web/web-prerequisites.md){target="_blank"}-->
* Med webbkanalen kan du ändra allt på sidan och ha en fördefinierad lista över åtgärder som du kan använda för att göra ändringar. [Läs mer](../web/web-visual-editor.md){target="_blank"}
* Det är enkelt att konfigurera och komma igång snabbt.
* Det är fokuserat på marknadsföring och personalisering.

**Kodbaserad upplevelse**

* Redigera ditt innehåll med [anpassningsredigeraren](create-code-based.md#edit-code).
* Du behöver antingen [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html){target="_blank"} - implementering på klientsidan eller [AEP Edge Network Server API](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html){target="_blank"} - implementering på serversidan.
* Den kodbaserade upplevelsen kräver tidigare utvecklingsarbete med implementeringen för att säkerställa att dina program kan tolka och leverera innehåll som publiceras på kanten av [!DNL Journey Optimizer] för dessa platser. [Läs mer](code-based-surface.md)
* Det kräver mer planering och kan bara ändra det som utvecklarna anger. Därför är det viktigt att identifiera komponenterna (hembanner, hjältebild, menyrad osv.) i de program som behöver ändras för personalisering eller testning, och samarbeta med utvecklingsteamet för att skapa den implementering som behövs för att hantera dessa ändringar.
* Du kan använda JSON-kodinnehåll.
* Det är inriktat på utvecklare och persona.

## Så fungerar det {#how-it-works}

>[!CAUTION]
>
>Den här funktionen är avsedd för utvecklare och/eller erfarna användare. Den kan användas av marknadsförare med vissa kodskrivningskunskaper, förutsatt att kanalkonfigurationerna och den inledande konfigurationen hanteras av ditt utvecklingsteam.

Om du vill redigera ditt innehåll med den kodbaserade funktionen [!DNL Journey Optimizer] måste dina sidor eller appar vara instrumenterade. Om du vill göra det måste du deklarera de specifika enskilda platserna (så kallade [ytor](code-based-surface.md)) i förväg där du vill infoga eller ersätta innehåll.

>[!NOTE]
>
>Innehållet som är kopplat till en konfiguration kan för närvarande bara vara HTML eller JSON.

De viktigaste stegen för att skapa och leverera en kodbaserad upplevelse är följande.

1. Se till att ni följer de kanalspecifika kraven. [Läs mer](code-based-prerequisites.md)

1. Definiera en [yta](code-based-surface.md#surface-definition) i programimplementeringen, som i princip är den plats där du vill lägga till din upplevelse.

1. Skapa en kodbaserad kanalkonfiguration som refererar till den platsen. [Lär dig hur](code-based-configuration.md#create-code-based-configuration)

1. Skapa en resa eller kampanj i [!DNL Journey Optimizer] med den här konfigurationen. [Lär dig hur](create-code-based.md#create-code-based-campaign)

1. Skapa en upplevelse genom att ange innehåll för den valda konfigurationen med personaliseringsredigeraren [!DNL Journey Optimizer]. [Lär dig hur](create-code-based.md#edit-code)

1. Testa din kodbaserade upplevelse. [Lär dig hur](test-code-based.md)

1. Publicera den. [Lär dig hur](publish-code-based.md)

1. När den kodbaserade upplevelseresan eller kampanjen är live måste det program eller den sidimplementering som begär innehåll för ytan finnas på plats för att innehållet ska kunna hämtas och visas.

   >[!INFO]
   >
   >För att detta ska vara säkert gör implementeringsteamet för appen explicit API- eller SDK-anrop för att hämta innehåll för den yta som definieras i den kodbaserade konfigurationen, till exempel&quot;Banner Text&quot; eller&quot;Recommendations Tray 1&quot;, eller icke-UI-relaterade beslutspunkter i ett program, till exempel&quot;search algorithm parameters&quot;. <!--In this case, the implementation team is responsible for rendering or otherwise interpreting and acting on the returned content.--> [Läs mer](code-based-implementation-samples.md)

## Ytterligare resurser

* **[Skapa kodbaserade upplevelser](create-code-based.md)** - Lär dig hur du skapar och konfigurerar kodbaserade kampanjer och resor för anpassade implementeringar.
* **[Konfigurera kodbaserad kanal](code-based-configuration.md)** - Konfigurera kodbaserade upplevelsekonfigurationer med korrekta inställningar för yta och implementering.
* **[Kodbaserade förutsättningar](code-based-prerequisites.md)** - Förstå de tekniska krav och utvecklarresurser som krävs för implementeringen.
* **[Testa kodbaserade upplevelser](test-code-based.md)** - Lär dig hur du förhandsgranskar och testar kodbaserade upplevelser innan du publicerar.
* **[Implementeringsexempel](code-based-implementation-samples.md)** - Utforska kodexempel och implementeringsmönster för olika användningsområden.
* **[Kodbaserade självstudiekurser för upplevelser](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/channels/code-based-experience-channel/create-a-code-based-experience-campaign){target="_blank"}** - Utforska stegvisa videokurser om kodbaserade funktioner och metodtips.

