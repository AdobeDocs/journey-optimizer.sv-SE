---
solution: Journey Optimizer
product: journey optimizer
title: Om Adobe Experience Platform målgrupper
description: Lär dig arbeta med Adobe Experience Platform målgrupper
feature: Audiences, Profiles
topic: Content Management
role: User
level: Beginner
exl-id: 10d2de34-23c1-4a5e-b868-700b462312eb
source-git-commit: 3f96cc0037b5bcdb2ce94e2721b02ba13b3cff36
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 0%

---

# Kom igång med Adobe Experience Platform målgrupper {#about-segments}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment_segment"
>title="Målgrupp"
>abstract="Genom att utnyttja kundprofildata i realtid kan Adobe Experience Platform enkelt skapa segmentdefinitioner för att skapa målgrupper som fångar upp kundernas unika beteenden och önskemål."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_audience"
>title="Välj kampanjmålgrupp"
>abstract="I den här listan visas alla tillgängliga Adobe Experience Platform-målgrupper. Välj målgrupp för er kampanj. Meddelandet som konfigurerats i kampanjen skickas till alla personer som tillhör den valda målgruppen. [Läs mer om målgrupper](../audience/about-audiences.md)"

[!DNL Journey Optimizer] kan ni bygga upp och utnyttja Adobe Experience Platform målgrupper med hjälp av kundprofildata i realtid direkt från **[!UICONTROL Audiences]** och använda dem i era resor eller kampanjer.

Läs mer i [Dokumentation för Adobe Experience Platform Segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html).

## Använd målgrupper i [!DNL Journey Optimizer] {#segments-in-journey-optimizer}

Ni kan utnyttja målgrupper i **[!DNL Journey Optimizer]** på olika sätt:

* Välj en målgrupp för **kampanj**, där meddelandet skickas till alla personer som tillhör den valda målgruppen. [Lär dig definiera målgruppen för en kampanj](../campaigns/create-campaign.md#define-the-audience-audience).

* Använd en **Läsa målgrupper** orkestreringsaktivitet på en resa för att få alla personer i publiken att komma in på resan och ta emot de meddelanden som ingår i resan.

  Säg att ni har en&quot;silverkund&quot; som målgrupp. Med den här aktiviteten kan ni få alla silverkunder att ta sig in på en resa och skicka en serie personaliserade meddelanden till dem. [Lär dig konfigurera en målgruppsaktivitet för läsning](../building-journeys/read-audience.md#configuring-segment-trigger-activity).

* Använd **Målgruppskvalifikation** händelseaktivitet på en resa för att få individer att komma in på eller gå framåt i resan baserat på Adobe Experience Platform entréer och utgångar.

  Du kan till exempel få alla nya silverkunder att resa och skicka meddelanden till dem. Mer information om hur du använder den här aktiviteten finns i [Lär dig hur du konfigurerar en aktivitet för målgruppskvalificering](../building-journeys/audience-qualification-events.md).

* Använd **Villkor** aktiviteter på en resa för att skapa villkor baserade på medlemskap för målgrupper. [Lär dig hur du använder målgrupper under förhållanden](../building-journeys/condition-activity.md#using-a-segment).

## Metoder för utvärdering av målgrupper{#evaluation-method-in-journey-optimizer}

I Adobe Journey Optimizer genereras målgrupper från segmentdefinitioner med en av två utvärderingsmetoder:

* **Direktuppspelningssegmentering**: Profillistan för målgruppen hålls uppdaterad i realtid när nya data flödar in i systemet.

  Direktuppspelningssegmentering är en kontinuerlig process för datamarkering som uppdaterar era målgrupper som svar på användaraktivitet. När en segmentdefinition har skapats och målgruppen har sparats, tillämpas segmentdefinitionen på inkommande data till Journey Optimizer. Det innebär att enskilda personer läggs till eller tas bort från målgruppen när deras profildata ändras, vilket säkerställer att målgruppen alltid är relevant.

* **Gruppsegmentering**: Profillistan för målgruppen utvärderas var 24:e timme.

  Gruppsegmentering är ett alternativ till direktuppspelningssegmentering som bearbetar alla profildata samtidigt genom segmentdefinitioner. Detta skapar en ögonblicksbild av målgruppen som kan sparas och exporteras för användning. Till skillnad från direktuppspelningssegmentering kommer gruppsegmentering inte att kontinuerligt uppdatera målgruppslistan i realtid, och nya data som kommer in efter gruppbearbetningen kommer inte att återspeglas i målgruppen förrän nästa gruppbearbetning.&quot;

Fastställandet mellan gruppsegmentering och direktuppspelningssegmentering görs av systemet för varje målgrupp utifrån komplexiteten och kostnaden för att utvärdera segmentdefinitionsregeln. Du kan visa utvärderingsmetoden för varje målgrupp i **[!UICONTROL Evaluation method]** -kolumnen i målgruppslistan.

![](assets/evaluation-method.png)

>[!NOTE]
>
>Om **[!UICONTROL Evaluation method]** -kolumnen visas inte, du måste lägga till den med hjälp av konfigurationsknappen högst upp till höger i listan.

När du har definierat en målgrupp för första gången läggs profiler till i målgruppen när de kvalificerar sig.

Det kan ta upp till 24 timmar att fylla målgruppen med tidigare data. När målgruppen har fyllts i på nytt hålls målgruppen kontinuerligt uppdaterad och alltid redo för målinriktning.
