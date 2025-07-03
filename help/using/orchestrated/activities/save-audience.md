---
solution: Journey Optimizer
product: journey optimizer
title: Använda aktiviteten Spara målgrupp
description: Lär dig hur du använder aktiviteten Spara som i en strukturerad kampanj
badge: label="Alpha"
hide: true
hidefromtoc: true
source-git-commit: 6439be00315dfde7ab385d7f848b7031d95060f4
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Spara målgrupp {#save-audience}

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](configuration-steps.md)<br/><br/>[Få åtkomst till och hantera samordnade kampanjer](access-manage-orchestrated-campaigns.md) | [Viktiga steg för att skapa samordnade kampanjer](gs-campaign-creation.md)<br/><br/>[Skapa och schemalägg kampanjen](create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/><b>[Starta och övervaka kampanjen](start-monitor-campaigns.md)</b><br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med regelbyggaren](orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md)<br/><br/>[Återmarknadsföring](retarget.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](activities/and-join.md) - [Bygg målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kanalaktiviteter](activities/channels.md) - [Kombinera](activities/combine.md) - [Deduplicering](activities/deduplication.md) - [Enrichment](activities/enrichment.md) - [Fork](activities/fork.md)  - [Avstämning](activities/reconciliation.md) - [Spara målgrupp](save-audience.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

Aktiviteten **[!UICONTROL Save audience]** är en **[!UICONTROL Targeting]**-aktivitet som gör att du kan uppdatera en befintlig målgrupp eller skapa en ny från den tidigare populationen i den orkestrerade kampanjen. När de har skapats läggs dessa målgrupper till i listan över programmålgrupper och kan nås från menyn **[!UICONTROL Audiences]**.

Denna aktivitet är särskilt användbar för att bevara målgruppssegment som beräknas inom samma samordnade kampanj, så att de blir tillgängliga för återanvändning i framtida kampanjer. Den är vanligtvis kopplad till andra målinriktningsaktiviteter, som **[!UICONTROL Build audience]** eller **[!UICONTROL Combine]**, för att hämta och spara den resulterande populationen.

## Konfigurera aktiviteten Spara målgrupp {#save-audience-configuration}

Så här konfigurerar du aktiviteten **Spara målgrupp**:

1. Lägg till en **Spara målgruppsaktivitet** i den orkestrerade kampanjen.

1. I listrutan **Läge** väljer du den åtgärd som du vill utföra:

   * **Skapa eller uppdatera en befintlig målgrupp**: Definiera en **publiketikett**. Om målgruppen redan finns uppdateras den, annars skapas en ny målgrupp.

   * **Uppdatera en befintlig målgrupp**: Välj den **målgrupp** som du vill uppdatera i listan över befintliga målgrupper.

1. Välj det **uppdateringsläge** som gäller för befintliga målgrupper:

   * **Ersätt målgruppsinnehåll med nya data**: Allt målgruppsinnehåll ersätts och gamla data går förlorade. Endast data från den inkommande övergången för aktiviteten **Spara målgrupp** behålls. Med det här alternativet raderas målgruppstypen och målgruppsdimensionen för den uppdaterade målgruppen.

   * **Fullständig målgrupp med nya data**: Det gamla målgruppsinnehållet behålls och data från den inkommande övergången för aktiviteten **Spara målgrupp** läggs till i den.

1. Markera alternativet **Generera en utgående övergång** om du vill lägga till en övergång efter aktiviteten **Spara målgrupp**.

Innehållet i den sparade målgruppen är sedan tillgängligt i detaljvyn för målgruppen, som du kommer åt på menyn **Publiker** . Kolumnerna som är tillgängliga i den här vyn motsvarar kolumnerna för den inkommande övergången för den orkestrerade kampanjen **Spara målgruppsaktivitet**.

## Exempel {#save-audience-example}

I följande exempel visas en enkel målgruppsuppdatering från målinriktning. En schemaläggare kör den orkestrerade kampanjen en gång i månaden. En fråga hämtar alla profiler som prenumererar på de olika tillgängliga programmen. Aktiviteten **Spara målgrupp** uppdaterar målgruppen genom att ta bort profiler som har avbeställt tjänsten sedan den senaste kampanjkörningen och lagt till nya prenumerationsprofiler.
