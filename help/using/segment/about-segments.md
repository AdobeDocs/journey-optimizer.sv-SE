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
source-git-commit: 6c255d66fb89ba756add062d8a4315dd622fd8e7
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---

# Kom igång med Adobe Experience Platform {#about-segments}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment_segment"
>title="Segment"
>abstract="Genom att utnyttja kundprofildata i realtid kan Adobe Experience Platform enkelt skapa riktade segment som fångar upp kundernas unika beteenden och preferenser."

[!DNL Journey Optimizer]  kan du skapa Adobe Experience Platform-segment med hjälp av kundprofildata i realtid direkt från **[!UICONTROL Segments]** och använda dem i era resor eller kampanjer.

Dessutom kan segment också skapas från själva segmenteringstjänsten. Läs mer i [Dokumentation för Adobe Experience Platform Segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html).

## Använd segment i [!DNL Journey Optimizer] {#segments-in-journey-optimizer}

Du kan använda segment i **[!DNL Journey Optimizer]** på olika sätt:

* Välj ett segment som **målgrupp för en kampanj**, där meddelandet skickas till alla personer som tillhör det valda segmentet. [Lär dig definiera målgruppen för en kampanj](../campaigns/create-campaign.md#define-the-audience-audience).

* Använd en **Lässegment** samordning av en resa för att få alla personer i segmentet att komma in på resan och ta emot de meddelanden som ingår i resan.

   Säg att du har ett &quot;silverkundssegment&quot;. Med den här aktiviteten kan ni få alla silverkunder att ta sig in på en resa och skicka en serie personaliserade meddelanden till dem. [Lär dig konfigurera en Läs-segmentaktivitet](../building-journeys/read-segment.md#configuring-segment-trigger-activity).

* Använd **Segmentkvalificering** händelseaktivitet på en resa som får enskilda att komma in på eller gå framåt i resan baserat på Adobe Experience Platform segmentingångar och utgångar.

   Du kan till exempel få alla nya silverkunder att resa och skicka meddelanden till dem. Mer information om hur du använder den här aktiviteten finns i [Lär dig konfigurera en segmentkvalificeringsaktivitet](../building-journeys/segment-qualification-events.md).

* Använd **Villkor** aktivitet i en resa för att skapa villkor baserade på segmentmedlemskap. [Lär dig hur du använder segment under förhållanden](../building-journeys/condition-activity.md#using-a-segment).

## Metoder för utvärdering av målgrupper{#evaluation-method-in-journey-optimizer}

I Adobe Journey Optimizer genereras målgrupper från segmentdefinitioner med en av två utvärderingsmetoder:

* **Direktuppspelningssegmentering**: Målgruppslistan för segmentet hålls uppdaterad i realtid när nya data flödar in i systemet.

   Direktuppspelningssegmentering är en kontinuerlig process för val av data som uppdaterar era segment som svar på användaraktivitet. När ett segment har skapats och sparats tillämpas segmentdefinitionen på inkommande data till Journey Optimizer. Det innebär att enskilda personer läggs till eller tas bort från segmentet när profildata ändras, vilket säkerställer att målgruppen alltid är relevant.

* **Gruppsegmentering**: Målgruppslistan för segmentet utvärderas var 24:e timme.

   Gruppsegmentering är ett alternativ till direktuppspelningssegmentering som bearbetar alla profildata samtidigt genom segmentdefinitioner. Detta skapar en ögonblicksbild av målgruppen som kan sparas och exporteras för användning. Till skillnad från direktuppspelningssegmentering kommer gruppsegmentering inte att kontinuerligt uppdatera målgruppslistan i realtid, och nya data som kommer in efter gruppbearbetningen kommer inte att återspeglas i segmentet förrän nästa gruppbearbetning.&quot;

Fastställandet mellan gruppsegmentering och direktuppspelningssegmentering görs av systemet för varje segmentdefinition, baserat på komplexiteten och kostnaden för att utvärdera segmentregeln. Du kan visa utvärderingsmetoden för varje segment i **[!UICONTROL Evaluation method]** kolumn i segmentlistan.

![](assets/evaluation-method.png)

>[!NOTE]
>
>Om **[!UICONTROL Evaluation method]** -kolumnen visas inte, du måste lägga till den med hjälp av konfigurationsknappen högst upp till höger i listan.

När du har definierat ett segment första gången läggs profiler till i målgruppen när de kvalificerar sig.

Det kan ta upp till 24 timmar att fylla målgruppen med tidigare data. När målgruppen har fyllts i på nytt hålls målgruppen kontinuerligt uppdaterad och alltid redo för målinriktning.
