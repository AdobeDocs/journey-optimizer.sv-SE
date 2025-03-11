---
solution: Journey Optimizer
product: journey optimizer
title: Viktiga principer för att skapa kampanjer i flera steg
description: Lär dig grunderna för flerstegskampanjer med Adobe Journey Optimizer
hide: true
hidefromtoc: true
exl-id: b04aa15a-71bf-4683-bcbf-f611c189ffe1
source-git-commit: 271c4739a5537a99da981913606bc9eb099b5139
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 0%

---

# Viktiga principer för samordnade kampanjer {#ms-campaign-creation}

Med Adobe Journey Optimizer kan ni skapa flerstegskampanjer i en visuell arbetsyta för att utforma flerkanalsprocesser som segmentering, kampanjutförande och filhantering.

## Skapa en fråga

## Personalization riktlinjer

## Vad ingår i en flerstegskampanj? {#gs-ms-campaign-inside}

Kampanjarbetsytan i flera steg är en representation av vad som ska hända. Det beskriver de olika åtgärder som ska utföras och hur de är sammankopplade.

![](assets/workflow-example.png){zoomable="yes"} {zoomable="yes"}

Varje kampanj i flera steg innehåller:

* **Aktiviteter**: En aktivitet är en aktivitet som ska utföras. De olika aktiviteterna visas i diagrammet med ikoner. Varje aktivitet har specifika egenskaper och andra egenskaper som är gemensamma för alla aktiviteter.

  I ett kampanjdiagram i flera steg kan en viss aktivitet producera flera uppgifter, särskilt när det finns en slinga eller återkommande åtgärder.

* **Övergångar**: Övergångar länkar en källaktivitet till en målaktivitet och definierar deras sekvens.

* **Arbetstabeller**: Arbetstabellen innehåller all information som följer med övergången. Varje kampanj i flera steg använder flera arbetsflöden. De data som förmedlas i dessa tabeller kan användas under hela flerstegskampanjens livscykel.

## Viktiga steg för att skapa en kampanj i flera steg {#gs-ms-campaign-steps}

Så här skapar du flerstegskampanjer:

![](assets/workflow-creation-process.png){zoomable="yes"}

## Status och livscykel

Kampanjer kan ha flera statusvärden:

* **[!UICONTROL Draft]**: Flerstegskampanjen har skapats och sparats.
* **[!UICONTROL In progress]**: Flerstegskampanjen körs för närvarande.
* **[!UICONTROL Finished]**: Flerstegskampanjen har slutförts.
* **[!UICONTROL Paused]**: Flerstegskampanjen har pausats.
* **[!UICONTROL Erroneous]**: Ett fel uppstod i flerstegskampanjen. Öppna flerstegskampanjen och gå till loggarna och aktiviteterna för att identifiera felet och åtgärda det.

