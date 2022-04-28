---
title: Reaktionshändelser
description: Läs mer om reaktionshändelser
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 235384f3-0dce-4797-8f42-1d4d01fa42d9
source-git-commit: 5596c851b70cc38cd117793d492a15fd4ce175ef
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 3%

---

# Reaktionshändelser {#reaction-events}

>[!CONTEXTUALHELP]
>id="ajo_journey_event_reaction"
>title="Reaktionshändelser"
>abstract="Med den här aktiviteten kan du reagera på spårningsdata som är relaterade till ett meddelande som skickas inom samma resa. Vi hämtar denna information i realtid när den delas med Adobe Experience Platform."

Bland de olika aktiviteterna som finns på paletten finns de inbyggda **[!UICONTROL Reactions]** -händelse. Med den här aktiviteten kan du reagera på spårningsdata som är relaterade till ett meddelande som skickas inom samma resa. Vi hämtar denna information i realtid när den delas med Adobe Experience Platform.

Du kan reagera på klickade eller öppna meddelanden.

Du kan också använda den här funktionen för att utföra en åtgärd när det inte finns någon reaktion på dina meddelanden. Det gör du genom att skapa en andra sökväg parallellt med reaktionsaktiviteten och lägga till en vänteaktivitet. Om ingen reaktion inträffar under den period som anges i vänteaktiviteten väljs den andra banan. Du kan välja att skicka t.ex. ett uppföljningsmeddelande.

Observera att du bara kan använda en reaktionsaktivitet på arbetsytan om det finns en **Meddelande** aktivitet före.

Se [Om funktionsmakron](../building-journeys/about-journey-activities.md#action-activities).

![](assets/journey45.png)

Här följer de olika stegen för att konfigurera reaktionshändelser:

1. Lägg till en **[!UICONTROL Label]** till reaktionen. Det här steget är valfritt.
1. Välj den åtgärd som du vill reagera på i listrutan. Du kan välja vilken åtgärdsaktivitet som helst som placerats i banans tidigare steg.
1. Beroende på vilken åtgärd du har valt väljer du vad du vill reagera på.
1. Du kan definiera en timeout för en händelse (mellan 40 sekunder och 30 dagar) och en timeout-sökväg. Detta kommer att skapa en andra väg för individer som inte reagerade inom den definierade tidsperioden. När du testar en resa där en reaktionshändelse används, testläget **[!UICONTROL Wait time]** standard och minsta värde är 40 sekunder. Se [det här avsnittet](../building-journeys/testing-the-journey.md).

>[!NOTE]
>
>
>Reaktionshändelser kan inte spåra meddelanden som äger rum under en annan resa.
>
>Reaktionshändelser spårar klickningar på länkar av typen &quot;spårade&quot;. Ta inte hänsyn till länkar för att ta bort prenumerationer och spegla sidor.

>[!IMPORTANT]
>
>E-postklienter som Gmail tillåter bildblockering. E-postmeddelanden som öppnas spåras med en bild på 0 pixlar som ingår i e-postmeddelandet. Om bilder blockeras kommer e-postöppningar inte att beaktas.
