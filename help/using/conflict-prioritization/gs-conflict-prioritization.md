---
title: Konflikthantering och -prioritering
description: Lär dig utnyttja Journey Optimizer verktyg för konfliktlösning och prioritering.
role: User
level: Beginner
exl-id: 9dc0cd89-d29a-42d2-a73f-d95f9c39c86e
source-git-commit: a0eda2e1d021af37eb54f3ffa5bac0ac6e8ef6ce
workflow-type: tm+mt
source-wordcount: '828'
ht-degree: 0%

---

# Konflikthantering och -prioritering {#conflict-prioritization}

I Journey Optimizer är det viktigt att hantera kampanjernas och resornas volym och tidpunkter för att undvika överväldigande kunder med alltför många interaktioner. Med verktyg för hantering och prioritering av konflikter kan ni leverera genomtänkta, vältajmade meddelanden, vilket förhindrar att kunderna tröttnar och ser till att rätt budskap når ut till er målgrupp. Genom att använda konfliktidentifiering, prioritetspoäng och regeluppsättningar kan ni effektivisera kampanjer och resor för att undvika överlappningar och balansera frekvensen över olika kanaler.

De här verktygen är tillgängliga för kampanjer och för enkät-, målgrupps- och läsmålgruppsresor. Oavsett om ni sätter gränser för hur ofta meddelanden skickas eller bestämmer vilka kampanjer som prioriteras, fungerar dessa funktioner tillsammans för att förenkla beslutsfattandet och optimera er marknadsföringsstrategi.

## Var ska jag börja? {#where-to-start}

| Ditt mål | Verktyg | Åtgärd |
|-----------|------|--------|
| Se om resor eller kampanjer överlappar varandra (tidslinje, målgrupp, kanal) | **Konfliktidentifiering** | [Identifiera potentiella konflikter](conflicts.md) |
| Bestäm vilket meddelande som vinner när en profil kvalificerar sig för flera | **Prioritetspoäng** | [Tilldela prioritetspoäng](priority-scores.md) |
| Begränsa hur ofta eller hur många meddelanden en profil tar emot | **Regeluppsättningar** (frekvensbegränsning, resefackning, tysta timmar) | [Ange regler för capping av meddelanden och resor](../../rp_landing_pages/capping-rules-landing-page.md) |

**Normalt flöde:** Använd konfliktidentifiering för att identifiera överlappningar, och använd sedan prioritetspoäng och regeluppsättningar för att kontrollera vilka meddelanden som skickas och hur ofta.

## Konflikthantering och prioriteringsverktyg {#tools}

### Konfliktidentifieringsverktyg

Med **konfliktidentifieringsverktyget** kan du identifiera potentiella överlappningar i resor och kampanjer. Detta är avgörande eftersom alltför många samtidiga kommunikationer kan leda till att kunderna blir trötta. Med Journey Optimizer kan du övervaka element som tidslinjer, målgruppsöverlappning och kanalkonfigurationer. Genom att identifiera konflikter tidigt kan ni förfina era kampanjer för att undvika att bombardera kunder med flera meddelanden samtidigt.

[Lär dig hur du upptäcker potentiella konflikter i resor och kampanjer](conflicts.md)

### Prioritetspoäng

**Prioritetspoäng** hjälper dig att styra vilka kampanjer eller resor som prioriteras när en kund kvalificerar sig för flera kommunikationer. Detta är särskilt användbart för inkommande kanaler som webben och mobiler, där endast en kampanj kan visas åt gången. Genom att tilldela varje resa eller kampanj en prioritetspoäng kan ni se till att det viktigaste meddelandet levereras först.

[Lär dig hur du tilldelar prioritetspoäng till resor och kampanjer](priority-scores.md)

### Regeluppsättningar

Med regeluppsättningar kan du **gruppera flera regler** och tillämpa dem på de resor och kampanjer du vill använda. Detta ger förbättrad detaljrikedom för att begränsa hur ofta och hur många resor en kund kan ta sig in inom en viss tidsperiod, eller för att styra hur ofta användarna får meddelanden beroende på typ av kommunikation.

* **Resebegränsning och skiljeförfarande** - Begränsa hur ofta och hur många resor en kund kan ta sig in inom en viss tidsperiod. Ni kan begränsa antalet reseposter för en profil eller begränsa antalet resor som en kund kan registrera samtidigt. Använd skiljedomsinställningar för att bestämma vilken resa en kund ska delta i om de är kvalificerade för flera resor, och använd prioriteringspoäng för att avgöra vilken resa som passar bäst. [Lär dig hur du arbetar med capping och medling på resan](journey-capping.md)

* **Frekvensbegränsning efter kanal- och kommunikationstyp** - Ange frekvensbegränsning efter kommunikationstyp (t.ex. försäljning, marknadsföring) för att förhindra att kunder med liknande meddelanden överbelastas. Styr frekvensen i flera kanaler och exkludera automatiskt överbegärda profiler. [Lär dig hur du anger frekvensbegränsning efter kanal- och kommunikationstyp](channel-capping.md)

* **Tysta timmar** - Definiera tidsbaserade undantag så att inga meddelanden skickas under specifika perioder (e-post, SMS, push, whatsApp). [Lär dig hur du ställer in tysta timmar](quiet-hours.md)

[Lär dig arbeta med regeluppsättningar](rule-sets.md)

## Skyddsritningar och begränsningar {#guardrails}

* **Kampanjer och prioritetspoäng** - I kampanjer är prioritetspoäng endast tillgängligt för de inkommande kanalerna **web**, **in-app** och **code-based**.

* **Fördröjning för uppdatering av profilräknare** - Det kan ta upp till 10 minuter efter att en kund har gjort en resa för att profilräknarvärdet ska uppdateras. Om en profil går in i två resor inom ett kort fönster kanske den andra resan inte korrekt känner igen att frekvensgränsen redan har nåtts, vilket kan göra det möjligt för profilen att gå in på båda resorna.

* **Namnområdesprioritet för spärrning av reseinmatning** - Endast friskrivning av poster stöds om det namnområde som valts under resan är det högsta prioritetsnamnområde som definieras i sandlådan. Om namnområdesprioriteten inte har konfigurerats explicit är e-post den högsta standardprioriteten.

* **Samtidiga aktiveringar i målgruppsklassificeringsresor** - När flera målgruppsklassificeringsresor aktiveras av samma målgruppsklassificeringshändelse, kommer antalet för inmatningsspärr inte att vara korrekt. Om antalet ligger under gränsen fortsätter resan att godtyckas, men den kommer inte att kunna få de senaste siffrorna med samtidiga aktiveringar.

## Ytterligare resurser

* **[Identifiera potentiella konflikter](conflicts.md)** - Lär dig hur du identifierar och löser konflikter mellan överlappande kampanjer och resor.
* **[Tilldela prioritetspoäng](priority-scores.md)** - Lär dig hur du tilldelar och använder prioritetspoäng för att styra prioritet för meddelandeleverans.
* **[Arbeta med regeluppsättningar](rule-sets.md)** - Lär dig hur du skapar och använder regeluppsättningar för konflikthantering och meddelandestyrning.
* **[Resebegränsning och skiljeförfarande](journey-capping.md)** - Ange regler för capping på resenivå och skiljeförfarande.
* **[Frekvensbegränsning per kanal](channel-capping.md)** - Ange frekvensgränser på kanalnivå för att förhindra övermeddelanden.
* **[Ange tysta timmar](quiet-hours.md)** - Definiera tidsbaserade undantag för meddelandeleverans.
* **[Självstudiekurser för hantering av konflikter](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/conflict-management/identify-potential-conflicts){target="_blank"}** - Självstudiekurser på video steg för steg.
