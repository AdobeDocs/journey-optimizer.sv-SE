---
title: Frågor och svar om beslut
description: Få svar på vanliga frågor om beslutsfunktioner
feature: Decisioning
topic: Integrations
role: User
level: Intermediate
version: Journey Orchestration
source-git-commit: 74f8db8f71cbf51260868a93702a563b3c0d4a2d
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 0%

---

# Frågor och svar om beslut {#decisioning-faq}

På den här sidan hittar du svar på vanliga frågor om beslutsfunktioner i Adobe Journey Optimizer.

## Begränsningsregler {#capping-rules}

+++**Vad händer när flera appningsregler tillämpas på ett erbjudande?**

Ett erbjudande har ett tak så snart **ett enskilt villkor är uppfyllt**. När det finns flera regler för begränsning av antalet prenumerationer upphör erbjudandet att visas när en regel når sitt tröskelvärde.

**Exempel:**
Om du definierar två regler för begränsning av ett erbjudande:
* 5 gånger per profil och vecka
* 100 gånger totalt för alla användare

Erbjudandet kommer att upphöra att visas för en användare när de har sett det fem gånger i veckan, även om det totala taket på 100 inte har uppnåtts än. På samma sätt upphör erbjudandet att visas för alla användare när 100 totala visningar har uppnåtts.

Läs mer om [begränsning av regler](items.md#capping).

+++

## Rankningsformler {#ranking-formulas}

+++**Vilken är målgruppernas roll jämfört med en fullständig datauppsättning i AI-modeller?**

När du konfigurerar [AI-modeller](ranking/ai-models.md) har både datauppsättningar och målgrupper olika syften.

* **Datauppsättningar**: Hämta konverteringshändelser (klick, order, intäkter) som fungerar som optimeringsmål för modellen.
* **Publiker**: Funktion som prediktorvariabler som gör att modellen kan anpassa rekommendationer baserat på medlemskap i kundsegment.

Målgrupperna begränsar inte eller utökar inte modellens omfång. I stället tillhandahåller de sammanhangsberoende attribut som förbättrar modellens förmåga att skapa personaliserade prognoser över olika kundsegment.

Båda komponenterna krävs för effektiva [personaliserade optimeringsmodeller](ranking/personalized-optimization-model.md) med modellprestanda.

+++

+++**Hur påverkar ändringar i erbjudandesamlingar automatisk optimering eller personaliserade optimeringsmodeller?**

Den automatiska optimeringsmodellen levererar trafik till nästa bästa tillgängliga erbjudande baserat på trafikdata från de senaste 14 dagarna, oavsett om den personaliserade optimeringsmodellen använder trafikdata från de senaste 30 dagarna eller inte.

När flera erbjudanden tas bort samtidigt och de återstående erbjudandena har minimala trafikdata inom 14-dagars- eller 30-dagarsfönstret kan modellen uppvisa ett ooptimalt beteende, inklusive slumpmässiga distributionsmönster eller fördomar mot erbjudanden med högre konverteringsgrad baserat på begränsade visningsdata.

**Bästa praxis**: När erbjudandesamlingar ändras avsevärt bör du kontrollera att återstående erbjudanden har tillräckliga historiska prestandadata för att behålla modellens effektivitet.

+++

+++**Hur snabbt inför AI-modeller nya erbjudanden?**

AI-modeller identifierar och börjar testa nya erbjudanden i nästa utbildningscykel:

* **Automatisk optimering** identifierar och börjar testa nya erbjudanden under nästa utbildningscykel. Automatisk optimeringskurs sker 3 till 4 gånger dagligen, ungefär var 6: e timme.
* **Anpassad optimering** identifierar och börjar testa nya erbjudanden allt eftersom de läggs till i erbjudandestrategin. De kommer att inkluderas i slumpmässig provtrafik. Sedan personaliseras dessa erbjudanden i modellens nästa utbildningscykel, som sker varje vecka.

När båda modellerna har identifierats börjar de leverera nya erbjudanden till vissa besökare omedelbart för att testa deras prestanda och samla in uppgifter om deras effektivitet.

Läs mer om modellerna [automatisk optimering](ranking/auto-optimization-model.md) och [personlig optimering](ranking/personalized-optimization-model.md).

+++

+++**Hur optimerar AI-modeller utan kontrollgrupper?**

Både automatisk optimering och personaliserade optimeringsmodeller har en strategi där man kan utnyttja saker och ting som eliminerar behovet av dedikerade kontrollgrupper.

* **Inledande fas**: Modeller börjar med 100 % utforskande, och testar olika erbjudanden för att upprätta baslinjeprestandadata.
* **Adaptiv optimering**: När beteendehändelser ackumuleras och förutsägelsenoggrannheten förbättras balanserar modellerna automatiskt utforskande och utnyttjande.
* **Pågående inlärning**: Systemet tilldelar progressivt mer trafik till högpresterande erbjudanden samtidigt som det fortsätter att testa alternativen.

Detta garanterar kontinuerlig inlärning och optimering över all trafik utan att särskilda kontrollgrupper behövs.

+++

+++**Vilka är de lägsta trafikkraven för optimal AI-modellprestanda?**

Adobe rekommenderar följande minimitrösklar för att säkerställa effektiva modellprestanda:
* 1 000 visningar per erbjudande/artikel per vecka
* 100 konverteringshändelser per erbjudande/artikel per vecka

<!--**Absolute minimums (per 30 days):**
* At least **250 impressions** per offer/item  
* At least **25 conversion events** per offer/item-->

Som standard försöker systemet inte skapa personaliserade modeller för erbjudanden/artiklar med färre än 1 000 visningar eller 50 konverteringshändelser.

>[!NOTE]
>
>I produktionsmiljöer med stora erbjudandekataloger (~300 erbjudanden) och begränsande affärsregler kan vissa erbjudanden närma sig lägre absoluta tröskelvärden (250 visningar och 25 konverteringar per 30 dagar). Dessa utgör de lägsta datakraven för modellutbildning, men garanterar kanske inte optimala prestanda.

Läs mer om [datainsamlingskrav](data-collection/data-collection.md).

+++

+++**Hur påverkar liknande erbjudanden prestanda för AI-modeller?**

AI-modeller genererar större personaliseringsfördelar när erbjudanden passar olika kundsegment. När erbjudandena liknar varandra i hög grad är det två typiska utfall:

* **Motsvarande prestanda**: Erbjudandena fungerar likadant och får ungefär samma trafikfördelning.
* **Dominerande erbjudande**: Mindre skillnader gör att ett erbjudande presterar bättre än andra i alla segment, vilket fångar huvuddelen av trafiken.

>[!NOTE]
>
>Offertdifferentieringen garanterar inte en balanserad trafikfördelning. Erbjudanden med objektivt sett oöverträffade priser (t.ex. 100 euro i rabatt jämfört med 50 euro) kommer normalt att dominera i alla kundsegment oavsett personaliseringsgrad.

**Bästa praxis**: Designa erbjuder med meningsfull differentiering som är anpassad efter olika kundsegmentsinställningar för att maximera AI-modellens effektivitet.

+++

+++**Hur påverkar trafikavvikelser AI-modellens prestanda?**

Trafikavvikelser införlivas i modellen proportionellt i det 30-dagars rullande fönstret, vilket ger modellstabilitet vid tillfälliga trafikfluktuationer. Kortsiktiga toppar och fall påverkar inte modellens prognoser eller prestanda nämnvärt.

En tillfällig trafiktoppning (till exempel två gånger den dagliga trafiken) har minimal effekt på den totala modellprestandan eftersom den onormala trafiken utgör en liten del av den 30-dagars datauppsättningen.

+++
