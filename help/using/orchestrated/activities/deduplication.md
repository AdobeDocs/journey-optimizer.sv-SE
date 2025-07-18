---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Deduplicering
description: Lär dig hur du använder aktiviteten Deduplicering
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 4aa79448-f75a-48d5-8819-f4cb4baad5c7
source-git-commit: 1a9ea09fcbf304b1649a5ae88da34bd209e9ac8b
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 0%

---

# Deduplicering {#deduplication}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_deduplication_fields"
>title="Fält som identifierar dubbletter"
>abstract="I avsnittet **Fält som ska identifiera dubbletter** klickar du på knappen **Lägg till attribut** för att ange för vilka fält identiska värden gör att dubbletter kan identifieras, t.ex. e-postadress, förnamn, efternamn osv. I fältordningen kan du ange vilka som ska behandlas först."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_deduplication"
>title="Dedupliceringsaktivitet"
>abstract="Med aktiviteten **Deduplicering** kan du ta bort dubbletter i resultatet av inkommande aktiviteter. Det används främst efter målinriktningsaktiviteter och före aktiviteter som tillåter användning av målinriktade data."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_deduplication_complement"
>title="Generera ett komplement"
>abstract="Du kan generera ytterligare en utgående övergång med den återstående populationen, som har uteslutits som en dubblett. Aktivera alternativet **Generera komplement** om du vill göra det."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_deduplication_settings"
>title="Inställningar för borttagning av dubbletter"
>abstract="Om du vill ta bort dubbletter i inkommande data definierar du dedupliceringsmetoden i fälten nedan. Som standard sparas bara en post. Du bör också välja dedupliceringsläget baserat på ett uttryck eller ett attribut. Som standard väljs den post som ska hållas utanför dubbletterna slumpmässigt."


+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](../gs-orchestrated-campaigns.md)<br/><br/>Skapa och hantera relationsscheman och datauppsättningar:</br> <ul><li>[Kom igång med scheman och datauppsättningar](../gs-schemas.md)</li><li>[Manuellt schema](../manual-schema.md)</li><li>[Filöverföringsschema](../file-upload-schema.md)</li><li>[Ingest data](../ingest-data.md)</li></ul>[Få åtkomst till och hantera samordnade kampanjer](../access-manage-orchestrated-campaigns.md) | [Viktiga steg för att skapa en orkestrerad kampanj](../gs-campaign-creation.md)<br/><br/>[Skapa och schemalägg kampanjen](../create-orchestrated-campaign.md)<br/><br/>[Orchestrate-aktiviteter](../orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](../start-monitor-campaigns.md)<br/><br/>[Rapportera](../reporting-campaigns.md) | [Arbeta med regelbyggaren](../orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](../build-query.md)<br/><br/>[Redigera uttryck](../edit-expressions.md)<br/><br/>[Återmarknadsföring](../retarget.md) | [Kom igång med aktiviteter](about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](and-join.md) - [Bygg målgrupp](build-audience.md) - [Ändra dimension](change-dimension.md) - [Kanalaktiviteter](channels.md) - [Kombinera](combine.md) - <b>[Deduplicering](deduplication.md)</b> - [Enrichment](enrichment.md) - [Fork](fork.md)  - [Avstämning](reconciliation.md) - [Spara målgrupp](save-audience.md) - [Dela](split.md) - [Vänta](wait.md) |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

</br>

Innehållet på den här sidan är inte slutgiltigt och kan komma att ändras.

>[!ENDSHADEBOX]

Aktiviteten **[!UICONTROL Deduplication]** är en **[!UICONTROL Targeting]**-aktivitet. Med den här aktiviteten kan du ta bort dubbletter i resultatet av de inkommande aktiviteterna, till exempel duplicerade profiler i mottagarlistan. Aktiviteten **[!UICONTROL Deduplication]** används vanligtvis efter målinriktningsaktiviteter och före aktiviteter som tillåter användning av måldata.

## Konfigurera aktiviteten Deduplicering{#deduplication-configuration}

Så här konfigurerar du aktiviteten **[!UICONTROL Deduplication]**:


1. Lägg till en **[!UICONTROL Deduplication]**-aktivitet i din samordnade kampanj.

1. Klicka på knappen **[!UICONTROL Fields to identify duplicates]** i avsnittet **[!UICONTROL Add attribute]** för att ange de fält där identiska värden gör att dubbletter kan identifieras, till exempel e-postadress, förnamn, efternamn osv. I fältordningen kan du ange vilka som ska behandlas först.

   ![](../assets/deduplication-1.png)

1. I avsnittet **[!UICONTROL Deduplication settings]** väljer du hur många unika poster som ska fortsätta att använda fältet Duplicates. Standardvärdet är 1, vilket behåller en post per dubblettgrupp. Ange 0 om du vill behålla alla dubbletter.

   Om posterna A och B till exempel är dubbletter av Y och posten C är en dubblett av Z:

   * **Om värdet för fältet är 1** behålls bara Y- och Z-posterna.
   * **Om värdet för fältet är 0** behålls alla poster (A, B, C, Y, Z).
   * **Om värdet för fältet är 2** behålls C och Z, plus två värden från A, B och Y, slumpmässigt eller baserat på din dedupliceringsmetod.

1. Välj en **[!UICONTROL Deduplication Method]**, som definierar hur systemet avgör vilka poster som ska behållas från varje grupp av dubbletter:

   * **[!UICONTROL Random selection]**: Markerar slumpmässigt den post som ska hållas utanför dubbletterna.
   * **[!UICONTROL Using an expression]**: Behåller poster med det högsta eller lägsta värdet baserat på ett uttryck som du definierar.
   * **[!UICONTROL Non-empty values]**: Behåller poster där det markerade fältet inte är tomt, t.ex. bara behålla profiler med ett telefonnummer.
   * **[!UICONTROL Following a list of values]**: Gör att du kan prioritera specifika värden för ett eller flera fält, t.ex. kan du prioritera poster med &quot;Land&quot; inställt på Frankrike. Klicka på **[!UICONTROL Attribute]** om du vill välja ett fält eller skapa ett anpassat uttryck. Använd **[!UICONTROL Add button]** för att ange önskade värden i prioritetsordningen.

   ![](../assets/deduplication-2.png)

1. Markera alternativet **[!UICONTROL Generate complement]** om du vill utnyttja den återstående populationen. Komplementet består av alla dubbletter. Därefter läggs ytterligare en övergång till aktiviteten.

## Exempel{#deduplication-example}

I följande exempel används en **[!UICONTROL Deduplication]**-aktivitet för att ta bort dubblettposter från målgruppen innan en leverans skickas. Publiken filtreras först så att den bara innehåller profiler med ett e-postfält som inte är tomt. Aktiviteten **[!UICONTROL Deduplication]** använder sedan e-postadressen för att identifiera och exkludera dubbletter.

![](../assets/deduplication-3.png)
