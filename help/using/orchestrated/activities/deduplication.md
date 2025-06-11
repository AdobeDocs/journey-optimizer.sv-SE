---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Deduplicering
description: Lär dig hur du använder aktiviteten Deduplicering
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 4aa79448-f75a-48d5-8819-f4cb4baad5c7
source-git-commit: d59643f18a335fe1e094156a1cfee65b717b9fce
workflow-type: tm+mt
source-wordcount: '689'
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
| [Kom igång med samordnade kampanjer](../gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](../configuration-steps.md)<br/><br/>[Viktiga steg för att skapa samordnade kampanjer](../gs-campaign-creation.md) | [Skapa en orkestrerad kampanj](../create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](../orchestrate-activities.md)<br/><br/>[Skicka meddelanden med orkestrerade kampanjer](../send-messages.md)<br/><br/>[Starta och övervaka kampanjen](../start-monitor-campaigns.md)<br/><br/>[Rapportera](../reporting-campaigns.md) | [Arbeta med Query Modeler](../orchestrated-rule-builder.md)<br/><br/>[Skapa din första fråga](../build-query.md)<br/><br/>[Redigera uttryck](../edit-expressions.md) | [Kom igång med aktiviteter](about-activities.md)<br/><br/>Aktiviteter:<br/>[Och-join](and-join.md) - [Skapa målgrupp](build-audience.md) - [Ändra dimension](change-dimension.md) - [Kombinera](combine.md) - [Ta bort dubbletter](deduplication.md) - [Förbättra](enrichment.md) - [Förena](fork.md) - [Förena{1 ](reconciliation.md) - [Dela](split.md) - [Vänta](wait.md) |

{style="table-layout:fixed"}

+++

<br/>

Aktiviteten **Deduplicering** är en **målaktivitet**. Med den här aktiviteten kan du ta bort dubbletter i resultatet av de inkommande aktiviteterna, till exempel duplicerade profiler i mottagarlistan. Aktiviteten **Deduplicering** används vanligtvis efter målinriktningsaktiviteter och före aktiviteter som tillåter användning av måldata.

## Konfigurera aktiviteten Deduplicering{#deduplication-configuration}

Så här konfigurerar du aktiviteten **Deduplicering**:


1. Lägg till en **borttagning av dubbletter**-aktivitet i den orkestrerade kampanjen.

1. I avsnittet **Fält som ska identifiera dubbletter** klickar du på knappen **Lägg till attribut** för att ange för vilka fält identiska värden gör att dubbletter kan identifieras, t.ex. e-postadress, förnamn, efternamn osv. I fältordningen kan du ange vilka som ska behandlas först.

![](../assets/deduplication-1.png)

1. I avsnittet **Dedupliceringsinställningar** väljer du hur många unika poster som ska fortsätta att använda fältet Duplicates. Standardvärdet är 1, vilket behåller en post per dubblettgrupp. Ange 0 om du vill behålla alla dubbletter.

   Om posterna A och B till exempel är dubbletter av Y och posten C är en dubblett av Z:

   * **Om värdet för fältet är 1** behålls bara Y- och Z-posterna.
   * **Om värdet för fältet är 0** behålls alla poster (A, B, C, Y, Z).
   * **Om värdet för fältet är 2** behålls C och Z, plus två värden från A, B och Y, slumpmässigt eller baserat på din dedupliceringsmetod.

1. Välj en **dedupliceringsmetod**, som definierar hur systemet avgör vilka poster som ska behållas från varje grupp av dubbletter:

   * **Slumpmässig markering**: Markerar slumpmässigt den post som ska tas bort från dubbletterna.
   * **Använder ett uttryck**: Behåller poster med det högsta eller lägsta värdet baserat på ett uttryck som du definierar.
   * **Värden som inte är tomma**: Behåller poster där det markerade fältet inte är tomt, t.ex. bara behålla profiler med ett telefonnummer.
   * **Följ en lista med värden**: Gör att du kan prioritera specifika värden för ett eller flera fält, t.ex. kan du prioritera poster med &quot;Land&quot; inställt på Frankrike. Klicka på **Attribut** om du vill välja ett fält eller skapa ett anpassat uttryck. Använd knappen **Lägg till** för att ange önskade värden i prioritetsordningen.

   ![](../assets/deduplication-2.png)

1. Markera alternativet **Generera komplement** om du vill utnyttja den återstående populationen. Komplementet består av alla dubbletter. Därefter läggs ytterligare en övergång till aktiviteten.

## Exempel{#deduplication-example}

I följande exempel används en **borttagning av dubbletter**-aktivitet för att ta bort dubblettposter från målgruppen innan en leverans skickas. Publiken filtreras först så att den bara innehåller profiler med ett e-postfält som inte är tomt. Sedan använder aktiviteten **Deduplicering** e-postadressen för att identifiera och exkludera dubbletter.

![](../assets/deduplication-3.png)
