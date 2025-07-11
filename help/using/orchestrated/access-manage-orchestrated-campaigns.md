---
solution: Journey Optimizer
product: journey optimizer
title: Få åtkomst till och hantera samordnade kampanjer
description: Lär dig grunderna för att skapa samordnade kampanjer med Adobe Journey Optimizer
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 7b42d317-cd01-4c6a-b61e-5b03e5a8ff3c
source-git-commit: d464668582fbb4bea6f8d4ef57e17f80b5d83378
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 0%

---

# Få åtkomst till och hantera samordnade kampanjer {#orchestrated-campaign-creation}

>[!CONTEXTUALHELP]
>id="ajo_targeting_workflow_list"
>title="Samlad kampanj"
>abstract="På den här skärmen kan du få tillgång till den fullständiga listan över samordnade kampanjer, kontrollera deras aktuella status, sista/nästa körningsdatum och skapa en ny strukturerad kampanj."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_campaign_action"
>title="Åtgärd"
>abstract="I det här avsnittet visas alla åtgärder som används i den samordnade kampanjen."

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](configuration-steps.md)<br/><br/><b>[Få åtkomst till och hantera samordnade kampanjer](access-manage-orchestrated-campaigns.md)</b><br/><br/>[Viktiga steg för att skapa en strukturerad kampanj](gs-campaign-creation.md) | [Skapa och schemalägg kampanjen](create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](start-monitor-campaigns.md)<br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med regelbyggaren](orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md)<br/><br/>[Återmarknadsföring](retarget.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](activities/and-join.md) - [Bygg målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kanalaktiviteter](activities/channels.md) - [Kombinera](activities/combine.md) - [Deduplicering](activities/deduplication.md) - [Enrichment](activities/enrichment.md) - [Fork](activities/fork.md)  - [Avstämning](activities/reconciliation.md) - [Spara målgrupp](activities/save-audience.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

<br/>

## Få tillgång till samordnade kampanjer

Navigera till menyn **[!UICONTROL Campaigns]** och välj fliken **[!UICONTROL Orchestration]** för att få tillgång till den fullständiga listan över samordnade kampanjer.

![bild som visar det orkestrerade kampanjlagret](assets/inventory.png){zoomable="yes"}{zoomable="yes"}

Varje orkestrerad kampanj i listan visar information som kampanjens aktuella [status](#status), den associerade kanalen och de associerade taggarna eller den senaste gången den ändrades. Du kan anpassa de kolumner som visas genom att klicka på knappen ![Konfigurera layout](assets/do-not-localize/inventory-configure-layout.svg) .

Dessutom finns det ett sökfält och filter som gör det enklare att söka i listan. Du kan t.ex. filtrera de orkestrerade kampanjerna så att endast de som är kopplade till en viss kanal eller tagg visas, eller de som har skapats under ett visst datumintervall.

![Bilden som visar knappen Fler åtgärder](assets/do-not-localize/rule-builder-icon-more.svg) i kampanjinventeringen gör att du kan utföra olika åtgärder som beskrivs nedan.

![bilden av kampanjlagret](assets/inventory-actions.png)

* **[!UICONTROL View all time report]** / **[!UICONTROL View last 24 hours report]** - Få tillgång till rapporter för att mäta och visualisera effekten och resultatet av dina samordnade kampanjer. [Läs mer om rapportering av samordnade kampanjer](../orchestrated/reporting-campaigns.md)
* **[!UICONTROL Edit tags]** - Redigera de taggar som är associerade med kampanjen.
* **[!UICONTROL Duplicate]** - I vissa fall kan du behöva duplicera en orchestrerad kampanj, till exempel för att köra en kampanj som har stoppats eller för att ändra körningsfrekvensen för en schemalagd kampanj.
* **[!UICONTROL Delete]** - Ta bort kampanjen. Den här åtgärden är endast tillgänglig för **[!UICONTROL Draft]** kampanjer.
* **[!UICONTROL Archive]** - Arkivera kampanjen. Alla arkiverade kampanjer tas bort 30 dagar efter det att de senast ändrades. Den här åtgärden är tillgänglig för alla kampanjer förutom **[!UICONTROL Draft]** kampanjer.

## Vad finns i en iscensatt kampanj? {#gs-ms-campaign-inside}

Den iscensatta kampanjarbetsytan är en representation av vad som ska hända. Det beskriver de olika åtgärder som ska utföras och hur de är sammankopplade.

![bild som visar en orkestrerad kampanjarbetsyta](assets/canvas-example.png)

Varje orkestrerad kampanj innehåller:

* **Aktiviteter**: En aktivitet är en aktivitet som ska utföras. De olika aktiviteterna visas i diagrammet med ikoner. Varje aktivitet har specifika egenskaper och andra egenskaper som är gemensamma för alla aktiviteter.

  I ett iscensatt kampanjdiagram kan en viss aktivitet producera flera uppgifter, särskilt när det finns en slinga eller återkommande åtgärder.

* **Övergångar**: Övergångar länkar en källaktivitet till en målaktivitet och definierar deras sekvens.

* **Arbetstabeller**: Arbetstabellen innehåller all information som följer med övergången. För varje iscensatt kampanj används flera arbetstabeller. De data som förmedlas i dessa tabeller kan användas under hela den orkestrerade kampanjens livscykel.

## Kampanjstatus {#status}

Samordnade kampanjer kan ha flera statusvärden:

* **[!UICONTROL Draft]**: Den orkestrerade kampanjen har skapats. Den har inte publicerats än.
* **[!UICONTROL Publishing]**: Den orkestrerade kampanjen publiceras.
* **[!UICONTROL Live]**: Den orkestrerade kampanjen har publicerats och körs.
* **[!UICONTROL Scheduled]**: Den samordnade kampanjkörningen har schemalagts.
* **[!UICONTROL Completed]**: Den orkestrerade kampanjkörningen har slutförts. Statusen Slutförd tilldelas automatiskt upp till 3 dagar efter det att en kampanj har slutfört meddelanden som skickas utan fel.
* **[!UICONTROL Closed]**: Den här statusen visas när en återkommande kampanj har stängts. Kampanjen fortsätter att köras tills alla dess aktiviteter har slutförts, men inga fler profiler kan gå in i kampanjen.
* **[!UICONTROL Archived]**: Den orkestrerade kampanjen har arkiverats. Alla arkiverade kampanjer tas bort vid en rullande tidplan 30 dagar efter det senaste ändringsdatumet. Du kan duplicera en arkiverad kampanj om det behövs för att fortsätta arbeta med den.
* **[!UICONTROL Stopped]**: Den orkestrerade kampanjkörningen har stoppats. Om du vill starta kampanjen igen måste du duplicera den.
