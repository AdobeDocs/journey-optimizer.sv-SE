---
solution: Journey Optimizer
product: journey optimizer
title: Global reserapport
description: Lär dig använda data från reserapporten
feature: Reporting, Journeys
topic: Content Management
role: User
level: Intermediate
badge: label="Begränsad tillgänglighet" type="Informative"
exl-id: d43ae701-6e3b-4dcf-8da1-11c07be10fcf
source-git-commit: b80d794f3782056a10310c65144a8eecbddaaf3e
workflow-type: tm+mt
source-wordcount: '3821'
ht-degree: 0%

---

# Reserapport {#journey-global-report}

Resursrapporten **Journey** fungerar som en heltäckande kontrollpanel, som tillhandahåller en analys av viktig information som är kopplad till din resa. Detta omfattar detaljer som antalet inskrivna profiler och förekomster av misslyckade enskilda resor, vilket ger en heltäckande insikt i hur effektiv resan är och hur hög engagemanget är.

**Reserapporten** kan nås direkt från din resa med knappen **[!UICONTROL View report]** .

![](assets/gs-cja-report-3.png)

Sidan **[!UICONTROL Journey report]** visas med följande flikar beroende på vilka meddelandeaktiviteter som pågår under din resa:

* [Resa](#journey-global)
* [E-post](#email-global)
* [Push](#push-global)
* [SMS](#sms-global)
* [I appen](#in-app-global)
* [Webb](#web-cja)
* [Direktmeddelande](#direct-mail-cja)

Mer information om Customer Journey Analytics Workspace och hur du filtrerar och analyserar data finns på [den här sidan](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/home).

## Reseöversikt {#journey-global}

Rapporten **[!UICONTROL Journey]** ger dig en tydlig bild av de viktigaste spårningsdata som rör din resa.

### KPI:er för resan {#journey-perfomance}

![](assets/cja-journey-kpis.png)

**[!UICONTROL Journey]** KPI:er (Key Performance Indicators) fungerar som en heltäckande kontrollpanel, som tillhandahåller en analys av viktiga mått som är kopplade till din resa. Detta omfattar detaljer som antalet inskrivna profiler och förekomster av misslyckade enskilda resor, vilket ger en heltäckande insikt i hur effektiv resan är och hur hög engagemanget är.

+++ Läs mer om nyckeltal för resan

* **[!UICONTROL Journey engagement]**: Totalt antal personer som interagerat med meddelanden som skickats från resan

* **[!UICONTROL Journey enters]**: Totalt antal personer som har nått resans anmälningshändelse.

* **[!UICONTROL Journey exits]**: Totalt antal personer som avbrutit resan.

* **[!UICONTROL Journey failures]**: Totalt antal enskilda resor som inte kördes korrekt.

+++

### Resestatistik {#journey-stats}

![](assets/cja-journey-stats.png)

Tabellen **[!UICONTROL Journey Statistics]** innehåller en detaljerad sammanfattning av viktiga data om dina resor. Det innehåller viktiga mätvärden som antalet misslyckanden och lyckade tävlingsbidrag, som ger värdefulla insikter om hur väl era e-postmeddelanden och resor fungerar och når ut.

+++ Läs mer om statistik om resan

* **[!UICONTROL Journey engagement]**: Totalt antal personer som interagerat med meddelanden som skickats från resan.

* **[!UICONTROL Journey enters]**: Totalt antal personer som har nått resans anmälningshändelse.

* **[!UICONTROL Journey exits]**: Totalt antal personer som avbrutit resan.

* **[!UICONTROL Journey failures]**: Totalt antal enskilda resor som inte kördes korrekt.

* **[!UICONTROL Unique Journey enters]**: Totalt antal personer som har nått ingångshändelsen för resan, flera interaktioner för en profil beaktas inte.

* **[!UICONTROL Unique Journey exits]**: Totalt antal personer som avbrutit resan, flera interaktioner för en profil beaktas inte.

* **[!UICONTROL Unique Journey failures]**: Totalt antal enskilda resor som inte har utförts, flera interaktioner i en profil beaktas inte.

+++

## Reseduk {#journey-canvas}

![](assets/cja-journey-canvas.png)

Med widgeten **[!UICONTROL Journey Canvas]** kan du visuellt spåra sökvägen för dina målprofiler när de navigerar genom din resa.

Förbättra anpassningen av arbetsytan med följande alternativ:

* Lägg till eller ta bort önskad aktivitetstyp, till exempel meddelanden eller villkor, från den nedrullningsbara menyn **[!UICONTROL Node type]**.
* Justera **[!UICONTROL Percentage value]** för att fastställa flödesfördelningen mellan olika resevägar.
* Anpassa **[!UICONTROL Arrow settings]** så att den innehåller etiketter, villkor eller väljer en ren visning.
* Aktivera alternativet **[!UICONTROL Show fallout]** för att visualisera profiler som slutade din resa direkt på arbetsytan.

## Åtgärdens prestanda {#action-performance}

### Prestanda över tid {#action-overtime}

![](assets/cja-journey-action-performance.png)

I diagrammet **[!UICONTROL Performance Over time]** kan du identifiera och analysera antalet profiler som uppfyller kriterierna som ska betraktas som målprofiler för dina åtgärder. Denna visualisering ger värdefulla insikter om hur effektiva era strategier är och hjälper er att fatta datadrivna beslut för att optimera er prestanda.

### Åtgärdsöversikt {#action-overview}

![](assets/cja-journey-action-overview.png)

Tabellen **[!UICONTROL Action overview]** fungerar som en omfattande kontrollpanel som innehåller en analys av viktiga mått relaterade till åtgärderna under din resa. Detta inkluderar viktiga detaljer som antalet interaktioner och klickfrekvensen

+++ Läs mer om mätvärden i Åtgärdsöversikt

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina åtgärder.

* **[!UICONTROL Click trough rate]**: Procentandel användare som interagerade med åtgärden.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina åtgärder.

* **[!UICONTROL Delivered]**: Antal åtgärder som har skickats, i relation till det totala antalet skickade åtgärder.

+++

## Händelseprestanda {#events-performance}

### Prestanda över tid {#event-overtime}

![](assets/cja-journey-performance-event.png)

Med diagrammet **[!UICONTROL Performance over time]** kan du identifiera och analysera antalet profiler som kvalificerar som målprofiler för dina händelser. Detta kraftfulla verktyg hjälper er att spåra trender och mönster över tid och ger värdefulla insikter för att optimera era era händelsestrategier.

### Översikt över händelser {#event-overview}

![](assets/cja-journey-events-overview.png)

Tabellen **[!UICONTROL Event overview]** visar hur många profiler som uppfyller dina händelsevillkor över tid. Det här verktyget hjälper dig att identifiera mönster i kvalificeringsgrader för att förfina din händelsestrategi.

+++ Läs mer om statistik om resan

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina händelser.

+++

## E-postinformation {#email-global}

Från din reserapport anger fliken **[!UICONTROL Email]** huvudinformationen i förhållande till de e-postmeddelanden som skickas under din resa.

### Levererat kontra klicktrend {#delivered-click}

![](assets/cja-journey-email-delivered.png)

Diagrammet **[!UICONTROL Delivered vs Click trend]** innehåller en detaljerad analys av hur era profiler interagerar med era e-postmeddelanden och ger värdefulla insikter om hur olika domäner interagerar med ert innehåll.

+++ Läs mer om Levererat jämfört med Click-trendstatistik

* **[!UICONTROL Delivered]**: Antal e-postmeddelanden som har skickats, i relation till det totala antalet skickade e-postmeddelanden.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina e-postmeddelanden.

+++

### Leveransstatus {#delivery-status}

![](assets/cja-journey-email-delivery-stat.png)

I diagrammet **[!UICONTROL Delivery status]** kan du snabbt se hur dina e-postmeddelanden fungerar. Spåra viktiga mätvärden som leveranser och studsar, så att ni snabbt kan förstå hur effektiv e-postresan är.

+++ Läs mer om leveransstatusvärden

* **[!UICONTROL Delivered]**: Antal e-postmeddelanden som har skickats, i relation till det totala antalet skickade e-postmeddelanden.

* **[!UICONTROL Bounces for outbound channels]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Outbound errors]**: Totalt antal fel som uppstod under en sändningsprocess och som förhindrar att den skickas till profiler.

* **[!UICONTROL Excluded]**: Antal profiler som har undantagits av Adobe Journey Optimizer.

+++

### Skicka statistik {#email-sending-statistics}

![](assets/cja-journey-email-sending-stat.png)

Tabellen **[!UICONTROL Sending Statistics]** ger en tydlig bild av hur dina e-postmeddelanden fungerar på dina resor. Den håller koll på viktiga mätvärden som leveransfrekvenser och interaktioner och ger er värdefulla insikter för att optimera er e-poststrategi för bättre räckvidd och engagemang.

+++ Läs mer om Skicka statistik-statistik

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina meddelanden.

* **[!UICONTROL Targeted]**: Totalt antal e-postmeddelanden som bearbetats under sändningsprocessen.

* **[!UICONTROL Sends]**: Totalt antal skickade meddelanden för din e-post.

* **[!UICONTROL Delivered]**: Antal e-postmeddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Outbound Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

* **[!UICONTROL Outbound Exclusions]**: Antal profiler som har undantagits av Adobe Journey Optimizer.

+++


### E-post - Spårningsstatistik {#email-tracking}

![](assets/cja-journey-email-track-stat.png)

Tabellen **[!UICONTROL Email - Tracking statistics]** innehåller en detaljerad redovisning av profilaktivitet som rör e-postmeddelanden som ingår i din resa. Detta inkluderar mätvärden för öppningar, klick och andra relevanta interaktionsindikatorer, som ger en heltäckande bild av hur profiler interagerar med ert e-postinnehåll.

+++ Läs mer om statistik för spårning

* **[!UICONTROL Click through rate (CTR)]**: Procentandel användare som interagerade med e-postmeddelandet.

* **[!UICONTROL Click-through open rate (CTOR)]**: Antal gånger som e-postmeddelandet öppnades.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina e-postmeddelanden.

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickat på ett innehåll i ett e-postmeddelande.

* **[!UICONTROL Email Opens]**: Antal gånger som dina e-postmeddelanden öppnats under en resa.

* **[!UICONTROL Unique Email Opens]**: Procentandel öppnade e-postmeddelanden.

* **[!UICONTROL Spam complaints]**: Antal gånger ett meddelande har deklarerats som skräppost eller skräppost.

* **[!UICONTROL Unsubscribes]**: Antal klick på länken för att avbryta prenumerationen.

+++

### E-postdomäner {#email-domains}

![](assets/cja-journey-email-domain.png)

Tabellen **[!UICONTROL Email Domains]** innehåller en detaljerad beskrivning av e-postmeddelanden kategoriserade efter domän, vilket ger omfattande insikter om prestandamätningarna för dina e-postresor. Denna omfattande analys gör att ni kan förstå beteendet hos olika domäner som svar på ert e-postinnehåll.

+++ Läs mer om mätvärden för e-postdomäner

* **[!UICONTROL Sends]**: Totalt antal skickade meddelanden för din e-post.

* **[!UICONTROL Delivered]**: Antal e-postmeddelanden som har skickats, i relation till det totala antalet skickade e-postmeddelanden.

* **[!UICONTROL Email Opens]**: Antal gånger som dina e-postmeddelanden öppnats under en resa.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina e-postmeddelanden.

* **[!UICONTROL Bounces for outbound channels]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning i relation till totalt antal skickade e-postmeddelanden.

* **[!UICONTROL Outbound Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.
+++

### Spårade länketiketter {#track-link-label}

![](assets/cja-journey-tracked-link-labels.png)

Tabellen **[!UICONTROL Tracked link labels]** innehåller en omfattande översikt över länketiketterna i dina e-postmeddelanden, som visar vilka som genererar störst besökstrafik. Med den här funktionen kan du identifiera och prioritera de mest populära länkarna.

+++ Läs mer om mätvärden för spårade länketiketter

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickat på ett innehåll i ett e-postmeddelande.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina e-postmeddelanden.

+++

### URL för spårad länk {#track-link-url}

![](assets/cja-journey-tracked-link-urls.png)

Tabellen **[!UICONTROL Tracked link URLs]** innehåller en omfattande översikt över de URL:er i ditt e-postmeddelande som lockar den högsta besökstrafiken. På så sätt kan ni identifiera och prioritera de mest populära länkarna och öka er förståelse för hur proffsen interagerar med specifikt innehåll i era e-postmeddelanden.

+++ Läs mer om URL:er för spårade länkar

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickat på ett innehåll i ett e-postmeddelande.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina e-postmeddelanden.

* **[!UICONTROL Displays]**: Antal gånger som meddelandet öppnades.

* **[!UICONTROL Unique displays]**: Det antal gånger som meddelandet öppnades tas ingen hänsyn till flera interaktioner för en profil.

+++

### E-postämnen {#email-subject}

![](assets/cja-journey-email-subjects.png)

Tabellen **[!UICONTROL Email subjects]** innehåller en grundlig översikt över e-postämnen som har fått den högsta besökstrafiken. Den här resursen ger värdefulla insikter om målgruppsengagemangets dynamik.

+++ Läs mer om ämnesstatistik för e-post

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina e-postmeddelanden.

+++

### Brytningsorsaker {#email-bounce-reasons}

Tabellen **[!UICONTROL Bounce Reasons]** kompilerar tillgängliga data som är relaterade till studsade meddelanden och ger detaljerade insikter om de specifika orsakerna bakom e-poststudsar.

Mer information om studsar finns på sidan [Suppressionslista](../reports/suppression-list.md).

### Undantagna orsaker {#email-excluded}

Tabellen **[!UICONTROL Excluded reasons]** ger en heltäckande bild av de olika faktorer som har lett till att användarprofiler har exkluderats från målgruppen, vilket leder till att meddelandet inte tas emot.

Se [den här sidan](exclusion-list.md) för en utförlig lista över orsaker till undantag.

### Felorsaker {#email-errors}

Tabellen **[!UICONTROL Error Reasons]** ger synlighet för de specifika fel som uppstod under sändningsprocessen, vilket ger värdefull information om felens art och förekomst.

## Fliken Push-meddelanden {#push-global}

Från din reserapport anger fliken **[!UICONTROL Push notification]** huvudinformationen i förhållande till push-meddelanden som skickas under din resa.

## Push-meddelande {#push-notification}

### Skicka statistik {#sending-statistics-push}

![](assets/cja-campaign-push-sending-stat.png)

Tabellen **[!UICONTROL Sending Statistics]** hjälper dig att förstå hur push-meddelanden fungerar. Det innehåller viktiga mätvärden som leveransfrekvens och målgruppsstorlek som ger er värdefulla insikter om hur effektiva och omfattande era resor är.

+++ Läs mer om Skicka statistik-statistik

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina SMS-meddelanden.

* **[!UICONTROL Targeted]**: Totalt antal push-meddelanden som bearbetats under analysen.

* **[!UICONTROL Sends]**: Totalt antal skickade för push-meddelandet.

* **[!UICONTROL Delivered]**: Antal push-meddelanden som har skickats, i relation till det totala antalet skickade push-meddelanden.

* **[!UICONTROL Bounces for outbound channels]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning i relation till totalt antal push-meddelanden.

* **[!UICONTROL Outbound errors]**: Totalt antal fel som har inträffat som förhindrar att den skickas till profiler.

* **[!UICONTROL Outbound exclusions]**: Antal profiler som har undantagits av Adobe Journey Optimizer.

+++

### Spårningsstatistik {#tracking-statistics-push}

![](assets/cja-campaign-push-track-stat.png)

Tabellen **[!UICONTROL Tracking statistics]** erbjuder en detaljerad ögonblicksbild av profilaktivitet som är kopplad till dina push-meddelanden, vilket ger viktiga insikter om engagemang och push-meddelandenas effektivitet.

+++ Läs mer om statistik för spårning

* **[!UICONTROL Click through rate (CTR)]**: Procentandel användare som interagerade med push-meddelandet.

* **[!UICONTROL Clickthrough open rate (CTOR)]**: Antal gånger som push-meddelandet öppnades.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i ditt push-meddelande.

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickat på ett innehåll i ditt push-meddelande.

<!--
* **[!UICONTROL Push custom actions]**: 
-->
+++

### Spårade länketiketter {#track-link-label-push}

![](assets/cja-campaign-push-link-labels.png)

Tabellen **[!UICONTROL Tracked link labels]** innehåller en omfattande översikt över länketiketterna i dina push-meddelanden, som visar de som genererar den högsta besökstrafiken. Med den här funktionen kan du identifiera och prioritera de mest populära länkarna.

+++ Läs mer om mätvärden för spårade länketiketter

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickat på ett innehåll i dina push-meddelanden.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina push-meddelanden.

+++

### URL för spårad länk {#track-link-url-push}

![](assets/cja-campaign-push-link-urls.png)

Tabellen **[!UICONTROL Tracked link URLs]** innehåller en omfattande översikt över de URL:er i dina push-meddelanden som lockar den högsta besökstrafiken. På så sätt kan ni identifiera och prioritera de populäraste länkarna och öka er förståelse för hur proffsen interagerar med specifikt innehåll i era push-meddelanden.

+++ Läs mer om URL:er för spårade länkar

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickat på ett innehåll i dina push-meddelanden.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina push-meddelanden.

+++

### Brytningsorsaker {#bounce-reasons-push}

Tabellen **[!UICONTROL Bounces Reasons]** innehåller en omfattande översikt över data relaterade till studsade push-meddelanden, vilket ger värdefulla insikter om de specifika orsakerna bakom instanser av push-meddelanden.

### Felorsaker {#error-reasons-push}

I tabellen **[!UICONTROL Error Reasons]** kan du identifiera de specifika fel som uppstod under sändningsprocessen för dina push-meddelanden, vilket underlättar en grundlig analys av eventuella problem som uppstått.

### Undantagna orsaker {#exclude-reasons-push}

![](assets/cja-campaign-push-excluded.png)

Tabellen **[!UICONTROL Exclude Reasons]** visar de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen, vilket förhindrar dem från att ta emot push-meddelanden.

Se [den här sidan](exclusion-list.md) för en utförlig lista över orsaker till undantag.

## SMS {#sms}

### Levererat kontra klicktrend {#delivered-click-sms}

Diagrammet **[!UICONTROL Delivered vs Click trend]** innehåller en detaljerad analys av dina profilers engagemang i dina SMS-meddelanden och ger värdefulla insikter om hur olika domäner interagerar med ditt innehåll.

+++ Läs mer om Levererat jämfört med Click-trendstatistik

* **[!UICONTROL Delivered]**: Antal SMS-meddelanden som har skickats, i relation till totalt antal SMS-meddelanden.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina SMS-meddelanden.

+++

### Leveransstatus {#delivery-status-sms}

Tabellen **[!UICONTROL Delivery status]** innehåller en detaljerad beskrivning av profilaktiviteten som är relaterad till dina SMS-meddelanden. Detta inkluderar mätvärden för levererade data, klickningar och andra relevanta interaktionsindikatorer, som ger en heltäckande bild av hur profiler interagerar med ert SMS-innehåll.

+++ Läs mer om leveransstatusvärden

* **[!UICONTROL Delivered]**: Antal SMS-meddelanden som har skickats, i relation till totalt antal SMS-meddelanden.

* **[!UICONTROL Bounces for outbound channels]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning i relation till det totala antalet skickade SMS-meddelanden.

* **[!UICONTROL Outbound errors]**: Totalt antal fel som har inträffat som förhindrar att den skickas till profiler.

* **[!UICONTROL Outbound exclusions]**: Antal profiler som har undantagits av Adobe Journey Optimizer.

+++

### Spårade länketiketter {#track-link-label-sms}

Tabellen **[!UICONTROL Tracked link labels]** innehåller en omfattande översikt över länketiketterna i dina SMS-meddelanden, som visar vilka som genererar den högsta besökstrafiken. Med den här funktionen kan du identifiera och prioritera de mest populära länkarna.

+++ Läs mer om mätvärden för spårade länketiketter

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickade på ett innehåll i SMS-meddelandet.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina SMS-meddelanden.

+++

### URL för spårad länk {#track-link-url-sms}

Tabellen **[!UICONTROL Tracked link URLs]** innehåller en omfattande översikt över de URL:er i dina SMS-meddelanden som lockar den högsta besökstrafiken. På så sätt kan ni identifiera och prioritera de mest populära länkarna och öka er förståelse för hur proffsen interagerar med specifikt innehåll i era SMS-meddelanden.

+++ Läs mer om URL:er för spårade länkar

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickade på ett innehåll i SMS-meddelandet.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina SMS-meddelanden.

* **[!UICONTROL Displays]**: Antal gånger som meddelandet öppnades.

* **[!UICONTROL Unique displays]**: Det antal gånger som meddelandet öppnades tas ingen hänsyn till flera interaktioner för en profil.

+++

### SMS inkommande meddelande {#sms-inbound}

Tabellen **[!UICONTROL SMS inbound message]** innehåller en detaljerad översikt över vilka SMS-meddelanden som har dragit till sig den högsta besökstrafiken. Den här resursen ger värdefulla insikter om målgruppsengagemangets dynamik.

+++ Läs mer om mätvärden för inkommande SMS-meddelanden

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina SMS-meddelanden.

+++

### SMS-meddelandetyp {#sms-message-type}

Tabellen **[!UICONTROL SMS Message type]** innehåller en detaljerad översikt över vilken SMS-meddelandetyp som har dragit till sig den högsta besökstrafiken. Den här resursen ger värdefulla insikter om målgruppsengagemangets dynamik.

+++ Läs mer om mätvärden för SMS-meddelandetyp

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina SMS-meddelanden.

+++

### SMS-leverantörer {#sms-providers}

Tabellen **[!UICONTROL SMS providers]** innehåller en detaljerad översikt över vilka SMS-leverantörer som har dragit till sig den högsta besökstrafiken. Den här resursen ger värdefulla insikter om målgruppsengagemangets dynamik.

+++ Läs mer om mätvärden för SMS-leverantörer

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina SMS-meddelanden.

+++

### Brytningsorsaker {#bounce-reasons-sms}

Tabellen **[!UICONTROL Bounces Reasons]** innehåller en omfattande översikt över data relaterade till avvisade SMS-meddelanden och ger värdefull information om de specifika orsakerna bakom instanser av SMS-meddelandegränser.

### Felorsaker {#error-reasons-sms}

I tabellen **[!UICONTROL Error Reasons]** kan du identifiera de specifika fel som uppstod under sändningsprocessen för dina SMS-meddelanden, vilket underlättar en grundlig analys av eventuella problem som påträffas.

### Exkludera orsaker {#excluded-reasons-sms}

Tabellen **[!UICONTROL Exclude Reasons]** visar de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen, vilket förhindrar dem från att ta emot dina SMS-meddelanden.

Se [den här sidan](exclusion-list.md) för en utförlig lista över orsaker till undantag.

## I appen

### Trend för tryck och klickning {#impression-click-trend}

![](assets/cja-inapp-impressions-click.png)

Diagrammet **[!UICONTROL Impression & Click trend]** innehåller en detaljerad analys av hur dina profiler interagerar med dina meddelanden i appen och ger värdefulla insikter om hur profilerna interagerar med ditt innehåll.

+++ Läs mer om intryckt- och klicktrendstatistik

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina meddelanden i appen.

* **[!UICONTROL Displays]**: Antal gånger som meddelandet öppnades.

+++

### Klickningar {#clicks-inapp}

Diagrammet **[!UICONTROL Clicks]** visar klickvärden i appen, som visar både det totala antalet innehållsklickningar och antalet unika profiler som klickade på innehållet.

+++ Läs mer om klickningsstatistik

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickat på ett innehåll i meddelanden i appen

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina meddelanden i appen.

+++

### Visa {#display-inapp}

Diagrammet **[!UICONTROL Displays]** hjälper dig att förstå både meddelandets övergripande räckvidd och antalet unika profiler som är kopplade till det.

+++ Läs mer om visningsmått

* **[!UICONTROL Displays]**: Antal gånger som meddelandet öppnades.

* **[!UICONTROL Unique displays]**: Det antal gånger som meddelandet öppnades tas ingen hänsyn till flera interaktioner för en profil.

+++

### Spårningsdata {#tracking-data-inapp}

Tabellen **[!UICONTROL Tracking data]** innehåller en detaljerad ögonblicksbild av profilaktiviteten som är kopplad till dina meddelanden i appen, vilket ger viktiga insikter i hur engagemanget och i appmeddelanden fungerar.

+++ Läs mer om att spåra datamätningar

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar som målprofiler för meddelanden i appen.

* **[!UICONTROL Click through rate (CTR)]**: Procentandel användare som interagerade med meddelanden i appen.

* **[!UICONTROL Click through open rate (CTOR)]**: Antal gånger som meddelanden i programmet öppnades.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina meddelanden i appen.

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickat på ett innehåll i meddelanden i appen.

* **[!UICONTROL Displays]**: Antal gånger som meddelandet öppnades.

* **[!UICONTROL Unique displays]**: Det antal gånger som meddelandet öppnades tas ingen hänsyn till flera interaktioner för en profil.

* **[!UICONTROL Sends]**: Totalt antal skickade meddelanden i appen.

<!--
* **[!UICONTROL Inbound triggered]**: 

* **[!UICONTROL Inbound dismisses]**: 
-->
+++

### Spårade länketiketter {#track-link-label-inapp}

![](assets/cja-inapp-tracked-link-labels.png)

Tabellen **[!UICONTROL Tracked link labels]** innehåller en omfattande översikt över länketiketterna i dina meddelanden i appen, som visar de som genererar den högsta besökstrafiken. Med den här funktionen kan du identifiera och prioritera de mest populära länkarna.

+++ Läs mer om mätvärden för spårade länketiketter

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickat på ett innehåll i meddelanden i appen.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina meddelanden i appen.

* **[!UICONTROL Displays]**: Antal gånger som meddelandet öppnades.

* **[!UICONTROL Unique displays]**: Det antal gånger som meddelandet öppnades tas ingen hänsyn till flera interaktioner för en profil.

+++

### URL för spårad länk {#track-link-url-inapp}

![](assets/cja-inapp-tracked-link-urls.png)

Tabellen **[!UICONTROL Tracked link URLs]** innehåller en omfattande översikt över de URL:er i dina meddelanden i appen som lockar den högsta besökstrafiken. På så sätt kan ni identifiera och prioritera de populäraste länkarna och öka er förståelse för hur proffsen interagerar med specifikt innehåll i era meddelanden i appen.

+++ Läs mer om URL:er för spårade länkar

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickat på ett innehåll i meddelanden i appen

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina meddelanden i appen.

+++

## Webb {#web-cja}

### Trend för tryck och klickning {#impressions-web}

![](assets/cja-web-impression.png)

Diagrammet **[!UICONTROL Impression & Click trend]** innehåller en detaljerad analys av hur dina profiler interagerar med dina webbsidor, och ger värdefulla insikter om hur profiler interagerar med ditt innehåll.

+++ Läs mer om intryckt- och klicktrendstatistik

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll har klickats på på dina webbsidor.

* **[!UICONTROL Displays]**: Antal gånger som meddelandet öppnades.

+++

### Klickningar {#clicks-web}

![](assets/cja-web-clicks.png)

Diagrammet **[!UICONTROL Clicks]** visar klickvärden för webbsidor, som visar både det totala antalet innehållsklickningar och antalet unika profiler som klickade på innehållet.

+++ Läs mer om klickningsstatistik

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickat på ett innehåll på dina webbsidor.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll har klickats på på dina webbsidor.

+++

### Visar {#displays-web}

![](assets/cja-web-displays.png)

Diagrammet **[!UICONTROL Displays]** hjälper dig att förstå både meddelandets övergripande räckvidd och antalet unika profiler som är kopplade till det.

+++ Läs mer om visningsmått

* **[!UICONTROL Displays]**: Antal gånger som meddelandet öppnades.

* **[!UICONTROL Unique displays]**: Det antal gånger som meddelandet öppnades tas ingen hänsyn till flera interaktioner för en profil.

+++


### Spårningsdata {#track-data-web}

![](assets/cja-web-tracking-data.png)

Tabellen **[!UICONTROL Tracking data]** innehåller en detaljerad ögonblicksbild av profilaktiviteten som är kopplad till dina webbsidor, vilket ger viktiga insikter i hur engagemanget och webbsidorna fungerar.

+++ Läs mer om att spåra datamätningar

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina webbsidor.

* **[!UICONTROL Click through rate (CTR)]**: Procentandel användare som interagerade med webbsidorna.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll har klickats på på dina webbsidor.

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickat på ett innehåll på dina webbsidor.

* **[!UICONTROL Displays]**: Antal gånger som webbsidan öppnades.

* **[!UICONTROL Unique displays]**: Antal gånger webbsidan öppnades, flera interaktioner i en profil beaktas inte.

+++

### Spårade länketiketter {#track-link-web}

![](assets/cja-web-tracked-link-labels.png)

Tabellen **[!UICONTROL Tracked link labels]** innehåller en omfattande översikt över länketiketterna på dina webbsidor, och här framhävs de som genererar störst besökstrafik. Med den här funktionen kan du identifiera och prioritera de mest populära länkarna.

+++ Läs mer om mätvärden för spårade länketiketter

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickat på ett innehåll på dina webbsidor.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll har klickats på på dina webbsidor.

* **[!UICONTROL Displays]**: Antal gånger som meddelandet öppnades.

* **[!UICONTROL Unique displays]**: Det antal gånger som meddelandet öppnades tas ingen hänsyn till flera interaktioner för en profil.

+++

### URL för spårad länk {#track-url-web}

![](assets/cja-web-tracked-link-urls.png)

Tabellen **[!UICONTROL Tracked link URLs]** innehåller en omfattande översikt över de webbadresser på dina webbsidor som tillför den högsta besökstrafiken. På så sätt kan du identifiera och prioritera de populäraste länkarna och öka din förståelse för hur proffsen interagerar med specifikt innehåll på dina webbsidor.

+++ Läs mer om URL:er för spårade länkar

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickat på ett innehåll på dina webbsidor.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll har klickats på på dina webbsidor.

* **[!UICONTROL Displays]**: Antal gånger som meddelandet öppnades.

* **[!UICONTROL Unique displays]**: Det antal gånger som meddelandet öppnades tas ingen hänsyn till flera interaktioner för en profil.

+++

## Direktmeddelande {#direct-mail-cja}

### Skicka statistik {#sending-statistics-directmail}

![](assets/cja-direct-sending-stat.png)

Tabellen **[!UICONTROL Sending Statistics]** ger dig en inblick i hur direktreklamresorna fungerar. Se viktiga mätvärden, som antalet mottagare och levererade delar, som hjälper dig att mäta hur omfattande och effektiva utskicken är.

+++ Läs mer om Skicka statistik-statistik

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina meddelanden.

* **[!UICONTROL Targeted]**: Totalt antal direktmeddelandemeddelanden som bearbetats under sändningsprocessen.

* **[!UICONTROL Sends]**: Totalt antal skickade meddelanden för dina direktutskick.

* **[!UICONTROL Delivered]**: Antal skickade direktmeddelanden i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Outbound Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

* **[!UICONTROL Outbound Exclusions]**: Antal profiler som har undantagits av Adobe Journey Optimizer.

+++

### Leveransstatus {#delivery-status-directmail}

![](assets/cja-direct-delivery-status.png)

Diagrammet **[!UICONTROL Delivery status]** ger en heltäckande bild av data relaterade till skickade direktutskick under din resa, med insikter i viktiga mått som levererade och fel. Detta möjliggör en detaljerad analys av sändningsprocessen för direktreklam och ger värdefull information om hur effektiva och effektiva era resor är.

+++ Läs mer om leveransstatusvärden

* **[!UICONTROL Delivered]**: Antal direktmeddelandemeddelanden som har skickats, i relation till det totala antalet skickade direktmeddelandemeddelanden.

* **[!UICONTROL Outbound errors]**: Totalt antal fel som uppstod under en sändningsprocess och som förhindrar att dina direktmeddelanden skickas till profiler.

* **[!UICONTROL Outbound exclusions]**: Antal profiler som har undantagits av Adobe Journey Optimizer.

+++

### Felorsaker {#error-reasons-directmail}

I tabellen **[!UICONTROL Error Reasons]** kan du identifiera de specifika fel som uppstod under sändningsprocessen för dina direktutskick, vilket underlättar en grundlig analys av eventuella problem som uppstått.

### Undantagna orsaker {#exclude-reasons-directmail}

[](assets/cja-direct-excluded.png)

Tabellen **[!UICONTROL Exclude Reasons]** visar de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen, vilket förhindrar dem från att ta emot dina direktutskick.

Se [den här sidan](exclusion-list.md) för en utförlig lista över orsaker till undantag.
