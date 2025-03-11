---
solution: Journey Optimizer
product: journey optimizer
title: Viktiga principer för att skapa kampanjer i flera steg
description: Lär dig grunderna för flerstegskampanjer med Adobe Journey Optimizer
hide: true
hidefromtoc: true
exl-id: b04aa15a-71bf-4683-bcbf-f611c189ffe1
source-git-commit: 3ecb1691cc8a1c429d9bd9919b06ddc5a316eff7
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 0%

---

# Viktiga principer {#ms-campaign-creation}

>[!CONTEXTUALHELP]
>id="ajo_targeting_workflow_list"
>title="Flerstegskampanj"
>abstract="På den här skärmen kan du få tillgång till den fullständiga listan över flerstegskampanjer, kontrollera deras aktuella status, senaste/nästa körningsdatum och skapa en ny flerstegskampanj."

Med Adobe Journey Optimizer kan ni skapa flerstegskampanjer i en visuell arbetsyta för att utforma flerkanalsprocesser som segmentering, kampanjutförande och filhantering.

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

## Få tillgång till flerstegskampanjer

På menyn **[!UICONTROL Campaigns]** kan du bläddra till fliken Flersteg för att få tillgång till den fullständiga listan över flerstegskampanjer.

Varje kampanj i flera steg i listan visar information om dess aktuella [status](#status), den senaste gången den kördes eller ändrades samt nästa schemalagda körningsdatum och -tid.

Du kan anpassa de kolumner som visas genom att klicka på ikonen **[!UICONTROL Configure column for a custom layout]** i det övre högra hörnet av listan. På så sätt kan du lägga till ytterligare information i listan, t.ex. den senaste felaktiviteten för varje flerstegskampanj eller den använda måldimensionen.

Dessutom finns det ett sökfält och filter som gör det enklare att söka i listan. Du kan t.ex. filtrera flerstegskampanjer så att de endast visas för kampanjer som tillhör en kampanj, eller kampanjer som bearbetas under ett visst datumintervall.

Om du vill duplicera eller ta bort en kampanj i flera steg klickar du på ellipsknappen och väljer sedan **[!UICONTROL Duplicate]** eller **[!UICONTROL Delete]**.

>[!NOTE]
>
>När en kampanj i flera steg pågår kan du duplicera den, men du kan inte ta bort den.

## Status och livscykel {#status}

Kampanjer kan ha flera statusvärden:

* **[!UICONTROL Draft]**: Flerstegskampanjen har skapats och sparats.
* **[!UICONTROL In progress]**: Flerstegskampanjen körs för närvarande.
* **[!UICONTROL Finished]**: Flerstegskampanjen har slutförts.
* **[!UICONTROL Paused]**: Flerstegskampanjen har pausats.
* **[!UICONTROL Erroneous]**: Ett fel uppstod i flerstegskampanjen. Öppna flerstegskampanjen och gå till loggarna och aktiviteterna för att identifiera felet och åtgärda det.


## Skapa en fråga

## Personalization riktlinjer
