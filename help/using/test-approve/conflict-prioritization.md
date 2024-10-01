---
title: Konflikthantering och -prioritering
description: Lär dig hur du förhandsgranskar och testar innehåll.
feature: Preview, Proofs
role: User
level: Beginner
badge: label="Beta"
hide: true
hidefromtoc: true
source-git-commit: 0322a13304875c4ba9ae8a9e7710fa2e71e459b3
workflow-type: tm+mt
source-wordcount: '950'
ht-degree: 0%

---


# Konflikthantering och -prioritering {#conflict-prioritization}

>[!AVAILABILITY]
>
>Konflikthanterings- och prioriteringsverktygen är för närvarande bara tillgängliga som betaversion för utvalda användare.

I Journey Optimizer är det viktigt att hantera kampanjernas och resornas volym och tidpunkter för att undvika överväldigande kunder med alltför många interaktioner. I följande två avsnitt presenteras viktiga verktyg som hjälper dig att upprätthålla balansen och prioritera kommunikationen effektivt.

## Visa potentiella konflikter i resor och kampanjer {#conflict}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_campaign_conflict"
>title="Visningsprogrammet i konflikt i kampanjer"
>abstract="Det här verktyget kan hjälpa dig att avgöra om andra resor, kampanjer eller kanalkonfigurationer överlappar varandra. Om du vill identifiera överlappning för målgrupper, start- och slutdatum, kanalkonfiguration, kanal eller regeluppsättning kan du visa potentiella konflikter här."

>[!CONTEXTUALHELP]
>id="ajo_journey_conflict"
>title="Konfliktvisningsprogrammet under resor"
>abstract="Det här verktyget kan hjälpa dig att avgöra om andra resor, kampanjer eller kanalkonfigurationer överlappar varandra. Om du vill identifiera överlappning för målgrupper, start- och slutdatum, kanalkonfiguration, kanal eller regeluppsättning kan du visa potentiella konflikter här."

I takt med att marknadsförarna ökar antalet kampanjer och resor i Journey Optimizer blir det allt svårare för en marknadsförare att veta om de bombar sina kunder med alltför många marknadsföringsinteraktioner. Det är därför viktigt att enkelt identifiera när det finns överlappande kampanjer och resor för att säkerställa att de når rätt balans mellan marknadsföringskommunikation och samtidigt minska risken för att kunderna ska tröttna.

De viktigaste områdena att övervaka för eventuell överlappning är:

* **Tidslinje** (start- och slutdatum): Kör för många resor samtidigt?
* **Målgrupp**: Vilken procentandel av min kundresa är också del av andra resor?
* **Kanal**: Finns det annan kommunikation schemalagd för samma tidsram och, om så är fallet, hur många?
* **Begränsningsregeluppsättning**: Vilka typer av resor är jag capping och överlappar de?
* **Kanalkonfiguration**: Finns det andra resor eller kampanjer som använder den här kanalkonfigurationen som kan förhindra att kampanjen visas för användaren?

Med Journey Optimizer kan ni kontrollera närhelst det finns en möjlighet att överlappa andra resor eller kampanjer. Följ dessa steg för att göra detta:

1. När du redigerar en resa eller kampanj klickar du på knappen **[!UICONTROL View Potential Conflicts]** i resans eller kampanjens egenskaper.

   ![](assets/view-conflicts.png)

   >[!NOTE]
   >
   >Knappen **[!UICONTROL View potential conflicts]** blir tillgänglig att välja så snart du har tilldelat någon av följande inställningar: **[!UICONTROL Start / end date]**, **[!UICONTROL Audience]**, **[!UICONTROL Channel]**, **[!UICONTROL Channel configuration]** och **[!UICONTROL Rule set]**. Se till att du väljer **[!UICONTROL Save]** när du har tilldelat de här inställningarna eftersom knappen inte kan markeras förrän ändringarna har sparats.

1. Fönstret **[!UICONTROL Potential conflicts]** öppnas så att du kan visualisera alla element som överlappar den aktuella resan/kampanjen.

   Du kan öppna en överlappande resa eller kampanj direkt från den här skärmen genom att välja dess namn.

   ![](assets/potential-conflicts.png)

>[!NOTE]
>
>Om du vill förfina din sökning efter potentiella överlappningar kan du filtrera listan över kampanjer och resor baserat på vilket fält som är relevant. Det gör du genom att välja filterikonen i lagervyn. [Lär dig arbeta med filter](../start/search-filter-categorize.md#filter-lists)

När potentiella överlappningar har identifierats kan Journey Optimizer åtgärda dem på flera olika sätt.

* Justera **start-/slutdatum** för att undvika överlappande kampanjer eller resor.
* Förfina **målgruppsanpassningen** för att minimera överlappning mellan resor.
* Implementera **frekvensgränser** för att hindra kunder från att ta emot för många meddelanden.
* Minska antalet **aktiva resor** för att hantera kundupplevelsen mer effektivt.
* Ange **prioritet** för inkommande åtgärder för att se till att den viktigaste åtgärden visas för kunderna.

Genom att utnyttja dessa funktioner kan ni se till att era marknadsföringssatsningar är anpassade efter varandra och att ni upprätthåller rätt balans i er kommunikationsstrategi.

## Tilldela prioritetspoäng till resor och kampanjer {#priority}

>[!CONTEXTUALHELP]
>id="ajo_journey_priority"
>title="Prioritet"
>abstract="Tilldela en prioritetspoäng till resan, från 0 till 100. Ett högre tal anger en högre prioritet. Prioritetsvärdet som infogas här ärvs av alla inkommande åtgärder (till exempel i appen) som ingår i den här resan. I situationer där samma konfiguration för inkommande kanal används i andra kampanjer eller resor visas den inkommande åtgärden med högsta prioritet för mottagaren. Om flera resor eller kampanjer har samma poäng väljs det element som senast ändrades."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_campaign_priority"
>title="Prioritet"
>abstract="Tilldela kampanjens prioritetspoäng, från 0 till 100. Ett högre tal anger en högre prioritet. I situationer där samma konfiguration för inkommande kanal (till exempel i appen) används i andra kampanjer eller resor visas den inkommande åtgärden med högsta prioritet för mottagaren. Om flera resor eller kampanjer har samma poäng väljs det element som senast ändrades."

Med Journey Optimizer kan ni tilldela en prioritetspoäng till en resa eller kampanj. Prioritet är viktigt för att prioritera en resa, kampanj eller åtgärd när det finns en begränsning (t.ex. ett frekvenstak). I situationer där en kund är berättigad till många resor, kampanjer eller kommunikationer och du vill vara selektiv vad de ska delta i och ta emot, bör du använda det här fältet.

>[!NOTE]
>
>Prioritetspoäng är tillgängligt för inkommande kanaler: webbkanaler, appkanaler och kodbaserade kanaler. Prioritetspoäng är endast tillgänglig för kanalerna **i appen** och **kodbaserad**.

Det är viktigt att du tilldelar en prioritetspoäng för inkommande kommunikation, som webben, mobiler och appar. Om du har flera kampanjer med samma kanalkonfiguration (t.ex. en banderoll högst upp på webbsidan) kan det vara problematiskt eftersom bara innehåll från en kampanj kan visas. Prioritetspoängen är den plats där du infogar din inställning för vilken kampanj ska visas när mottagaren kan kvalificera sig för mer än en kampanj.

Om du vill tilldela en prioritetspoäng till en resa eller kampanj anger du ett numeriskt värde (från 0-100) i fältet **[!UICONTROL Priority score]** som finns i resans eller kampanjens egenskaper. Observera att ju högre tal desto högre prioritet. Om ni redigerade den här kampanjen och ville se till att kampanjinnehållet visas ger ni den 100 poäng.

![](assets/priority-score.png)

I situationer där två kampanjer har samma prioritetspoäng visas den senast aktiverade kampanjen.
