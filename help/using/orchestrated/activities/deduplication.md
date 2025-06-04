---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Deduplicering
description: Lär dig hur du använder aktiviteten Deduplicering
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 4aa79448-f75a-48d5-8819-f4cb4baad5c7
source-git-commit: 2935e611bb9682256a324485b28e7dd2552e1dd2
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 15%

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
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](configuration-steps.md)<br/><br/>[Viktiga steg för att skapa samordnade kampanjer](gs-campaign-creation.md) | [Skapa en orkestrerad kampanj](create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/>[Skicka meddelanden med orkestrerade kampanjer](send-messages.md)<br/><br/>[Starta och övervaka kampanjen](start-monitor-campaigns.md)<br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med Query Modeler](orchestrated-query-modeler.md)<br/><br/>[Skapa din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[Och-join](activities/and-join.md) - [Skapa målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kombinera](activities/combine.md) - [Ta bort dubbletter](activities/deduplication.md) - [Förbättra](activities/enrichment.md) - [Förena](activities/fork.md) - [Förena&lbrace;1 ](activities/reconciliation.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

<br/><br/>

Aktiviteten **Deduplicering** är en **målaktivitet**. Med den här aktiviteten kan du ta bort dubbletter i resultatet av de inkommande aktiviteterna, till exempel duplicerade profiler i mottagarlistan. Aktiviteten **Deduplicering** används vanligtvis efter målinriktningsaktiviteter och före aktiviteter som tillåter användning av måldata.

## Konfigurera aktiviteten Deduplicering{#deduplication-configuration}

Så här konfigurerar du aktiviteten **Deduplicering**:

![](../assets/workflow-deduplication.png)

1. Lägg till en **borttagning av dubbletter**-aktivitet i den orkestrerade kampanjen.

1. I avsnittet **Fält som ska identifiera dubbletter** klickar du på knappen **Lägg till attribut** för att ange för vilka fält identiska värden gör att dubbletter kan identifieras, t.ex. e-postadress, förnamn, efternamn osv. I fältordningen kan du ange vilka som ska behandlas först.

1. I avsnittet **Dedupliceringsinställningar** väljer du antalet unika **dubbletter som ska behållas**. Standardvärdet för det här fältet är 1. Med värdet 0 kan du behålla alla dubbletter.

   Om till exempel posterna A och B betraktas som dubbletter av posten Y, och en post C betraktas som en dubblett av posten Z:

   * Om värdet för fältet är 1: endast Y- och Z-posterna behålls.
   * Om värdet för fältet är 0: alla register förs.
   * Om värdet för fältet är 2: Posterna C och Z förvaras och två poster från A, B och Y sparas, av en tillfällighet eller beroende på vilken dedupliceringsmetod som valts därefter.

1. Välj den **borttagningsmetod** som ska användas:

   * **Slumpmässig markering**: Markerar slumpmässigt den post som ska tas bort från dubbletterna.
   * **Använder ett uttryck**: Behåll de poster där det angivna uttryckets värde är det minsta eller största.
   * **Värden som inte är tomma**: Behåll de poster som uttrycket inte är tomt för.
   * **Följ en lista med värden**: Definiera en värdeprioritet för ett eller flera fält. Om du vill definiera värdena klickar du på **Attribut** för att välja ett fält eller skapa ett uttryck och lägger sedan till värdena i rätt tabell. Om du vill definiera ett nytt fält klickar du på knappen **Lägg till** som finns ovanför listan med värden.

1. Markera alternativet **Generera komplement** om du vill utnyttja den återstående populationen. Komplementet består av alla dubbletter. Därefter läggs ytterligare en övergång till aktiviteten.

## Exempel{#deduplication-example}

I följande exempel använder du en dedupliceringsaktivitet för att exkludera dubbletter från målet innan du skickar en leverans. De identifierade duplicerade profilerna läggs till i en dedikerad målgrupp som kan återanvändas om det behövs. Identifiera dubbletterna genom att välja **E-postadress**. Behåll 1 post och välj borttagningsmetoden **Slumpmässig**.

![](../assets/workflow-deduplication-example.png)
