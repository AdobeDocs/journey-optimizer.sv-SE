---
solution: Journey Optimizer
product: journey optimizer
title: Kampanjrapport
description: Lär dig hur du använder data för direktreklam från Campaign-rapporten
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: b0771fd9-72bd-4891-a394-f08e3dde6126
source-git-commit: 7945ab9369498f23685aa2f727542c7367c2d830
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 0%

---

# Rapport om direktreklamkampanj {#campaign-global-report-cja-direct}

>[!BEGINSHADEBOX]

Du kommer åt kampanjrapporten för direktreklam genom att klicka på knappen **[!UICONTROL Reports]** i kampanjen och sedan välja **[!UICONTROL View all time report]**. [Läs mer](report-gs-cja.md)

![](assets/report-access.png)

>[!ENDSHADEBOX]

## Skicka statistik {#sending-statistics-directmail}

![](assets/cja-direct-sending-stat.png)

Tabellen **[!UICONTROL Sending Statistics]** innehåller en omfattande sammanfattning av viktiga data om dina direktreklamkampanjer. Här finns viktiga mätvärden, till exempel storleken på målgruppen och antalet direktutskick som levererats, och där finns värdefulla insikter om direktutskickens effektivitet och räckvidd.

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

Diagrammet **[!UICONTROL Delivery status]** ger en heltäckande bild av data relaterade till skickade direktutskick i kampanjen, och ger insikter i viktiga mått som levererade och fel. Detta möjliggör en detaljerad analys av sändningsprocessen för direktreklam, vilket ger värdefull information om kampanjernas effektivitet och resultat.

+++ Läs mer om leveransstatusvärden

* **[!UICONTROL Delivered]**: Antal direktmeddelandemeddelanden som har skickats, i relation till det totala antalet skickade direktmeddelandemeddelanden.

* **[!UICONTROL Outbound errors]**: Totalt antal fel som uppstod under en sändningsprocess och som förhindrar att dina direktmeddelanden skickas till profiler.

* **[!UICONTROL Ountbound exclusions]**: Antal profiler som har undantagits av Adobe Journey Optimizer.

+++

## Felorsaker {#error-reasons-directmail}

I tabellen **[!UICONTROL Error Reasons]** kan du identifiera de specifika fel som uppstod under sändningsprocessen för dina direktutskick, vilket underlättar en grundlig analys av eventuella problem som uppstått.

## Undantagna orsaker {#exclude-reasons-directmail}

[&#128279;](assets/cja-direct-excluded.png)

Tabellen **[!UICONTROL Exclude Reasons]** visar de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen, vilket förhindrar dem från att ta emot dina direktutskick.

Se [den här sidan](exclusion-list.md) för en utförlig lista över orsaker till undantag.
