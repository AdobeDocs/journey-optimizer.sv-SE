---
solution: Journey Optimizer
product: journey optimizer
title: Reserapport
description: Lär dig hur du använder push-meddelandedata från reserapporten
feature: Reporting, Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 6d4b7669-7852-42f0-9347-399a3994011f
source-git-commit: 7945ab9369498f23685aa2f727542c7367c2d830
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 0%

---

# Push-rapport om meddelanderesa {#journey-global-report}

>[!BEGINSHADEBOX]

Du kan komma åt din push-meddelandereserapport genom att klicka på knappen **[!UICONTROL View report]** under din resa. [Läs mer](report-gs-cja.md)

![](assets/report-access-jo.png)

>[!ENDSHADEBOX]

## Skicka statistik {#sending-statistics-push}

![](assets/cja-campaign-push-sending-stat.png)

Tabellen **[!UICONTROL Sending Statistics]** hjälper dig att förstå hur push-meddelanden fungerar. Det innehåller viktiga mätvärden som leveransfrekvens och målgruppsstorlek som ger er värdefulla insikter om hur effektiva och omfattande era resor är.

+++ Läs mer om att skicka statistik

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina SMS-meddelanden.

* **[!UICONTROL Targeted]**: Antal profiler som kvalificerats för målgruppen innan undantag, inaktiveringar eller medgivandeborttagningar tillämpades. På resor där återinträde är aktiverat kan en profil användas flera gånger.

* **[!UICONTROL Sends]**: Totalt antal skickade för push-meddelandet.

* **[!UICONTROL Delivered]**: Antal push-meddelanden som har skickats, i relation till det totala antalet skickade push-meddelanden.

* **[!UICONTROL Bounces for outbound channels]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning i relation till totalt antal push-meddelanden.

* **[!UICONTROL Outbound errors]**: Totalt antal fel som har inträffat som förhindrar att den skickas till profiler.

* **[!UICONTROL Outbound exclusions]**: Antal profiler som har undantagits av Adobe Journey Optimizer.

+++

## Spårningsstatistik {#tracking-statistics-push}

![](assets/cja-campaign-push-track-stat.png)

Tabellen **[!UICONTROL Tracking statistics]** erbjuder en detaljerad ögonblicksbild av profilaktivitet som är kopplad till dina push-meddelanden, vilket ger viktiga insikter om engagemang och push-meddelandenas effektivitet.

+++ Läs mer om statistik för spårning

* **[!UICONTROL Click through rate (CTR)]**: Procentandel användare som interagerade med push-meddelandet.

* **[!UICONTROL Clickthrough open rate (CTOR)]**: Antal gånger som push-meddelandet öppnades.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades på i ditt push-meddelande.

* **[!UICONTROL Unique Clicks]**: Antal profiler som klickat på ett innehåll i ditt push-meddelande.

* **[!UICONTROL Push custom actions]**: Antal anpassade åtgärder som vidtas av profiler som svar på push-meddelanden.
+++

## Spårade länketiketter {#track-link-label-push}

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

## Undantagna orsaker {#exclude-reasons-push}

![](assets/cja-campaign-push-excluded.png)

Tabellen **[!UICONTROL Exclude Reasons]** visar de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen, vilket förhindrar dem från att ta emot push-meddelanden.

Se [den här sidan](exclusion-list.md) för en utförlig lista över orsaker till undantag.
