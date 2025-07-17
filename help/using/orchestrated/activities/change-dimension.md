---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Ändra dimension
description: Lär dig hur du använder aktiviteten Ändra dimension
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 83e66f10-93dd-4759-840c-2c83abc42a28
source-git-commit: 25120dd71159d0233783ac4c189f528ff2c93ae3
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 0%

---

# Ändra dimension {#change-dimension}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_dimension_complement"
>title="Generera ett komplement"
>abstract="Du kan generera ytterligare en utgående övergång med den återstående populationen, som har uteslutits som en dubblett. Aktivera alternativet **Generera komplement** om du vill göra det."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_change_dimension"
>title="Ändra dimensionsaktivitet"
>abstract="Med den här aktiviteten kan ni ändra målgruppsdimensionen när ni skapar en målgrupp. Axeln flyttas beroende på datamallen och indatamängden. Du kan till exempel växla från dimensionen &quot;kontrakt&quot; till dimensionen &quot;kunder&quot;."

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](../gs-orchestrated-campaigns.md)<br/><br/>Skapa och hantera relationsscheman och datauppsättningar:</br> <ul><li>[Manuellt schema](../manual-schema.md)</li><li>[Filöverföringsschema](../file-upload-schema.md)</li><li>[Ingest data](../ingest-data.md)</li></ul>[Få åtkomst till och hantera samordnade kampanjer](../access-manage-orchestrated-campaigns.md) | [Viktiga steg för att skapa en orkestrerad kampanj](../gs-campaign-creation.md)<br/><br/>[Skapa och schemalägg kampanjen](../create-orchestrated-campaign.md)<br/><br/>[Orchestrate-aktiviteter](../orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](../start-monitor-campaigns.md)<br/><br/>[Rapportera](../reporting-campaigns.md) | [Arbeta med regelbyggaren](../orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](../build-query.md)<br/><br/>[Redigera uttryck](../edit-expressions.md)<br/><br/>[Återmarknadsföring](../retarget.md) | [Kom igång med aktiviteter](about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](and-join.md) - [Bygg målgrupp](build-audience.md) - <b>[Ändra dimension](change-dimension.md)</b> - [Kanalaktiviteter](channels.md) - [Kombinera](combine.md) - [Deduplicering](deduplication.md) - [Enrichment](enrichment.md) - [Fork](fork.md)  - [Avstämning](reconciliation.md) - [Spara målgrupp](save-audience.md) - [Dela](split.md) - [Vänta](wait.md) |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

Innehållet på den här sidan är inte slutgiltigt och kan komma att ändras.

>[!ENDSHADEBOX]

Som marknadsförare kan ni förbättra målgruppsanpassningen genom att gå över från en datatabell till en relaterad enhet i en strukturerad kampanj. På så sätt kan du gå steget längre än användarprofiler och fokusera på specifika beteenden som inköp, bokningar eller andra interaktioner.

Använd aktiviteten **[!UICONTROL Change dimension]** för att uppnå detta. Ni kan anpassa målinriktningsdimensionen under den samordnade kampanjen.

<!--
>[!IMPORTANT]
>
>Please note that the **[!UICONTROL Change Dimension]** and **[!UICONTROL Change Data source]** activities should not be added in one row. If you need to use both activities consecutively, make sure you include an **[!UICONTROL Enrichement]** activity in between them. This ensures proper execution and prevents potential conflicts or errors.-->

## Konfigurera aktiviteten Ändra dimension {#configure}

Så här konfigurerar du aktiviteten **[!UICONTROL Change dimension]**:

1. Lägg till en **[!UICONTROL Change dimension]**-aktivitet i din samordnade kampanj.

   ![](../assets/orchestrated-change-dimension.png)

1. Definiera **[!UICONTROL New target dimension]**. Vid dimensionsändring sparas alla poster.


## Exempel {#example}

Det här användningsexemplet fokuserar på att skicka ett SMS till profiler som har skapat en önskelista under den senaste månaden.

Börja med en **[!UICONTROL Build audience]**-aktivitet och använd målinriktningsdimensionen **[!UICONTROL Wishlist]** för att identifiera alla relevanta önskelistor.

Lägg sedan till en **[!UICONTROL Change dimension]**-aktivitet för att växla måldimensionen från **[!UICONTROL Wishlist]** till **[!UICONTROL Recipient].** Det här steget ser till att den orkestrerade kampanjen har rätt profiler länkade till dessa önskelistor, vilket gör att SMS:et kan skickas till de avsedda profilerna.

![](../assets/orchestrated-change-dimension-example.png)
