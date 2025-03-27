---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med GenStudio-integrering i Journey Optimizer
description: Lär dig arbeta med GenStudio i Journey Optimizer
feature: Content Assistant, Integrations
topic: Content Management, Artificial Intelligence
role: User
level: Beginner, Intermediate
source-git-commit: b24e50f698567e1f45318d942dff87febba179c9
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 0%

---

# Kom igång med GenStudio-integrationen {#gs-genstudio}

>[!CONTEXTUALHELP]
>id="ajo_genstudio_button"
>title="Använda en mall som byggts med GenStudio"
>abstract="Tack vare den smidiga integrationen med Adobe GenStudio for Performance Marketing kan du enkelt importera en GenStudio-mall som har förbättrats med Adobe AI-teknik."

>[!AVAILABILITY]
>
>GenStudio-integreringen i [!DNL Adobe Journey Optimizer] är för närvarande inte tillgänglig för användning med tilläggserbjudandena **Hälsovårdssköld** eller **Sekretess och säkerhetssköld**.
>
>Integreringen med GenStudio är endast tillgänglig för e-postkanalen.

[Adobe GenStudio for Performance Marketing](https://business.adobe.com/products/genstudio-for-performance-marketing.html){target="_blank"} är en generativ AI-tillämpning som gör att marknadsföringsteamen kan skapa egna annonser och e-postmeddelanden för att driva effektiva, personaliserade marknadsföringskampanjer som följer varumärkesstandarderna och följer företagets policyer. Genom att utnyttja Adobe AI-teknik får du en omfattande verktygslåda som förenklar komplexa funktioner för att skapa och hantera innehåll så att kreatörerna kan fokusera på innovation.

Läs mer om [!DNL GenStudio for Performance Marketing] i den dedikerade [dokumentationen](https://experienceleague.adobe.com/en/docs/genstudio-for-performance-marketing/user-guide/home){target="_blank"}.

>[!INFO]
>
>Mer information finns i [översikten](https://business.adobe.com/products/genstudio-for-performance-marketing.html#watch-overview){target="_blank"} och i [demon](https://business.adobe.com/products/genstudio-for-performance-marketing.html#demo){target="_blank"} av [!DNL Adobe GenStudio for Performance Marketing].

<!--To access the GenStudio integration in [!DNL Adobe Journey Optimizer] feature, users need to be granted the **xxx** permission. [Learn more](../administration/permissions.md)

>[!IMPORTANT]
>
>* Before starting using this capability, read out related [Guardrails and Limitations](#generative-guardrails).-->

För att öka marknadsföringens effektivitet och upprätthålla varumärkets enhetlighet kan du sömlöst integrera [!DNL **GenStudio for Performance Marketing**]-upplevelser med [!DNL **Adobe Journey Optimizer**]. Detta gör att du kan utnyttja [!DNL GenStudio]s AI-power-innehåll tillsammans med [!DNL Journey Optimizer]s avancerade orkestreringsfunktioner.

<!--![](../rn/assets/do-not-localize/genstudio.gif)-->

<!--Guardrails and limitations {#genstudio-guardrails}

General guidelines for using the GenStudio integration in [!DNL Adobe Journey Optimizer] for email generation are listed below:

See if guidelines/limitations such as the ones listed [here](gs-generative.md#generative-guardrails) for the AI Assistant can apply.

The following limitations apply to GenStudio integration in [!DNL Adobe Journey Optimizer]:-->

## Utnyttja GenStudio i Journey Optimizer {#use-genstudio}

Integreringen [!DNL GenStudio for Performance Marketing] och [!DNL Journey Optimizer] gör att du kan låta marknadsförare från ditt företag samarbeta bättre för att effektivisera processerna.

En teknisk marknadsförare, som använder [!DNL Journey Optimizer] för att utveckla och automatisera e-postkampanjer, kan till exempel samarbeta med en resultatmarknadsförare som skapar innehåll med [!DNL GenStudio].

Med den här integreringen kan båda fungera tillsammans för att enkelt integrera varumärkesinnehåll från [!DNL GenStudio] i [!DNL Journey Optimizer] och leverera engagerande e-postmeddelanden som riktar sig till specifika kundsegment och ökar försäljningen.

### Exportera en HTML-mall från Journey Optimizer till GenStudio {#export-from-ajo-to-genstudio}

Först kan du exportera en [!DNL Journey Optimizer] HTML-mall med ditt varumärkes riktlinjer till [!DNL GenStudio for Performance Marketing]. Följ stegen nedan.

1. I [!DNL Journey Optimizer] får du tillgång till innehållet i din e-post under en resa eller kampanj. [Lär dig hur](../email/get-started-email-design.md#key-steps)

1. I e-postmeddelandet för Designer väljer du **[!UICONTROL Export HTML]** från knappen **[!UICONTROL More]**.

   ![](assets/genstudio-export-template.png){zoomable="yes"}

1. Överför den här HTML-exporterade mallen till [!DNL GenStudio for Performance Marketing]. <!--Make sure you detect the fields that the generative AI uses to insert content in order to create an actionable template.-->

   >[!NOTE]
   >
   >Lär dig hur du överför en HTML-mall till [!DNL GenStudio] i det dedikerade avsnittet [Adobe GenStudio for Performance Marketing användarhandbok](https://experienceleague.adobe.com/en/docs/genstudio-for-performance-marketing/user-guide/content/templates/use-templates#templates-from-ajo-and-marketo){target="_blank"} .

1. I GenStudio använder du den här mallen för att skapa flera e-postvarianter med AI-uppmaningar och spara dem.

   >[!NOTE]
   >
   >Lär dig hur du skapar e-postupplevelser i den dedikerade [sektionen](https://experienceleague.adobe.com/en/docs/genstudio-for-performance-marketing/user-guide/create/create-email-experience){target="_blank"} i GenStudio.

### Utnyttja GenStudio upplevelser i Journey Optimizer {#leverage-genstudio-experiences}

Följ stegen nedan om du vill utnyttja de [!DNL GenStudio] e-postvarianter som du nyss skapade genom att importera dem till [!DNL Journey Optimizer].

1. I [!DNL Journey Optimizer] [lägger du till ett e-postmeddelande ](../email/create-email.md) i en kampanj.

1. Gå igenom skärmen [Redigera innehåll](../email/create-email.md#define-email-content) på konfigurationsskärmen för kampanjen och klicka på **[!UICONTROL Edit email body]** för att öppna e-post-Designer. [Lär dig hur](../email/get-started-email-design.md#key-steps)

1. Markera **[!UICONTROL Import HTML]** på startsidan för e-post till Designer och klicka på knappen **[!UICONTROL Adobe GenStudio for Performance Marketing]**.

   ![](assets/genstudio-pem-import-email.png){zoomable="yes"}

1. Bläddra bland GenStudio upplevelser för att börja bygga ditt innehåll. Ni kan filtrera upplevelserna utifrån flera kriterier som produkter, personer, varumärken eller till och med färger.

   <!--![](assets/genstudio-filter-experiences.png){zoomable="yes"}-->

1. Välj en upplevelse och klicka på **[!UICONTROL Use]**.

   ![](assets/genstudio-use-experience.png){zoomable="yes"}

1. Markera den mapp där du vill importera GenStudio-upplevelsen.

   ![](assets/genstudio-choose-destination.png){zoomable="yes"}

1. Det markerade innehållet visas i e-post-Designer.

   ![](assets/genstudio-email-content.png){zoomable="yes"}

   >[!NOTE]
   >
   >GenStudio-upplevelser [ som skapats från en [!DNL Journey Optimizer] mall](#export-from-ajo-to-genstudio) importeras direkt till e-postens Designer. GenStudio-upplevelser som skapats utan en [!DNL Journey Optimizer]-mall importeras till [kompatibilitetsläge](../email/existing-content.md).

   Använd [redigeringsverktygen för e-postinnehåll](../email/content-from-scratch.md) och [anpassningsfälten](../personalization/personalize.md) för att redigera din e-post efter behov. Spara innehållet.

1. Gå tillbaka till kampanjsammanfattningssidan och klicka på **[!UICONTROL Create experiment]** om du vill använda experimenterande. [Lär dig skapa ett innehållsexperiment](../content-management/content-experiment.md)

   <!--![](assets/genstudio-create-experiment.png){zoomable="yes"}-->

1. Skapa flera behandlingar och upprepa stegen ovan för att importera och snabbt utnyttja de andra variationerna i e-postupplevelsen som du skapade i [!DNL GenStudio].

   ![](assets/genstudio-define-treatments.png){zoomable="yes"}

1. Spara ändringarna och [aktivera](../campaigns/review-activate-campaign.md) kampanjen.

När du har kört experimentet kan du följa upp hur kampanjbehandlingarna fungerar med [rapporten om experimentella kampanjer](../reports/campaign-global-report-cja-experimentation.md). Sedan kan du tolka resultatet av ditt experiment. [Lär dig hur](../content-management/get-started-experiment.md#interpret-results)