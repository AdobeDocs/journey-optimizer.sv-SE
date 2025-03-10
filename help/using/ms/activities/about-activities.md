---
solution: Journey Optimizer
product: journey optimizer
title: Arbeta med kampanjaktiviteter i flera steg
description: Lär dig hur du kan skapa kampanjaktiviteter i flera steg
hide: true
hidefromtoc: true
source-git-commit: 658d82820d3f307481c44a142c38727f777fd879
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 0%

---


# Om kampanjaktiviteter i flera steg {#ms-campaign-activities}

Flerstegskampanjer grupperas i tre kategorier. Beroende på sammanhanget kan tillgängliga aktiviteter variera.

Alla aktiviteter beskrivs i avsnitten nedan:

* [Verksamheter som rör målinriktning och datahantering](#targeting)
* [Kanalaktiviteter](#channel)
* [Flödeskontroll](#flow-control)

![](../assets/workflow-activities.png)

## Verksamheter som riktar sig till {#targeting}

Dessa aktiviteter är specifika för målgruppsanpassning. Med dem kan du skapa ett eller flera mål genom att definiera en målgrupp och dela eller kombinera dessa målgrupper med hjälp av skärnings-, union- eller uteslutningsåtgärder.

* [Skapa målgrupp](build-audience.md): Definiera målpopulationen. Du kan antingen välja en befintlig målgrupp eller använda frågemodelleraren för att definiera en egen fråga.
* [Ändra dimension](change-dimension.md): Ändra måldimensionen när du skapar en flerstegskampanj.
* [Kombinera](combine.md): Utför segmentering på den inkommande populationen. Du kan använda en union, en skärning eller ett undantag.
* [Deduplicering](deduplication.md): Ta bort dubbletter i resultatet/resultaten av inkommande aktiviteter.
* [Berikning](enrichment.md): Definiera ytterligare data som ska bearbetas i din flerstegskampanj. Med den här aktiviteten kan du utnyttja den inkommande övergången och konfigurera aktiviteten för att slutföra utdataövergången med ytterligare data.
* [Avstämning](reconciliation.md): Definiera länken mellan data i Journey Optimizer-data och data i en arbetstabell, till exempel data som lästs in från en extern fil.
* [Spara målgrupp](save-audience.md): Uppdatera en befintlig målgrupp eller skapa en ny målgrupp från populationen som beräknas uppströms i en flerstegskampanj.
* [Dela](split.md): Segmentera inkommande population i flera deluppsättningar.

## Datahanteringsaktiviteter {#data}

Dessa aktiviteter är specifika för att hantera och berika populationsdata.

* [Läs in fil](load-file.md): Arbeta med profiler och data som lagras i en extern fil.
* [Uppdatera data](update-data.md): Utför massuppdateringar för fält i databasen. Flera alternativ gör att du kan anpassa datauppdateringen.

## Kanalaktiviteter {#channel}

Med Adobe Journey Optimizer kan ni automatisera och genomföra marknadsföringskampanjer i flera kanaler. Ni kan kombinera kanalaktiviteter på arbetsytan för att skapa flerstegskampanjer för flera kanaler som kan utlösa åtgärder baserat på kundbeteende. Följande **kanalaktiviteter** är tillgängliga: E-post, SMS, Android och iOS push-meddelanden. [Lär dig hur du ställer in en leverans i samband med en flerstegskampanj](channels.md).

## Flödeskontroll {#flow-control}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_end"
>title="Avsluta aktivitet"
>abstract="Med aktiviteten **End** kan du grafiskt markera slutet av en flerstegskampanj. Denna aktivitet har ingen funktionell inverkan och är därför frivillig."

Följande aktiviteter är specifika för att organisera och köra flerstegskampanjer. Deras huvuduppgift är att samordna de övriga verksamheterna:

* [And-join](and-join.md): Synkronisera flera körningsgrenar för en flerstegskampanj.
* **Slut**: Markera grafiskt slutet på en kampanj i flera steg. Denna aktivitet har ingen funktionell inverkan och är därför valfri
* [Förgrening](fork.md): Skapa utgående övergångar om du vill starta flera aktiviteter samtidigt.
* [Schemaläggare](scheduler.md): Schemalägg när flerstegskampanjen startas.
* [Test](test.md): Aktivera övergångar baserat på angivna villkor.
* [Vänta](wait.md): Pausa körningen av en del av en flerstegskampanj tillfälligt.
