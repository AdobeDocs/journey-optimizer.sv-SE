---
solution: Journey Optimizer
product: journey optimizer
title: Använda aktiviteten Kombinera
description: Lär dig använda aktiviteten Kombinera
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: af3c3a9c-8172-43b0-bba1-4a3d068b9a9e
source-git-commit: 3be1b238962fa5d0e2f47b64f6fa5ab4337272a5
workflow-type: tm+mt
source-wordcount: '1080'
ht-degree: 2%

---

# Kombinera {#combine}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_combine"
>title="Kombinera aktivitet"
>abstract="Med aktiviteten **Kombinera** kan du utföra segmentering på den inkommande populationen. Du kan alltså kombinera flera populationer, exkludera delar av dem eller bara behålla data som är gemensamma för flera mål."

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](../gs-orchestrated-campaigns.md)<br/><br/>Skapa och hantera relationsscheman och datauppsättningar:</br> <ul><li>[Kom igång med scheman och datauppsättningar](../gs-schemas.md)</li><li>[Manuellt schema](../manual-schema.md)</li><li>[Filöverföringsschema](../file-upload-schema.md)</li><li>[Ingest data](../ingest-data.md)</li></ul>[Få åtkomst till och hantera samordnade kampanjer](../access-manage-orchestrated-campaigns.md) | [Viktiga steg för att skapa en orkestrerad kampanj](../gs-campaign-creation.md)<br/><br/>[Skapa och schemalägg kampanjen](../create-orchestrated-campaign.md)<br/><br/>[Orchestrate-aktiviteter](../orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](../start-monitor-campaigns.md)<br/><br/>[Rapportera](../reporting-campaigns.md) | [Arbeta med regelbyggaren](../orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](../build-query.md)<br/><br/>[Redigera uttryck](../edit-expressions.md)<br/><br/>[Återmarknadsföring](../retarget.md) | [Kom igång med aktiviteter](about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](and-join.md) - [Bygg målgrupp](build-audience.md) - [Ändra dimension](change-dimension.md) - [Kanalaktiviteter](channels.md) - <b>[Kombinera](combine.md)</b> - [Deduplicering](deduplication.md) - [Enrichment](enrichment.md) - [Fork](fork.md)  - [Avstämning](reconciliation.md) - [Spara målgrupp](save-audience.md) - [Dela](split.md) - [Vänta](wait.md) |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

</br>

Innehållet på den här sidan är inte slutgiltigt och kan komma att ändras.

>[!ENDSHADEBOX]

Aktiviteten **[!UICONTROL Combine]** är en typ av **[!UICONTROL Targeting]**-aktivitet som gör att du kan segmentera den inkommande populationen effektivt. Det gör att du kan sammanfoga flera populationer, exkludera specifika segment eller behålla endast data som delas över flera mål.

Följande segmenteringsalternativ är tillgängliga:

* **[!UICONTROL Union]**: sammanfogar resultaten av flera aktiviteter till ett enda enhetligt mål.

* **[!UICONTROL Intersection]**: behåller endast de element som är gemensamma för alla inkommande populationer.

* **[!UICONTROL Exclusion]**: tar bort element från en population baserat på angivna villkor.

## Konfigurera Kombinera-aktiviteten {#combine-configuration}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_intersection_merging_options"
>title="Sammanfogningsalternativ för skärningar"
>abstract="Med skärningspunkten kan du bara behålla de element som är gemensamma för de olika inkommande populationerna i aktiviteten. Markera alla tidigare aktiviteter som du vill ansluta till i sektionen Uppsättningar att ansluta."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_exclusion_merging_options"
>title="Alternativ för uteslutningssammanslagning"
>abstract="Med det här undantaget kan du utesluta element från en population enligt vissa kriterier. Markera alla tidigare aktiviteter som du vill ansluta till i sektionen Uppsättningar att ansluta."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_combine_options"
>title="Välj segmenteringstyp"
>abstract="Välj hur målgrupper ska kombineras. Med **Union** kan du gruppera om resultatet av flera aktiviteter till ett enda mål. Med **skärningspunkten** kan du bara behålla element som är gemensamma för de olika inkommande populationerna i aktiviteten. Med **Uteslutning** kan du utesluta element från en population enligt vissa villkor. "

Följ de här vanliga stegen för att börja konfigurera aktiviteten **[!UICONTROL Combine]**:

![](../assets/orchestrated-union.png)

1. Lägg till flera aktiviteter, till exempel **[!UICONTROL Build audience]** aktiviteter, för att skapa minst två olika körningsgrenar.
1. Lägg till en **[!UICONTROL Combine]**-aktivitet i någon av de tidigare grenarna.
1. Välj segmenteringstyp: [union](#union), [skärningspunkt](#intersection) eller [exkludering](#exclusion).
1. Klicka på **[!UICONTROL Continue]**.
1. I avsnittet **[!UICONTROL Sets to join]** markerar du alla tidigare aktiviteter du vill gå med i.

## Sammanslutning {#combine-union}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_combine_reconciliation"
>title="Avstämningsalternativ"
>abstract="Välj **Avstämningstypen** för att definiera hur dubbletter ska hanteras. Som standard är alternativet **Tangenter** aktiverat, vilket innebär att aktiviteten bara behåller ett element när element från olika inkommande övergångar har samma nyckel. Använd alternativet **Ett urval kolumner** för att definiera listan med kolumner som datavstämningen ska användas på."

Inom aktiviteten **[!UICONTROL Combine]** kan du konfigurera en **[!UICONTROL Union]** genom att välja en **[!UICONTROL Reconciliation type]** för att avgöra hur dubblettposter hanteras:

* **[!UICONTROL Keys only]** (standard): behåller en post när flera inkommande övergångar delar samma nyckel. Detta alternativ är endast tillämpligt när de inkommande populationerna är homogena.

* **[!UICONTROL A selection of columns]**: gör att du kan ange vilka kolumner som ska användas för datavstämning. Välj **[!UICONTROL Add attribute]**.

I följande exempel används en **[!UICONTROL Combine]**-aktivitet med en **[!UICONTROL Union]** för att sammanfoga resultaten från två frågor, **Lojalitetsmedlemmar** och **Inköpare**, till en enda större målgrupp som innehåller alla profiler från båda segmenten.

![](../assets/orchestrated-union-example.png)

## Skärningspunkt {#combine-intersection}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_intersection_reconciliation_options"
>title="Avstämningsalternativ för skärningar"
>abstract="Välj **Avstämningstypen** för att definiera hur dubbletter ska hanteras. Som standard är alternativet **Tangenter** aktiverat, vilket innebär att aktiviteten bara behåller ett element när element från olika inkommande övergångar har samma nyckel. Använd alternativet **Ett urval kolumner** för att definiera listan med kolumner som datavstämningen ska användas på."

I aktiviteten **[!UICONTROL Combine]** kan du konfigurera en **[!UICONTROL Intersection]**. För detta behöver du följa de extra stegen nedan:

1. Välj **[!UICONTROL Reconciliation type]** för att definiera hur dubbletter hanteras:

   * **[!UICONTROL Keys only]** (standard): behåller en post när flera inkommande övergångar delar samma nyckel. Detta alternativ är endast tillämpligt när de inkommande populationerna är homogena.

   * **[!UICONTROL A selection of columns]**: gör att du kan ange vilka kolumner som ska användas för datavstämning. Välj **[!UICONTROL Add attribute]**.

1. Aktivera **[!UICONTROL Generate completement]** om du vill bearbeta den återstående fyllningen. Komplementet innehåller en förening av alla inkommande aktivitetsresultat, exklusive skärningspunkten. En ytterligare utgående övergång läggs till i aktiviteten.

I följande exempel visas hur **[!UICONTROL Intersection]** används mellan två frågeaktiviteter. Det används för att identifiera profiler som är **lojalitetsmedlemmar** och som har gjort ett köp under den senaste månaden.

![](../assets/orchestrated-intersection-example.png)


## Uteslutning {#combine-exclusion}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_exclusion_options"
>title="Uteslutningsregler"
>abstract="Vid behov kan du ändra inkommande tabeller. För att utesluta ett mål från en annan dimension måste detta mål återställas till samma måldimension som huvudmålet. Det gör du genom att klicka på Lägg till en regel i avsnittet Uteslutningsregler och ange villkoren för dimensionsändring. Datavstämning utförs antingen via ett attribut eller en koppling."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_combine_sets"
>title="Markera uppsättningar som ska kombineras"
>abstract="I avsnittet **Uppsättningar att gå med i** väljer du den **primära uppsättningen** bland de inkommande övergångarna. Detta är den uppsättning från vilken element utesluts. De andra uppsättningarna matchar element innan de utesluts från den primära uppsättningen."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_combine_exclusion"
>title="Uteslutningsregler"
>abstract="Vid behov kan du ändra inkommande tabeller. För att utesluta ett mål från en annan dimension måste detta mål återställas till samma måldimension som huvudmålet. Det gör du genom att klicka på Lägg till en regel i avsnittet Uteslutningsregler och ange villkoren för dimensionsändring. Datavstämning utförs antingen via ett attribut eller en koppling."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_combine_complement"
>title="Kombinera skapa komplementfärger"
>abstract="Växla till komplementalternativet Generera om du vill bearbeta den återstående populationen i en ytterligare övergång."

I aktiviteten **[!UICONTROL Combine]** kan du konfigurera en **[!UICONTROL Exclusion]**. För detta behöver du följa de extra stegen nedan:

1. I avsnittet **[!UICONTROL Sets to join]** väljer du **[!UICONTROL Primary set]**, som representerar huvudpopulationen. Poster som hittas i de andra uppsättningarna tas inte med i den här primära uppsättningen.

1. Vid behov kan du justera inkommande tabeller för att justera mål från olika dimensioner. Om du vill utesluta ett mål från en annan dimension måste det först ingå i samma målgruppsdimension som huvudpopulationen. Det gör du genom att klicka på **[!UICONTROL Add a rule]** och definiera villkoren för att ändra dimensionen. Avstämningen görs sedan med antingen ett attribut eller en koppling.

1. Aktivera **[!UICONTROL Generate completement]** om du vill bearbeta den återstående fyllningen. Komplementet innehåller en förening av alla inkommande aktivitetsresultat, exklusive skärningspunkten. En ytterligare utgående övergång läggs till i aktiviteten.

I följande **[!UICONTROL Exclusion]**-exempel visas två frågor som har konfigurerats för att filtrera profiler som köpt en produkt. De profiler som inte har något lojalitetsmedlemskap exkluderas sedan från den första uppsättningen.

![](../assets/orchestrated-exclusion-example.png)

