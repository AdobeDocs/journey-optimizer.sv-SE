---
solution: Journey Optimizer
product: journey optimizer
title: Arbeta med samordnade kampanjaktiviteter
description: Lär dig att samordna kampanjaktiviteter
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 02f986b2-8200-4e0e-8918-44e528a6a3ec
source-git-commit: c46c202d68613f08e2d2b23ea882fb6561669b08
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---

# Om samordnade kampanjaktiviteter {#orchestrated-campaign-activities}

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](../gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](../configuration-steps.md)<br/><br/>[Viktiga steg för att skapa samordnade kampanjer](../gs-campaign-creation.md) | [Skapa en orkestrerad kampanj](../create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](../orchestrate-activities.md)<br/><br/>[Skicka meddelanden med orkestrerade kampanjer](../send-messages.md)<br/><br/>[Starta och övervaka kampanjen](../start-monitor-campaigns.md)<br/><br/>[Rapportera](../reporting-campaigns.md) | [Arbeta med Query Modeler](../orchestrated-query-modeler.md)<br/><br/>[Skapa din första fråga](../build-query.md)<br/><br/>[Redigera uttryck](../edit-expressions.md) | [Kom igång med aktiviteter](about-activities.md)<br/><br/>Aktiviteter:<br/>[Och-join](and-join.md) - [Skapa målgrupp](build-audience.md) - [Ändra dimension](change-dimension.md) - [Kombinera](combine.md) - [Ta bort dubbletter](/deduplication.md) - [Förbättra](enrichment.md) - [Förena](fork.md) - [Förena&lbrace;1 ](reconciliation.md) - [Dela](split.md) - [Vänta](wait.md) |

{style="table-layout:fixed"}

+++

<br/><br/>

Samordnade kampanjaktiviteter grupperas i tre kategorier. Beroende på sammanhanget kan tillgängliga aktiviteter variera.

Alla aktiviteter beskrivs i avsnitten nedan:

* [Verksamheter som riktar sig till](#targeting)
* [Kanalaktiviteter](#channel)
* [Flödeskontroll](#flow-control)

![Lista över tillgängliga aktiviteter på arbetsytan](../assets/workflow-activities.png){width="80%" align="left"}

## Verksamheter som riktar sig till {#targeting}

Dessa aktiviteter är specifika för målgruppsanpassning. Med dem kan du skapa ett eller flera mål genom att definiera en målgrupp och dela eller kombinera dessa målgrupper med hjälp av skärnings-, union- eller uteslutningsåtgärder.

![Lista över målinriktade aktiviteter](../assets/targeting-activities.png){width="40%" align="left"}

* [Skapa målgrupp](build-audience.md): Definiera målpopulationen. Du kan antingen välja en befintlig målgrupp eller använda frågemodelleraren för att definiera en egen fråga.
* [Ändra dimension](change-dimension.md): Ändra målinriktningsdimensionen när du skapar din samordnade kampanj.
* [Kombinera](combine.md): Utför segmentering på den inkommande populationen. Du kan använda en union, en skärning eller ett undantag.
* [Deduplicering](deduplication.md): Ta bort dubbletter i resultatet/resultaten av inkommande aktiviteter.
* [Berikning](enrichment.md): Definiera ytterligare data som ska bearbetas i den orkestrerade kampanjen. Med den här aktiviteten kan du utnyttja den inkommande övergången och konfigurera aktiviteten för att slutföra utdataövergången med ytterligare data.
* [Avstämning](reconciliation.md): Definiera länken mellan data i Journey Optimizer-data och data i en arbetstabell, till exempel data som lästs in från en extern fil.
* [Dela](split.md): Segmentera inkommande population i flera deluppsättningar.

## Kanalaktiviteter {#channel}

Med Adobe Journey Optimizer kan ni automatisera och genomföra marknadsföringskampanjer i flera kanaler. Ni kan kombinera kanalaktiviteter på arbetsytan för att skapa flerkanaliga samordnade kampanjer som kan utlösa åtgärder baserat på kundbeteende. Följande **kanalaktiviteter** är tillgängliga: E-post, SMS, Android och iOS push-meddelanden. [Lär dig hur du skapar en kanalåtgärd i samband med en orkestrerad kampanj](channels.md).

## Flödeskontroll {#flow-control}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_end"
>title="Avsluta aktivitet"
>abstract="Med aktiviteten **End** kan du grafiskt markera slutet på en orkestrerad kampanj. Denna aktivitet har ingen funktionell inverkan och är därför frivillig."

![Lista över flödeskontrollaktiviteter](../assets/flow-control-activities.png){width="30%" align="left"}

Följande aktiviteter är specifika för att organisera och köra samordnade kampanjer. Deras huvuduppgift är att samordna de övriga verksamheterna:

* [And-join](and-join.md): Synkronisera flera körningsgrenar för en orkestrerad kampanj.
* [Förgrening](fork.md): Skapa utgående övergångar om du vill starta flera aktiviteter samtidigt.
  <!--* [Test](test.md): Enable transitions based on specified conditions.-->
* [Vänta](wait.md): Pausa körningen av en del av en orkestrerad kampanj tillfälligt.

>[!NOTE]
>Aktiviteten **End** markerar slutet på en orkestrerad kampanj grafiskt. Denna aktivitet har ingen funktionell inverkan och är därför valfri
