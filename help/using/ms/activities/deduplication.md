---
solution: Journey Optimizer
product: journey optimizer
title: Använda aktiviteten Deduplicering
description: Lär dig hur du använder aktiviteten Deduplicering
hide: true
hidefromtoc: true
exl-id: 4aa79448-f75a-48d5-8819-f4cb4baad5c7
source-git-commit: 3d380d2d02eb7043aebcffd00bb2092e7341b0d5
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 17%

---

# Deduplicering {#deduplication}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_deduplication_fields"
>title="Fält som identifierar dubbletter"
>abstract="I avsnittet **Fält som ska identifiera dubbletter** klickar du på knappen **Lägg till attribut** för att ange för vilka fält identiska värden gör att dubbletter kan identifieras, t.ex. e-postadress, förnamn, efternamn osv. Ordningen på fälten gör att du kan ange vilka som ska bearbetas först."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_deduplication"
>title="Aktivitet för deduplicering"
>abstract="Med **aktiviteten Deduplication** kan du ta bort dubbletter i resultatet av de inkommande aktiviteterna. Den används främst efter inriktningsaktiviteter och före aktiviteter som tillåter användning av riktade data."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_deduplication_complement"
>title="Generera ett komplement"
>abstract="Du kan generera ytterligare en utgående övergång med den återstående populationen, som uteslöts som en dubblett. För att göra detta, slå på **alternativet Generera komplement**"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_deduplication_settings"
>title="Inställningar för deduplicering"
>abstract="Om du vill ta bort dubbletter i inkommande data definierar du dedupliceringsmetoden i fälten nedan. Som standard sparas bara en post. Du bör också välja dedupliceringsläget baserat på ett uttryck eller ett attribut. Som standard väljs den post som ska hållas utanför dubbletterna slumpmässigt."

Aktiviteten **Deduplicering** är en **målaktivitet**. Med den här aktiviteten kan du ta bort dubbletter i resultatet av de inkommande aktiviteterna, till exempel duplicerade profiler i mottagarlistan. Aktiviteten **Deduplicering** används vanligtvis efter målinriktningsaktiviteter och före aktiviteter som tillåter användning av måldata.

## Konfigurera aktiviteten Deduplicering{#deduplication-configuration}

Följ dessa steg för att konfigurera **aktiviteten Deduplication** :

![](../assets/workflow-deduplication.png)

1. Lägg till en **dedupliceringsaktivitet** i din orkestrerade kampanj.

1. **I avsnittet Fält för att identifiera dubbletter** klickar du på **knappen Lägg till attribut** för att ange de fält för vilka identiska värden gör att dubbletterna kan identifieras, till exempel: e-postadress, förnamn, efternamn osv. Ordningen på fälten gör att du kan ange vilka som ska bearbetas först.

1. **I avsnittet Dedupliceringsinställningar** väljer du antalet unika **dubbletter som ska behållas**. Standardvärdet för det här fältet är 1. Med värdet 0 kan du behålla alla dubbletter.

   Om till exempel posterna A och B betraktas som dubbletter av posten Y, och en post C betraktas som en dubblett av posten Z:

   * Om värdet för fältet är 1: endast Y- och Z-posterna behålls.
   * Om värdet för fältet är 0: alla register förs.
   * Om värdet för fältet är 2: Posterna C och Z förvaras och två poster från A, B och Y sparas, av en tillfällighet eller beroende på vilken dedupliceringsmetod som valts därefter.

1. Välj den dedupliceringsmetod **som** ska användas:

   * **Slumpmässigt urval**: Väljer slumpmässigt den post som ska hållas borta från dubbletterna.
   * **Använda ett uttryck**: Behåll de poster där värdet för det angivna uttrycket är det minsta eller det största.
   * **Icke-tomma värden**: Behåll de poster som uttrycket inte är tomt för.
   * **Följande en lista med värden**: Definiera en värdeprioritet för ett eller flera fält. Om du vill definiera värdena klickar du på **Attribut** för att välja ett fält eller skapa ett uttryck och lägger sedan till värdena i lämplig tabell. Om du vill definiera ett nytt fält klickar du på **knappen** Lägg till ovanför listan med värden.

1. **Markera alternativet Generera komplement** om du vill utnyttja den återstående populationen. Komplementet består av alla dubbletter. En ytterligare övergång kommer då att läggas till i aktiviteten.

## Exempel{#deduplication-example}

I följande exempel använder du en dedupliceringsaktivitet för att exkludera dubbletter från målet innan du skickar en leverans. De identifierade duplicerade profilerna läggs till i en dedikerad målgrupp som kan återanvändas om det behövs. Identifiera dubbletterna genom att välja **E-postadress**. Behåll 1 post och välj borttagningsmetoden **Slumpmässig**.

![](../assets/workflow-deduplication-example.png)
