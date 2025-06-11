---
solution: Journey Optimizer
product: journey optimizer
title: Få åtkomst till och hantera samordnade kampanjer
description: Lär dig grunderna för att skapa samordnade kampanjer med Adobe Journey Optimizer
badge: label="Alpha"
hide: true
source-git-commit: 38d4cc896414fce2e8453940fb4674ce7e60fd2b
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---


# Få åtkomst till och hantera samordnade kampanjer {#orchestrated-campaign-creation}

>[!CONTEXTUALHELP]
>id="ajo_targeting_workflow_list"
>title="Samlad kampanj"
>abstract="På den här skärmen kan du få tillgång till den fullständiga listan över samordnade kampanjer, kontrollera deras aktuella status, sista/nästa körningsdatum och skapa en ny strukturerad kampanj."

Ni kan skapa samordnade kampanjer på en visuell arbetsyta för att utforma flerkanalsprocesser som segmentering, kampanjutförande och filbearbetning.

## Få tillgång till samordnade kampanjer

På menyn **[!UICONTROL Campaigns]** kan du bläddra till fliken Flerstegsfliken för att få tillgång till den fullständiga listan med samordnade kampanjer.

Varje orkestrerad kampanj i listan visar information om dess aktuella [status](#status), den senaste gången den kördes eller ändrades samt nästa schemalagda körningsdatum och -tid.

Du kan anpassa de kolumner som visas genom att klicka på ikonen **[!UICONTROL Configure column for a custom layout]** i det övre högra hörnet av listan. På så sätt kan du lägga till ytterligare information i listan, till exempel den senaste felaktiviteten för varje orkestrerad kampanj eller den använda måldimensionen.

Dessutom finns det ett sökfält och filter som gör det enklare att söka i listan. Du kan t.ex. filtrera de orkestrerade kampanjerna så att de endast visar kampanjer som tillhör en kampanj, eller kampanjer som bearbetas under ett visst datumintervall.

Om du vill duplicera eller ta bort en orkestrerad kampanj klickar du på ellipsknappen och väljer sedan **[!UICONTROL Duplicate]** eller **[!UICONTROL Delete]**.

>[!NOTE]
>
>När en orkestrerad kampanj pågår kan du duplicera den, men du kan inte ta bort den.

## Vad finns i en iscensatt kampanj? {#gs-ms-campaign-inside}

Den iscensatta kampanjarbetsytan är en representation av vad som ska hända. Det beskriver de olika åtgärder som ska utföras och hur de är sammankopplade.

![](assets/workflow-example.png){zoomable="yes"} {zoomable="yes"}

Varje orkestrerad kampanj innehåller:

* **Aktiviteter**: En aktivitet är en aktivitet som ska utföras. De olika aktiviteterna visas i diagrammet med ikoner. Varje aktivitet har specifika egenskaper och andra egenskaper som är gemensamma för alla aktiviteter.

  I ett iscensatt kampanjdiagram kan en viss aktivitet producera flera uppgifter, särskilt när det finns en slinga eller återkommande åtgärder.

* **Övergångar**: Övergångar länkar en källaktivitet till en målaktivitet och definierar deras sekvens.

* **Arbetstabeller**: Arbetstabellen innehåller all information som följer med övergången. För varje iscensatt kampanj används flera arbetstabeller. De data som förmedlas i dessa tabeller kan användas under hela den orkestrerade kampanjens livscykel.

## Status och livscykel {#status}

Kampanjer kan ha flera statusvärden:

* **[!UICONTROL Draft]**: Den orkestrerade kampanjen har skapats och sparats.
* **[!UICONTROL In progress]**: Den orkestrerade kampanjen körs för närvarande.
* **[!UICONTROL Finished]**: Den orkestrerade kampanjkörningen har slutförts.
* **[!UICONTROL Paused]**: Den orkestrerade kampanjen har pausats.
* **[!UICONTROL Erroneous]**: Den orchestrerade kampanjen påträffade ett fel. Öppna den samordnade kampanjen och gå till loggarna och aktiviteterna för att identifiera felet och åtgärda det.
