---
title: Om Adobe Experience Platform-segment
description: Lär dig konfigurera ett Adobe Experience Platform-segment
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---

# Om Adobe Experience Platform-segment {#about-segments}

![](../assets/do-not-localize/badge.png)

Med Journey Optimizer kan ni skapa Adobe Experience Platform-segment med hjälp av kundprofildata i realtid direkt från **[!UICONTROL Segments]**-menyn och utnyttja dem i era resor.

Observera att segment också kan skapas från själva segmenteringstjänsten. Läs mer i [Adobe Experience Platform Segmentation Service-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html).

Du kan utnyttja segment i resor på olika sätt:

* Använd en **Läs segment**-koordinationsaktivitet för att få alla personer som tillhör det angivna segmentet att komma in på resan. Meddelanden som ingår i resan skickas till personer som tillhör segmentet. Säg att du har ett &quot;silverkundssegment&quot;. Med den här aktiviteten kan ni få alla silverkunder att ta sig in på en resa och skicka en serie personaliserade meddelanden till dem.

   Mer information om hur du använder aktiviteten **[!UICONTROL Read segment]** finns i [det här avsnittet](../building-journeys/read-segment.md#configuring-segment-trigger-activity).

* Använd aktiviteten **Segmentkvalificering** för att få individer att komma in på eller gå framåt i en resa baserat på Adobe Experience Platform segmentingångar och utgångar. Du kan till exempel få alla nya silverkunder att resa och skicka meddelanden till dem. Mer information om hur du använder den här aktiviteten finns i [det här avsnittet](../building-journeys/segment-qualification-events.md).

* Bygg **komplexa villkor** på resorna med den enkla eller avancerade uttrycksredigeraren. Läs mer i [det här avsnittet](../building-journeys/condition-activity.md#using-a-segment).
