---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med reseaktiviteter
description: Kom igång med reseaktiviteter
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: resa, aktiviteter, komma igång, händelser, åtgärd
exl-id: 239b3d72-3be0-4a82-84e6-f219e33ddca4
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 16%

---

# Kom igång med reseaktiviteter {#about-journey-activities}

Kombinera de olika händelserna, orkestreringen och åtgärderna för att skapa scenarier i flera steg över olika kanaler.

## Händelseaktiviteter {#event-activities}

Det är händelser som utlöser en personaliserad resa, till exempel ett onlineköp. När någon väl går in på en resa förflyttas de som en individ, och inga två personer följer med på samma hastighet eller längs samma väg. När du påbörjar din resa med en händelse aktiveras resan när händelsen tas emot. Varje person på resan följer sedan, individuellt, de steg som definieras på din resa.

Händelser som konfigurerats av den tekniska användaren (se [den här sidan](../event/about-events.md)) visas i den första kategorin på paletten, till vänster på skärmen. Följande aktiviteter är tillgängliga:

* [Allmänna händelser](../building-journeys/general-events.md)
* [Reaktion](../building-journeys/reaction-events.md)
* [Segmentkvalificering](../building-journeys/segment-qualification-events.md)

![](assets/journey43.png)

Starta din resa genom att dra och släppa en händelseaktivitet. Du kan också dubbelklicka på den.

![](assets/journey44.png)

## Orkestreringsaktiviteter {#orchestration-activities}

Orchestration-aktiviteter är olika villkor som hjälper till att bestämma nästa steg i resan. Det kan vara om personen har ett öppet supportärende eller inte, väderprognosen på sin nuvarande plats, om de slutförde ett köp eller inte, eller uppnådde 10 000 förmånspoäng.

På paletten till vänster på skärmen finns följande orkestreringsfunktioner:

* [Villkor](../building-journeys/condition-activity.md)
* [Vänta](../building-journeys/wait-activity.md)
* [Läs segment](../building-journeys/read-segment.md)

![](assets/journey49.png)

## Åtgärdsaktiviteter {#action-activities}

Åtgärder är vad du vill ska hända som ett resultat av någon typ av utlösare, som att skicka ett meddelande. Det är den del av resan som kundupplevelsen innebär.

Från paletten, till vänster på skärmen, nedanför **[!UICONTROL Events]** och **[!UICONTROL Orchestration]** hittar du **[!UICONTROL Actions]** kategori. Följande åtgärdsaktiviteter är tillgängliga:

* [E-post, SMS, push](../building-journeys/journeys-message.md)
* [Anpassade åtgärder](../building-journeys/using-custom-actions.md)
* [Hoppa](../building-journeys/jump.md)

![](assets/journey58.png)

Dessa aktiviteter representerar olika tillgängliga kommunikationskanaler. Du kan kombinera dem för att skapa ett flerkanalsscenario.

Om du har konfigurerat anpassade åtgärder visas de också här. [Läs mer](../building-journeys/using-custom-actions.md)).

## God praxis {#best-practices}

De flesta aktiviteter gör att du kan definiera en **[!UICONTROL Label]**. Detta lägger till ett suffix till namnet som visas under din aktivitet på arbetsytan. Detta är användbart om du använder samma aktivitet flera gånger under resan och vill identifiera dem enklare. Felsökningen blir också enklare om fel uppstår, vilket gör det lättare att läsa rapporterna. Du kan också lägga till ett valfritt **[!UICONTROL Description]**.

![](assets/journey59bis.png)

När ett fel inträffar i en åtgärd eller ett villkor upphör en individs resa. Det enda sättet att få den att fortsätta är att markera rutan **[!UICONTROL Add an alternative path in case of a timeout or an error]**. Se [det här avsnittet](../building-journeys/using-the-journey-designer.md#paths).

![](assets/journey42.png)
