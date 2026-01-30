---
solution: Journey Optimizer
product: journey optimizer
title: Reserapport
description: Lär dig använda direkt data från reserapporten
feature: Reporting, Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 6fae8beb-ca40-40a1-8939-c309fbf46c4f
source-git-commit: 7945ab9369498f23685aa2f727542c7367c2d830
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---

# Rapport om direktreklam {#journey-global-report}

>[!BEGINSHADEBOX]

Du kan komma åt din rapport om direktutskick genom att klicka på knappen **[!UICONTROL View report]** under din resa. [Läs mer](report-gs-cja.md)

![](assets/report-access-jo.png)

>[!ENDSHADEBOX]

## Skicka statistik {#sending-statistics-directmail}

![](assets/cja-direct-sending-stat.png)

Tabellen **[!UICONTROL Sending Statistics]** ger dig en inblick i hur direktreklamresorna fungerar. Se viktiga mätvärden, som antalet mottagare och levererade delar, som hjälper dig att mäta hur omfattande och effektiva utskicken är.

+++ Läs mer om att skicka statistik

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina meddelanden.

* **[!UICONTROL Targeted]**: Antal profiler som kvalificerats för målgruppen innan undantag, inaktiveringar eller medgivandeborttagningar tillämpades. På resor där återinträde är aktiverat kan en profil användas flera gånger.

* **[!UICONTROL Sends]**: Totalt antal skickade meddelanden för dina direktutskick.

* **[!UICONTROL Delivered]**: Antal skickade direktmeddelanden i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Outbound Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

* **[!UICONTROL Outbound Exclusions]**: Antal profiler som har undantagits av Adobe Journey Optimizer.

+++

## Leveransstatus {#delivery-status-directmail}

![](assets/cja-direct-delivery-status.png)

Diagrammet **[!UICONTROL Delivery status]** ger en heltäckande bild av data relaterade till skickade direktutskick under din resa, med insikter i viktiga mått som levererade och fel. Detta möjliggör en detaljerad analys av sändningsprocessen för direktreklam och ger värdefull information om hur effektiva och effektiva era resor är.

+++ Läs mer om leveransstatusvärden

* **[!UICONTROL Delivered]**: Antal direktmeddelandemeddelanden som har skickats, i relation till det totala antalet skickade direktmeddelandemeddelanden.

* **[!UICONTROL Outbound errors]**: Totalt antal fel som uppstod under en sändningsprocess och som förhindrar att dina direktmeddelanden skickas till profiler.

* **[!UICONTROL Outbound exclusions]**: Antal profiler som har undantagits av Adobe Journey Optimizer.

+++

## Felorsaker {#error-reasons-directmail}

I tabellen **[!UICONTROL Error Reasons]** kan du identifiera de specifika fel som uppstod under sändningsprocessen för dina direktutskick, vilket underlättar en grundlig analys av eventuella problem som uppstått.

## Undantagna orsaker {#exclude-reasons-directmail}

[](assets/cja-direct-excluded.png)

Tabellen **[!UICONTROL Exclude Reasons]** visar de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen, vilket förhindrar dem från att ta emot dina direktutskick.

Se [den här sidan](exclusion-list.md) för en utförlig lista över orsaker till undantag.
