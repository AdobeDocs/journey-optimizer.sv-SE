---
solution: Journey Optimizer
product: journey optimizer
title: Använda aktiviteten Spara målgrupp
description: Lär dig hur du använder aktiviteten Spara som i en strukturerad kampanj
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 7b5b03ba-fbb1-4916-8c72-10778752d8e4
source-git-commit: 6eb49e954b7906f668b1c1779c16f3e67003307b
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Spara målgrupp {#save-audience}

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](../gs-orchestrated-campaigns.md)<br/><br/>Skapa och hantera relationsscheman och datauppsättningar:</br> <ul><li>[Manuellt schema](../manual-schema.md)</li><li>[Filöverföringsschema](../file-upload-schema.md)</li><li>[Ingest data](../ingest-data.md)</li></ul><br/><br/>[Få åtkomst till och hantera samordnade kampanjer](../access-manage-orchestrated-campaigns.md) | [Viktiga steg för att skapa en orkestrerad kampanj](../gs-campaign-creation.md)<br/><br/>[Skapa och schemalägg kampanjen](../create-orchestrated-campaign.md)<br/><br/>[Orchestrate-aktiviteter](../orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](../start-monitor-campaigns.md)<br/><br/>[Rapportera](../reporting-campaigns.md) | [Arbeta med regelbyggaren](../orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](../build-query.md)<br/><br/>[Redigera uttryck](../edit-expressions.md)<br/><br/>[Återmarknadsföring](../retarget.md) | [Kom igång med aktiviteter](about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](and-join.md) - [Bygg målgrupp](build-audience.md) - [Ändra dimension](change-dimension.md) - [Kanalaktiviteter](channels.md) - [Kombinera](combine.md) - [Deduplicering](deduplication.md) - [Enrichment](enrichment.md) - [Fork](fork.md)  - [Avstämning](reconciliation.md) - <b>[Spara målgrupp](save-audience.md)</b> - [Dela](split.md) - [Vänta](wait.md) |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

Innehållet på den här sidan är inte slutgiltigt och kan komma att ändras.

>[!ENDSHADEBOX]

Aktiviteten **[!UICONTROL Save audience]** är en **[!UICONTROL Targeting]**-aktivitet som gör att du kan uppdatera en befintlig målgrupp eller skapa en ny från den tidigare populationen i den orkestrerade kampanjen. När de har skapats läggs dessa målgrupper till i listan över programmålgrupper och kan nås från menyn **[!UICONTROL Audiences]**.

Denna aktivitet är särskilt användbar för att bevara målgruppssegment som beräknas inom samma samordnade kampanj, så att de blir tillgängliga för återanvändning i framtida kampanjer. Den är vanligtvis kopplad till andra målinriktningsaktiviteter, som **[!UICONTROL Build audience]** eller **[!UICONTROL Combine]**, för att hämta och spara den resulterande populationen.

## Konfigurera aktiviteten Spara målgrupp {#save-audience-configuration}

Så här konfigurerar du aktiviteten **[!UICONTROL Save audience]**:

1. Lägg till en **[!UICONTROL Save audience]**-aktivitet i din samordnade kampanj.

1. Ange en **[!UICONTROL Audience label]** som identifierar den sparade målgruppen.

1. Klicka på **[!UICONTROL Add audience attribute]** för att definiera hur målgruppsdata ska struktureras och lagras för framtida återanvändning.

   ![](../assets/save-audience-1.png)

1. Välj sedan lämplig **[!UICONTROL Primary identity field]**-&#x200B; och **[!UICONTROL Identity namespace]** för att säkerställa korrekt profilupplösning.

   ![](../assets/save-audience-2.png)

1. Slutför konfigurationen genom att spara och publicera den orkestrerade kampanjen. Detta genererar och lagrar er målgrupp.

Innehållet i den sparade målgruppen är sedan tillgängligt i detaljvyn för målgruppen, som du kommer åt via menyn **[!UICONTROL Audiences]**.

![](../assets/save-audience-3.png)

## Exempel {#save-audience-example}

I följande exempel visas hur du skapar en enkel målgrupp med målinriktning. En fråga identifierar alla profiler som har köpt något under de senaste 30 dagarna. Aktiviteten **[!UICONTROL Save audience]** hämtar sedan dessa profiler för att skapa en återanvändbar målgrupp med nyligen använda köpare.

![](../assets/save-audience-4.png)
