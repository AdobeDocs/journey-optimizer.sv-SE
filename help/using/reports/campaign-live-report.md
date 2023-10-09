---
solution: Journey Optimizer
product: journey optimizer
title: Kampanjrapport
description: Lär dig hur du använder data från Campaign-rapporten
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 925494b6-e08a-4bd3-8a2f-96a5d9cbc387
source-git-commit: 6bceccc561daac594f5c84d3d3250d887a349b7b
workflow-type: tm+mt
source-wordcount: '1907'
ht-degree: 0%

---

# Kampanjrapport {#campaign-live-report}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_report"
>title="Kampanjrapport"
>abstract="Med rapporten Campaign live kan ni i realtid mäta och visualisera effekten och resultatet av era kampanjer bara under de senaste 24 timmarna. Din rapport är uppdelad i olika widgetar som detaljerat beskriver kampanjens framgångar och fel. Varje rapportkontrollpanel kan ändras genom att widgetar storleksändras eller tas bort."

Live-rapporter, som du kommer åt från fliken Senaste 24 timmarna, visar händelser som har inträffat under de senaste 24 timmarna, med ett tidsintervall på minst två minuter från händelseförekomsten. Som jämförelse fokuserar Global-rapporter på händelser som inträffade för minst två timmar sedan och täcker händelser under en vald tidsperiod.

Kampanjens live-rapport kan nås direkt från kampanjen med **[!UICONTROL Live view]** -knappen.

Kampanjen **[!UICONTROL Live report]** visas med följande flikar:

* [Campaign](#campaign-live)
* [E-post](#email-live)
* [I appen](#inapp-live)
* [Push](#push-live)
* [SMS](#sms-live)
* [Webb](#web-tab)
* [Direktmeddelande](#direct-mail-tab)

Kampanjen **[!UICONTROL Live report]** är uppdelat i olika widgetar som detaljerat beskriver kampanjens framgångar och fel. Varje widget kan storleksändras och tas bort vid behov. Mer information finns i [section](../reports/live-report.md#modify-dashboard).

En detaljerad lista över alla mätvärden som är tillgängliga i Adobe Journey Optimizer finns på [den här sidan](live-report.md#list-of-components-live).

## Fliken Kampanj {#campaign-live}

### Leverans {#delivery-live}

The **[!UICONTROL Campaign Statistics]** widgetinformation om huvudinformationen i förhållande till kampanjen:

* **[!UICONTROL Entered profiles]**: Antal profiler som påbörjade resan.

<!--
### Experimentation tab (#experimentation-live)

From your Campaign **[!UICONTROL Live report]**, the **[!UICONTROL Experimentation]** tab details the main information relative to how each variant is performing and if there is was winner during the test.
-->

## Fliken E-post {#email-live}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_email_sending_statistics"
>title="E-post - Sändande statistik"
>abstract="Diagrammet E-post - Skicka statistik sammanfattar viktiga data om din e-post, som Målinriktad eller Levererad under de senaste 24 timmarna."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_email_statistics"
>title="E-post - statistik"
>abstract="Registret E-post - statistik innehåller data om profilaktivitet för din e-post de senaste 24 timmarna."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_email_bounce_categories"
>title="E-post - studskategorier"
>abstract="Diagram och tabell för kategorierna E-post - studsa ger data om både tillfälliga och permanenta fel från de senaste 24 timmarna."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_email_performance_bydate"
>title="E-post - Prestanda efter datum"
>abstract="Diagrammet E-post - prestation efter datum visar omfattande data från de senaste 24 timmarna när det gäller skickade e-postmeddelanden, och ger insikter i viktiga mätvärden som leveranser och studsar, vilket möjliggör en detaljerad analys av e-postleveransprocessen."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_email_bounce_reasons"
>title="E-post - studsar orsaker"
>abstract="E-post - studsar orsaksdiagram och tabell innehåller tillgängliga data som relaterar till studsade meddelanden från de senaste 24 timmarna."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_email_error_reasons"
>title="E-post - felorsaker"
>abstract="Med diagrammen E-post - felorsaker och tabellen kan du identifiera de specifika fel som uppstod under sändningsprocessen de senaste 24 timmarna."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_email_excluded_reasons"
>title="E-post - orsaker som inte tas med"
>abstract="I diagrammen och tabellen Exkluderade orsaker visas de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen och inte fick meddelandet under de senaste 24 timmarna."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_email_best_recipient"
>title="E-post - Bästa mottagardomän"
>abstract="Diagrammet E-post - Bästa mottagardomän och tabellen ger en detaljerad beskrivning av de domäner som mottagarna oftast använder för att öppna e-postmeddelandet, och ger värdefulla insikter om mottagarnas beteende de senaste 24 timmarna."

Från er kampanj **[!UICONTROL Live report]**, **[!UICONTROL Email]** -fliken anger huvudinformationen i relation till det e-postmeddelande som skickas i kampanjen.

![](assets/campaign_report_live_1.png)

+++Läs mer om de olika mätvärden och widgetar som är tillgängliga för e-postrapporten.

The **[!UICONTROL Email Sending Statistics]** widgeten innehåller information om den viktigaste informationen i förhållande till ditt meddelande:

* **[!UICONTROL Delivered]**: Antal meddelanden som skickats.

* **[!UICONTROL Bounces]**: Totalt antal fel som ackumulerats under sändningsprocessen och automatisk returbearbetning.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

The **[!UICONTROL Sending metrics by Email]** tabell och **[!UICONTROL Email Summary]** diagram visar hur bra ditt e-postmeddelande är:

* **[!UICONTROL Sent]**: Totalt antal överföringar.

* **[!UICONTROL Delivered]**: Antal meddelanden som skickats.

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

* **[!UICONTROL Opens]**: Antal gånger ett meddelande öppnades.

* **[!UICONTROL Clicks]**: Antal gånger som användaren klickat på ett innehåll.

* **[!UICONTROL Unsubscribe]**: Antal klick på länken för att avbryta prenumerationen.

* **[!UICONTROL Spam complaints]**: Antal gånger ett meddelande har deklarerats som skräppost eller skräppost.

The **[!UICONTROL Bounce Reasons]** och **[!UICONTROL Bounce categories]** widgetar innehåller tillgängliga data som är relaterade till studsade meddelanden, som:

* **[!UICONTROL Hard bounce]**: Det totala antalet permanenta fel, t.ex. fel e-postadress. Detta inbegriper ett felmeddelande som uttryckligen anger att adressen är ogiltig, till exempel Okänd användare.

* **[!UICONTROL Soft bounce]**: Det totala antalet tillfälliga fel, till exempel en fullständig inkorg.

* **[!UICONTROL Ignored]**: Det totala antalet tillfälliga, t.ex. frånvaro, eller ett tekniskt fel, t.ex. om avsändartypen är postmaster.

The **[!UICONTROL Error Reasons]** och **[!UICONTROL Exclude Reasons]** Med diagram och tabeller kan du se vilka fel och undantag som inträffade under sändningsprocessen.

The **[!UICONTROL Email - Best recipient domain]** diagram och tabeller visar vilka domäner som är de mest använda av mottagarna för att öppna e-postmeddelandet.
+++

## Fliken I appen {#inapp-live}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_inapp_performance"
>title="Prestanda i appen"
>abstract="KPI:erna för prestanda i appen ger viktiga insikter i besökarnas engagemang med meddelanden i appen de senaste 24 timmarna."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_inapp_interactions"
>title="Interaktioner per typ"
>abstract="Interaktionen per typ av diagram och tabell visar hur användarna interagerade med meddelandet i appen genom att spåra varje klick, avbruten eller interaktion de senaste 24 timmarna."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_inapp_summary"
>title="Sammanfattning i appen"
>abstract="I sammanfattningsdiagrammet i appen visas utvecklingen av dina visningar och interaktioner i appen under de senaste 24 timmarna."

Från er kampanj **[!UICONTROL Live report]**, **[!UICONTROL In-app]** -fliken innehåller information om huvudinformationen i förhållande till de meddelanden i appen som skickas i kampanjen.

+++Läs mer om de olika mätvärden och widgetar som är tillgängliga för rapporten i appen.

The **[!UICONTROL In-app performance]** Nyckeltal anger den viktigaste informationen i relation till besökarnas engagemang i era meddelanden i appen, som:

* **[!UICONTROL Impressions]**: totalt antal meddelanden i appen som skickats till alla användare.

* **[!UICONTROL Interactions]**: totalt antal ärenden för meddelandet i appen. Detta inkluderar alla åtgärder som användaren utför, t.ex. klickningar, uppsägningar eller annan interaktion.

The **[!UICONTROL In-app summary]** diagram visar utvecklingen av dina visningar och interaktioner i appen för den aktuella perioden.

The **[!UICONTROL Interactions by type]** diagram och tabeller visar hur användare interagerade med meddelanden i appen genom att spåra varje klick, avgång eller interaktion.

+++

## Fliken Push-meddelanden {#push-live}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_push_sending_performance"
>title="Push-meddelande - Sändande prestanda"
>abstract="Prestandadiagrammet för push-meddelandesändning sammanfattar viktiga data om ditt push-meddelande, till exempel fel eller levererade meddelanden från de senaste 24 timmarna."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_push_statistics"
>title="Push-meddelande - statistik"
>abstract="Tabellen Push-statistik innehåller data om mottagaraktivitet för ditt push-meddelande från de senaste 24 timmarna."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_push_sending_summary"
>title="Push-meddelande - Skickar sammanfattning"
>abstract="I diagrammet Översikt över sändning av push-meddelanden visas tillgängliga data för skickade push-meddelanden från de senaste 24 timmarna."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_push_excluded_reasons"
>title="Push-meddelande - Undantagna orsaker"
>abstract="I diagrammen och tabellen Exkluderade orsaker visas de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen och inte fick meddelandet under de senaste 24 timmarna."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_push_error_reasons"
>title="Push-meddelande - felorsaker"
>abstract="Med diagrammen och tabellen Felorsaker kan du identifiera de specifika fel som inträffade de senaste 24 timmarna under sändningsprocessen."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_push_breakdown_platform"
>title="Push-meddelande - uppdelning efter plattform"
>abstract="Diagram och tabell över uppdelningar per plattform visar hur väl push-meddelandena lyckades under de senaste 24 timmarna baserat på mottagarens operativsystem."

Från er kampanj **[!UICONTROL Live report]**, **[!UICONTROL Push notification]** -fliken anger huvudinformationen i förhållande till push-meddelandet som skickas i kampanjen.

![](assets/campaign_report_live_2.png)

+++Läs mer om de olika mätvärden och widgetar som är tillgängliga för rapporten Push.

**[!UICONTROL Push notification sending performance]**, **[!UICONTROL Push notification summary]** och **[!UICONTROL Push notification - Statistics]** widgetar anger huvudinformationen i förhållande till ditt meddelande:

* **[!UICONTROL Sent]**: Totalt antal överföringar.

* **[!UICONTROL Delivered]**: Antal meddelanden som skickats.

* **[!UICONTROL Bounces]**: Totalt antal fel som ackumulerats under sändningsprocessen och automatisk returbearbetning.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

* **[!UICONTROL Opens]**: Antal gånger ett meddelande öppnades.

* **[!UICONTROL Actions]**: Totalt antal åtgärder för push-meddelandet som levererats, t.ex. knappklickning eller avvisning.

* **[!UICONTROL Engagements]**: Totalt antal öppningar och åtgärder för detta push-meddelande, dvs. om profilen öppnade push-meddelandet eller om någon klickade på en knapp.

The **[!UICONTROL Error Reasons]** och **[!UICONTROL Exclude Reasons]** Med diagram och tabeller kan du se vilka fel och undantag som inträffade under sändningsprocessen.

The **[!UICONTROL Sending statistics - Failed]** kan du se hur många fel och studsar som har inträffat.

The **[!UICONTROL Tracking by platform]**, **[!UICONTROL Sending by platform]** och **[!UICONTROL Breakdown by platform]** diagram och tabeller visar hur bra push-meddelandena är beroende på vilket operativsystem som används.
+++

## fliken SMS {#sms-live}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_sms_statistics"
>title="SMS - statistik"
>abstract="Registret SMS Sending Statistics sammanfattar viktiga data om dina SMS-meddelanden som riktade eller levererade meddelanden från de senaste 24 timmarna."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_sms_performance"
>title="SMS - Prestanda per datum"
>abstract="Widgeten SMS Performance by Date (SMS-prestanda efter datum) innehåller viktig information om dina meddelanden under de senaste 24 timmarna via en grafisk representation."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_sms_error_reasons"
>title="SMS - Felorsaker"
>abstract="Med hjälp av diagram och tabeller för felorsaker kan du identifiera de specifika fel som uppstått under de senaste 24 timmarna under sändningsprocessen."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_sms_excluded_reasons"
>title="SMS - Undantagna orsaker"
>abstract="I diagrammen och tabellen Exkluderade orsaker visas de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen och inte fick meddelandet under de senaste 24 timmarna."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_sms_bounces_reasons"
>title="SMS - studsar orsaker"
>abstract="Diagram och tabell över studentorsaker innehåller tillgängliga data från de senaste 24 timmarna för studsade meddelanden."

Från er kampanj **[!UICONTROL Live report]**, **[!UICONTROL SMS]** -fliken innehåller huvudinformationen om SMS-meddelandet som skickas i kampanjen.

![](assets/campaign_report_live_3.png)

+++Läs mer om de olika mätvärden och widgetar som är tillgängliga för SMS-rapporten.

The **[!UICONTROL SMS - Statistics]** tabellen visar hur ditt SMS lyckades:

* **[!UICONTROL Targeted]**: Antal användarprofiler som kvalificerar sig som målprofiler.

* **[!UICONTROL Excluded]**: Antal användarprofiler, exkluderade från målprofilerna, som inte fick meddelandet.

* **[!UICONTROL Sent]**: Totalt antal överföringar.

* **[!UICONTROL Bounces]**: Totalt antal fel som ackumulerats under sändningsprocessen och automatisk returbearbetning.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

* **[!UICONTROL Clicks]**: Totalt antal URL-besök.

The **[!UICONTROL SMS Performance by date]** widgeten visar huvudinformationen i förhållande till meddelandet med ett diagram:

* **[!UICONTROL Sent]**: Totalt antal överföringar.

* **[!UICONTROL Bounces]**: Totalt antal fel som ackumulerats under sändningsprocessen och automatisk returbearbetning.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

The **[!UICONTROL Exclude Reasons]**, **[!UICONTROL Bounces Reasons]** och **[!UICONTROL Error Reasons]** Med diagram och tabeller kan du se vilka fel och undantag som inträffade under sändningsprocessen.
+++

## Fliken Webb {#web-tab}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_web_performance"
>title="Webbprestanda"
>abstract="KPI:erna för Web Performance ger omfattande information om besökarnas engagemang med dina webbupplevelser de senaste 24 timmarna."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_web_summary"
>title="Webbsammanfattning"
>abstract="I webbsammanfattningsdiagrammet visas hur webbupplevelserna har utvecklats, inklusive visningar, unika intryck och interaktioner från de senaste 24 timmarna."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_web_interactions"
>title="Interaktioner per element"
>abstract="Tabellen Interaktioner per element innehåller viktig information om besökarnas engagemang med olika element på webbsidorna de senaste 24 timmarna."

Från er kampanj **[!UICONTROL Live report]**, **[!UICONTROL Web]** -fliken anger huvudinformationen för dina webbsidor.

+++Läs mer om de olika mätvärden och widgetar som finns för webbrapporten.

The **[!UICONTROL Web performance]** Nyckeltal anger den viktigaste informationen i relation till besökarnas engagemang i era webbupplevelser, till exempel:

* **[!UICONTROL Impressions]**: totalt antal webbupplevelser som levereras till alla användare.

* **[!UICONTROL Interactions]**: totalt antal interaktioner med din webbsida. Detta inkluderar alla åtgärder som användaren utför, t.ex. klickningar eller andra interaktioner.

The **[!UICONTROL Web summary]** diagram visar hur webbupplevelserna har utvecklats (intryck, unika intryck och interaktioner) de senaste 24 timmarna.

The **[!UICONTROL Interactions by element]** tabellen innehåller huvudinformationen om besökarnas engagemang för de olika elementen på webbsidorna.
+++

## Fliken Direktreklam {#direct-mail-tab}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_direct_sending_statistics"
>title="Direktreklam - skicka statistik"
>abstract="Registret Skicka direkt e-post - statistik sammanfattar viktiga data från de senaste 24 timmarna om dina Direct-e-postmeddelanden, som riktade eller levererade meddelanden."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_direct_error_reasons"
>title="Direktreklam - felorsaker"
>abstract="Med diagrammen och tabellen Direktreklam - Felorsaker kan du identifiera de specifika fel som har uppstått under de senaste 24 timmarna."

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_direct_excluded_reasons"
>title="Direktreklam - orsaker som inte ingår"
>abstract="Diagram och tabell över orsaker till varför direktreklam exkluderades visar de olika faktorer som ledde till användarprofiler, som uteslöts från målgruppen och inte fick meddelandet de senaste 24 timmarna."

Från er kampanj **[!UICONTROL Live report]**, **[!UICONTROL Direct mail]** -fliken anger huvudinformationen i förhållande till din Direct-post.

![](assets/direct-mail-report_2.png)

+++Läs mer om de olika mätvärden och widgetar som finns för rapporten Direct mail.

The **[!UICONTROL Direct Mail - Sending statistics]** tabellen visar hur bra ditt Direct-postmeddelande är:

* **[!UICONTROL Targeted]**: Antal användarprofiler som kvalificerar sig som målprofiler.

* **[!UICONTROL Sent]**: Totalt antal överföringar.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

* **[!UICONTROL Excluded]**: Antal användarprofiler, exkluderade från målprofilerna, som inte fick ditt direktutskick.

The **[!UICONTROL Direct Mail - Excluded reasons]** och **[!UICONTROL Direct Mail - Error reasons]** Med diagram och tabeller kan du se vilka fel och undantag som inträffade under sändningsprocessen.
+++

## Ytterligare resurser

* [Kom igång med kampanjer](../campaigns/get-started-with-campaigns.md)
* [Skapa en kampanj](../campaigns/create-campaign.md)
* [Skapa API-utlösta kampanjer](../campaigns/api-triggered-campaigns.md)
* [Ändra eller stoppa en kampanj](../campaigns/modify-stop-campaign.md)
* [Global kampanjrapport](campaign-global-report.md)
