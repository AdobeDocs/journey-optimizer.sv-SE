---
title: Create code-based experiences
description: Learn how to create code-based experiences in Journey Optimizer
feature: Code-based Experiences
topic: Content Management
role: User
level: Experienced
exl-id: 25c2c448-9380-47b0-97c5-16d9afb794c5
source-git-commit: ac8ccb52bd16a26c14dea148f989256e28170765
workflow-type: tm+mt
source-wordcount: '1740'
ht-degree: 1%

---

# Create code-based experiences {#create-code-based}

I [!DNL Journey Optimizer] kan du skapa kodbaserade upplevelser under en resa eller en kampanj.

Specifika skyddsutkast och rekommendationer för kodbaserade upplevelser finns på [den här sidan](code-based-prerequisites.md).

## Lägg till en kodbaserad upplevelse genom en resa eller en kampanj {#create-code-based-experience}

Följ stegen nedan för att börja bygga upp din kodbaserade upplevelse genom en resa eller en kampanj.

>[!BEGINTABS]

>[!TAB Lägg till en kodbaserad upplevelse på en resa]

****

1. [Skapa en resa](../building-journeys/journey-gs.md).

1. Starta din resa med en [Event](../building-journeys/general-events.md)- eller [Read Audience](../building-journeys/read-audience.md)-aktivitet.

1. Dra och släpp en **[!UICONTROL Code-based experience]**-aktivitet från **[!UICONTROL Actions]**-delen av paletten.

   ![](assets/code-based-activity-journey.png)

   >[!NOTE]
   >
   >Eftersom **Kodbaserad upplevelse** är en inkommande meddelandeaktivitet levereras den med en 3-dagars **Wait**-aktivitet. [Läs mer](../building-journeys/wait-activity.md#auto-wait-node)

1. **[!UICONTROL Label]****[!UICONTROL Description]**

1. [](code-based-configuration.md)

   ![](assets/code-based-activity-config.png)

1. **[!UICONTROL Edit content]** [Läs mer](#edit-code)

   You can also use an existing content template as a basis for your code content. Note that the templates available to choose are scoped to either HTML or JSON based on the channel configuration that has been chosen beforehand. [](../content-management/use-content-templates.md)

1. If necessary, complete your journey flow by dragging and dropping additional actions or events. [Läs mer](../building-journeys/about-journey-activities.md)

1. Once your code-base experience is ready, finalize the configuration and publish your journey to activate it. [Läs mer](../building-journeys/publishing-the-journey.md)

Mer information om hur du konfigurerar en resa finns på [den här sidan](../building-journeys/journey-gs.md).

>[!TAB Skapa en kodbaserad upplevelsekampanj]

Följ stegen nedan för att börja skapa din **kodbaserade**-upplevelse via en kampanj.

1. Create a campaign. [Läs mer](../campaigns/create-campaign.md)

1. Select the type of campaign that you want to execute

   * **[!UICONTROL Scheduled - Marketing]** **** They are configured and executed from the user interface.

   * **[!UICONTROL API-triggered - Marketing/Transactional]** ******** [](../campaigns/api-triggered-campaigns.md)

1. [](../audience/about-audiences.md)[](../campaigns/create-campaign.md#schedule) [](../campaigns/get-started-with-campaigns.md)

1. **[!UICONTROL Code-based experience]**

1. Select or create the code-based experience configuration. [Läs mer](code-based-configuration.md)

   ![](assets/code-based-campaign-surface.png)

1. Redigera ditt innehåll med personaliseringsredigeraren. [Läs mer](#edit-code)

   Du kan också använda en befintlig innehållsmall som bas för kodinnehållet. Observera att mallarna som är tillgängliga att välja omfattar antingen HTML eller JSON baserat på den kanalkonfiguration som har valts tidigare. [Lär dig använda innehållsmallar](../content-management/use-content-templates.md)

   <!--![](assets/code-based-campaign-edit-content.png)-->

Mer information om hur du konfigurerar en kampanj finns på [den här sidan](../campaigns/get-started-with-campaigns.md).

>[!ENDTABS]

## Edit the code content {#edit-code}

>[!CONTEXTUALHELP]
>id="ajo_code_based_experience"
>title="Använda personaliseringsredigeraren"
>abstract="Insert and edit the code you want to deliver as part of this code-based experience action."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions.html" text="Get started with the personalization editor"

1. **[!UICONTROL Edit code]**

   ![](assets/code-based-campaign-edit-code.png)

1. [](../personalization/personalization-build-expressions.md) Det är ett gränssnitt för att skapa icke-visuella upplevelser som gör att du kan skapa koden.

1. You can switch the authoring mode from HTML to JSON, and vice versa.

   ![](assets/code-based-campaign-code-editor.png)

   >[!CAUTION]
   >
   >Changing the authoring mode will result in losing all of your current code, so make sure to switch modes before you start authoring.

1. Enter your code as needed. [!DNL Journey Optimizer] [Läs mer](../personalization/personalization-build-expressions.md)

1. You can add HTML or JSON expression fragments if needed. [Lär dig hur](../personalization/use-expression-fragments.md)

   Du kan också spara en del av kodinnehållet som fragment. [Lär dig hur](../content-management/fragments.md#save-as-expression-fragment)

1. Med kodbaserade upplevelser kan ni använda beslutsfunktionen. Välj ikonen **[!UICONTROL Decision policy]** i det vänstra fältet och klicka på **[!UICONTROL Add decision policy]**. [Läs mer](../experience-decisioning/create-decision.md)

   ![](assets/code-based-campaign-create-decision.png)

   >[!NOTE]
   >
   >Beslut är för närvarande bara tillgängligt för en uppsättning organisationer (begränsad tillgänglighet). To gain access, contact your Adobe representative.


1. Klicka på **[!UICONTROL Save and close]** för att bekräfta ändringarna.

Så snart utvecklaren gör ett API- eller SDK-anrop för att hämta innehåll för den yta som definieras i kanalkonfigurationen tillämpas ändringarna på webbsidan eller appen.

## Testa den kodbaserade upplevelsen {#test-code-based-experience}

>[!CONTEXTUALHELP]
>id="ajo_code_based_preview"
>title="Preview your code-based experience"
>abstract="Get a simulation of what your code-based experience will look like."

Följ stegen nedan för att visa en förhandsgranskning av din ändrade kodbaserade upplevelse.

>[!CAUTION]
>
>Du måste ha testprofiler tillgängliga för att simulera vilka erbjudanden som ska levereras till dem. Lär dig hur du [skapar testprofiler](../audience/creating-test-profiles.md).

1. Välj **[!UICONTROL Simulate content]** på resan eller i kampanjen, antingen från personaliseringsredigeraren eller från redigeringsfönstret för innehåll.

   ![](assets/code-based-campaign-simulate.png)

1. Klicka på **[!UICONTROL Manage test profiles]** för att välja en eller flera testprofiler.

1. En förhandsgranskning av den ändrade kodbaserade upplevelsen visas.

Detaljerad information om hur du väljer testprofiler och förhandsgranskar ditt innehåll finns i [det här avsnittet](../content-management/preview.md).

### Förhandsgranska på enhet {#preview-on-device}

>[!CONTEXTUALHELP]
>id="ajo_code_based_preview_device"
>title="Förgranska din kodbaserade upplevelse på en riktig enhet"
>abstract="Få en förgranskning av era personaliserade upplevelser direkt i webbläsaren eller på era mobila enheter för att se hur de ser ut på riktiga enheter."

>[!CONTEXTUALHELP]
>id="ajo_code_based_preview_device_web"
>title="Förhandsgranska din kodbaserade webbupplevelse på enheten"
>abstract="Skanna QR-koden eller kopiera länken för att förhandsgranska på enheten."

>[!CONTEXTUALHELP]
>id="ajo_code_based_preview_device_mobile"
>title="Preview your code-based mobile experience on device"
>abstract="Scan the QR code or copy the link to preview on device. Once connected, enter the pin on the device. You may need to restart your app to see the changes each time you update your preview links."

>[!CONTEXTUALHELP]
>id="ajo_code_based_preview_device_refresh"
>title="Refresh the preview link to reflect the current view"
>abstract="The on-device preview will show the content as of when you created or refreshed the preview link. If you&#39;ve modified the content or selected a different test profile or treatment, refresh the preview to have it reflect the current view."

When building code-based experiences for web pages or mobile apps, you can preview your personalized experiences right on your browser or on your mobile devices, in order to see how these experiences look on real devices.

>[!WARNING]
>
>[](../experience-decisioning/create-decision.md)[](../personalization/personalization-build-expressions.md)

1. Klicka på knappen **[!UICONTROL Open preview options]** på skärmen **[!UICONTROL Simulate]**. Förhandsvisningsalternativen beror på vilken plattform du har valt i den [kodbaserade konfigurationen](code-based-configuration.md#create-code-based-configuration).

1. Om du använder en [webbplattform](code-based-configuration.md#web) i din kodbaserade konfiguration är det **[!UICONTROL Device preview URL]** skrivskyddade fältet ifyllt med den URL som angetts för den aktuella kanalkonfigurationen.

   ![](assets/preview-on-device-web.png)

   Du kan antingen:

   * **[!UICONTROL Copy link]** You can also share the link with your team and stakeholders, who can preview the new experience in any browser before the changes go live.

   * **[!UICONTROL Open in new tab]**

   * Scan the QR code with your mobile device to open the preview link on a mobile browser.

1. [](code-based-configuration.md#mobile)**[!UICONTROL Deeplink]****[!UICONTROL Preview URL]**

   **[!UICONTROL iOS]****[!DNL Android]**

   ![](assets/preview-on-device-mobile.png)

   You can either:

   * **[!UICONTROL Copy link]**

   * Scan the QR code with your mobile device to open the preview link directly in the mobile application. [](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/tutorials/implement-assurance){target="_blank"}

     >[!NOTE]
     >
     >**** [](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/home){target="_blank"}

1. Länkar för förhandsgranskning genereras för den valda testprofilen och, om du använder [innehållsexperiment](../content-management/content-experiment.md) under din resa eller kampanj, för den valda behandlingen.

   <!--If you have modified the content or selected a different treatment or test profile, scroll down to the bottom of the **[!UICONTROL Preview on device]** pop-up and click **[!UICONTROL Refresh preview link]** to reflect the current state.

   ![](assets/preview-on-device-refresh.png)-->

   <!--When creating a content experiment, you need to select a given treatment and click the **[!UICONTROL Simulate content]** button to obtain the link corresponding to that treatment, then select another treatment, click the **[!UICONTROL Simulate content]** button to obtain a new preview link, and so on.-->

   When updating the content, or selecting a different test profile or treatment, the preview link is automatically refreshed. You can copy the link into different browser tabs, and compare the experiences.

## Make your code-based experience live {#code-based-experience-live}

>[!IMPORTANT]
>
> If your campaign is subject to an approval policy, you will need to request approval in order to be able to activate your code-based experiences. [Läs mer](../test-approve/gs-approval.md)

När du har definierat din kodbaserade upplevelse och redigerat ditt innehåll efter behov med den [kodbaserade redigeraren](#edit-code) kan du aktivera din resa eller kampanj för att göra ändringarna synliga för din målgrupp.

You can also preview your code-based experience content before making it live. [Läs mer](#test-code-based-experience)

>[!NOTE]
>
>If you activate a code-based journey/campaign impacting the same pages as another journey or campaign which is already live, all the changes will be applied to your content.
>
>If multiple code-based journeys or campaigns update the same element(s) of your content, the highest priority journey/campaign takes precedence.

[](code-based-configuration.md) [](code-based-implementation-samples.md)

### Publish a code-based journey {#publish-code-based-journey}

To make your code-based experience live from a journey, follow the steps below.

1. Verify that your journey is valid and that there is no error. [Läs mer](../building-journeys/troubleshooting.md#checking-for-errors-before-testing)

1. **[!UICONTROL Publish]**

   ![](assets/code-based-journey-publish.png)

   >[!NOTE]
   >
   >[](../building-journeys/publishing-the-journey.md)

Din kodbaserade resa har statusen **[!UICONTROL Live]** och är nu synlig för den valda målgruppen. Varje mottagare av resan kan se dina ändringar.

>[!NOTE]
>
>När du har klickat på **[!UICONTROL Publish]** kan det ta upp till 15 minuter innan ändringarna är tillgängliga live.

### Aktivera en kodbaserad kampanj {#activate-code-based-campaign}

1. Välj **[!UICONTROL Review to activate]** från din kodbaserade kampanj.

   ![](assets/code-based-campaign-review.png)

1. Check and edit if needed the content, properties, configuration, audience and schedule.

1. Välj **[!UICONTROL Activate]**.

   ![](assets/code-based-campaign-activate.png)

   >[!NOTE]
   >
   >Läs mer om hur du aktiverar kampanjer i [det här avsnittet](../campaigns/review-activate-campaign.md).

Din kodbaserade kampanj har statusen **[!UICONTROL Live]** och är nu synlig för den valda målgruppen. Alla mottagare av kampanjen kan se de ändringar du har lagt till i innehållet.

>[!NOTE]
>
>**[!UICONTROL Activate]**
>
>**[!UICONTROL Scheduled]**

## Stoppa en kodbaserad resa eller kampanj {#stop-code-based-experience}

När en kodbaserad upplevelse är aktiv kan ni stoppa den för att hindra publiken från att se ändringarna. Följ stegen nedan.

1. Välj en direktresa eller kampanj i respektive lista.

1. Utför lämplig åtgärd utifrån ditt fall:

   * Välj **[!UICONTROL Stop campaign]** på den översta kampanjmenyn.

     ![](assets/code-based-campaign-stop.png)

   * Klicka på knappen **[!UICONTROL More]** på den översta menyn på resan och välj **[!UICONTROL Stop]**.

     ![](assets/code-based-journey-stop.png)

1. De ändringar du har lagt till visas inte längre för den målgrupp du har definierat.

>[!NOTE]
>
>När en kodbaserad resa eller kampanj har stoppats kan du inte redigera eller aktivera den igen. Du kan bara duplicera den och aktivera den duplicerade resan/kampanjen.

<!--Reporting TBC

## Check the code-based experience reports {#check-code-based-reports}

Once your code-based experience is live, you can check the **[!UICONTROL Code-based]** tab of the  [Journey report](../reports/journey-global-report-cja.md#web-cja) and [Campaign report](../reports/campaign-global-report-cja.md#web) to compare elements such as the number of experiences delivered to your audience, and the number of engagements with your content.-->

<!--## Code-based reports

You can access code-based journey or campaign reports from the summary screen.

Global reports display events that occurred at least two hours ago and cover events over a selected time period. In comparison, Live reports focus on events that took place within the past 24 hours, with a minimum time interval of two minutes from the event occurrence.

### Code-based live report {#live-report-code-based}

From your campaign **[!UICONTROL Live report]**, the **[!UICONTROL Code-based experience]** tab details the main information relative to your apps or web pages. [Learn more on live report](../reports/campaign-live-report.md)

+++Learn more on the different metrics and widgets available for the Code-based experience report.

The **[!UICONTROL Code-based experience performance]** KPIs detail the main information relative to your visitors' engagement with your code-based experiences, such as:

* **[!UICONTROL Impressions]**: total number of experiences delivered to all users.

* **[!UICONTROL Interactions]**:  total number of engagements with your app/page. This includes any actions taken by the users, such as clicks or any other interactions.

The **[!UICONTROL Code-based experience summary]** graph shows the evolution of your experiences (impressions, unique impressions and interactions) for the last 24 hours.

TBC: The **[!UICONTROL Interactions by element]** table details the main information relative to your visitors' engagement with the various elements on your app/pages.
+++

### Code-based global report {#global-report-code-based}

Code-based campaign global report can be accessed directly from your journey or campaign with the **[!UICONTROL View report]** button. [Learn more on global report](../reports/campaign-global-report-cja.md)

From your Campaign **[!UICONTROL Global report]**, the **[!UICONTROL Code-based experience]** tab details the main information relative to your apps or web pages.

![](assets/code-based-campaign-global-report.png)

Add image TBC

+++Learn more on the different metrics and widgets available for the Code-based experience report.

The **[!UICONTROL Code-based experience performance]** KPIs detail the main information relative to your visitors' engagement with your experiences, such as:

* **[!UICONTROL Unique impressions]**: number of unique users to whom the experience was delivered.

* **[!UICONTROL Impressions]**: total number of experiences delivered to all users.

* **[!UICONTROL Interactions]**: percentage of engagements with your app/page. This includes any actions taken by the users, such as clicks or any other interactions.

The **[!UICONTROL Code-based experience summary]** graph shows the evolution of your experiences (unique impressions, impressions and interactions) for the concerned period.

TBC: The **[!UICONTROL Interactions by element]** table details the main information relative to your visitors' engagement with the various elements on your apps/pages.
+++

TBC video if existing

## How-to video{#video}

The video below shows how to create a code-based campaign, configure its properties, review, and publish it.

>[!VIDEO]()

-->
