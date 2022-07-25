---
title: Om reseaktiviteter
description: Läs om reseaktiviteter
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 239b3d72-3be0-4a82-84e6-f219e33ddca4
source-git-commit: 0e978d0eab570a28c187f3e7779c450437f16cfb
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 24%

---

# Om reseaktiviteter {#about-journey-activities}

Kombinera de olika händelserna, orkestreringen och åtgärderna för att skapa scenarier i flera steg över olika kanaler.

## Händelseaktiviteter {#event-activities}

Händelser som konfigurerats av den tekniska användaren (se [den här sidan](../event/about-events.md)) visas i den första kategorin på paletten, till vänster på skärmen. Följande aktiviteter är tillgängliga:

* [Allmänna händelser](../building-journeys/general-events.md)
* [Reaktion](../building-journeys/reaction-events.md)
* [Segmentkvalificering](../building-journeys/segment-qualification-events.md)

![](assets/journey43.png)

Starta din resa genom att dra och släppa en händelseaktivitet. Du kan också dubbelklicka på den.

![](assets/journey44.png)

## Orkestreringsaktiviteter {#orchestration-activities}

På paletten till vänster på skärmen finns följande orkestreringsfunktioner:

* [Villkor](../building-journeys/condition-activity.md)
* [End](../building-journeys/end-activity.md)
* [Vänta](../building-journeys/wait-activity.md)
* [Läs segment](../building-journeys/read-segment.md)

![](assets/journey49.png)

## Åtgärdsaktiviteter {#action-activities}

Från paletten, till vänster på skärmen, nedanför **[!UICONTROL Events]** och **[!UICONTROL Orchestration]** hittar du **[!UICONTROL Actions]** kategori. Följande åtgärdsaktiviteter är tillgängliga:

* [E-post, SMS, push](../building-journeys/journeys-message.md)
* [Anpassade åtgärder](../building-journeys/using-custom-actions.md)
* [Hoppa](../building-journeys/jump.md)

![](assets/journey58.png)

Dessa aktiviteter representerar olika tillgängliga kommunikationskanaler. Du kan kombinera dem för att skapa ett flerkanalsscenario.

Om du har konfigurerat anpassade åtgärder visas de här (se [den här sidan](../building-journeys/using-custom-actions.md)).

## God praxis {#best-practices}

De flesta aktiviteter gör att du kan definiera en **[!UICONTROL Label]**. Detta lägger till ett suffix till namnet som visas under din aktivitet på arbetsytan. Detta är användbart om du använder samma aktivitet flera gånger under resan och vill identifiera dem enklare. Felsökningen blir också enklare om fel uppstår, vilket gör det lättare att läsa rapporterna. Du kan också lägga till ett valfritt **[!UICONTROL Description]**.

![](assets/journey59bis.png)

När ett fel inträffar i en åtgärd eller ett villkor upphör en individs resa. Det enda sättet att få den att fortsätta är att markera rutan **[!UICONTROL Add an alternative path in case of a timeout or an error]**. Se [det här avsnittet](../building-journeys/using-the-journey-designer.md#paths).

![](assets/journey42.png)
