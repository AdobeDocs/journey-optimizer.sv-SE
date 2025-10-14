---
title: Konflikthantering och -prioritering
description: Lär dig utnyttja Journey Optimizer verktyg för konfliktlösning och prioritering.
role: User
level: Beginner
exl-id: 9dc0cd89-d29a-42d2-a73f-d95f9c39c86e
source-git-commit: 8146221975b7460bf1deaca9363d1624b719b480
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 0%

---

# Konflikthantering och -prioritering {#conflict-prioritization}

## Konflikthantering och prioriteringsverktyg {#tools}

I Journey Optimizer är det viktigt att hantera kampanjernas och resornas volym och tidpunkter för att undvika överväldigande kunder med alltför många interaktioner. Journey Optimizer har flera verktyg för konflikthantering och -prioritering.

De här verktygen är tillgängliga för kampanjer och för enkät-, målgrupps- och läsmålgruppsresor.

Genom att utnyttja dessa verktyg kan ni säkerställa smidigare och mer målinriktad marknadsföring och leverera rätt budskap vid rätt tidpunkt samtidigt som ni undviker konflikter och överbelastningar.

### Konfliktidentifieringsverktyg

Med **konfliktidentifieringsverktyget** kan du identifiera potentiella överlappningar i resor och kampanjer. Detta är avgörande eftersom alltför många samtidiga kommunikationer kan leda till att kunderna blir trötta. Med Journey Optimizer kan du övervaka element som tidslinjer, målgruppsöverlappning och kanalkonfigurationer. Genom att identifiera konflikter tidigt kan ni förfina era kampanjer för att undvika att bombardera kunder med flera meddelanden samtidigt.

➡️ [Lär dig hur du upptäcker potentiella konflikter i resor och kampanjer &#x200B;](conflicts.md)

### Prioritetspoäng

**Prioritetspoäng** hjälper dig att styra vilka kampanjer eller resor som prioriteras när en kund kvalificerar sig för flera kommunikationer. Detta är särskilt användbart för inkommande kanaler som webben och mobiler, där endast en kampanj kan visas åt gången. Genom att tilldela varje resa eller kampanj en prioritetspoäng kan ni se till att det viktigaste meddelandet levereras först.

➡️ [Lär dig hur du tilldelar prioritetspoäng till resor och kampanjer](priority-scores.md)

### Regeluppsättningar

Med regeluppsättningar kan du **gruppera flera regler i regeluppsättningar** och använda dem på de resor och kampanjer du vill använda. Detta ger förbättrad detaljrikedom för att begränsa hur ofta och hur många resor en kund kan gå in på inom en viss tidsram eller styra hur ofta användaren får ett meddelande beroende på kommunikationstypen. [Lär dig arbeta med regeluppsättningar](../conflict-prioritization/rule-sets.md)

* **Resebegränsning och skiljeförfarande**

  Med regeluppsättningar kan du begränsa hur ofta och hur många resor en kund kan registrera inom en viss tidsperiod. Du kan också ställa in regler för att begränsa antalet reseposter för en profil eller begränsa antalet resor som en kund kan registrera samtidigt.

  Dessutom kan ni använda skiljedomsinställningar för att bestämma vilken resa en kund ska ange om de är kvalificerade för flera resor, och använda prioriteringspoäng för att avgöra vilken resa som passar bäst.

  ➡️ [Lär dig hur du arbetar med capping och medling på resan](journey-capping.md)

* **Frekvensbegränsning per kanal och kommunikationstyp**

  Du kan också använda regeluppsättningar för att ange frekvensbegränsning efter kommunikationstyp (t.ex. Försäljning, Kampanj) för att förhindra att kunder med liknande meddelanden överbelastas. Ni kan styra frekvensen över flera kanaler och automatiskt utesluta överbegärda profiler för att få en bättre kundupplevelse.

  ➡️ [Lär dig hur du anger frekvensbegränsning efter kanal- och kommunikationstyp](../conflict-prioritization/channel-capping.md)

## Skyddsritningar och begränsningar

* **Kampanjer och prioritetspoäng** - I kampanjer är prioritetspoäng endast tillgängligt för de inkommande kanalerna **web**, **in-app** och **code-based**.

* **Fördröjning för uppdatering av profilräknare**

  Det kan ta upp till 10 minuter efter att en kund har registrerat en resa för att uppdatera profilräknarvärdet.

  Om en profil går in i två resor inom ett kort fönster kanske den andra resan inte korrekt känner igen att frekvensgränsen redan har nåtts, vilket kan göra det möjligt för profilen att gå in på båda resorna.

* **Namnområdesprioritet för spärrning av resepost**

  Fästning vid inmatning stöds bara om det namnutrymme som valts under resan är det högsta prioritetsnamnområde som definieras i sandlådan. Om namnområdesprioriteten inte har konfigurerats explicit är e-post den högsta standardprioriteten.

* **Samtidiga aktiveringar i målgruppsklassificeringsresor**

  När flera kvalificeringsresor aktiveras av samma publikkvalificeringshändelse, kommer antalet för att klippa in inte att vara korrekt. Om antalet ligger under gränsen fortsätter resan att godtyckas, men den kommer inte att kunna få de senaste siffrorna med samtidiga aktiveringar.
