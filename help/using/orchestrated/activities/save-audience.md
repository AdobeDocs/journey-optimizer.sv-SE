---
solution: Journey Optimizer
product: journey optimizer
title: Använda aktiviteten Spara målgrupp
description: Lär dig hur du använder aktiviteten Spara som i en strukturerad kampanj
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 7b5b03ba-fbb1-4916-8c72-10778752d8e4
source-git-commit: 0abe441a413b748b46379871f3b70842715921a3
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 0%

---

# Spara målgrupp {#save-audience}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_save_audience"
>title="Spara målgruppsaktivitet"
>abstract="Aktiviteten **Spara målgrupp** är en **målgruppsaktivitet** som gör att du kan uppdatera en befintlig målgrupp eller skapa en ny från den målgrupp som genererades tidigare i den orkestrerade kampanjen. När de har skapats läggs dessa målgrupper till i listan över programmålgrupper och kan nås från menyn **Publiker** ."


+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](../gs-orchestrated-campaigns.md)<br/><br/>Skapa och hantera relationsscheman och datauppsättningar:</br> <ul><li>[Kom igång med scheman och datauppsättningar](../gs-schemas.md)</li><li>[Manuellt schema](../manual-schema.md)</li><li>[Filöverföringsschema](../file-upload-schema.md)</li><li>[Ingest data](../ingest-data.md)</li></ul>[Få åtkomst till och hantera samordnade kampanjer](../access-manage-orchestrated-campaigns.md) | [Viktiga steg för att skapa en orkestrerad kampanj](../gs-campaign-creation.md)<br/><br/>[Skapa och schemalägg kampanjen](../create-orchestrated-campaign.md)<br/><br/>[Orchestrate-aktiviteter](../orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](../start-monitor-campaigns.md)<br/><br/>[Rapportera](../reporting-campaigns.md) | [Arbeta med regelbyggaren](../orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](../build-query.md)<br/><br/>[Redigera uttryck](../edit-expressions.md)<br/><br/>[Återmarknadsföring](../retarget.md) | [Kom igång med aktiviteter](about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](and-join.md) - [Bygg målgrupp](build-audience.md) - [Ändra dimension](change-dimension.md) - [Kanalaktiviteter](channels.md) - [Kombinera](combine.md) - [Deduplicering](deduplication.md) - [Enrichment](enrichment.md) - [Fork](fork.md)  - [Avstämning](reconciliation.md) - <b>[Spara målgrupp](save-audience.md)</b> - [Dela](split.md) - [Vänta](wait.md) |

{style="table-layout:fixed"}

+++


<br/>

>[!BEGINSHADEBOX]

</br>

Innehållet på den här sidan är inte slutgiltigt och kan komma att ändras.

>[!ENDSHADEBOX]

Aktiviteten **[!UICONTROL Save audience]** är en **[!UICONTROL Targeting]**-aktivitet som används för att skapa en ny målgrupp eller uppdatera en befintlig utifrån den population som skapades tidigare i den orkestrerade kampanjen. När målgruppen har sparats läggs den till i listan över programmålgrupper och blir tillgänglig på menyn **[!UICONTROL Audiences]**.

Det används ofta för att fånga målgruppssegment som skapats i samma kampanjarbetsflöde, så att de kan återanvändas i framtida kampanjer. Det är vanligtvis kopplat till andra målinriktningsaktiviteter, som **[!UICONTROL Build audience]** eller **[!UICONTROL Combine]**, för att spara den slutliga målpopulationen.

## Konfigurera aktiviteten Spara målgrupp {#save-audience-configuration}

Så här konfigurerar du aktiviteten **[!UICONTROL Save audience]**:

1. Lägg till en **[!UICONTROL Save audience]**-aktivitet i din samordnade kampanj.

1. Ange en **[!UICONTROL Audience label]** som identifierar den sparade målgruppen.

1. Välj en **[!UICONTROL Profile mapping field&#x200B;]** från din Campaign-måldimension.

   ➡️ [Följ stegen som beskrivs på den här sidan för att skapa din Campaign Targeting-dimension](../target-dimension.md)

   ![](../assets/save-audience-1.png)

1. Klicka på **[!UICONTROL Add audience mappings]** om du vill associera den sparade målgruppen med ytterligare identitetsfält.

   ![](../assets/save-audience-2.png)

1. Slutför konfigurationen genom att spara och publicera den orkestrerade kampanjen. Detta genererar och lagrar er målgrupp.

Innehållet i den sparade målgruppen är sedan tillgängligt i detaljvyn för målgruppen, som du kommer åt via menyn **[!UICONTROL Audiences]**, eller kan väljas när du riktar dig till en målgrupp, till exempel med en **[!UICONTROL Read audience]** -aktivitet.

![](../assets/save-audience-4.png)


## Exempel {#save-audience-example}

I följande exempel visas hur du skapar en enkel målgrupp med målinriktning. En fråga identifierar alla mottagare som har bokat en resa de senaste 30 dagarna genom att filtrera den här populationen i din samordnade kampanj. Genom att välja **Mottagare - CRMID** som **måldimension**, målgruppen för varje enskild bokningshändelse i stället för bara mottagaren som helhet. Aktiviteten **[!UICONTROL Save audience]** hämtar sedan dessa profiler för att skapa en återanvändbar målgrupp med nyligen använda köpare.

![](../assets/save-audience-3.png)
