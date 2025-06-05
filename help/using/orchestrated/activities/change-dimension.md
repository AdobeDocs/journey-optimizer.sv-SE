---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Ändra dimension
description: Lär dig hur du använder aktiviteten Ändra dimension
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 83e66f10-93dd-4759-840c-2c83abc42a28
source-git-commit: 457445e1c5f3e5819b484a26e9944f1295726d1e
workflow-type: tm+mt
source-wordcount: '391'
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
| [Kom igång med samordnade kampanjer](../gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](../configuration-steps.md)<br/><br/>[Viktiga steg för att skapa samordnade kampanjer](../gs-campaign-creation.md) | [Skapa en orkestrerad kampanj](../create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](../orchestrate-activities.md)<br/><br/>[Skicka meddelanden med orkestrerade kampanjer](../send-messages.md)<br/><br/>[Starta och övervaka kampanjen](../start-monitor-campaigns.md)<br/><br/>[Rapportera](../reporting-campaigns.md) | [Arbeta med Query Modeler](../orchestrated-rule-builder.md)<br/><br/>[Skapa din första fråga](../build-query.md)<br/><br/>[Redigera uttryck](../edit-expressions.md) | [Kom igång med aktiviteter](about-activities.md)<br/><br/>Aktiviteter:<br/>[Och-join](and-join.md) - [Skapa målgrupp](build-audience.md) - [Ändra dimension](change-dimension.md) - [Kombinera](combine.md) - [Ta bort dubbletter](deduplication.md) - [Förbättra](enrichment.md) - [Förena](fork.md) - [Förena&lbrace;1 ](reconciliation.md) - [Dela](split.md) - [Vänta](wait.md) |

{style="table-layout:fixed"}

+++

<br/>

Som marknadsförare kan ni förfina målgruppsanpassningen genom att byta från en datatabell till en annan länkad enhet inom en orkestrerad kampanj. På så sätt kan ni gå över från målgruppsprofiler till fokusering på specifika åtgärder, som inköp, bokningar eller andra interaktioner.

Använd aktiviteten **[!UICONTROL Change dimension]** om du vill göra det. Det gör att ni kan ändra målinriktningsdimensionen under den samordnade kampanjen, baserat på datamodellens struktur och indatadimensionen.

Du kan till exempel ändra målinriktningsdimensionen från **Profil** till **Kontrakt** för att skicka meddelanden direkt till de avtalsägare som är kopplade till den valda målgruppen.

<!--
>[!IMPORTANT]
>
>Please note that the **[!UICONTROL Change Dimension]** and **[!UICONTROL Change Data source]** activities should not be added in one row. If you need to use both activities consecutively, make sure you include an **[!UICONTROL Enrichement]** activity in between them. This ensures proper execution and prevents potential conflicts or errors.-->

## Konfigurera aktiviteten Ändra dimension {#configure}

Följ de här stegen för att konfigurera aktiviteten **Ändra dimension**:

1. Lägg till en **Ändra dimension**-aktivitet i den orkestrerade kampanjen.

   ![](../assets/change-dimension.png)

1. Definiera den **nya måldimensionen**. Vid dimensionsändring sparas alla poster.

1. Kör den orkestrerade kampanjen för att visa resultatet. Jämför data i tabellerna före och efter ändringsdimensionsaktiviteten och jämför strukturen i de samordnade kampanjtabellerna.

## Exempel {#example}

Det här användningsexemplet innebär att ett SMS skickas till profiler som har skapat en önskelista den senaste månaden.

Börja med en **[!UICONTROL Build audience]**-aktivitet och använd målinriktningsdimensionen **Önstlista** för att välja alla relevanta önskelistor.

Infoga sedan en **[!UICONTROL Change dimension]**-aktivitet för att växla måldimensionen från **Önsklista** till **Mottagare**. Detta gör att den samordnade kampanjen kan skicka SMS:et till de profiler som är associerade med dessa önskelistor.

![](../assets/change-dimension-example.png)
