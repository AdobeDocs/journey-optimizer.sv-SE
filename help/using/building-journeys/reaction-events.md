---
solution: Journey Optimizer
product: journey optimizer
title: Reaktionshändelser
description: Lär dig hur du använder reaktionshändelser för att svara på data om meddelandespårning, som öppningar och klickningar inom dina resor, och konfigurera timeoutsökvägar för deltagare som inte svarar.
feature: Journeys, Activities
topic: Content Management
role: User
level: Intermediate
keywords: resa, händelser, reaktion, spårning, plattform
exl-id: 235384f3-0dce-4797-8f42-1d4d01fa42d9
version: Journey Orchestration
source-git-commit: 97fa287d94efb7fb95817fc15268e736517cb629
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 2%

---

# Reaktionshändelser {#reaction-events}

>[!CONTEXTUALHELP]
>id="ajo_journey_event_reaction"
>title="Reaktionshändelser"
>abstract="Med den här aktiviteten kan du reagera på spårningsdata som är relaterade till ett meddelande som skickas inom samma resa. Den här informationen registreras i realtid när den delas med [!DNL Adobe Experience Platform]."

## Översikt {#overview}

En av de olika händelseaktiviteterna som finns på paletten finns i den inbyggda **[!UICONTROL Reactions]**-händelsen. Med den här aktiviteten kan du reagera på spårningsdata som är relaterade till ett meddelande som skickas inom samma resa. Den här informationen registreras i realtid när den delas med [!DNL Adobe Experience Platform].

Du kan reagera på klickade eller öppna meddelanden. Du kan till exempel skicka ett annat meddelande om en person har öppnat det tidigare e-postmeddelandet eller klickat i det, eller skicka ett annat uppföljningsmeddelande om personen inte har interagerat med din kommunikation.

Se [Åtgärder](../building-journeys/about-journey-activities.md#action-activities).

Du kan använda aktiviteten **[!UICONTROL Reaction]** för att utföra en åtgärd när det inte finns någon reaktion på dina meddelanden. Det gör du genom att skapa en andra sökväg som är parallell med aktiviteten **[!UICONTROL Reaction]** och lägga till en aktivitet av typen **[!UICONTROL Wait]**. Om ingen reaktion inträffar under den period som definierats i aktiviteten **[!UICONTROL Wait]** väljs den andra sökvägen. Du kan välja att skicka t.ex. ett uppföljningsmeddelande.

## Konfigurera reaktionshändelser {#configure}

![Konfiguration av reaktionshändelser med kanalval och händelsetyp &#x200B;](assets/journey45.png)

Följ de här stegen för att konfigurera reaktionshändelser:

1. Placera en **[!UICONTROL Reaction]**-aktivitet **omedelbart** efter en [kanalåtgärdsaktivitet](journey-action.md) på arbetsytan för resan.
1. Lägg till en **[!UICONTROL Label]** i svaret. Det här steget är valfritt.
1. Välj den åtgärd som du vill reagera på i listrutan. Du kan välja vilken åtgärdsaktivitet som helst som placerats i banans tidigare steg.
1. Beroende på vilken åtgärd du har valt väljer du vad du vill reagera på.
1. Du kan definiera en timeout för en händelse (mellan 40 sekunder och 90 dagar) och en timeout-sökväg. Detta skapar en andra väg för individer som inte reagerade inom den angivna tiden. När du testar en resa som använder en reaktionshändelse är standardvärdet **[!UICONTROL Wait time]** och minimivärdet 40 sekunder. Se [det här avsnittet](../building-journeys/testing-the-journey.md).

## Skyddsritningar och begränsningar {#guardrails-limitations}

* En **[!UICONTROL Reaction]**-aktivitet måste placeras **omedelbart** efter en [kanalåtgärdsaktivitet](journey-action.md) på arbetsytan för resan.
* Du kan inte använda en **[!UICONTROL Reaction]**-aktivitet om det inte finns någon kanalåtgärdsaktivitet innan.
* Placering av en **[!UICONTROL Wait]**-aktivitet eller någon annan aktivitet mellan kanalåtgärden och **[!UICONTROL Reaction]**-aktiviteten stöds inte och kan leda till att åtgärden inte fungerar som förväntat.
* Reaktionshändelser kan bara spåra meddelanden som skickas inom samma resa. De kan inte spåra meddelanden som äger rum under en annan resa.
* Reaktionshändelser spårar klickningar på länkar av typen &quot;spårade&quot;. Ta inte hänsyn till länkar för att ta bort prenumerationer och spegla sidor.
* E-postöppningar spåras med en bild på 0 pixlar som ingår i e-postmeddelandet. Om e-postklienter (t.ex. Gmail) blockerar bilder tas ingen hänsyn till e-postöppningar.
