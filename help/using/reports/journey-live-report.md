---
solution: Journey Optimizer
product: journey optimizer
title: Rapport om livesändning på resa
description: Lär dig använda data från reserapporten
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: e3781f79-7c8d-4512-b44f-835639b1471f
source-git-commit: fa704bd6c82a3068f163bb74542107b34f1815d1
workflow-type: tm+mt
source-wordcount: '2647'
ht-degree: 0%

---

# Rapport om livesändning på resa {#journey-live-report}

>[!CONTEXTUALHELP]
>id="ajo_journey_live_report"
>title="Rapport om livesändning på resa"
>abstract="Med reserapporten kan ni i realtid mäta och visualisera påverkan och resultat av era resor bara under de senaste 24 timmarna. Din rapport är uppdelad i olika widgetar som detaljerar hur framgångsrik och felfri din resa är. Varje rapportkontrollpanel kan ändras genom att widgetar storleksändras eller tas bort."

Live-rapporter, som du kommer åt från fliken Senaste 24 timmarna, visar händelser som har inträffat under de senaste 24 timmarna, med ett tidsintervall på minst två minuter från händelseförekomsten. Som jämförelse fokuserar Global-rapporter på händelser som inträffade för minst två timmar sedan och täcker händelser under en vald tidsperiod.

Du kan få åtkomst till liverapporten från din resa med **[!UICONTROL View report]** -knappen.

![](assets/report_journey.png)

Resan **[!UICONTROL Live report]** visas med följande flikar:

* [Resa](#journey-live)
* [E-post](#email-live)
* [Push](#push-live)
* [SMS](#sms-live)
* [I appen](#in-app-live)

Resan **[!UICONTROL Live report]** är uppdelat i olika widgetar som detaljerat beskriver hur framgångsrik och felfri din resa är. Varje widget kan storleksändras och tas bort vid behov. Mer information finns i [section](live-report.md#modify-dashboard).

En detaljerad lista över alla mätvärden som är tillgängliga i Adobe Journey Optimizer finns på [den här sidan](live-report.md#list-of-components-live).

## Fliken Resor {#journey-live}

Från din resa **[!UICONTROL Live report]**, **[!UICONTROL Journey]** -fliken ger en tydlig bild av de viktigaste spårningsdata som rör kundresan.

### Resans resultat {#journey-performance}

>[!CONTEXTUALHELP]
>id="ajo_journey_performance_live"
>title="Resans resultat"
>abstract="XX"

![](assets/journey_live_performance.png)

**[!UICONTROL Journey Performance]** gör att du kan se vägen för dina målprofiler steg för steg under hela kundresan.

### Resestatistik {#journey-statistics}

>[!CONTEXTUALHELP]
>id="ajo_journey_statistics_live"
>title="Resestatistik"
>abstract="XX"

![](assets/journey_live_statistics.png)

The **[!UICONTROL Journey Statistics]** KPI (Key Performance Indicators) fungerar som en heltäckande kontrollpanel som levererar en analys av viktig statistik som är kopplad till din resa under de senaste 24 timmarna. Detta omfattar detaljer som antalet inskrivna profiler och förekomster av misslyckade enskilda resor, vilket ger en heltäckande insikt i hur effektiv resan är och hur hög engagemanget är.

+++ Läs mer om statistik från Journey

* **[!UICONTROL Entered profiles]**: Totalt antal personer som har nått ingångshändelsen för resan.

* **[!UICONTROL Exited profiles]**: Totalt antal personer som avbrutit resan.

* **[!UICONTROL Failed individual journeys]**: Totalt antal enskilda resor som inte slutfördes.
+++

### Åtgärd utförd de senaste 24 timmarna {#action-executed}

>[!CONTEXTUALHELP]
>id="ajo_journey_actions_executed_live"
>title="Åtgärd utförd de senaste 24 timmarna"
>abstract="XX"

![](assets/journey_live_executed_24hours.png)

The **[!UICONTROL Action executed over the last 24 hours]** widgeten är den mest framgångsrika åtgärden som inträffade när dina åtgärder utlöstes.

+++ Läs mer om hur du använder Action under de senaste 24 timmarna

* **[!UICONTROL Actions executed]**: Totalt antal genomförda åtgärder för en resa.

* **[!UICONTROL Error in actions]**: Totalt antal fel som inträffat för åtgärder.

+++

### Körda åtgärder och fel {#actions-errors}

>[!CONTEXTUALHELP]
>id="ajo_journey_actions_executed__errors_live"
>title="Körda åtgärder och fel"
>abstract="XX"

![](assets/journey_live_actions_errors.png)

The **[!UICONTROL Actions executed and errors]** -widgeten är den mest framgångsrika åtgärden och de fel som inträffade när dina åtgärder utlöstes.

+++ Läs mer om utförda åtgärder och felmått

* **[!UICONTROL Actions executed]**: Totalt antal genomförda åtgärder för en resa.

* **[!UICONTROL Error in actions]**: Totalt antal fel som inträffat för åtgärder.

+++

### Orsaker till funktionsfel {#actions-error-reasons}

>[!CONTEXTUALHELP]
>id="ajo_journey_actions_errors_live"
>title="Orsaker till funktionsfel"
>abstract="XX"

![](assets/journey_live_error_reasons.png)

The **[!UICONTROL Action error reasons]** tabell och diagram innehåller en omfattande översikt över fel som inträffat under utförandet av dina åtgärder under de senaste 24 timmarna.

### Feltyp efter åtgärder {#error-type-actions}

>[!CONTEXTUALHELP]
>id="ajo_journey_actions_error_type_live"
>title="Feltyp efter åtgärder"
>abstract="XX"

![](assets/journey_live_error_type.png)

The **[!UICONTROL Error type by actions]** tabellen och diagrammet innehåller en omfattande översikt över de fel som inträffat under de senaste 24 timmarna.

### Händelse som har utförts under de senaste 24 timmarna {#event-executed-24hours}

>[!CONTEXTUALHELP]
>id="ajo_journey_event_24hours_live"
>title="Händelse som har utförts under de senaste 24 timmarna"
>abstract="XX"

![](assets/journey_live_event_24hours.png)

The **[!UICONTROL Event executed over the last 24 hours]** Med kan du identifiera vilka av dina händelser som har slutförts under de senaste 24 timmarna.

### Händelser {#events}

>[!CONTEXTUALHELP]
>id="ajo_journey_events_live"
>title="Händelser"
>abstract="XX"

![](assets/journey_live_events.png)

The **[!UICONTROL Events]** kan du se vilken av dina händelser som utfördes genom sammanfattningsnummer, diagram och tabell.

### Händelser efter ursprung {#events-origin}

>[!CONTEXTUALHELP]
>id="ajo_journey_events_origin_live"
>title="Händelser efter ursprung"
>abstract="XX"

![](assets/journey_events_origin.png)

The **[!UICONTROL Events by origin]** tabell och diagram ger ett detaljerat perspektiv på hur dina händelser tagits emot under de senaste 24 timmarna. Genom dessa visuella representationer kan ni ta reda på exakt vilka av era evenemang som har tagits emot effektivt och ge värdefulla insikter om hur enskilda händelser under resan fungerar och påverkas.

## Fliken E-post {#email-live}

Från din resa **[!UICONTROL Live report]**, **[!UICONTROL Email]** fliken innehåller huvudinformationen om de e-postmeddelanden som skickas under din resa.

### E-post - Sändande prestanda {#email-sending-performance}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_sending_performance_live"
>title="E-post - Sändande prestanda"
>abstract="XX"

![](assets/journey_live_email_performance.png)

The **[!UICONTROL Email - Sending performance]** diagram ger en heltäckande bild av data som rör skickade e-postmeddelanden under resan, och ger insikter i viktiga mätvärden som levererade och studsar som har hänt under de senaste 24 timmarna. Detta möjliggör en detaljerad analys av e-postsändningsprocessen och ger värdefull information om hur effektiva och effektiva era resor är.

+++ Läs mer om e-post - Sändande prestandamått

* **[!UICONTROL Delivered]**: Antal skickade e-postmeddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som ackumulerats under sändningsprocessen och automatisk returbearbetning.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

* **[!UICONTROL Retries]**: Antal e-postmeddelanden i kön för återförsök.

+++

### E-post - statistik {#email-stat}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_statistics_live"
>title="E-post - statistik"
>abstract="XX"

![](assets/journey_live_email_statistics.png)

The **[!UICONTROL Email - Statistics]** tabellen innehåller en omfattande sammanfattning av viktiga uppgifter om e-post under de senaste 24 timmarna. Den innehåller viktiga mätvärden som målgruppens storlek och antalet e-postmeddelanden som levererats, och ger värdefulla insikter om hur effektiva och omfattande era e-postmeddelanden och resor är.

+++ Läs mer om statistik för e-postsändning

* **[!UICONTROL Targeted]**: Totalt antal meddelanden som bearbetats under sändningsprocessen.

* **[!UICONTROL Excluded]**: Antal profiler som har uteslutits av Adobe Journey Optimizer.

* **[!UICONTROL Sent]**: Totalt antal skickade e-postmeddelanden.

* **[!UICONTROL Delivered]**: Antal e-postmeddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

* **[!UICONTROL Opens]**: Antal gånger som dina e-postmeddelanden öppnats.

* **[!UICONTROL Clicks]**: Antal gånger ett innehåll klickades i e-postmeddelanden.

* **[!UICONTROL Unsubscribe]**: Antal klick på länken för att avbryta prenumerationen.

* **[!UICONTROL Spam complaints]**: Antal gånger ett meddelande har deklarerats som skräppost eller skräppost.

* **[!UICONTROL Retries]**: Antal e-postmeddelanden i kön för återförsök.

+++

### E-post - Prestanda efter datum {#email-perf-date}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_performance_bydate_live"
>title="E-post - Prestanda efter datum"
>abstract="XX"

![](assets/journey_live_email_performance_date.png)

The **[!UICONTROL Email - Performance by date]** widgeten ger en detaljerad översikt över viktig information om dina e-postmeddelanden, som presenteras i ett diagram, och ger insikter om prestandatrender under de senaste 24 timmarna.

+++ Läs mer om e-post - prestanda efter datummått

* **[!UICONTROL Sent]**: Totalt antal skickade e-postmeddelanden.

* **[!UICONTROL Delivered]**: Antal skickade e-postmeddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som ackumulerats under sändningsprocessen och automatisk returbearbetning.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

* **[!UICONTROL Opens]**: Antal gånger som dina e-postmeddelanden öppnats.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina e-postmeddelanden.

* **[!UICONTROL Unsubscribe]**: Antal klick på länken för att avbryta prenumerationen.

* **[!UICONTROL Spam complaints]**: Antal gånger ett meddelande har deklarerats som skräppost eller skräppost.

+++

### E-post - studskategorier och orsaker {#email-bounce-categories}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_bounces_live"
>title="E-post - studskategorier och orsaker"
>abstract="XX"

![](assets/journey_live_email_bounce.png)

The **[!UICONTROL Bounce Reasons]** och **[!UICONTROL Bounce categories]** widgetar sammanställer tillgängliga data för studsade meddelanden och ger detaljerade insikter om de specifika orsakerna och kategorierna bakom e-poststudenterna de senaste 24 timmarna.

Mer information om studsar finns i [Undertryckningslista](../reports/suppression-list.md) sida.

+++ Läs mer om e-post - studskategorier och anledningsstatistik

* **[!UICONTROL Hard bounce]**: Det totala antalet permanenta fel, t.ex. fel e-postadress. Detta inbegriper ett felmeddelande som uttryckligen anger att adressen är ogiltig, till exempel Okänd användare.

* **[!UICONTROL Soft bounce]**: Det totala antalet tillfälliga fel, till exempel en fullständig inkorg.

* **[!UICONTROL Ignored]**: Det totala antalet tillfälliga, t.ex. frånvaro, eller ett tekniskt fel, t.ex. om avsändartypen är postmaster.

+++

### E-post - felorsaker {#email-error-reasons}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_errors_live"
>title="E-post - felorsaker"
>abstract="XX"

![](assets/journey_live_email_error_reasons.png)

The **[!UICONTROL Error Reasons]** diagram och tabeller ger synlighet i de specifika fel som uppstått under sändningsprocessen de senaste 24 timmarna, vilket ger värdefull information om felens art och förekomst.

### E-post - orsaker som inte tas med {#email-excluded}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_excluded_live"
>title="E-post - orsaker som inte tas med"
>abstract="XX"

![](assets/journey_live_email_excluded.png)

The **[!UICONTROL Excluded Reasons]** diagram och tabeller ger en heltäckande bild av de olika faktorer som har lett till att användarprofiler har tagits bort från målgruppen, vilket har lett till att meddelandet inte har tagits emot under de senaste 24 timmarna.

Se [den här sidan](exclusion-list.md) En fullständig förteckning över orsaker till uteslutning.

### E-post - Bästa mottagardomän {#email-best-recipient}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_best_recipient_live"
>title="E-post - Bästa mottagardomän"
>abstract="XX"

![](assets/journey_live_email_best_recipient.png)

The **[!UICONTROL Email - Best recipient domain]** diagram och tabeller ger en detaljerad beskrivning av de domäner som oftast används för att öppna e-postmeddelanden de senaste 24 timmarna. Detta ger värdefulla insikter om profilbeteendet och hjälper er att förstå vilka plattformar ni föredrar.

### E-posterbjudanden {#email-offers}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_offers_live"
>title="E-post - erbjudanden"
>abstract="XX"

>[!NOTE]
>
>Widgetarna och mätvärdena för erbjudanden är bara tillgängliga om ett beslut har infogats i ett e-postmeddelande. Mer information om beslutsförvaltning finns i denna [page](../offers/get-started/starting-offer-decisioning.md).

The **[!UICONTROL Offers statistic]** och **[!UICONTROL Offers statistics over time]** widgetar mäter hur väl erbjudandet har lyckats och vilken effekt det har på er målgrupp. Den innehåller detaljerad huvudinformation om meddelandet med KPI:er.

+++ Läs mer om e-post - ger statistik

* **[!UICONTROL Offer sent]**: Totalt antal utskick för erbjudandet.

* **[!UICONTROL Offer impression]**: Antal gånger som erbjudandet öppnades i e-postmeddelanden.

* **[!UICONTROL Offer clicks]**: Antal gånger ett erbjudande klickades på i dina e-postmeddelanden.

+++

### E-post - optimering {#email-sto}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_optimization_live"
>title="E-post - optimering"
>abstract="XX"

![](assets/journey_email_sto.png)

>[!NOTE]
>
>The **[!UICONTROL Send time optimization]** och **[!UICONTROL Optimized vs non optimized]** widgetar är bara tillgängliga om alternativet för optimering av sändningstid är aktiverat för leverans. Mer information om optimering av sändningstid finns i [den här sidan](../building-journeys/journeys-message.md#send-time-optimization).

The **[!UICONTROL Send time optimization]** och **[!UICONTROL Optimized vs non optimized]** widgetar visar hur bra dina e-postmeddelanden är beroende på sändningsmetod: optimerad eller normal.

+++ Läs mer om optimering av sändningstid och optimerade jämfört med icke-optimerade mätvärden

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.
* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Sent]**: Totalt antal e-postmeddelanden som skickats för resan.

* **[!UICONTROL Opens]**: Antal gånger som dina e-postmeddelanden öppnats under resan.

* **[!UICONTROL Clicks]**: Antal gånger ett innehåll klickades i e-postmeddelanden.

+++

## Fliken Push-meddelanden {#push-live}

Från din resa **[!UICONTROL Live report]**, **[!UICONTROL Push notification]** fliken innehåller huvudinformationen i förhållande till det push-meddelande som skickas under din resa.

### Push-meddelande - Sändande prestanda {#push-sending-performance}

>[!CONTEXTUALHELP]
>id="ajo_journey_push_sending_performance_live"
>title="Push-meddelande - Sändande prestanda"
>abstract="Prestandadiagrammet för push-meddelandesändning sammanfattar viktiga data om ditt push-meddelande, till exempel fel eller levererade meddelanden från de senaste 24 timmarna."

![](assets/campain_push_live_sending_performance.png)

The **[!UICONTROL Push notification sending performance]** diagrammet ger en grundlig översikt över data som rör push-meddelanden som skickats de senaste 24 timmarna. Den ger insikter i viktiga mätvärden som levererade och studsade, vilket möjliggör en detaljerad granskning av sändningsprocessen för push-meddelanden.

+++ Läs mer om push-meddelanden - Skicka prestandamått

* **[!UICONTROL Delivered]**: Antal meddelanden som skickats.

* **[!UICONTROL Bounces]**: Totalt antal fel som ackumulerats under sändningsprocessen och automatisk returbearbetning.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

+++

### Push-meddelande - statistik {#push-statistics}

>[!CONTEXTUALHELP]
>id="ajo_journey_push_statistics_live"
>title="Push-meddelande - statistik"
>abstract="XX"

![](assets/journey_live_push_statistics.png)

**[!UICONTROL Push notification - Statistics]** tabellen ger en kortfattad sammanfattning av viktiga data relaterade till dina push-meddelanden, inklusive nyckeltal som antalet riktade meddelanden och antalet lyckade meddelanden under de senaste 24 timmarna.

+++ Läs mer om push-meddelanden - statistik

* **[!UICONTROL Targeted]**: Antal profiler som ska användas för åtgärder som att skicka e-post eller SMS.

* **[!UICONTROL Excluded]**: Antal profiler som har uteslutits av Adobe Journey Optimizer.

* **[!UICONTROL Sent]**: Totalt antal skickade push-meddelanden.

* **[!UICONTROL Delivered]**: Antal push-meddelanden som har skickats.

* **[!UICONTROL Bounces]**: Totalt antal fel som ackumulerats under sändningsprocessen och automatisk returbearbetning.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

* **[!UICONTROL Opens]**: Antal gånger ditt push-meddelande öppnades.
+++

### Push-meddelande - uppdelning efter plattform {#push-breakdown}

>[!CONTEXTUALHELP]
>id="ajo_journey_push_breakdown_live"
>title="Push-meddelande - uppdelning efter plattform"
>abstract="XX"

![](assets/journey_push_breakdown.png)

The **[!UICONTROL Push notification - Breakdown by platform]** diagram och tabeller ger en detaljerad analys av hur väl push-meddelandena fungerar och ger insikter baserat på din profils operativsystem. Den här nedbrytningen ger en bättre förståelse för hur bra dina push-meddelanden fungerar på olika plattformar.

### Push-meddelande - Skickar sammanfattning {#push-sending-summary}

>[!CONTEXTUALHELP]
>id="ajo_journey_push_sending_summary_live"
>title="Push-meddelande - Skickar sammanfattning"
>abstract="XX"

![](assets/journey_live_push_sending.png)

The **[!UICONTROL Push notification summary]** graph erbjuder en dynamisk representation som visar en analys av din push-meddelandeaktivitet under de senaste 24 timmarna. Denna grafiska representation ger en omfattande beskrivning av skickade push-meddelanden.

+++ Läs mer om push-meddelanden - Skicka sammanfattningsmått

* **[!UICONTROL Sent]**: Totalt antal skickade push-meddelanden.

* **[!UICONTROL Delivered]**: Antal push-meddelanden som har skickats.

* **[!UICONTROL Bounces]**: Totalt antal fel som ackumulerats under sändningsprocessen och automatisk returbearbetning.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

* **[!UICONTROL Opens]**: Antal gånger dina push-meddelanden har öppnats.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina push-meddelanden.

+++

### Push-meddelande - felorsaker {#push-error}

>[!CONTEXTUALHELP]
>id="ajo_journey_push_error_reasons_live"
>title="Push-meddelande - felorsaker"
>abstract="XX"

![](assets/journey_live_push_error.png)

The **[!UICONTROL Error Reasons]** Med tabeller och diagram kan du identifiera de specifika fel som uppstod under sändningsprocessen för dina push-meddelanden och få detaljerade insikter om eventuella problem som uppstått under de senaste 24 timmarna.

### Push-meddelande - Undantagna orsaker {#push-excluded}

>[!CONTEXTUALHELP]
>id="ajo_journey_push_excluded_reasons_live"
>title="Push-meddelande - Undantagna orsaker"
>abstract="XX"

![](assets/journey_live_push_excluded.png)

The **[!UICONTROL Excluded Reasons]** I diagram och tabeller visas de olika anledningar som gjorde att användarprofiler som inte ingår i målprofilerna inte kunde ta emot push-meddelanden inom de senaste 24 timmarna.

Se [den här sidan](exclusion-list.md) En fullständig förteckning över orsaker till uteslutning.

## fliken SMS {#sms-live}

### SMS - statistik {#sms-statistics}

>[!CONTEXTUALHELP]
>id="ajo_journey_sms_statistics_live"
>title="SMS - statistik"
>abstract="XX"

![](assets/journey_live_sms_statistics.png)

The **[!UICONTROL SMS - Statistics]** tabellen ger en kortfattad sammanfattning av viktiga data relaterade till dina SMS-meddelanden, med nyckelmått som antalet riktade meddelanden och antalet lyckade meddelanden som levererats under de senaste 24 timmarna.

+++ Läs mer om SMS - statistik

* **[!UICONTROL Targeted]**: Antal användarprofiler som kvalificerar sig som målprofiler.

* **[!UICONTROL Excluded]**: Antal användarprofiler, exkluderade från målprofilerna, som inte fick meddelandet.

* **[!UICONTROL Sent]**: Totalt antal skickade SMS-meddelanden.

* **[!UICONTROL Opens]**: Antal gånger dina SMS-meddelanden öppnades.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i SMS-meddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

+++

### SMS - Prestanda per datum {#sms-performance}

>[!CONTEXTUALHELP]
>id="ajo_journey_sms_performance_live"
>title="SMS - Prestanda per datum"
>abstract="XX"

![](assets/journey_live_sms_performance.png)

The **[!UICONTROL SMS - Performance by date]** widgeten ger en detaljerad översikt över viktig information om dina meddelanden, som presenteras i ett diagram, och ger insikter om prestandatrender under de senaste 24 timmarna.

+++ Läs mer om SMS - Prestanda efter datummått

* **[!UICONTROL Sent]**: Totalt antal skickade SMS-meddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som ackumulerats under sändningsprocessen och automatisk returbearbetning.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

+++

### SMS - studsar orsaker {#sms-bounces}

>[!CONTEXTUALHELP]
>id="ajo_journey_sms_bounces_live"
>title="SMS - studsar orsaker"
>abstract="XX"

![](assets/journey_sms_bounce_reasons.png)

The **[!UICONTROL SMS - Bounces reasons]** diagram och tabeller ger en omfattande översikt över data relaterade till studsade SMS-meddelanden och ger värdefulla insikter om de specifika orsakerna bakom instanserna av SMS-meddelandestudsar under de senaste 24 timmarna.

### SMS - Felorsaker {#sms-error}

>[!CONTEXTUALHELP]
>id="ajo_journey_sms_error_live"
>title="SMS - Felorsaker"
>abstract="XX"

![](assets/journey_sms_error.png)

The **[!UICONTROL SMS - Error Reasons]** Med diagram och tabeller kan du identifiera de specifika fel som uppstod under sändningsprocessen för SMS-meddelanden, vilket underlättar en grundlig analys av eventuella problem som uppstått under de senaste 24 timmarna.

### SMS - Undantagna orsaker {#sms-excluded}

>[!CONTEXTUALHELP]
>id="ajo_journey_sms_excluded_live"
>title="SMS - Undantagna orsaker"
>abstract="XX"

![](assets/journey_live_sms_excluded.png)

The **[!UICONTROL SMS - Excluded Reasons]** grafer och tabeller visar visuellt de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen, vilket förhindrar dem från att ta emot SMS-meddelanden.

Se [den här sidan](exclusion-list.md) En fullständig förteckning över orsaker till uteslutning.

<!--
### SMS - Clicks by links {#sms-clicks}

![](assets/journey_sms_clicks.png)

The **[!UICONTROL SMS - Clicks by links]** widget offers essential insights into your visitors' engagement with the URLs included in your messages, providing valuable information about which links attract the most interaction within the last 24 hours.
-->

## Fliken I appen {#in-app-live}

### Prestanda i appen {#inapp-performance}

>[!CONTEXTUALHELP]
>id="ajo_journey_inapp_performance_live"
>title="Prestanda i appen"
>abstract="XX"

![](assets/journey_live_inapp_performance.png)

The **[!UICONTROL In-app performance]** Nyckeltal ger viktiga insikter i era profilers interaktion med meddelanden i appen de senaste 24 timmarna, vilket ger viktiga mätvärden för att utvärdera effektiviteten och effekten av de meddelanden i appen som ingår i kundresan.

+++ Läs mer om prestandamått i appen

* **[!UICONTROL Impressions]**: totalt antal meddelanden i appen som levereras till alla användare.

  >[!NOTE]
  >
  >För att säkerställa att en Impression räknas måste användaren uppfylla två kriterier:
  >* Kvalificering i upplevelsen i appen, som uppnås genom att man når den specifika aktiviteten i appen under resan.
  >* Uppfyller villkoren som anges i utlösarreglerna.
  > 
  >På grund av det andra kriteriet kan det finnas betydande variationer mellan antalet riktade profiler och antalet unika visningar.

* **[!UICONTROL Interactions]**: totalt antal ärenden för meddelandet i appen. Detta inkluderar alla åtgärder som användaren utför, t.ex. klickningar, uppsägningar eller annan interaktion.

+++

### Sammanfattning i appen {#inapp-summary}

>[!CONTEXTUALHELP]
>id="ajo_journey_inapp_summary_live"
>title="Sammanfattning i appen"
>abstract="XX"

![](assets/journey_live_inapp_summary.png)

The **[!UICONTROL In-app summary]** I diagrammet visas utvecklingen av dina visningar och interaktioner i appen under de senaste 24 timmarna, vilket ger en omfattande översikt över hur dina meddelanden i appen fungerar.

+++ Läs mer om sammanfattningsstatistik i appar

* **[!UICONTROL Impressions]**: totalt antal meddelanden i appen som levereras till alla användare.

  >[!NOTE]
  >
  >För att säkerställa att en Impression räknas måste användaren uppfylla två kriterier:
  >* Kvalificering i upplevelsen i appen, som uppnås genom att man når den specifika aktiviteten i appen under resan.
  >* Uppfyller villkoren som anges i utlösarreglerna.
  > 
  >På grund av det andra kriteriet kan det finnas betydande variationer mellan antalet riktade profiler och antalet unika visningar.

* **[!UICONTROL Interactions]**: totalt antal ärenden för meddelandet i appen. Detta inkluderar alla åtgärder som användaren utför, t.ex. klickningar, uppsägningar eller annan interaktion.

+++

### Interaktioner per typ {#interactions-type}

>[!CONTEXTUALHELP]
>id="ajo_journey_inapp_interactions_live"
>title="Interaktioner per typ"
>abstract="XX"

![](assets/journey_live_inapp_interactions.png)

The **[!UICONTROL Interactions by type]** diagram och tabeller visar hur användarna interagerade med meddelandet i appen genom att spåra varje klickning, stängning eller interaktion.
