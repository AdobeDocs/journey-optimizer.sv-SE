---
solution: Journey Optimizer
product: journey optimizer
title: Reserapport
description: Lär dig hur du använder SMS-data från reserapporten
feature: Reporting, Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: cf50ce33-7934-4e37-a757-08cda14e97ac
source-git-commit: 7d1b89ca851442d2a67dda1e5c08d50d74d44028
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 0%

---

# SMS-reserapport{#sms}

>[!BEGINSHADEBOX]

Du kommer åt din SMS-reserapport genom att klicka på knappen **[!UICONTROL View report]** under din resa. [Läs mer](report-gs-cja.md)

![](assets/report-access-jo.png)

>[!ENDSHADEBOX]

## Levererat kontra klicktrend {#delivered-click-sms}

Diagrammet **[!UICONTROL Delivered vs Click trend]** innehåller en detaljerad analys av dina profilers engagemang i dina SMS-meddelanden och ger värdefulla insikter om hur olika domäner interagerar med ditt innehåll.

+++ Läs mer om Levererat jämfört med Click-trendstatistik

* **[!UICONTROL Delivered]**: Antal SMS-meddelanden som har skickats, i relation till totalt antal SMS-meddelanden.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina SMS-meddelanden.

+++

## Leveransstatus {#delivery-status-sms}

Tabellen **[!UICONTROL Delivery status]** innehåller en detaljerad beskrivning av profilaktiviteten som är relaterad till dina SMS-meddelanden. Detta inkluderar mätvärden för levererade data, klickningar och andra relevanta interaktionsindikatorer, som ger en heltäckande bild av hur profiler interagerar med ert SMS-innehåll.

+++ Läs mer om leveransstatusvärden

* **[!UICONTROL Delivered]**: Antal SMS-meddelanden som har skickats, i relation till totalt antal SMS-meddelanden.

* **[!UICONTROL Bounces for outbound channels]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning i relation till det totala antalet skickade SMS-meddelanden.

* **[!UICONTROL Outbound errors]**: Totalt antal fel som har inträffat som förhindrar att den skickas till profiler.

* **[!UICONTROL Outbound exclusions]**: Antal profiler som har undantagits av Adobe Journey Optimizer.

+++

## Spårade länketiketter {#track-link-label-sms}

Tabellen **[!UICONTROL Tracked link labels]** innehåller en omfattande översikt över länketiketterna i dina SMS-meddelanden, som visar vilka som genererar den högsta besökstrafiken. Med den här funktionen kan du identifiera och prioritera de mest populära länkarna.

+++ Läs mer om mätvärden för spårade länketiketter

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickade på ett innehåll i SMS-meddelandet.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina SMS-meddelanden.

+++

## URL för spårad länk {#track-link-url-sms}

Tabellen **[!UICONTROL Tracked link URLs]** innehåller en omfattande översikt över de URL:er i dina SMS-meddelanden som lockar den högsta besökstrafiken. På så sätt kan ni identifiera och prioritera de mest populära länkarna och öka er förståelse för hur proffsen interagerar med specifikt innehåll i era SMS-meddelanden.

+++ Läs mer om URL:er för spårade länkar

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickade på ett innehåll i SMS-meddelandet.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina SMS-meddelanden.

* **[!UICONTROL Displays]**: Antal gånger som meddelandet öppnades.

* **[!UICONTROL Unique displays]**: Det antal gånger som meddelandet öppnades tas ingen hänsyn till flera interaktioner för en profil.

+++

## SMS inkommande meddelande {#sms-inbound}

Tabellen **[!UICONTROL SMS inbound message]** innehåller en detaljerad översikt över vilka SMS-meddelanden som har dragit till sig den högsta besökstrafiken. Den här resursen ger värdefulla insikter om målgruppsengagemangets dynamik.

+++ Läs mer om mätvärden för inkommande SMS-meddelanden

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina SMS-meddelanden.

+++

## SMS-meddelandetyp {#sms-message-type}

Tabellen **[!UICONTROL SMS Message type]** innehåller en detaljerad översikt över vilken SMS-meddelandetyp som har dragit till sig den högsta besökstrafiken. Den här resursen ger värdefulla insikter om målgruppsengagemangets dynamik.

+++ Läs mer om mätvärden för SMS-meddelandetyp

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina SMS-meddelanden.

+++

## SMS-leverantörer {#sms-providers}

Tabellen **[!UICONTROL SMS providers]** innehåller en detaljerad översikt över vilka SMS-leverantörer som har dragit till sig den högsta besökstrafiken. Den här resursen ger värdefulla insikter om målgruppsengagemangets dynamik.

+++ Läs mer om mätvärden för SMS-leverantörer

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina SMS-meddelanden.

+++

## Brytningsorsaker {#bounce-reasons-sms}

Tabellen **[!UICONTROL Bounces Reasons]** innehåller en omfattande översikt över data relaterade till avvisade SMS-meddelanden och ger värdefull information om de specifika orsakerna bakom instanser av SMS-meddelandegränser.

### Felorsaker {#error-reasons-sms}

I tabellen **[!UICONTROL Error Reasons]** kan du identifiera de specifika fel som uppstod under sändningsprocessen för dina SMS-meddelanden, vilket underlättar en grundlig analys av eventuella problem som påträffas.

### Exkludera orsaker {#excluded-reasons-sms}

Tabellen **[!UICONTROL Exclude Reasons]** visar de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen, vilket förhindrar dem från att ta emot dina SMS-meddelanden.

Se [den här sidan](exclusion-list.md) för en utförlig lista över orsaker till undantag.
