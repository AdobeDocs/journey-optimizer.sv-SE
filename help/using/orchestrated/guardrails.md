---
solution: Journey Optimizer
product: journey optimizer
title: Samordnade kampanjer skyddar mot detaljer och begränsningar
description: Läs mer om säkra kampanjer och begränsningar
hide: true
hidefromtoc: true
source-git-commit: 54d5b3386da4eed53fca79a2135ab54548855150
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 0%

---

# Skyddsritningar och begränsningar {#guardrails}

>[!CONTEXTUALHELP]
>id="ajo_campaign_publication"
>title="Publicera orkestrerad kampanj"
>abstract="Du måste publicera kampanjen för att kunna starta den. Kontrollera att alla varningar är rensade före publiceringen."

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](configuration-steps.md)<br/><br/>[Få åtkomst till och hantera samordnade kampanjer](access-manage-orchestrated-campaigns.md)<br/><br/>[Viktiga steg för att skapa en strukturerad kampanj](gs-campaign-creation.md) | [Skapa och schemalägg kampanjen](create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](start-monitor-campaigns.md)<br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med regelbyggaren](orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md)<br/><br/>[Återmarknadsföring](retarget.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](activities/and-join.md) - [Bygg målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kanalaktiviteter](activities/channels.md) - [Kombinera](activities/combine.md) - [Deduplicering](activities/deduplication.md) - [Enrichment](activities/enrichment.md) - [Fork](activities/fork.md)  - [Avstämning](activities/reconciliation.md) - [Spara målgrupp](activities/save-audience.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

## Begränsningar för dataflöde till datauppsättning

Varje datauppsättning i Adobe Experience Platform kan bara kopplas till ett aktivt dataflöde i taget. Denna 1:1-kardinalitet används strikt av plattformen.

Om du behöver byta datakälla (t.ex. från Amazon S3 till Salesforce):

Du måste ta bort det befintliga dataflödet som är anslutet till datauppsättningen.

Skapa sedan ett nytt dataflöde med den nya källan mappad till samma datauppsättning.

Detta garanterar tillförlitlig datainhämtning och är nödvändigt när du använder Change Data Capture (CDC), som är beroende av en definierad primärnyckel och ett versionsattribut (t.ex. lastmodifierad) för inkrementella uppdateringar.


## Relationsscheman/begränsningar för dataöverföring

* Antal scheman - Det maximala antalet relationsscheman (tabeller i relationsdatalagret) är 200
* Relationsschemastorlek - maximal relationsschemastorlek för kampanjsamordning blir 100 GB.
* Dataöverföringsfrekvens - batchdatainmatningsfrekvens för kampanjsamordning får inte överstiga en var femton:e minut.
* Ändringar/uppdateringar - Dagliga uppdateringar/ändringar ska vara mindre än 20 % av det totala antalet poster för ett givet relationsschema