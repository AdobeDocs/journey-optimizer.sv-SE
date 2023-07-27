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
source-git-commit: 4112ac79a1f21fb369119ccd801dcbceac3c1e58
workflow-type: tm+mt
source-wordcount: '2225'
ht-degree: 0%

---

# Global kampanjrapport {#campaign-global-report}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_report"
>title="Global kampanjrapport"
>abstract="Med den globala rapporten Campaign kan ni mäta effekten av era kampanjer under en viss tidsperiod. Din rapport är uppdelad i olika widgetar som detaljerat beskriver kampanjens framgångar och fel. Varje rapportkontrollpanel kan ändras genom att widgetar storleksändras eller tas bort."

Globala rapporter, som du kommer åt från fliken All time, visar händelser som inträffat för minst två timmar sedan och täcker händelser under en vald tidsperiod. Live-rapporter fokuserar på händelser som har inträffat under de senaste 24 timmarna, med ett tidsintervall på minst två minuter från händelseförekomsten.

Kampanjens globala rapport kan nås direkt från er Campaign via **[!UICONTROL View report]** -knappen.

![](assets/campaign_report_global_5.png)

Kampanjen **[!UICONTROL Global report]** visas med följande flikar:

* [Campaign](#campaign-global)
* [E-post](#email-global)
* [I appen](#inapp-global)
* [Push](#push-global)
* [SMS](#sms-global)
* [Webb](#web-tab)
* [Direktmeddelande](#direct-mail-global)

Kampanjen **[!UICONTROL Global report]** är uppdelat i olika widgetar som detaljerat beskriver kampanjens framgångar och fel. Varje widget kan storleksändras och tas bort vid behov. Mer information finns i [section](../reports/global-report.md#modify-dashboard).

En detaljerad lista över alla mätvärden som är tillgängliga i Adobe Journey Optimizer finns på [den här sidan](global-report.md#list-of-components-global.md)

## Fliken Kampanj {#campaign-global}

### Leverans {#delivery-global}

![](assets/campaign_report_global_1.png)

The **[!UICONTROL Campaign's Statistics]** widgetinformation om huvudinformationen i förhållande till kampanjen:

* **[!UICONTROL Entered profiles]**: Antal profiler som påbörjade resan.

* **[!UICONTROL Actions delivered]**: Totalt antal unika gånger en åtgärd i resan har utförts.

* **[!UICONTROL Actions failed in %]**: Totalt antal unika gånger en åtgärd misslyckades under resan jämfört med det totala antalet unika gånger en åtgärd har levererats.

<!--
### Objectives report {#objectives-global}

![](assets/performance_report.gif)

The **[!UICONTROL Objectives]** tab allows you to better fine-tune your deliveries' reports by targeting one specific metric.

The **[!UICONTROL Objectives]** listed are linked to **[!UICONTROL Datasets]** that define a connection to a system in order to retrieve additional information. A list of built-in **[!UICONTROL Objectives]** is available but you can add your own by adding new **[!UICONTROL Dataset]**. For the detailed procedure, refer to this [section](../campaigns/reporting-configuration.md).

After selecting the Objectives you want to target on, the two **[!UICONTROL Performance overview]** and **[!UICONTROL Campaign objective]** widgets will provide a detailed summary of your delivery performance. 

With the **[!UICONTROL Campaign objective]** widget, you can also choose to compare your main objective with another metric.
-->

### Experimentationsrapport {#experimentation-global}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment_click"
>title="Resultatmått"
>abstract="Det totala värdet för resultatmåttet, som tidigare valts när du skapade dina experiment, delat med antalet profiler."

![](assets/experimentation_report_3.png)

The **[!UICONTROL Experimentation]** ger viktiga insikter om prestanda för varje variant och identifierar den mest framgångsrika.

Observera att det kan ta en stund att definiera den bästa utföraren, men den representeras av den här ikonen ![](assets/experimentation_report_1.png).

+++Läs mer om de olika mätvärden och widgetar som är tillgängliga för rapporten Experimentation.

The **[!UICONTROL Experiment result]** widgeten anger prestanda för varje variant. Du kan ändra din baslinje genom att välja en av behandlingarna i **[!UICONTROL Baseline]** listrutan. Den bästa behandlingen visas med en stjärnikon.

Tabellen visar följande mått:

* **[!UICONTROL Lift over baseline]**: Mät den procentuella förbättringen av konverteringsgraden för en viss behandling jämfört med baslinjen.

* **[!UICONTROL Confidence]** Bevis på att en viss behandling är densamma som den initiala behandlingen. [Läs mer](../campaigns/experiment-calculations.md#understand-confidence)

* **[!UICONTROL Unique outbound clicks]**: Totalt antal klick i utgående kanaler.

* **[!UICONTROL Profiles]**: Antal profiler som är avsedda för den här behandlingen.

* **[!UICONTROL Unique outbound clicks/profiles]**: Totalt värde för resultatmåttet, som tidigare valdes när du skapade dina experiment, delat med antalet profiler.

The **[!UICONTROL Confidence interval]** graf mäter osäkerheten kring förbättringen. Här anges den procentuella skillnaden i prestanda mellan baslinjen och den bästa behandlingen. [Läs mer](../campaigns/experiment-calculations.md#confidence-intervals).

![](assets/experimentation_report_4.png)

Den sista widgeten innehåller data relaterade till **[!UICONTROL Success metric]** du tidigare valde för dina behandlingar. Du kan välja ett annat målmått på menyn **[!UICONTROL Metric]** för att spåra alternativa data.

>[!CAUTION]
>
>När du arbetar med experimentellt filtrerade mätvärden bör du tänka på att om du ändrar måttvalet från listrutan på jämförelsesidan för experimenterande behålls inte filtervärdet. Om du till exempel växlar från&quot;Klickningar&quot; till&quot;Unika klickningar&quot; kommer det använda filtret att gå förlorat, vilket gör jämförelsen felaktig eller ogiltig.

+++

En djupdykning i dessa resultat och hur du tolkar dem finns i [den här sidan](../campaigns/get-started-experiment.md#interpret-results).

## Fliken E-post {#email-global}

![](assets/campaign_report_global_2.png)

Från er kampanj **[!UICONTROL Global report]**, **[!UICONTROL Email]** -fliken innehåller huvudinformationen om de e-postleveranser som skickas i din kampanj.

+++Läs mer om de olika mätvärden och widgetar som är tillgängliga för e-postrapporten.

The **[!UICONTROL Email Sending Statistics]** diagram visar hur framgångsrik leveransen är:

* **[!UICONTROL Targeted]**: Totalt antal meddelanden som bearbetats under leveransanalysen.

* **[!UICONTROL Sent]**: Totalt antal försändelser för leveransen.

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Delivery Rate]**: Procentandel meddelanden som skickades.

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Bounce Rate]**: Procentandel e-postmeddelanden som studsade jämfört med skickade e-postmeddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

* **[!UICONTROL Error Rate]**: Procentandel fel som uppstod under en leverans och som förhindrar att den skickas jämfört med skickade e-postmeddelanden.

* **[!UICONTROL Retries]**: Antal e-postmeddelanden i kön för återförsök.

* **[!UICONTROL Excluded]**: Antal profiler som har uteslutits av Adobe Journey Optimizer.

The **[!UICONTROL Email - Tracking statistics]** widgeten innehåller tillgängliga data för mottagaraktivitet för leveransen:

* **[!UICONTROL Opens]**: Antal gånger som leveransen öppnades i en leverans.

* **[!UICONTROL Unique Opens]**: Procent av öppnade leveranser.

* **[!UICONTROL Open Rate]**: Totalt antal öppnade e-postmeddelanden jämfört med antalet levererade e-postmeddelanden.

* **[!UICONTROL Clicks]**: Antal gånger ett innehåll klickades i ett e-postmeddelande.

* **[!UICONTROL Unique Clicks]**:Antal mottagare som klickat på ett innehåll i ett e-postmeddelande.

* **[!UICONTROL Unique Click Rate]**: Procentandel användare som interagerade med leveransen.

* **[!UICONTROL Unsubscriptions]**: Antal klick på länken för att avbryta prenumerationen.

* **[!UICONTROL Spam complaints]**: Antal gånger ett meddelande har deklarerats som skräppost eller skräppost.

The **[!UICONTROL Sending Statistics]** diagrammet innehåller de data som är tillgängliga för skickade e-postmeddelanden, som:

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Retries]**: Antal e-postmeddelanden i kön för återförsök.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

The **[!UICONTROL Bounce Reasons]** och **[!UICONTROL Bounce categories]** widgetar innehåller tillgängliga data som är relaterade till studsade meddelanden, som:

* **[!UICONTROL Hard bounce]**: Det totala antalet permanenta fel, t.ex. fel e-postadress. Detta inbegriper ett felmeddelande som uttryckligen anger att adressen är ogiltig, till exempel Okänd användare.

* **[!UICONTROL Soft bounce]**: Det totala antalet tillfälliga fel, till exempel en fullständig inkorg.

* **[!UICONTROL Ignored]**: Det totala antalet tillfälliga, t.ex. frånvaro, eller ett tekniskt fel, t.ex. om avsändartypen är postmaster.

Mer information om studsar finns i [Undertryckningslista](../reports/suppression-list.md) sida.

The **[!UICONTROL Error Reasons]** Med diagram och tabeller kan du se vilket fel som inträffade under leveransen.

The **[!UICONTROL Excluded reasons]** I diagram och tabeller visas de olika anledningar som gjorde att användarprofiler som inte ingår i målprofilerna inte kunde ta emot meddelandet.

The **[!UICONTROL Email - Top Url]** diagram- och tabellinformation om vilka URL:er från leveransen som besöks mest.

The **[!UICONTROL Email - Top recipient domain]** diagram och tabeller visar vilka domäner som är de mest använda av mottagarna för att öppna e-postmeddelandet.

>[!NOTE]
>
>The **[!UICONTROL Optimized vs non optimized]** och **[!UICONTROL Send time optimization]**  widgetar är bara tillgängliga om alternativet för optimering av sändningstid är aktiverat för leverans. Mer information om optimering av sändningstid finns i [den här sidan](../building-journeys/journeys-message.md#send-time-optimization).

The **[!UICONTROL Optimized vs non optimized]** diagram anger huvudinformationen i förhållande till meddelandet, oavsett om de är optimerade eller inte:

* **[!UICONTROL Sent]**: Totalt antal försändelser för leveransen.
* **[!UICONTROL Opens]**: Antal gånger som leveransen öppnades i en leverans.
* **[!UICONTROL Clicks]**: Antal gånger ett innehåll klickades i ett e-postmeddelande.

The **[!UICONTROL Send time optimization]** innehåller information om leveransens framgångar beroende på sändningsmetod: optimerad eller normal.

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.
* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.
+++

## Fliken I appen {#inapp-global}

Från er kampanj **[!UICONTROL Global report]**, **[!UICONTROL In-app]** -fliken innehåller huvudinformationen om de leveranser i appen som skickas i kampanjen.

![](assets/campaign_report_global_6.png)

+++Läs mer om de olika mätvärden och widgetar som är tillgängliga för rapporten i appen.

The **[!UICONTROL In-app performance]** Nyckeltal anger den viktigaste informationen i relation till besökarnas engagemang i era meddelanden i appen, till exempel:

* **[!UICONTROL Unique impressions]**: antal unika användare som meddelandet i appen levererades till.

* **[!UICONTROL Impressions]**: totalt antal meddelanden i appen som levereras till alla användare.

* **[!UICONTROL Click rate]**: Andel användare som interagerade med knapparna i meddelandet i appen jämfört med användare som såg meddelandet.

* **[!UICONTROL Dismiss rate]**: procent av meddelanden i appen som mottagarna avvisade.

The **[!UICONTROL In-app summary]** diagram visar hur dina visningar i appen har utvecklats för den aktuella perioden.

The **[!UICONTROL Clicks by button]** diagram och tabell innehåller tillgängliga data för mottagarnas beteende per knapp:

* **[!UICONTROL Clicks]**: totalt antal mottagare som interagerat med knapparna i meddelandet i appen.

* **[!UICONTROL Click rate]**: Andel användare som interagerade med knapparna i meddelandet i appen jämfört med användare som såg meddelandet.
+++

## Fliken Push-meddelanden {#push-global}

Från er kampanj **[!UICONTROL Global report]**, **[!UICONTROL Push notification]** -fliken innehåller huvudinformationen i förhållande till push-leveranser som skickas i kampanjen.

![](assets/campaign_report_global_3.png)

+++Läs mer om de olika mätvärden och widgetar som är tillgängliga för rapporten Push.

The **[!UICONTROL Push notification - Sending statistics]** tabellen visar huvudinformationen i förhållande till push-meddelanden med diagram och KPI:er:

* **[!UICONTROL Targeted]**: Totalt antal meddelanden som bearbetats under leveransanalysen.

* **[!UICONTROL Sent]**: Totalt antal försändelser för leveransen.

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Delivery Rate]**: Procentandel meddelanden som skickades.

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Bounce Rate]**: Procentandel push-meddelanden som studsade jämfört med skickade push-meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

* **[!UICONTROL Error Rate]**: Procentandel fel som uppstod under en leverans och som förhindrar att den skickas jämfört med push-meddelanden som skickas.

* **[!UICONTROL Excluded]**: Antal profiler som har uteslutits av Adobe Journey Optimizer.

The **[!UICONTROL Push - Tracking statistics]** innehåller tillgängliga data för mottagaraktivitet för leveransen:

* **[!UICONTROL Opens]**: Antal gånger ett meddelande öppnades i en leverans.

* **[!UICONTROL Open Rate]**: Procentandel öppnade push-meddelanden.

* **[!UICONTROL Actions]**: Totalt antal åtgärder för push-meddelandet som levererats, t.ex. knappklickning eller avvisning.

* **[!UICONTROL Engagements]**: Totalt antal öppningar och åtgärder för detta push-meddelande, dvs. om profilen öppnade push-meddelandet eller om någon klickade på en knapp.

* **[!UICONTROL Engagement Rate]**: Procentandel öppningar och åtgärder för det här push-meddelandet, dvs. om profilen öppnade push-meddelandet eller om någon klickade på en knapp.

The **[!UICONTROL Push notification summary]** diagrammet innehåller data som är tillgängliga för skickade push-meddelanden, som:

* **[!UICONTROL Opens]**: Antal gånger ett meddelande öppnades i en leverans.

* **[!UICONTROL Actions]**: Totalt antal åtgärder för push-meddelandet som levererats, t.ex. knappklickning eller avvisning.

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

>[!NOTE]
>
>The **[!UICONTROL Optimized vs non optimized]** och **[!UICONTROL Send time optimization]**  widgetar är bara tillgängliga om alternativet för optimering av sändningstid är aktiverat för leverans. Mer information om optimering av sändningstid finns i [den här sidan](../building-journeys/journeys-message.md#send-time-optimization).

The **[!UICONTROL Optimized vs non optimized]** diagram anger huvudinformationen i förhållande till meddelandet, oavsett om de är optimerade eller inte:

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.
* **[!UICONTROL Opens]**: Antal gånger som leveransen öppnades i en leverans.
* **[!UICONTROL Actions]**: Totalt antal åtgärder för push-meddelandet som levererats, t.ex. knappklickning eller avvisning.

The **[!UICONTROL Send time optimization]** innehåller information om leveransens framgångar beroende på sändningsmetod: optimerad eller normal.

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.
* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.

The **[!UICONTROL Error Reasons]** Med diagram och tabeller kan du se vilket fel som inträffade under leveransen.

The **[!UICONTROL Excluded reasons]** I diagram och tabeller visas de olika anledningar som gjorde att användarprofiler som inte ingår i målprofilerna inte kunde ta emot meddelandet.

The **[!UICONTROL Tracking by platform]**, **[!UICONTROL Sending by platform]** och **[!UICONTROL Breakdown by platform]** diagram och tabeller visar hur bra push-meddelandena är beroende på mottagarens operativsystem.
+++

## fliken SMS {#sms-global}

Från er kampanj **[!UICONTROL Global report]**, **[!UICONTROL SMS]** -fliken innehåller huvudinformationen om SMS-leveranser som skickas i kampanjen.

![](assets/campaign_report_global_4.png)

+++Läs mer om de olika mätvärden och widgetar som är tillgängliga för SMS-rapporten.

The **[!UICONTROL SMS - Sending statistics]** tabellen visar hur framgångsrik leveransen är:

* **[!UICONTROL Targeted]**: Antal användarprofiler som kvalificerar sig som målprofiler för den här leveransen.

* **[!UICONTROL Excluded]**: Antal användarprofiler, exkluderade från målprofilerna, som inte fick meddelandet.

* **[!UICONTROL Sent]**: Totalt antal försändelser för leveransen.

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

The **[!UICONTROL SMS Performance by date]** widgeten visar huvudinformationen i förhållande till meddelandet med ett diagram:

* **[!UICONTROL Sent]**: Totalt antal försändelser för leveransen.

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

The **[!UICONTROL Exclude Reasons]**, **[!UICONTROL Bounces Reasons]** och **[!UICONTROL Error Reasons]** Med diagram och tabeller kan du se vilka fel och undantag som inträffade under leveransen.

The **[!UICONTROL SMS - Clicks by links]** och **[!UICONTROL SMS - Tracking statistics]** widgetar detaljerar den viktigaste informationen i förhållande till besökarnas engagemang med dina URL-adresser.

+++

## Fliken Webb {#web-tab}

Från er kampanj **[!UICONTROL Global report]**, **[!UICONTROL Web]** -fliken anger huvudinformationen för dina webbsidor.

![](assets/web-report.png)

+++Läs mer om de olika mätvärden och widgetar som finns för webbrapporten.

The **[!UICONTROL Web performance]** Nyckeltal anger den viktigaste informationen i relation till besökarnas engagemang i era webbupplevelser, till exempel:

* **[!UICONTROL Unique impressions]**: antal unika användare som webbupplevelsen levererades till.

* **[!UICONTROL Impressions]**: totalt antal webbupplevelser som levereras till alla användare.

* **[!UICONTROL Click rate]**: Andel besökare som interagerade med de olika elementen på dina webbsidor.

The **[!UICONTROL Web summary]** diagram visar hur webbupplevelserna har utvecklats (visningar, unika intryck och klickningar) under den aktuella perioden.

The **[!UICONTROL Clicks by element]** tabellen innehåller huvudinformationen om besökarnas engagemang för de olika elementen på webbsidorna.
+++

## Fliken Direktreklam {#direct-mail-global}

Från er kampanj **[!UICONTROL Global report]**, **[!UICONTROL Direct mail]** -fliken anger huvudinformationen i förhållande till dina Direct-postleveranser.

+++Läs mer om de olika mätvärden och widgetar som finns för rapporten Direct mail.

The **[!UICONTROL Direct Mail - Sending statistics]** tabellen visar hur framgångsrik leveransen är:

* **[!UICONTROL Targeted]**: Antal användarprofiler som kvalificerar sig som målprofiler för den här leveransen.

* **[!UICONTROL Sent]**: Totalt antal försändelser för leveransen.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

* **[!UICONTROL Excluded]**: Antal användarprofiler, exkluderade från målprofilerna, som inte fick leveransen.

The **[!UICONTROL Direct Mail - Excluded reasons]** och **[!UICONTROL Direct Mail - Error reasons]** Med diagram och tabeller kan du se vilka fel och undantag som inträffade under leveransen.
+++

## Ytterligare resurser

* [Kom igång med kampanjer](../campaigns/get-started-with-campaigns.md)
* [Skapa en kampanj](../campaigns/create-campaign.md)
* [Skapa API-utlösta kampanjer](../campaigns/api-triggered-campaigns.md)
* [Ändra eller stoppa en kampanj](../campaigns/modify-stop-campaign.md)
* [Kampanjrapport](campaign-live-report.md)
