---
solution: Journey Optimizer
product: journey optimizer
title: Om Adobe Experience Platform-segment
description: Lär dig konfigurera ett Adobe Experience Platform-segment
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 10d2de34-23c1-4a5e-b868-700b462312eb
source-git-commit: adfd47f23188935f6382a18d0de4a6101f022d78
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 0%

---

# Kom igång med Adobe Experience Platform {#about-segments}

[!DNL Journey Optimizer]  kan du skapa Adobe Experience Platform-segment med hjälp av kundprofildata i realtid direkt från **[!UICONTROL Segments]** och utnyttja dem på era resor.

Observera att segment också kan skapas från själva segmenteringstjänsten. Läs mer i [Dokumentation för Adobe Experience Platform Segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html).

Du kan utnyttja segment i resor på olika sätt:

* Använd en **Lässegment** orkestreringsaktivitet för att få alla personer som tillhör det angivna segmentet att komma in på resan. Meddelanden som ingår i resan skickas till personer som tillhör segmentet. Säg att du har ett &quot;silverkundssegment&quot;. Med den här aktiviteten kan ni få alla silverkunder att ta sig in på en resa och skicka en serie personaliserade meddelanden till dem.

   Mer information om hur du använder **[!UICONTROL Read segment]** aktivitet, se [det här avsnittet](../building-journeys/read-segment.md#configuring-segment-trigger-activity).

* Använd **Segmentkvalificering** aktivitet för att få enskilda att komma in på eller gå vidare i en resa baserat på Adobe Experience Platform segmententréer och utträde. Du kan till exempel få alla nya silverkunder att resa och skicka meddelanden till dem. Mer information om hur du använder den här aktiviteten finns i [det här avsnittet](../building-journeys/segment-qualification-events.md).

* Bygge **komplexa förhållanden** på resorna med den enkla eller avancerade uttrycksredigeraren. Läs mer i [det här avsnittet](../building-journeys/condition-activity.md#using-a-segment).

## Målgruppsbedömningsmetod {#evaluation-method-in-journey-optimizer}

I Adobe Journey Optimizer genereras målgrupper från segmentdefinitioner med någon av dessa utvärderingsmetoder:

* Direktuppspelningssegmentering - målgruppslistan för segmentet hålls uppdaterad i realtid medan nya data flödar in i systemet. Direktuppspelningssegmentering är en kontinuerlig process för val av data som uppdaterar era segment som svar på användaraktivitet. När ett segment har skapats och sparats tillämpas segmentdefinitionen på inkommande data till Journey Optimizer. Tillägg och borttagningar av segment behandlas regelbundet, vilket säkerställer att målgruppen förblir relevant.

* Gruppsegmentering - målgruppslistan för segmentet utvärderas var 24:e timme. Som ett alternativ till en pågående dataurvalsprocess flyttar gruppsegmentering alla profildata samtidigt genom segmentdefinitioner för att skapa motsvarande målgrupper. När segmentet har skapats sparas det och lagras så att du kan exportera det för användning.

Fastställandet mellan gruppsegmentering och direktuppspelningssegmentering görs av systemet för varje segmentdefinition, baserat på komplexiteten och kostnaden för att utvärdera segmentregeln.

Du kan visa utvärderingsmetoden för varje segment i **[!UICONTROL Evaluation method]** kolumn i segmentlistan.

När du har definierat ett segment första gången läggs profiler till i målgruppen när de kvalificerar sig.

Det kan ta upp till 24 timmar att fylla målgruppen med tidigare data. När målgruppen har fyllts i på nytt hålls målgruppen kontinuerligt uppdaterad och alltid redo för målinriktning.
