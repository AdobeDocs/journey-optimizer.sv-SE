---
title: Frågor och svar om beslut
description: Få svar på vanliga frågor om beslutsfunktioner
feature: Decisioning
topic: Integrations
role: User
level: Intermediate
version: Journey Orchestration
hide: true
hidefromtoc: true
source-git-commit: 59e85eb7a14f88d95b2ef97e3ace11a65f115b75
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 0%

---

# Frågor och svar om beslut {#decisioning-faq}

På den här sidan hittar du svar på vanliga frågor om beslutsfunktioner i Adobe Journey Optimizer.

## Begränsningsregler {#capping-rules}

+++**Vad händer när du skapar mer än en begränsningsregel för ett erbjudande? Kommer vi sluta visa erbjudandet när vi matchar någon av appreglerna, eller alla?**

Erbjudandet har en övre gräns så snart **ett villkor är uppfyllt**. Detta innebär att alla regler om begränsning av prenumerationstak kommer att hindra att erbjudandet visas när tröskelvärdet har uppnåtts.

Om du till exempel har två regler för begränsning:
* 5 gånger per profil och vecka
* 100 gånger totalt för alla användare

Erbjudandet kommer att upphöra att visas för en användare när de har sett det fem gånger i veckan, även om det totala taket på 100 inte har uppnåtts än. På samma sätt upphör erbjudandet att visas för alla användare när 100 totala visningar har uppnåtts.

Läs mer om [begränsning av regler](items.md#capping).

+++

## Rankningsformler {#ranking-formulas}

+++**Varför skulle jag lägga till en målgrupp i en AI-modell? Vad är fördelen med att lägga till målgrupper jämfört med en fullständig datauppsättning? Begränsar det modellen eller utökar modellen?**

När du arbetar med AI-modeller (särskilt [personaliserade optimeringsmodeller](ranking/personalized-optimization-model.md)):

* **Datauppsättningar** läggs till för att samla in konverteringshändelser (klick, order, intäkter). Detta är de resultat som modellen försöker optimera för.
* **Publiker** läggs till för att användas som prediktorvariabler i modellen. De hjälper er att personalisera förutsägelser för att försöka förutse klick, order eller intäkter för olika kundsegment.

Både datauppsättningar och målgrupper behövs för att den personaliserade optimeringsmodellen ska fungera effektivt. Målgrupperna **varken begränsar eller utökar** modellen, utan i stället ger de ytterligare kontext som hjälper modellen att fatta bättre personaliserade beslut.

Läs mer om [AI-modeller](ranking/ai-models.md).

+++

+++**Kommer tillägg eller borttagning av erbjudanden i en samling att påverka modellen om jag använder automatiska optimeringsmodeller eller personaliserade optimeringsmodeller?**

Båda modellerna levererar trafik till nästa bästa tillgängliga erbjudande baserat på trafikdata från de senaste 30 dagarna.

Om flera erbjudanden tas bort samtidigt och de återstående erbjudandena inte når så mycket trafik under de senaste 30 dagarna, kan distributionen av erbjudanden uppträda oväntat. Detta kan leda till slumpmässig distribution eller partiskhet i vissa erbjudanden som har en högre konverteringsgrad baserat på bara ett fåtal visningar.

**Bästa praxis**: När du gör betydande ändringar i erbjudandesamlingar måste du se till att de återstående erbjudandena har tillräckligt med historiska prestandadata för att behålla optimala modellprestanda.

+++

+++**Hur lång tid tar det för AI-modellerna att förstå att det finns nytt innehåll tillagt och börja lägga till dem i mixen?**

Båda AI-modellerna identifierar nya erbjudanden under nästa utbildningsperiod:

* **Automatisk optimering**: Dagliga utbildningstillfällen
* **Anpassad optimering**: Veckokurser körs

När båda modellerna har identifierats börjar de leverera nya erbjudanden till vissa besökare omedelbart för att testa deras prestanda och samla in uppgifter om deras effektivitet.

Läs mer om modellerna [automatisk optimering](ranking/auto-optimization-model.md) och [personlig optimering](ranking/personalized-optimization-model.md).

+++

+++**Om vi inte har kontrollgrupper i AI-modellerna, lär vi oss och optimerar vi all trafik samtidigt?**

Ja. Båda AI-modellerna (automatisk optimering och personaliserad optimering) använder en utforskande och utnyttjandemetod:

* Till att börja med är båda modellerna **100 % prospektering**, vilket innebär att de testar olika erbjudanden för att samla in prestandadata.
* Med tiden hanterar modellerna **automatiskt utforsknings-/utnyttjandehandeln** allt eftersom beteendehändelser samlas in och förutsägelserna förbättras.
* Modellerna leder gradvis över mer trafik till bättre erbjudanden samtidigt som de fortsätter att utforska och testa andra alternativ.

Detta garanterar kontinuerlig inlärning och optimering över all trafik utan att särskilda kontrollgrupper behövs.

+++

+++**Hur många optimeringshändelser behöver vi vara statistiskt viktiga? Finns det ett lägsta tröskelvärde för trafik för en yta?**

För att optimera modellprestanda rekommenderar Adobe följande miniminivåer:

**Rekommenderade minimumvärden (per vecka):**
* Minst **1 000 visningar** per erbjudande/artikel
* Minst **100 konverteringshändelser** per erbjudande/artikel

<!--**Absolute minimums (per 30 days):**
* At least **250 impressions** per offer/item  
* At least **25 conversion events** per offer/item-->

Som standard försöker systemet inte skapa personaliserade modeller för erbjudanden/artiklar med färre än 1 000 visningar eller 50 konverteringshändelser.

**Viktigt**: I praktiken har vissa kunder många erbjudanden (~300) i en och samma modell, och vissa erbjudanden kan ha mycket restriktiva affärsregler. De absoluta minimumen (250 visningar/25 konverteringar per 30 dagar) är det lägsta tröskelvärde som systemet har stöd för för att bygga modeller.

Läs mer om [datainsamlingskrav](data-collection/data-collection.md).

+++

+++**Måste innehållet i erbjudandena vara tydligt differentierat för att AI-modellerna ska fungera bra? Vad händer om jag har flera erbjudanden som är för lika?**

I allmänhet är det mer sannolikt att AI-modellen genererar fördelar av personalisering när **erbjudanden passar olika typer av kunder**.

När erbjudandena är mycket lika är det troligt att ett av följande två utfall visas:

* **Liknande prestanda**: Erbjudandena fungerar likadant och får en relativt jämn andel av trafiken.
* **Dominans**: Små skillnader kan göra att ett erbjudande dominerar de andra för alla kundtyper, och det får större delen av trafiken.

>[!NOTE]
>
>Skillnader i erbjudanden är ingen garanti för att ett erbjudande inte kommer att dominera de andra. Ett erbjudande på 100 euro kommer till exempel nästan alltid att ge ett pris på 50 euro över alla kundtyper, oavsett personalisering.

**Bästa praxis**: Se till att dina erbjudanden ger meningsfull differentiering som kan tilltala olika kundsegment för optimala AI-modellprestanda.

+++

+++**Vad händer med modellen om det finns trafikavvikelser, som en stor trafikspik? Kommer det att orsaka problem eller öka tyngdkraften?**

En trafikspik skulle inkluderas i modellerna proportionellt mot annan trafik under de senaste 30 dagarna.

En trafiktopp på 2 gånger dagligen kommer till exempel att få en relativt blygsam effekt på den övergripande modellen, eftersom det finns 29 dagars normal trafik som representerar betydligt mer av den totala beteendeinformationen.

**Nyckelpunkt**: Det rullande 30-dagars fönstret hjälper modellen att behålla stabiliteten under temporära trafikavvikelser. Kortsiktiga toppar och dalar påverkar inte modellens prestanda nämnvärt.

+++

## Relaterade ämnen {#related-topics}

<!--* [Get started with Decisioning](gs-experience-decisioning.md)-->
* [Skapa beslutsobjekt](items.md)
* [Översikt över AI-modeller](ranking/ai-models.md)
* [Avgörande av skyddsräcken och begränsningar](decisioning-guardrails.md)

