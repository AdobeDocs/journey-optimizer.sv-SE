---
solution: Journey Optimizer
product: journey optimizer
title: Kampanjrapport
description: Lär dig använda push-data från Campaign-rapporten
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 43b10f54-0c19-46a1-8d51-eb6bf22e6da9
source-git-commit: 7945ab9369498f23685aa2f727542c7367c2d830
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 0%

---

# Kampanjrapport för push-meddelanden {#campaign-global-report-cja-push}

>[!BEGINSHADEBOX]

Du kommer åt rapporten för push-meddelandekampanjen genom att klicka på knappen **[!UICONTROL Reports]** i kampanjen och sedan välja **[!UICONTROL View all time report]**. [Läs mer](report-gs-cja.md)

![](assets/report-access.png)

>[!ENDSHADEBOX]

## Skicka statistik {#sending-statistics-push}

![](assets/cja-campaign-push-sending-stat.png)

Tabellen **[!UICONTROL Sending Statistics]** innehåller en omfattande sammanfattning av viktiga data om push-meddelandekampanjer. Den innehåller viktiga mätvärden, som målgruppens storlek och antalet push-meddelanden som levererats, och ger värdefulla insikter om hur effektivt och relevant ditt push-meddelande är.

+++ Läs mer om att skicka statistik

* **[!UICONTROL Targeted]**: Antal profiler som kvalificerats för målgruppen innan undantag, inaktiveringar eller medgivandeborttagningar tillämpades. På resor där återinträde är aktiverat kan en profil användas flera gånger.

* **[!UICONTROL Sends]**: Totalt antal skickade för push-meddelandet.

* **[!UICONTROL Delivered]**: Antal push-meddelanden som har skickats, i relation till det totala antalet skickade push-meddelanden.

* **[!UICONTROL Unique delivered]**: Antal profiler som har tagit emot minst ett push-meddelande.

* **[!UICONTROL Outbound errors]**: Totalt antal fel som har inträffat som förhindrar att den skickas till profiler.

* **[!UICONTROL Outbound exclusions]**: Antal profiler som har undantagits av Adobe Journey Optimizer.

+++

## Spårningsstatistik {#tracking-statistics-push}

![](assets/cja-campaign-push-track-stat.png)

Tabellen **[!UICONTROL Tracking statistics]** erbjuder en detaljerad ögonblicksbild av profilaktivitet som är kopplad till dina push-meddelanden, vilket ger viktiga insikter om engagemang och push-meddelandenas effektivitet.

+++ Läs mer om statistik för spårning

* **[!UICONTROL Click through rate (CTR)]**: Procentandel användare som interagerade med push-meddelanden.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina push-meddelanden.

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickat på ett innehåll i dina push-meddelanden.

* **[!UICONTROL Push custom actions]**: Antal anpassade åtgärder som vidtas av profiler som svar på push-meddelanden.

+++

## Spårade etiketter {#track-link-label-push}

![](assets/cja-campaign-push-link-labels.png)

Tabellen **[!UICONTROL Tracked link labels]** innehåller en omfattande översikt över länketiketterna i dina push-meddelanden, som visar de som genererar den högsta besökstrafiken. Med den här funktionen kan du identifiera och prioritera de mest populära länkarna.

+++ Läs mer om mätvärden för spårade länketiketter

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickat på ett innehåll i dina push-meddelanden.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina push-meddelanden.

+++

## URL för spårad länk {#track-link-url-push}

![](assets/cja-campaign-push-link-urls.png)

Tabellen **[!UICONTROL Tracked link URLs]** innehåller en omfattande översikt över de URL:er i dina push-meddelanden som lockar den högsta besökstrafiken. På så sätt kan ni identifiera och prioritera de populäraste länkarna och öka er förståelse för hur proffsen interagerar med specifikt innehåll i era push-meddelanden.

+++ Läs mer om URL-mått för spårad länk

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickat på ett innehåll i dina push-meddelanden.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i dina push-meddelanden.

+++

## Brytningsorsaker {#bounce-reasons-push}

Tabellen **[!UICONTROL Bounces Reasons]** innehåller en omfattande översikt över data relaterade till studsade push-meddelanden, vilket ger värdefulla insikter om de specifika orsakerna bakom instanser av push-meddelanden.

## Felorsaker {#error-reasons-push}

I tabellen **[!UICONTROL Error Reasons]** kan du identifiera de specifika fel som uppstod under sändningsprocessen för dina push-meddelanden, vilket underlättar en grundlig analys av eventuella problem som uppstått.

## Exkludera orsaker {#exclude-reasons-push}

![](assets/cja-campaign-push-excluded.png)

Tabellen **[!UICONTROL Exclude Reasons]** visar de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen, vilket förhindrar dem från att ta emot push-meddelanden.

Se [den här sidan](exclusion-list.md) för en utförlig lista över orsaker till undantag.
