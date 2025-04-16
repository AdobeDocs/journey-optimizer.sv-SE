---
solution: Journey Optimizer
product: journey optimizer
title: Arbeta med orkestrerade kampanjaktiviteter
description: Lär dig hur du orkestrerar kampanjaktiviteter
hide: true
hidefromtoc: true
exl-id: 02f986b2-8200-4e0e-8918-44e528a6a3ec
source-git-commit: 3d380d2d02eb7043aebcffd00bb2092e7341b0d5
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 0%

---

# Om orkestrerade kampanjaktiviteter {#ms-campaign-activities}

Orkestrerade kampanjaktiviteter grupperas i tre kategorier. Beroende på sammanhanget kan tillgängliga aktiviteter skilja sig åt.

Alla aktiviteter beskrivs i avsnitten nedan:

* [Verksamheter som rör målinriktning och datahantering](#targeting)
* [Kanalaktiviteter](#channel)
* [Flödeskontroll](#flow-control)

![](../assets/workflow-activities.png)

## Verksamheter som riktar sig till {#targeting}

Dessa aktiviteter är specifika för målgruppsanpassning. Med dem kan du skapa ett eller flera mål genom att definiera en målgrupp och dela eller kombinera dessa målgrupper med hjälp av skärnings-, union- eller uteslutningsåtgärder.

* [Bygg upp målgrupp](build-audience.md): Definiera din målgrupp. Du kan antingen välja en befintlig målgrupp eller använda frågemodelleraren för att definiera en egen fråga.
* [Ändra dimension](change-dimension.md): Ändra måldimensionen när du skapar din orkestrerade kampanj.
* [Kombinera](combine.md): Utför segmentering på din inkommande population. Du kan använda en fackförening, en skärningspunkt eller en uteslutning.
* [Deduplicering](deduplication.md): Ta bort dubbletter i resultaten av de inkommande aktiviteterna.
* [Berikning](enrichment.md): Definiera ytterligare data som ska bearbetas i den orkestrerade kampanjen. Med den här aktiviteten kan du utnyttja den inkommande övergången och konfigurera aktiviteten för att slutföra utdataövergången med ytterligare data.
* [Avstämning](reconciliation.md): Definiera länken mellan data i Journey Optimizer-data och data i en arbetstabell, till exempel data som lästs in från en extern fil.
* [Spara målgrupp](save-audience.md): Uppdatera en befintlig målgrupp eller skapa en ny målgrupp från populationen som beräknas uppströms i en orkestrerad kampanj.
* [Dela](split.md): Segmentera inkommande population i flera deluppsättningar.

## Datahanteringsaktiviteter {#data}

Dessa aktiviteter är specifika för att hantera och berika populationsdata.

* [Läs in fil](load-file.md): Arbeta med profiler och data som lagras i en extern fil.
* [Uppdatera data](update-data.md): Utför massuppdateringar av fält i databasen. Det finns flera alternativ som gör att du kan anpassa datauppdateringen.

## Kanalens aktiviteter {#channel}

Med Adobe Journey Optimizer kan ni automatisera och genomföra marknadsföringskampanjer i flera kanaler. Ni kan kombinera kanalaktiviteter på arbetsytan för att skapa flerkanaliga samordnade kampanjer som kan utlösa åtgärder baserat på kundbeteende. Följande **kanalaktiviteter** är tillgängliga: E-post, SMS, Android och iOS push-meddelanden. [Lär dig hur du ställer in en leverans i samband med en orkestrerad kampanj](channels.md).

## Flödeskontroll {#flow-control}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_end"
>title="Avsluta aktivitet"
>abstract="Med aktiviteten **End** kan du grafiskt markera slutet på en orkestrerad kampanj. Denna aktivitet har ingen funktionell inverkan och är därför frivillig."

Följande aktiviteter är specifika för att organisera och köra samordnade kampanjer. Deras huvuduppgift är att samordna de övriga verksamheterna:

* [And-join](and-join.md): Synkronisera flera körningsgrenar i en orkestrerad kampanj.
* **Slut**: Markera grafiskt slutet på en orkestrerad kampanj. Denna verksamhet har ingen funktionell inverkan och är därför frivillig
* [Förgrening](fork.md): Skapa utgående övergångar för att starta flera aktiviteter samtidigt.
* [Scheduler](scheduler.md): Schemalägg när den orkestrerade kampanjen startar.
* [Test](test.md): Aktivera övergångar baserat på angivna villkor.
* [Vänta](wait.md): Pausa körningen av en del av en orkestrerad kampanj tillfälligt.
