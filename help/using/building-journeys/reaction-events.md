---
solution: Journey Optimizer
product: journey optimizer
title: Reaktionshändelser
description: Läs mer om reaktionshändelser
feature: Journeys, Activities
topic: Content Management
role: User
level: Intermediate
keywords: resa, händelser, reaktion, spårning, plattform
exl-id: 235384f3-0dce-4797-8f42-1d4d01fa42d9
version: Journey Orchestration
source-git-commit: de71f603b98c44d09ede5cc6bafc945f124ceb09
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 2%

---

# Reaktionshändelser {#reaction-events}

>[!CONTEXTUALHELP]
>id="ajo_journey_event_reaction"
>title="Reaktionshändelser"
>abstract="Med den här aktiviteten kan du reagera på spårningsdata som är relaterade till ett meddelande som skickas inom samma resa. Vi hämtar denna information i realtid när den delas med Adobe Experience Platform."

En av de olika händelseaktiviteterna som finns på paletten finns i den inbyggda **[!UICONTROL Reactions]**-händelsen. Med den här aktiviteten kan du reagera på spårningsdata som är relaterade till ett meddelande som skickas inom samma resa. Vi hämtar denna information i realtid när den delas med Adobe Experience Platform.

Du kan reagera på klickade eller öppna meddelanden.

Du kan också använda den här funktionen för att utföra en åtgärd när det inte finns någon reaktion på dina meddelanden. Det gör du genom att skapa en andra sökväg parallellt med reaktionsaktiviteten och lägga till en vänteaktivitet. Om ingen reaktion inträffar under den period som anges i vänteaktiviteten väljs den andra banan. Du kan välja att skicka t.ex. ett uppföljningsmeddelande.

Se [Om åtgärdsaktiviteter](../building-journeys/about-journey-activities.md#action-activities).

>[!IMPORTANT]
>
>En **[!UICONTROL Reaction]**-aktivitet måste placeras **omedelbart** efter en [kanalåtgärdsaktivitet](journeys-message.md) på arbetsytan för resan. Du kan inte använda en **[!UICONTROL Reaction]**-aktivitet om det inte finns någon kanalåtgärdsaktivitet innan.
>
>Placering av en **[!UICONTROL Wait]**-aktivitet eller någon annan aktivitet mellan kanalåtgärden och **[!UICONTROL Reaction]**-aktiviteten stöds inte och kan leda till att åtgärden inte fungerar som förväntat.

![Konfiguration av reaktionshändelser med kanalval och händelsetyp ](assets/journey45.png)

Här följer de olika stegen för att konfigurera reaktionshändelser:

1. Placera en **[!UICONTROL Reaction]**-aktivitet omedelbart efter en [kanalåtgärdsaktivitet](journeys-message.md) på arbetsytan för resan.
1. Lägg till en **[!UICONTROL Label]** i svaret. Det här steget är valfritt.
1. Välj den åtgärd som du vill reagera på i listrutan. Du kan välja vilken åtgärdsaktivitet som helst som placerats i banans tidigare steg.
1. Beroende på vilken åtgärd du har valt väljer du vad du vill reagera på.
1. Du kan definiera en timeout för en händelse (mellan 40 sekunder och 90 dagar) och en timeout-sökväg. Detta skapar en andra väg för individer som inte reagerade inom den angivna tiden. När du testar en resa som använder en reaktionshändelse är standardvärdet **[!UICONTROL Wait time]** och minimivärdet 40 sekunder. Se [det här avsnittet](../building-journeys/testing-the-journey.md).

>[!NOTE]
>
>
>Reaktionshändelser kan inte spåra meddelanden som äger rum under en annan resa.
>
>Reaktionshändelser spårar klickningar på länkar av typen &quot;spårade&quot;. Ta inte hänsyn till länkar för att ta bort prenumerationer och spegla sidor.

>[!IMPORTANT]
>
>E-postklienter som Gmail tillåter bildblockering. E-postöppningar spåras med en bild på 0 pixlar som ingår i e-postmeddelandet. Om bilder blockeras kommer e-postöppningar inte att beaktas.
