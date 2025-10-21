---
product: experience platform
solution: Experience Platform
title: Automatiskt optimerade modeller
description: Läs mer om modeller för automatisk optimering
badge: label="Äldre" type="Informative"
feature: Ranking, Decision Management
role: User
level: Experienced
exl-id: a85de6a9-ece2-43da-8789-e4f8b0e4a0e7
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '1492'
ht-degree: 0%

---

# Automatiskt optimerade modeller {#auto-optimization-model}

En automatisk optimeringsmodell syftar till att leverera erbjudanden som maximerar den avkastning (KPI) som affärsklienterna sätter. Dessa nyckeltal kan vara i form av konverteringsgrader, intäkter osv. I nuläget fokuserar automatisk optimering på att optimera erbjudandeklick med erbjudandekonvertering som mål. Automatisk optimering är icke-personaliserat och optimerar baserat på erbjudandets&quot;globala&quot; prestanda.

## Krav för datauppsättning

För att utbilda en automatisk optimeringsmodell måste datauppsättningen uppfylla följande minimikrav:

* Minst två erbjudanden i datauppsättningen måste ha minst 100 visningshändelser och 5 klickningshändelser under de senaste 14 dagarna.
* Erbjudanden med färre än 100 skärmar och/eller 5 klickningar under de senaste 14 dagarna behandlas av modellen som nya erbjudanden och kan endast hanteras av undersökningsbanken.
* Erbjudanden med fler än 100 skärmar och 5 klickningshändelser under de senaste 14 dagarna behandlas av modellen som befintliga erbjudanden och kan hanteras av både utforsknings- och utnyttjandebanditer.

Tills första gången en automatisk optimeringsmodell tränas kommer erbjudanden inom en urvalsstrategi som använder en automatisk optimeringsmodell att presenteras på måfå.

## Begränsningar {#limitations}

Användningen av automatiska optimeringsmodeller för beslutshantering omfattas av nedanstående begränsningar:

* Automatiska optimeringsmodeller fungerar inte med API:t för gruppbeslut.
* Feedback som behövs för att skapa en modell måste skickas in som en upplevelsehändelse. Den ska inte skickas in automatiskt i [!DNL Journey Optimizer] kanaler.

## Terminologi {#terminology}

Följande termer är användbara när du diskuterar automatisk optimering:

* **Flerarmad bandit**: En [flerarmad bandit](https://en.wikipedia.org/wiki/Multi-armed_bandit){target="_blank"}-metod för optimering balanserar undersökande inlärning och utnyttjande av inlärningen.

* **Thomson-sampling**: Thompson-sampling är en algoritm för onlinebeslutsproblem där åtgärder vidtas sekventiellt på ett sätt som måste balansera mellan att utnyttja det som är känt för att maximera omedelbara prestanda och investera för att samla in ny information som kan förbättra framtida prestanda. [Läs mer](#thompson-sampling)

* [**Beta-distribution**](https://en.wikipedia.org/wiki/Beta_distribution){target="_blank"}: En uppsättning kontinuerliga [sannolikhetsfördelningar](https://en.wikipedia.org/wiki/Probability_distribution){target="_blank"} som definieras i intervallet [0, 1] [parametriserad](https://en.wikipedia.org/wiki/Statistical_parameter){target="_blank"} av två positiva [formparametrar](https://en.wikipedia.org/wiki/Shape_parameter){target="_blank"}.

## Thompson Sampling {#thompson-sampling}

Den algoritm som ligger till grund för automatisk optimering är **Thompson sampling**. I det här avsnittet diskuterar vi intuitionen bakom Thompson-provtagning.

[Thompson sampling](https://en.wikipedia.org/wiki/Thompson_sampling){target="_blank"}, eller Bayesian bandits, är en bayesisk lösning på problemet med flerarmad bandit.  Grundtanken är att behandla den genomsnittliga belöningen 𝛍 från varje erbjudande som en **slumpmässig variabel** och använda de data som vi har samlat in hittills för att uppdatera vår&quot;tro&quot; om den genomsnittliga belöningen. Denna trosuppfattning representeras matematiskt av en **sannolikhetsfördelning efter** - i stort sett ett intervall av värden för den genomsnittliga belöningen, tillsammans med den sannolikhet (eller sannolikhet) som belöningen har för varje erbjudande. För varje beslut ska vi sedan **ta ett prov från var och en av dessa belöningsfördelningar** och välja det erbjudande vars provbelöning hade det högsta värdet.

Denna process illustreras i bilden nedan, där vi har tre olika erbjudanden. Till att börja med har vi inga bevis från data och vi antar att alla erbjudanden har en enhetlig fördelning efter belöningen. Vi tar ett prov från varje offerts fördelning efter belöningen. Det exempel som valts ut från distributionen av erbjudandet 2 har det högsta värdet. Detta är ett exempel på **utforskande**. När vi har visat erbjudandet 2 samlar vi in eventuell belöning (t.ex. konvertering/ingen konvertering) och uppdaterar posteriordistributionen av erbjudandet 2 med hjälp av Bayes Theorem enligt nedan.  Vi fortsätter med den här processen och uppdaterar efterhandsfördelningen varje gång ett erbjudande visas och belöningen samlas in. I den andra siffran väljs erbjudande 3 - trots att erbjudandet 1 har den högsta genomsnittliga belöningen (den posteriorbelöningsfördelningen ligger längst till höger) har provtagningsprocessen från varje distribution lett till att vi valt ett till synes ooptimalt erbjudande 3. På så sätt ger vi oss själva möjlighet att lära oss mer om den verkliga belöningsfördelningen i Erbjudande 3.

I takt med att fler prover samlas in ökar förtroendet och en mer korrekt uppskattning av den möjliga belöningen görs (motsvarande mindre belöningar). Den här processen med att uppdatera vår tro allt eftersom fler bevis blir tillgängliga kallas **Bayesian Inference**.

Om ett erbjudande (t.ex. erbjudande 1) är en tydlig vinnare kommer dess belöningsfördelning att separeras från andra. För varje beslut är den utvalda belöningen från erbjudande 1 troligtvis den högsta, och vi väljer den med större sannolikhet. Det här är **utnyttjande** - vi är mycket övertygade om att erbjudande 1 är det bästa, så det väljs för att maximera belöningar.

![](../assets/ai-ranking-thompson-sampling.png)

**Figur 1**: *För varje beslut tar vi ett prov från en punkt från belöningsfördelningen. Erbjudandet med det högsta samplingsvärdet (konverteringsgrad) kommer att väljas. I den inledande fasen har alla erbjudanden en enhetlig fördelning eftersom vi inte har några belägg för konverteringsgraden för erbjudandena från uppgifterna. Efterhandsdistributionen blir snävare och mer exakt när vi samlar in fler prover. I slutändan väljs erbjudandet med den högsta konverteringsgraden varje gång.*

<!--
![](../assets/ai-ranking-thompson-sampling-initial.png)
![](../assets/ai-ranking-thompson-sampling-intermediate.png)
![](../assets/ai-ranking-thompson-sampling-ultimate.png)
-->

+++**Teknisk information**

För att beräkna/uppdatera distributioner använder vi **Bayes Theorem**. För varje erbjudande ***i*** vill vi beräkna deras ***P(𝛍i | data)***, dvs. för varje erbjudande ***i***, hur sannolikt det är att belöningsvärdet **𝛍i** är, med tanke på de data som vi hittills har samlat in för det erbjudandet.

Från Bayes Theorem:

***Posterior = Sannolikhet * Tidigare***

Sannolikheten **för föregående** är den inledande gissningen om sannolikheten för att skapa utdata. Sannolikheten, efter att vissa bevis har samlats in, kallas för den **posteriorsannolikheten**. 

Automatisk optimering är utformat för att ta hänsyn till binära belöningar (klicka/klicka inte). I det här fallet representerar sannolikheten antalet lyckade försök från N-testversioner och modelleras av en **binomialfördelning**. För vissa sannolikhetsfunktioner, om du väljer en viss tidigare version, hamnar den bakre delen i samma fördelning som den föregående. En sådan tidigare version kallas **konjugera tidigare**. Den här typen av förhandsversioner gör det väldigt enkelt att beräkna posteriorfördelningen. **Beta-fördelningen** är ett konjugat före binomialsannolikheten (binära belöningar) och är därför ett bekvämt och vettigt val för den tidigare och senare sannolikhetsfördelningen. Beta-distributionen har två parametrar, ***α*** och ***β***. Dessa parametrar kan ses som antalet lyckade och misslyckade samt medelvärdet som ges av:

![](../assets/ai-ranking-beta-distribution.png)

Sannolikhetsfunktionen, som vi förklarade ovan, modelleras av en binomial distribution, med lyckade (konverteringar) och fel (inga konverteringar) och q är en [slumpvariabel](https://en.wikipedia.org/wiki/Random_variable){target="_blank"} med en [betadistribution](https://en.wikipedia.org/wiki/Beta_distribution){target="_blank"}.

Föregående modell baseras på distributionen av Beta och den bakre distributionen har följande format:

![](../assets/ai-ranking-posterior-distribution.svg)

Bakgrundsvärdet beräknas genom att antalet lyckade och misslyckade försök läggs till i de befintliga parametrarna ***α***, ***β***.

För automatisk optimering, som visas i exemplet ovan, börjar vi med en tidigare distribution av ***Beta(1, 1)*** (enhetlig fördelning) för alla erbjudanden och efter att ha lyckats och misslyckats för ett visst erbjudande, blir den efterställda en Beta-distribution med parametrarna ***(s+α, f+β)*** för det erbjudandet.
+++

**Relaterade ämnen**:

Mer information om Thompson-provtagning finns i följande forskningsrapporter:

* [En empirisk utvärdering av Thompson Sampling](https://proceedings.neurips.cc/paper/2011/file/e53a0a2978c28872a4505bdb51db06dc-Paper.pdf){target="_blank"}
* [Analys av Thompson Sampling för det multiväpnade Bandit-problemet](https://proceedings.mlr.press/v23/agrawal12/agrawal12.pdf){target="_blank"}

## Problem med kallstart {#cold-start}

Problemet med&quot;kallstart&quot; uppstår när ett nytt erbjudande läggs till i en kampanj och det inte finns några tillgängliga uppgifter om det nya erbjudandets konverteringsgrad. Under den här perioden måste vi ta fram en strategi för hur ofta det nya erbjudandet väljs så att prestandasänkningen minimeras, samtidigt som vi samlar in information om konverteringsgraden för det nya erbjudandet. Det finns flera lösningar för att ta itu med det här problemet. Nyckeln är att hitta en balans mellan utforskandet av detta nya erbjudande, samtidigt som vi inte offrar utnyttjandet så mycket. För närvarande använder vi&quot;enhetlig fördelning&quot; som vår första gissning om det nya erbjudandets konverteringsgrad (tidigare distribution). I princip ger vi alla konverteringsgrader samma sannolikhet för förekomst.


![](../assets/ai-ranking-cold-start-strategies.png)

**Figur 2**: *Överväg en kampanj med 3 erbjudanden. Medan kampanjen är aktiv läggs erbjudande 4 till i kampanjen. Till att börja med har vi inga uppgifter om konverteringsgraden för erbjudande 4 och vi måste ta itu med problemet med kallstart. Vi använder enhetlig distribution som vår första gissning om konverteringsgraden i Erbjudande 4, medan vi samlar in data för det nya erbjudandet. Som förklaras i avsnittet [Thompson sampling](#thompson-sampling) kan vi ta prov på punkter från offerternas efterkommande belöningar och välja det erbjudande som har det högsta exempelvärdet för att välja vilket erbjudande som ska visas för en användare. I exemplet ovan väljs erbjudande 4 och senare baserat på den belöning som samlats in, uppdateras den bakre fördelningen av erbjudandet enligt beskrivningen i avsnittet [Thompson sampling](#thompson-sampling).*

## Lyft mätning {#lift}

&quot;Lyft&quot; är det mätvärde som används för att mäta resultatet för alla strategier som används i rangordningstjänsten, jämfört med baslinjestrategin (serbjudandena är bara slumpmässiga).

Om vi t.ex. är intresserade av att mäta resultatet för en Thompson Sampling-strategi (TS) som används i rangordningstjänsten och KPI är konverteringsgraden (CVR), definieras&quot;lyften&quot; i TS-strategin mot baslinjestrategin som:

![](../assets/ai-ranking-lift.png)
