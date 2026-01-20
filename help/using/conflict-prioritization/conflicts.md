---
title: Identifiera potentiella konflikter i resor och kampanjer
description: Lär dig identifiera potentiella konflikter i resor och kampanjer.
role: User
level: Beginner
exl-id: efbb5ac4-4c07-4c62-9460-39eb4fed129a
source-git-commit: a824e7342ee32eb261f2ecfb00b9ec12ec655f1e
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 1%

---

# Upptäck potentiella konflikter i resor och kampanjer {#conflict}

I takt med att marknadsförarna ökar antalet kampanjer och resor i Journey Optimizer blir det allt svårare för en marknadsförare att veta om de bombarderar sina kunder med alltför många marknadsföringsinteraktioner. Det är därför viktigt att enkelt identifiera när det finns överlappande kampanjer och resor för att se till att de når rätt balans mellan marknadsföringskommunikation och samtidigt minska risken för att kunderna tröttnar.

De viktigaste områdena att övervaka för eventuell överlappning är:

* **Tidslinje** (start- och slutdatum): Kör för många resor samtidigt?
* **Målgrupp**: Vilken procentandel av min kundresa är också del av andra resor?
* **Kanal**: Finns det annan kommunikation schemalagd för samma tidsram och, om så är fallet, hur många?
* **Begränsningsregeluppsättning**: Vilka typer av resor är jag capping och överlappar de?
* **Kanalkonfiguration**: Finns det andra resor eller kampanjer som använder någon kanalkonfiguration som används i samma resa eller kampanj som kan förhindra att resan eller kampanjen visas för slutanvändaren?

➡️ [Upptäck den här funktionen i en video](#video)

## Hur Journey Optimizer identifierar konflikter {#detection}

Nedan följer en sammanfattning av hur Journey Optimizer identifierar potentiella konflikter för resor och kampanjer:

* **Konfliktidentifieringsomfång**: Konflikter visas bara för live- eller schemalagda kampanjer och resor.
* **Unitära resor**: Om den valda resan är enhetlig visas andra resor som börjar med samma händelse, eftersom den här händelsen utlöser alla sådana resor.
* **Målgruppskvalificering och Läs målgrupps-/affärshändelse**-resor: Om den valda resan antingen är en målgruppskompetens eller en läs målgrupps-/affärshändelseresa visas alla andra resor av samma typ med en giltig målgrupp, eftersom det kan finnas överlappningar mellan målgrupperna.
* **Kampanjer**: Eftersom alla kampanjer riktar sig till målgrupper och det inte finns något koncept för händelser, kan alla kampanjer vara i konflikt med segmentutlösta resor (med början från en läs- och målgruppsaktivitet).
* **Live/schemalagda kampanjer**: Live-kampanjer och schemalagda kampanjer kan hamna i konflikt med varandra på grund av potentiell målgruppsöverlappning. Alla livekampanjer eller schemalagda kampanjer listas i konfliktvisningsprogrammet för alla angivna kampanjer.

## Visa identifierade konflikter för en viss resa eller kampanj {#view}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_campaign_conflict"
>title="Visa potentiella konflikter"
>abstract="Kontrollera när det finns risk för att kampanjer överlappar andra. Konflikter visas endast för direktsända och schemalagda kampanjer. Observera att knappen blir tillgänglig så snart du har tilldelat någon av följande inställningar: **[!UICONTROL Start / end date]**, **[!UICONTROL Audience]**, **[!UICONTROL Channel]**, **[!UICONTROL Channel configuration]** och **[!UICONTROL Rule set]**."

>[!CONTEXTUALHELP]
>id="ajo_journey_conflict"
>title="Visa potentiella konflikter"
>abstract="Kontrollera om det finns risk för att resorna överlappar andra. Konflikter visas endast för direktsända och schemalagda resor. Observera att knappen blir tillgänglig så snart du har tilldelat någon av följande inställningar: **[!UICONTROL Start / end date]**, **[!UICONTROL Audience]**, **[!UICONTROL Channel]**, **[!UICONTROL Channel configuration]** och **[!UICONTROL Rule set]**."

När ni skapar en resa eller kampanj kan ni i Journey Optimizer kontrollera om det finns en möjlighet att överlappa andra resor eller kampanjer. Följ dessa steg för att göra detta:

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
   >Nypublicerade resor och kampanjer kan ta upp till 3-7 minuter att visa i konfliktvisningsprogrammet på grund av cachelagring som har implementerats.

Om du vill förfina din sökning efter potentiella överlappningar kan du filtrera listan över kampanjer och resor baserat på vilket fält som är relevant. Det gör du genom att välja filterikonen i lagervyn. [Lär dig arbeta med filter](../start/search-filter-categorize.md#filter-lists)

## Lös konflikter {#resolve}

Här följer några tips för att minska antalet potentiella konflikter när de har identifierats:

* Justera **start-/slutdatum** för att undvika överlappande kampanjer eller resor.
* Förfina **målgruppsanpassningen** för att minimera överlappning mellan resor.
* Implementera **frekvensgränser** för att hindra kunder från att ta emot för många meddelanden.
* Minska antalet **aktiva resor** för att hantera kundupplevelsen mer effektivt.
* Ange **prioritet** för inkommande åtgärder för att se till att den viktigaste åtgärden visas för kunderna.

Genom att utnyttja dessa funktioner kan ni se till att era marknadsföringssatsningar är anpassade efter varandra och att ni upprätthåller rätt balans i er kommunikationsstrategi.

## Instruktionsvideo {#video}

>[!VIDEO](https://video.tv.adobe.com/v/3435528?quality=12)
