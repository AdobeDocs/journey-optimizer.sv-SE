---
solution: Journey Optimizer
product: journey optimizer
title: Global kampanjrapport
description: Lär dig använda data från rapporten Campaign Global
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: fa64f5b8-75f2-40e6-8566-5766fafe6cd6
source-git-commit: 94d6ebe6e0ad5fa48eaad9d8cfa8cff584f2b819
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Global kampanjrapport {#campaign-global-report}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_report"
>title="Global kampanjrapport"
>abstract="Med den globala rapporten Campaign kan ni mäta effekten av era kampanjer under en viss tidsperiod. Din rapport är uppdelad i olika widgetar som detaljerat beskriver kampanjens framgångar och fel. Varje rapportkontrollpanel kan ändras genom att widgetar storleksändras eller tas bort."

>[!AVAILABILITY]
>
>Den nuvarande rapportupplevelsen kommer att upphöra i januari 2025. Efter detta datum kommer den nya rapportupplevelsen att bli standard. Vi rekommenderar att du behärskar de nya funktionerna så att övergången blir smidig. [Kom igång med Journey Optimizer nya rapporteringsgränssnitt.](report-gs-cja.md)

Globala rapporter, som du kommer åt från fliken **All time**, visar händelser som inträffade för minst två timmar sedan och täcker händelser under en vald tidsperiod. Live-rapporter fokuserar på händelser som har inträffat under de senaste 24 timmarna, med ett tidsintervall på minst två minuter från händelseförekomsten.

Kampanjens globala rapport kan nås direkt från din kampanj med knappen **[!UICONTROL View report]**.

![](assets/campaign_report_global_5.png)

Sidan Campaign **[!UICONTROL Global report]** visas med följande flikar:

* [Campaign](#campaign-global)
* [E-post](#email-global)
* [I appen](#inapp-global)
* [Push](#push-global)
* [SMS](#sms-global)
* [Webb](#web-tab)
* [Direktmeddelande](#direct-mail-global)

Campaign **[!UICONTROL Global report]** är uppdelad i olika widgetar som beskriver kampanjens framgångar och fel. Varje widget kan storleksändras och tas bort vid behov. Mer information finns i [avsnittet](../reports/global-report.md#modify-dashboard).

En detaljerad lista över alla tillgängliga mätvärden i Adobe Journey Optimizer finns på [den här sidan](global-report.md#list-of-components-global.md)

## Fliken Kampanj {#campaign-global}

### Leverans {#delivery-global}

>[!CONTEXTUALHELP]
>id="ajo_campaign_delivery_global"
>title="Kampanjstatistik"
>abstract="Widgeten Statistik för Campaign visar huvudinformationen i förhållande till din kampanj, t.ex. Angivna profiler och levererade åtgärder."

![](assets/campaign_report_global_1.png)

KPI:erna **[!UICONTROL Campaign's Statistics]** fungerar som en omfattande instrumentpanel med en detaljerad beskrivning av nyckeltal relaterade till kampanjen. Detta inkluderar viktig information som antalet profiler och de åtgärder som utförts, vilket ger en grundlig förståelse för kampanjens resultat och engagemang.

+++ Läs mer om statistik för Campaign

* **[!UICONTROL Audience]**: Antal målprofiler.

* **[!UICONTROL Actions delivered]**: Totalt antal unika gånger en åtgärd har levererats.

* **[!UICONTROL Actions failed in %]**: Procentandel unika gånger en åtgärd misslyckades jämfört med det totala antalet unika gånger en åtgärd har levererats.

+++

<!--
### Objectives report {#objectives-global}

![](assets/performance_report.gif)

The **[!UICONTROL Objectives]** tab allows you to better fine-tune your deliveries' reports by targeting one specific metric.

The **[!UICONTROL Objectives]** listed are linked to **[!UICONTROL Datasets]** that define a connection to a system in order to retrieve additional information. A list of built-in **[!UICONTROL Objectives]** is available but you can add your own by adding new **[!UICONTROL Dataset]**. For the detailed procedure, refer to this [section](../content-management/reporting-configuration.md).

After selecting the Objectives you want to target on, the two **[!UICONTROL Performance overview]** and **[!UICONTROL Campaign objective]** widgets will provide a detailed summary of your delivery performance. 

With the **[!UICONTROL Campaign objective]** widget, you can also choose to compare your main objective with another metric.


### Experimentation report {#experimentation-global}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment_click"
>title="Success metric"
>abstract="The total value of the Success metric, previously selected when creating your Experiments, divided by the number of profiles."

![](assets/experimentation_report_3.png)

The **[!UICONTROL Experimentation]** tab provides key insights into the performance of each variant, and identifies the most successful one.

Note that defining the best performer might take some time, it will be represented by this icon ![](assets/experimentation_report_1.png).

+++Learn more on the different metrics and widgets available for the Experimentation report.

The **[!UICONTROL Experiment result]** widget details the performance of each variant. You can change your baseline by selecting one of the treatment from the **[!UICONTROL Baseline]** the drop-down. The best treatment will be represented with a star icon.

For a deep-dive in these results and how to interpret them, refer to [this page](../content-management/get-started-experiment.md#interpret-results).

The table presents the following metrics:

* **[!UICONTROL Lift over baseline]**: Measure of the percentage improvement in conversion rate of a given treatment over the baseline.

* **[!UICONTROL Confidence]**: Evidence that a given treatment is the same as the baseline treatment. [Learn more](../content-management/experiment-calculations.md#understand-confidence)

* **[!UICONTROL Unique outbound clicks]**: Total count of clicks across outbound channels.

* **[!UICONTROL Profiles]**: Number of profiles targeted for this treatment.

* **[!UICONTROL Unique outbound clicks/profiles]**: Total value of the Success metric, previously selected when creating your Experiments, divided by the number of profiles.

The **[!UICONTROL Confidence interval]** graph measures uncertainty around improvement. It details the percentage difference in performance between the baseline and the best performing treatment. [Learn more](../content-management/experiment-calculations.md#confidence-intervals). 

![](assets/experimentation_report_4.png)

The last widget provides data related to the **[!UICONTROL Success metric]** you previously selected for your Treatments. You have the option to select a different targeted metric from the **[!UICONTROL Metric]** drop-down menu to track alternative data.
    
>[!CAUTION]
>
>When working with experimentation filtered metrics, please note that changing the Metric selection from the drop-down on the comparison page for experimentation will not retain the filter value. For example, switching from "Clicks" to "Unique clicks" will lead to the loss of the applied filter, rendering the comparison inaccurate or invalid.

+++
-->

## Fliken E-post {#email-global}

### E-post - Sändande statistik {#sending-statistics-email}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_sending_statistics"
>title="E-post - Sändande statistik"
>abstract="Registret E-post - Skicka statistik innehåller en sammanfattning av viktiga data om din e-post, som Riktat eller Levererat."

![](assets/campaign_email_sending.png)

Tabellen **[!UICONTROL Email Sending Statistics]** innehåller en omfattande sammanfattning av viktiga data om dina e-postkampanjer. Den innehåller viktiga mätvärden som målgruppens storlek och antalet e-postmeddelanden som levererats, vilket ger värdefulla insikter om hur effektiva och omfattande era e-postmeddelanden är.

+++ Läs mer om statistik för e-postsändning

* **[!UICONTROL Targeted]**: Totalt antal e-postmeddelanden som bearbetats under sändningsprocessen.

* **[!UICONTROL Sent]**: Totalt antal skickade meddelanden för din e-post.

* **[!UICONTROL Delivered]**: Antal e-postmeddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Delivery Rate]**: Procentandel e-postmeddelanden har skickats.

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Bounce Rate]**: Procentandel e-postmeddelanden som studsade jämfört med skickade e-postmeddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

* **[!UICONTROL Error Rate]**: Procentandel fel som uppstod under sändningsprocessen som förhindrade att den skickades jämfört med skickade e-postmeddelanden.

* **[!UICONTROL Retries]**: Antal e-postmeddelanden i kön för nya försök.

* **[!UICONTROL Excluded]**: Antal profiler som har undantagits av Adobe Journey Optimizer.

+++

### E-post - Spårningsstatistik {#tracking-statistics-email}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_tracking_statistics"
>title="E-post - Spårningsstatistik"
>abstract="Registret E-post - Spårningsstatistik innehåller data om profilaktivitet för din e-post."

![](assets/campaign_email_tracking.png)

Tabellen **[!UICONTROL Email - Tracking statistics]** innehåller en detaljerad beskrivning av profilaktiviteten som är relaterad till dina e-postkampanjer. Detta inkluderar mätvärden för öppningar, klick och andra relevanta interaktionsindikatorer, som ger en heltäckande bild av hur profiler interagerar med ert e-postinnehåll.

+++ Läs mer om e-post - statistik för spårning

* **[!UICONTROL Opens]**: Antal gånger som e-postmeddelandet öppnades.

* **[!UICONTROL Unique Opens]**: Procentandel öppnade e-postmeddelanden.

* **[!UICONTROL Open Rate]**: Totalt antal öppnade e-postmeddelanden jämfört med antalet levererade e-postmeddelanden.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina e-postmeddelanden.

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickat på ett innehåll i ett e-postmeddelande.

* **[!UICONTROL Unique Click Rate]**: Procentandel användare som interagerade med dina e-postmeddelanden.

* **[!UICONTROL Unsubscriptions]**: Antal klick på länken för att avbryta prenumerationen.

* **[!UICONTROL Spam complaints]**: Antal gånger ett meddelande har deklarerats som skräppost eller skräppost.

+++

### E-post - Sändande prestanda {#sending-performance-email}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_sending_performance"
>title="E-post - Sändande prestanda"
>abstract="Prestandadiagrammet E-post - sändning innehåller omfattande data om skickade e-postmeddelanden, som ger insikter i viktiga mätvärden som levererade och studsade, vilket möjliggör en detaljerad analys av e-postleveransprocessen."

![](assets/campaign_email_sending_performance.png)

Diagrammet **[!UICONTROL Email - Sending Performance]** ger en heltäckande bild av data som är relaterade till skickade e-postmeddelanden och ger insikter i viktiga mått som levererade och studsade. Detta möjliggör en detaljerad analys av e-postsändningsprocessen och ger värdefull information om effektiviteten och resultatet för era e-postkampanjer.

+++ Läs mer om e-post - Sändande prestandamått

* **[!UICONTROL Delivered]**: Antal e-postmeddelanden som har skickats, i relation till det totala antalet skickade e-postmeddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning i relation till det totala antalet skickade e-postmeddelanden.

* **[!UICONTROL Retries]**: Antal e-postmeddelanden i kön för nya försök.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

+++

### E-post - studsorsaker och kategorier {#bounces-email}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_bounce_categories"
>title="E-post - studskategorier"
>abstract="Diagram och tabell för kategorierna E-post - studsa ger data om både tillfälliga och permanenta fel."

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_bounce_reasons"
>title="E-post - studsar orsaker"
>abstract="E-post - studsar orsaksdiagram och tabell innehåller tillgängliga data som relaterar till studsade meddelanden."

![](assets/campaign_email_bounces.png)

Widgetarna **[!UICONTROL Email - Bounce Reasons]** och **[!UICONTROL Email - Bounce categories]** kompilerar tillgängliga data som är relaterade till studsade meddelanden och ger detaljerade insikter om de specifika orsakerna och kategorierna bakom e-postgränserna.

Mer information om studsar finns på sidan [Suppressionslista](../reports/suppression-list.md).

+++ Läs mer om e-post - statistik om studskategorier

* **[!UICONTROL Hard bounce]**: Det totala antalet permanenta fel, till exempel en felaktig e-postadress. Detta inbegriper ett felmeddelande som uttryckligen anger att adressen är ogiltig, till exempel Okänd användare.

* **[!UICONTROL Soft bounce]**: Det totala antalet tillfälliga fel, till exempel en fullständig inkorg.

* **[!UICONTROL Ignored]**: Det totala antalet tillfälliga, till exempel frånvaro, eller ett tekniskt fel, till exempel om avsändartypen är postmaster.

+++


### E-post - felorsaker {#errors-email}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_error_reasons"
>title="E-post - felorsaker"
>abstract="Med diagrammen E-post - felorsaker och tabellen kan du identifiera de specifika fel som uppstod under sändningsprocessen."

![](assets/campaign_email_error_reasons.png)

Diagrammen och tabellen **[!UICONTROL Error Reasons]** ger synlighet för de specifika fel som uppstod under sändningsprocessen och ger värdefull information om felens art och förekomst.

Du kan välja att växla från en tabell, ett stapeldiagram eller en munk.

### E-post - orsaker som inte tas med {#excluded-email}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_excluded_reasons"
>title="E-post - orsaker som inte tas med"
>abstract="I diagrammen och tabellen Exkluderade orsaker visas de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen och inte fick meddelandet."

![](assets/campaign_email_excluded.png)

Diagrammen och tabellen **[!UICONTROL Excluded reasons]** innehåller en heltäckande bild av de olika faktorer som har lett till att användarprofiler har tagits bort från målgruppen, vilket leder till att meddelandet inte tas emot.

Se [den här sidan](exclusion-list.md) för en utförlig lista över orsaker till undantag.

### Skickat och levererat av domäner {#sent-domains}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_sent_domains"
>title="Skickat och levererat av domäner"
>abstract="Tabellen och grafen Skickat och levererat per domän ger en detaljerad beskrivning av e-postmeddelanden kategoriserade efter domäner och ger djupgående insikter om hur e-postkommunikationen fungerar generellt."

![](assets/campaign_email_sent_domains.png)

Tabellen och diagrammet **[!UICONTROL Sent & delivered by domains]** innehåller en detaljerad beskrivning av e-postmeddelanden på domännivå, med omfattande insikter om hur dina e-postmeddelanden fungerar.

+++ Läs mer om Sänd och levererad via domänmått

* **[!UICONTROL Sent]**: Totalt antal skickade meddelanden för din e-post.

* **[!UICONTROL Delivered]**: Antal e-postmeddelanden som har skickats, i relation till det totala antalet skickade e-postmeddelanden.

+++

### Begränsningar och fel per domäner {#bounces-domains}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_bounces_domains"
>title="Begränsningar och fel per domäner"
>abstract="Diagrammet och tabellen studsar och fel per domän ger en detaljerad fördelning på domännivå och ger insikter om specifika fel som uppstått under e-postsändningsprocessen."

![](assets/campaign_email_bounce_domains.png)

Diagrammet och tabellen **[!UICONTROL Bounces & errors by domains]** innehåller en beskrivning på domännivå av specifika fel som påträffats under sändningsprocessen, vilket ger en detaljerad analys av problem som uppstått.

+++ Läs mer om studsar och fel per domänmått

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning i relation till det totala antalet skickade e-postmeddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att din e-post skickas till profiler.

+++

### Öppna och klicka efter domäner {#opens-domains}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_open_domains"
>title="Öppna och klicka efter domäner"
>abstract="Diagrammet Öppna och klicka per domän och tabellen innehåller en detaljerad beskrivning på domännivå och en heltäckande bild av hur målgruppen interagerar med e-postmeddelanden."

![](assets/campaign_email_open_domains.png)

Diagrammet och tabellen **[!UICONTROL Open & clicks by domains]** visar en uppdelning på domännivå av dina profilers engagemang i ditt e-postmeddelande, vilket ger värdefulla insikter om hur olika domäner interagerar med ditt innehåll.

+++ Läs mer om Öppna och klickningar efter domänstatistik

* **[!UICONTROL Opens]**: Antal gånger som e-postmeddelandet öppnades.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i ett e-postmeddelande.

+++

### Studsa orsaker efter domän {#bounce-reasons-domains}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_bounces_reasons_domains"
>title="Studsa orsaker efter domän"
>abstract="Studsorsaker per domän - diagram och tabell ger en nedbrytning på domännivå som ger omfattande insikter om både tillfälliga och permanenta fel. Denna detaljerade analys ger värdefull information om de specifika orsakerna bakom studsade meddelanden."

![](assets/campaign_email_bounce_reasons_domains.png)

Diagrammet och tabellen **[!UICONTROL Bounce reasons by domain]** erbjuder en uppdelning på domännivå av data som gäller både tillfälliga och permanenta fel, vilket ger detaljerad information om orsakerna bakom studsade meddelanden.

+++ Läs mer om studsorsaker efter domänmått

* **[!UICONTROL Opens]**: Antal gånger som e-postmeddelandet öppnades.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i ett e-postmeddelande.

+++

### E-post - övre URL {#top-url-email}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_top_url"
>title="E-post - övre URL"
>abstract="Diagrammet E-post - övre URL och tabellen ger en omfattande översikt över de URL:er i ditt e-postmeddelande som tar emot mest besökstrafik, så att du kan identifiera de mest populära länkarna."

![](assets/campaign_email_topurl.png)

Diagrammet och tabellen **[!UICONTROL Email - Top Url]** innehåller en omfattande översikt över de URL:er i ditt e-postmeddelande som lockar den högsta besökstrafiken. På så sätt kan ni identifiera och prioritera de mest populära länkarna och öka er förståelse för hur proffsen interagerar med specifikt innehåll i era e-postmeddelanden.

### E-post - Bästa mottagardomän {#top-recipient-email}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_best_recipient"
>title="E-post - Bästa mottagardomän"
>abstract="Diagrammet E-post - Bästa mottagardomän och tabellen ger en detaljerad beskrivning av de domäner som mottagarna oftast använder för att öppna e-postmeddelandet, och ger värdefulla insikter om mottagarnas beteende."

![](assets/campaign_email_best_recipient.png)

>[!CAUTION]
>
> Widgeten **[!UICONTROL Email - Best recipient domain]** har en noggrannhetsgrad på 99,95 %.

Diagrammet och tabellen **[!UICONTROL Email - Best recipient domain]** innehåller en detaljerad beskrivning av de domäner som oftast används för att öppna e-postmeddelanden. Detta ger värdefulla insikter om profilbeteendet och hjälper er att förstå vilka plattformar ni föredrar.

+++ Läs mer om e-post - Bästa mottagardomänmått

* **[!UICONTROL Delivered]**: Antal e-postmeddelanden som har skickats, i relation till det totala antalet skickade e-postmeddelanden.

* **[!UICONTROL Delivery Rate]**: Procentandel e-postmeddelanden har skickats.

* **[!UICONTROL Bounces + Errors Rate]**: Procentandel e-postmeddelanden som studsade jämfört med skickade e-postmeddelanden.

+++

### E-post - optimering {#optimized-email}

![](assets/campaign_email_optimized.png)

>[!NOTE]
>
>Widgetarna **[!UICONTROL Optimized vs non optimized]** och **[!UICONTROL Send time optimization]** är bara tillgängliga om alternativet för optimering av sändningstid är aktiverat för ditt e-postmeddelande. Mer information om optimering av sändningstid finns på [den här sidan](../building-journeys/journeys-message.md#send-time-optimization).

Widgetarna **[!UICONTROL Optimized vs non optimized]** och **[!UICONTROL Send time optimization]** visar huvudinformationen i förhållande till ditt meddelande, oavsett om de är optimerade eller inte.

+++ Läs mer om optimeringsmått för sändningstid

* **[!UICONTROL Sent]**: Totalt antal skickade meddelanden.

* **[!UICONTROL Opens]**: Antal gånger som meddelandet öppnades.

* **[!UICONTROL Clicks]**: Antal gånger ett innehåll klickades i ett e-postmeddelande.

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning i relation till totalt antal skickade meddelanden.

+++

### E-post - erbjudanden {#email-offers}

![](assets/campaign_email_offers.png)

Widgetarna **[!UICONTROL Offers statistics]**, **[!UICONTROL Offers statistics over time]** och **[!UICONTROL Offers detailed statistic]** mäter hur bra ditt erbjudande är och hur det påverkar din målgrupp.

+++ Läs mer om e-post - ger statistik

* **[!UICONTROL Offer sent]**: Totalt antal utskick för erbjudandet.

* **[!UICONTROL Offer impression]**: Antal gånger som erbjudandet öppnades i dina e-postmeddelanden.

* **[!UICONTROL Offer clicks]**: Antal gånger som ett erbjudande klickades på i dina e-postmeddelanden.

* **[!UICONTROL Placement name]**: Namnet på din placering som användes för att visa ditt erbjudande. Mer information om placering finns på den här [sidan](../offers/offer-library/creating-placements.md).

* **[!UICONTROL Offer name]**: Namnet på erbjudandet som lagts till i leveransen. Mer information om placering finns på den här [sidan](../offers/offer-library/creating-personalized-offers.md).

* **[!UICONTROL Offer sent]**: Totalt antal utskick för erbjudandet.

* **[!UICONTROL Offer impression rate]**: Procentandel öppnade erbjudanden jämfört med antalet skickade erbjudanden.

+++

## Fliken I appen {#inapp-global}

Från din kampanj **[!UICONTROL Global report]** anger fliken **[!UICONTROL In-app]** huvudinformationen i förhållande till de meddelanden i appen som skickas i din kampanj.

### Prestanda i appen {#in-app-performance}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_inapp_performance"
>title="Prestanda i appen"
>abstract="KPI:erna för prestanda i appen ger viktiga insikter i besökarnas engagemang med meddelanden i appen."

![](assets/campaign_inapp_performance.png)

KPI:erna för **[!UICONTROL In-app performance]** ger viktiga insikter i besökarnas engagemang med meddelanden i appen, vilket ger viktiga mätvärden för att utvärdera effektiviteten och effekten av era kampanjer i appen.

+++ Läs mer om prestandamätningar i appen

* **[!UICONTROL Unique impressions]**: antal unika användare som meddelandet i appen levererades till.

* **[!UICONTROL Impressions]**: Totalt antal meddelanden i appen som har levererats till alla användare.

* **[!UICONTROL Interactions]**: Totalt antal ärenden för meddelandet i appen. Detta inkluderar alla åtgärder som användaren utför, t.ex. klickningar, uppsägningar eller annan interaktion.

+++

### Interaktioner per typ {#interactions-type}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_inapp_interactions"
>title="Interaktioner per typ"
>abstract="Interaktionen per typ av diagram och tabell visar hur användarna interagerade med meddelandet i appen genom att spåra varje klick, avbruten eller interaktion."

![](assets/campaign_inapp_interactions.png)

Diagrammen och tabellen **[!UICONTROL Interactions by type]** innehåller en detaljerad beskrivning av hur profiler interagerade med meddelandet i appen, spårningsåtgärder som klickningar, uppsägningar eller andra former av engagemang.

### Sammanfattning i appen {#in-app-summary}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_inapp_summary"
>title="Sammanfattning i appen"
>abstract="I sammanfattningsdiagrammet i appen visas utvecklingen för dina visningar och interaktioner i appen under den angivna perioden."

![](assets/campaign_inapp_summary.png)

Diagrammet **[!UICONTROL In-app summary]** illustrerar utvecklingen av dina visningar och interaktioner i appen under den angivna perioden, vilket ger en omfattande översikt över hur dina meddelanden i appen fungerar.

+++ Läs mer om sammanfattningsstatistik i appar

* **[!UICONTROL Unique impressions]**: antal unika användare som meddelandet i appen levererades till.

* **[!UICONTROL Impressions]**: Totalt antal meddelanden i appen som har levererats till alla användare.

* **[!UICONTROL Interactions]**: Totalt antal ärenden för meddelandet i appen. Detta inkluderar alla åtgärder som användaren utför, t.ex. klickningar, uppsägningar eller annan interaktion.

+++

## Fliken Push-meddelanden {#push-global}

Från din kampanj **[!UICONTROL Global report]** anger fliken **[!UICONTROL Push notification]** huvudinformationen i förhållande till push-meddelanden som skickas i din kampanj.

### Push-meddelande - skicka statistik {#push-sending-statistics}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_push_sending_statistics"
>title="Push-meddelande - skicka statistik"
>abstract="Registret Push Notification Sending Statistics sammanfattar viktiga data om dina push-meddelanden, som riktade eller levererade meddelanden."

![](assets/campaign_push_sending.png)

Tabellen **[!UICONTROL Push notification - Sending statistics]** innehåller en kortfattad sammanfattning av viktiga data relaterade till dina push-meddelanden, inklusive nyckelmått som antalet målmeddelanden och antalet meddelanden som levererats.

+++ Läs mer om push-meddelanden - Skicka statistik

* **[!UICONTROL Execution time]**: Starttid för varje körning av ditt återkommande push-meddelande. Om du bara vill ange ett eller flera återkommande push-meddelanden som mål väljer du det i listrutan **[!UICONTROL Execution time]**.

* **[!UICONTROL Targeted]**: Totalt antal push-meddelanden som bearbetats under analysen.

* **[!UICONTROL Sent]**: Totalt antal skickade för push-meddelandet.

* **[!UICONTROL Delivered]**: Antal push-meddelanden som har skickats, i relation till det totala antalet skickade push-meddelanden.

* **[!UICONTROL Delivery Rate]**: Procentandel push-meddelanden har skickats.

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning i relation till totalt antal push-meddelanden.

* **[!UICONTROL Bounce Rate]**: Procentandel push-meddelanden som studsade jämfört med skickade push-meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som har inträffat som förhindrar att den skickas till profiler.

* **[!UICONTROL Error Rate]**: Procentandel fel som inträffade när det inte kunde skickas jämfört med push-meddelanden som skickades.

* **[!UICONTROL Excluded]**: Antal profiler som har undantagits av Adobe Journey Optimizer.

+++

### Push-meddelande - Spårningsstatistik {#push-tracking-statistics}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_push_tracking_statistics"
>title="Push-meddelande - Spårningsstatistik"
>abstract="Statistik för push-spårning innehåller data om profilaktivitet för push-meddelanden."

![](assets/campaign_push_tracking.png)

Widgeten **[!UICONTROL Push notification- Tracking statistics]** erbjuder en detaljerad ögonblicksbild av profilaktivitet som är kopplad till dina push-meddelanden, vilket ger viktiga insikter om engagemang och push-meddelandenas effektivitet.

+++ Läs mer om push-meddelanden - Spåra statistik

* **[!UICONTROL Execution time]**: Starttid för varje körning av ditt återkommande push-meddelande. Om du bara vill ange ett eller flera återkommande push-meddelanden som mål väljer du det i listrutan **[!UICONTROL Execution time]**.

* **[!UICONTROL Opens]**: Antal gånger ditt push-meddelande öppnades.

* **[!UICONTROL Actions]**: Totalt antal åtgärder för det skickade push-meddelandet, t.ex. knappklickning eller avbruten.

+++

### Push-meddelande - Skickar sammanfattning {#push-summary}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_push_sending_summary"
>title="Push-meddelande - Skickar sammanfattning"
>abstract="I diagrammet Översikt över sändning av push-meddelanden visas tillgängliga data för skickade push-meddelanden."

![](assets/campaign_push_sending_summary.png)

Diagrammet **[!UICONTROL Push notification - Sending summary]** innehåller en dynamisk representation som visar en analys av din push-meddelandeaktivitet. Denna grafiska representation ger en omfattande beskrivning av skickade push-meddelanden.

+++ Läs mer om push-meddelanden - Skicka sammanfattningsmått

* **[!UICONTROL Opens]**: Antal gånger ditt push-meddelande öppnades.

* **[!UICONTROL Actions]**: Totalt antal åtgärder för det skickade push-meddelandet, t.ex. knappklickning eller avbruten.

* **[!UICONTROL Bounces]**: Totalt antal kumulerade fel och automatisk returbearbetning i relation till totalt antal skickade push-meddelanden.

* **[!UICONTROL Delivered]**: Antal push-meddelanden som har skickats, i relation till det totala antalet skickade push-meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som har inträffat som förhindrar att den skickas till profiler.

+++

### Push-meddelande - Optimering {#push-optimized}

>[!NOTE]
>
>Widgetarna **[!UICONTROL Optimized vs non optimized]** och **[!UICONTROL Send time optimization]** är bara tillgängliga om alternativet för optimering av sändningstid är aktiverat för ditt push-meddelande. Mer information om optimering av sändningstid finns på [den här sidan](../building-journeys/journeys-message.md#send-time-optimization).

Widgetarna **[!UICONTROL Optimized vs non optimized]** och **[!UICONTROL Send time optimization]** visar huvudinformationen i förhållande till ditt meddelande, oavsett om de är optimerade eller inte.

+++ Läs mer om push-meddelanden - Tidsoptimeringsmått för sändning

* **[!UICONTROL Delivered]**: Antal push-meddelanden som har skickats, i relation till det totala antalet skickade push-meddelanden.

* **[!UICONTROL Opens]**: Antal gånger ditt push-meddelande öppnades.

* **[!UICONTROL Actions]**: Totalt antal åtgärder för det skickade push-meddelandet, t.ex. knappklickning eller avbruten.

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning i relation till det totala antalet skickade push-meddelanden.

+++

### Push-meddelande - felorsaker {#error-reasons-push}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_push_error_reasons"
>title="Push-meddelande - felorsaker"
>abstract="Med hjälp av diagrammen och tabellen Felorsaker kan du identifiera de specifika fel som uppstod under sändningsprocessen."

![](assets/campaign_push_error_reasons.png)

Tabellen och diagrammen **[!UICONTROL Error Reasons]** ger dig möjlighet att identifiera de specifika fel som uppstod under sändningsprocessen för dina push-meddelanden, och ger dig detaljerade insikter om eventuella problem som påträffas längs vägen.

### Push-meddelande - Undantagna orsaker {#excluded-push}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_push_excluded_reasons"
>title="Push-meddelande - Undantagna orsaker"
>abstract="I diagrammen och tabellen Exkluderade orsaker visas de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen och inte fick meddelandet."

![](assets/campaign_push_excluded.png)

Diagrammen och tabellen **[!UICONTROL Excluded reasons]** visar olika orsaker som hindrade användarprofiler, exkluderade från målprofilerna, från att ta emot push-meddelanden.

Se [den här sidan](exclusion-list.md) för en utförlig lista över orsaker till undantag.

### Push-meddelande - uppdelning efter plattform {#breakdown-platform-push}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_push_breakdown_platform"
>title="Push-meddelande - uppdelning efter plattform"
>abstract="Push-meddelandet - Uppdelning efter plattform - diagram och tabell visar hur väl push-meddelandena lyckades baserat på profilens operativsystem."

![](assets/campaign_push_breakdown.png)

Diagrammet och tabellen **[!UICONTROL Push notification - Breakdown by platform]** innehåller en detaljerad analys av om push-meddelandena har lyckats och innehåller insikter baserade på din profils operativsystem. Den här nedbrytningen ger en bättre förståelse för hur bra dina push-meddelanden fungerar på olika plattformar.

+++ Läs mer om push-meddelanden - Uppdelning efter plattformsmått

* **[!UICONTROL Targeted]**: Totalt antal push-meddelanden som bearbetats under analysen.

* **[!UICONTROL Delivered]**: Antal push-meddelanden som har skickats, i relation till det totala antalet skickade push-meddelanden.

* **[!UICONTROL Opens]**: Antal gånger ditt push-meddelande öppnades.

* **[!UICONTROL Actions]**: Totalt antal åtgärder för det skickade push-meddelandet, t.ex. knappklickning eller avbruten.

* **[!UICONTROL Bounces]**: Totalt antal kumulerade fel och automatisk returbearbetning i relation till totalt antal skickade push-meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som har inträffat som förhindrar att den skickas till profiler.

* **[!UICONTROL Excluded]**: Antal profiler som har undantagits av Adobe Journey Optimizer.

+++

## fliken SMS {#sms-global}

Från din kampanj **[!UICONTROL Global report]** anger fliken **[!UICONTROL SMS]** huvudinformationen i relation till SMS-meddelandena som skickas i din kampanj.

### SMS - Sändande statistik {#sms-sending-statistics}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_sms_sending_statistics"
>title="SMS - Sändande statistik"
>abstract="Registret SMS - Sändande statistik sammanfattar viktiga data om dina SMS-meddelanden, som riktade eller levererade meddelanden."

![](assets/campaign_sms_sending.png)

Tabellen **[!UICONTROL SMS - Sending statistics]** innehåller en kortfattad sammanfattning av viktiga data relaterade till dina SMS-meddelanden, med nyckelmått som antalet målmeddelanden och antalet meddelanden som levererats.

+++ Läs mer om SMS - Skicka statistik

* **[!UICONTROL Execution time]**: Starttid för varje körning av ditt återkommande SMS-meddelande. Om du bara vill rikta in dig på ett eller flera återkommande SMS-meddelanden väljer du det i listrutan **[!UICONTROL Execution time]**.

* **[!UICONTROL Targeted]**: Antal användarprofiler som kvalificerar sig som målprofiler.

* **[!UICONTROL Excluded]**: Antal användarprofiler, exkluderade från målprofilerna, som inte fick meddelandet.

* **[!UICONTROL Sent]**: Totalt antal skickade meddelanden för dina SMS-meddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning i relation till det totala antalet skickade SMS-meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som har inträffat som förhindrar att den skickas till profiler.

+++

### SMS - Spårningsstatistik {#sms-tracking-statistics}

>[!CONTEXTUALHELP]
>id="ajo_campaign_sms_tracking_statistics"
>title="SMS - Spårningsstatistik"
>abstract="Widgeten SMS - Spårningsstatistik ger en omfattande översikt över viktig information som rör besökarnas interaktion med din URL."

![](assets/campaign_sms_tracking.png)

Widgeten **[!UICONTROL SMS - Tracking statistics]** ger en detaljerad översikt över viktig information som rör besökarnas interaktion med dina URL:er, och ger insikter om hur effektiva dina SMS-meddelanden är.

+++ Läs mer om SMS - Spåra statistik

* **[!UICONTROL Execution time]**: Starttid för varje körning av ditt återkommande SMS. Om du bara vill ange ett eller flera återkommande SMS som mål väljer du det i listrutan **[!UICONTROL Execution time]**.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades i ett SMS-meddelande.

+++

### SMS - Prestanda per datum {#sms-perfomance-date}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_sms_performance"
>title="SMS - Prestanda per datum"
>abstract="Widgeten - SMS Performance by Date (SMS-prestanda efter datum) ger viktig information om dina meddelanden via en grafisk representation."

![](assets/campaign_sms_performance.png)

Widgeten **[!UICONTROL SMS Performance by date]** ger en detaljerad översikt över viktig information som rör dina meddelanden, som presenteras i ett diagram, och ger insikter om prestandatrender under specifika tidsperioder.

+++ Läs mer om SMS - Prestanda efter datummått

* **[!UICONTROL Sent]**: Totalt antal skickade meddelanden för dina SMS-meddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning i relation till det totala antalet skickade SMS-meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som har inträffat som förhindrar att den skickas till profiler.

+++

### SMS - Felorsaker {#sms-error}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_sms_error_reasons"
>title="SMS - Felorsaker"
>abstract="Med hjälp av diagram och tabeller för felorsaker kan du identifiera de specifika fel som uppstod under sändningsprocessen."

![](assets/campaign_sms_error_reasons.png)

Med diagrammen och tabellen **[!UICONTROL Error Reasons]** kan du identifiera de specifika fel som uppstod under sändningsprocessen för SMS-meddelanden, vilket underlättar en grundlig analys av eventuella problem som påträffats.

### SMS - Undantagna orsaker {#sms-excluded-reasons}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_sms_excluded_reasons"
>title="SMS - Undantagna orsaker"
>abstract="I diagrammen och tabellen Exkluderade orsaker visas de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen och inte fick meddelandet."

![](assets/campaign_sms_excluded.png)

Diagrammen och tabellen **[!UICONTROL Excludes Reasons]** visar visuellt de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen, vilket förhindrar dem från att ta emot SMS-meddelanden.

Se [den här sidan](exclusion-list.md) för en utförlig lista över orsaker till undantag.

### SMS - studsar orsaker {#sms-bounces-reasons}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_sms_bounces_reasons"
>title="SMS - studsar orsaker"
>abstract="Diagram över studentorsaker och tabellen innehåller tillgängliga data om studsade meddelanden."

Diagrammen och tabellen **[!UICONTROL Bounces Reasons]** ger en omfattande översikt över data som är relaterade till studsade SMS-meddelanden och ger värdefulla insikter om de specifika orsakerna bakom instanser av SMS-meddelandegränser.

### SMS - Klicka på länkar {#sms-clicks-links}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_sms_clicks_links"
>title="SMS - Klicka på länkar"
>abstract="Widgeten SMS - Klicka på länkar ger viktiga insikter i besökarnas engagemang med URL:erna i dina meddelanden."

![](assets/campaign_sms_clicks.png)

Widgeten **[!UICONTROL SMS - Clicks by links]** ger viktiga insikter i besökarnas engagemang med de URL:er som ingår i dina meddelanden, och ger värdefull information om vilka länkar som lockar mest interaktion.

## Fliken Webb {#web-tab}

Från din kampanj **[!UICONTROL Global report]** anger fliken **[!UICONTROL Web]** huvudinformationen i förhållande till dina webbsidor.

### Webbprestanda {#web-performance}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_web_performance"
>title="Webbprestanda"
>abstract="KPI:erna för Web Performance ger omfattande information om besökarnas engagemang i era webbupplevelser."

![](assets/campaign_web_performance.png)

KPI:erna för **[!UICONTROL Web performance]** ger omfattande insikter om besökarnas engagemang på dina webbsidor, med nyckeltal som Impressions och Interactions.

+++ Läs mer om mätvärden för webbprestanda

* **[!UICONTROL Unique impressions]**: antal unika användare som webbupplevelsen har levererats till.

* **[!UICONTROL Impressions]**: Totalt antal webbupplevelser som levereras till alla användare.

* **[!UICONTROL Interaction rate]**: procentandel av interaktioner med din webbsida. Detta inkluderar alla åtgärder som användaren utför, t.ex. klickningar eller andra interaktioner.

+++

### Webbsammanfattning {#web-summary}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_web_summary"
>title="Webbsammanfattning"
>abstract="I webbsammanfattningsdiagrammet visas hur webbupplevelserna fortskrider, inklusive visningar, unika visningar och interaktioner under den angivna perioden."

![](assets/campaign_web_summary.png)

Diagrammet **[!UICONTROL Web summary]** visar hur webbupplevelsen (visningar, unika visningar och interaktioner) har utvecklats under den aktuella perioden.

+++ Läs mer om webbsammanfattningsstatistik

* **[!UICONTROL Unique impressions]**: antal unika användare som webbupplevelsen har levererats till.

* **[!UICONTROL Impressions]**: Totalt antal webbupplevelser som levereras till alla användare.

* **[!UICONTROL Interaction]**: totalt antal ärenden för din webbsida. Detta inkluderar alla åtgärder som användaren utför, t.ex. klickningar eller andra interaktioner.

+++

### Interaktioner per element {#web-interactions}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_web_interactions"
>title="Interaktioner per element"
>abstract="Tabellen Interaktioner per element innehåller viktig information om besökarnas engagemang med olika element på webbsidorna."

![](assets/campaign_web_interactions.png)

Tabellen **[!UICONTROL Interactions by element]** innehåller omfattande information om besökarnas engagemang med de olika elementen på dina webbsidor, vilket ger värdefulla insikter om användarinteraktioner och -inställningar.

+++ Läs mer om interaktioner per elementmått

* **[!UICONTROL Interaction]**: totalt antal ärenden för din webbsida. Detta inkluderar alla åtgärder som användaren utför, t.ex. klickningar eller andra interaktioner.

* **[!UICONTROL Interaction rate]**: procentandel av interaktioner med din webbsida. Detta inkluderar alla åtgärder som användaren utför, t.ex. klickningar eller andra interaktioner.

+++

## Fliken Direktreklam {#direct-mail-global}

Från din kampanj **[!UICONTROL Global report]** anger fliken **[!UICONTROL Direct mail]** huvudinformationen i relation till dina Direct-postmeddelanden.

### Direktreklam - skicka statistik {#direct-mail-sending-statistics}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_direct_sending_statistics"
>title="Direktreklam - skicka statistik"
>abstract="Registret Skicka direkt e-post - statistik sammanfattar viktiga data om dina Direct Mail-meddelanden, till exempel riktade eller levererade meddelanden."

![](assets/campaign_direct_sending.png)

Tabellen **[!UICONTROL Direct Mail - Sending statistics]** innehåller en kortfattad sammanfattning av viktiga data relaterade till dina Direct Mail-meddelanden. Den innehåller viktiga mått, till exempel antalet målmeddelanden och antalet meddelanden som har levererats.

+++ Läs mer om direktreklam - statistik skickas

* **[!UICONTROL Execution time]**: Starttid för varje körning av din återkommande direktpost. Om du bara vill ange ett eller flera återkommande direktmeddelanden som mål väljer du det i listrutan **[!UICONTROL Execution time]**.

* **[!UICONTROL Targeted]**: Antal användarprofiler som kvalificerar som målprofiler för dina direktutskick.

* **[!UICONTROL Sent]**: Totalt antal skickade meddelanden för dina direktutskick.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

* **[!UICONTROL Excluded]**: Antal användarprofiler, exkluderade från målprofilerna, som inte fick dina direktmeddelanden.

+++

### Direktreklam - felorsaker {#direct-mail-error}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_direct_error_reasons"
>title="Direktreklam - felorsaker"
>abstract="Med diagrammen och tabellen Direktreklam - Felorsaker kan du identifiera de specifika fel som uppstod under sändningsprocessen."

![](assets/direct-mail-report_1.png)

Diagrammen och tabellen **[!UICONTROL Direct Mail - Error reasons]** innehåller hjälpmedel för att identifiera specifika fel som uppstod under sändningsprocessen för dina direktutskick, så att du kan göra en detaljerad analys av eventuella problem som uppstått.

### Direktreklam - orsaker som inte ingår {#direct-mail-excluded}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_direct_excluded_reasons"
>title="Direktreklam - orsaker som inte ingår"
>abstract="Diagram och tabell över orsaker till varför direktreklam exkluderats visar de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen och inte fick meddelandet."

![](assets/campaign_direct_excluded.png)

Diagrammen och tabellen **[!UICONTROL Direct Mail - Excluded reasons]** illustrerar visuellt de olika faktorer som resulterade i att användarprofiler exkluderades från målgruppen, vilket förhindrar dem från att ta emot dina direktutskick.

Se [den här sidan](exclusion-list.md) för en utförlig lista över orsaker till undantag.

## Ytterligare resurser

* [Kom igång med kampanjer](../campaigns/get-started-with-campaigns.md)
* [Skapa en kampanj](../campaigns/create-campaign.md)
* [Skapa API-utlösta kampanjer](../campaigns/api-triggered-campaigns.md)
* [Ändra eller stoppa en kampanj](../campaigns/modify-stop-campaign.md)
* [Kampanjrapport](campaign-live-report.md)
