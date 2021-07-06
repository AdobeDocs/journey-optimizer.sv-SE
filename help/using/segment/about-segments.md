---
title: Om Adobe Experience Platform-segment
description: Lär dig konfigurera ett Adobe Experience Platform-segment
feature: Resor
topic: Innehållshantering
role: User
level: Intermediate
source-git-commit: b07970ff11f1ba7c4e6db30dc2eca1252a579ca4
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 0%

---

# Kom igång med segment {#about-segments}

[!DNL Journey Optimizer] Med kan ni skapa Adobe Experience Platform-segment med kundprofildata i realtid direkt från  **[!UICONTROL Segments]** menyn och utnyttja dem i era resor.

Observera att segment också kan skapas från själva segmenteringstjänsten. Läs mer i [Adobe Experience Platform Segmentation Service-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html){target=&quot;_blank&quot;}.

Du kan utnyttja segment i resor på olika sätt:

* Använd en **Läs segment**-koordinationsaktivitet för att få alla personer som tillhör det angivna segmentet att komma in på resan. Meddelanden som ingår i resan skickas till personer som tillhör segmentet. Säg att du har ett &quot;silverkundssegment&quot;. Med den här aktiviteten kan ni få alla silverkunder att ta sig in på en resa och skicka en serie personaliserade meddelanden till dem.

   Mer information om hur du använder aktiviteten **[!UICONTROL Read segment]** finns i [det här avsnittet](../building-journeys/read-segment.md#configuring-segment-trigger-activity).

* Använd aktiviteten **Segmentkvalificering** för att få individer att komma in på eller gå framåt i en resa baserat på Adobe Experience Platform segmentingångar och utgångar. Du kan till exempel få alla nya silverkunder att resa och skicka meddelanden till dem. Mer information om hur du använder den här aktiviteten finns i [det här avsnittet](../building-journeys/segment-qualification-events.md).

* Bygg **komplexa villkor** på resorna med den enkla eller avancerade uttrycksredigeraren. Läs mer i [det här avsnittet](../building-journeys/condition-activity.md#using-a-segment).

## Utvärderingsmetod i Adobe Journey Optimizer {#evaluation-method-in-journey-optimizer}

I Adobe Journey Optimizer genereras målgrupper från segmentdefinitioner med någon av dessa utvärderingsmetoder:

* Direktuppspelningssegmentering - målgruppslistan för segmentet hålls uppdaterad i realtid medan nya data flödar in i systemet.
* Gruppsegmentering - målgruppslistan för segmentet uppdateras varje timme baserat på data som erhållits under den senaste timmen.

Fastställandet mellan gruppsegmentering och direktuppspelningssegmentering görs av systemet för varje segmentdefinition, baserat på komplexiteten och kostnaden för att utvärdera segmentregeln.

Du kan visa utvärderingsmetoden för varje segment i kolumnen **[!UICONTROL Evaluation method]** i segmentlistan.

När du har definierat ett segment första gången läggs profiler till i målgruppen när de kvalificerar sig.

Det kan ta upp till 24 timmar att fylla målgruppen med tidigare data. När målgruppen har fyllts i på nytt hålls målgruppen kontinuerligt uppdaterad och alltid redo för målinriktning.
