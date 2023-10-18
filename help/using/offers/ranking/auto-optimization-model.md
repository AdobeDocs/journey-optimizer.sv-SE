---
product: experience platform
solution: Experience Platform
title: Automatiskt optimerade modeller
description: Läs mer om modeller för automatisk optimering
feature: Ranking, Decision Management
role: User
level: Experienced
exl-id: a85de6a9-ece2-43da-8789-e4f8b0e4a0e7
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: tm+mt
source-wordcount: '1365'
ht-degree: 0%

---

# Automatiskt optimerade modeller {#auto-optimization-model}

En automatisk optimeringsmodell syftar till att leverera erbjudanden som maximerar den avkastning (KPI) som affärsklienterna sätter. Dessa nyckeltal kan vara i form av konverteringsgrader, intäkter osv. I nuläget fokuserar automatisk optimering på att optimera erbjudandeklick med erbjudandekonvertering som mål. Automatisk optimering är icke-personaliserat och optimerar baserat på erbjudandets&quot;globala&quot; prestanda.

## Begränsningar {#limitations}

Användningen av automatiska optimeringsmodeller för beslutshantering omfattas av nedanstående begränsningar:

* Automatiska optimeringsmodeller fungerar inte med API:t för gruppbeslut.
* Feedback som behövs för att skapa en modell måste skickas in som en upplevelsehändelse. Den ska inte skickas in automatiskt [!DNL Journey Optimizer] kanaler.

## Terminologi {#terminology}

Följande termer är användbara när du diskuterar automatisk optimering:

* **Flerarmad bandit**: A [multiväpnad bandit](https://en.wikipedia.org/wiki/Multi-armed_bandit){target="_blank"} en strategi för optimering som ger en balans mellan undersökande och utnyttjande av det inlärningen.

* **Thomson sampling**: Thompson-sampling är en algoritm för onlinebeslutsproblem där åtgärder vidtas sekventiellt på ett sätt som måste balansera mellan att utnyttja det som är känt för att maximera omedelbara prestanda och investera för att samla in ny information som kan förbättra framtida prestanda. [Läs mer](#thompson-sampling)

* [**Betadistribution**](https://en.wikipedia.org/wiki/Beta_distribution){target="_blank"}: Set of continuous [probability distributions](https://en.wikipedia.org/wiki/Probability_distribution){target="_blank"} defined on the interval [0, 1] [parameterized](https://en.wikipedia.org/wiki/Statistical_parameter){target="_blank"} by two positive [shape parameters](https://en.wikipedia.org/wiki/Shape_parameter){target="_blank"}.

## Thompson Sampling {#thompson-sampling}

Den algoritm som ligger till grund för automatisk optimering är **Thompson sampling**. I det här avsnittet diskuterar vi intuitionen bakom Thompson-provtagning.

[Thompson sampling](https://en.wikipedia.org/wiki/Thompson_sampling){target="_blank"}, eller baysiska banditer, är en bayesisk lösning på problemet med den flerarmade banken.  Grundtanken är att behandla den genomsnittliga belöningen ? från varje erbjudande som en **random-variabel** och använda de data vi hittills har samlat in för att uppdatera vår&quot;tro&quot; om den genomsnittliga belöningen. Den här&quot;tron&quot; representeras matematiskt av en **sannolikhetsfördelning efter allvarlighetsgrad** - i stort sett ett värdeintervall för den genomsnittliga belöningen, tillsammans med den sannolikhet (eller sannolikhet) som belöningen har för varje erbjudande. För varje beslut kommer vi att **ta prov på en punkt från var och en av dessa belöningar** och välj det erbjudande vars provbelöning hade det högsta värdet.

Denna process illustreras i bilden nedan, där vi har tre olika erbjudanden. Till att börja med har vi inga bevis från data och vi antar att alla erbjudanden har en enhetlig fördelning efter belöningen. Vi tar ett prov från varje offerts fördelning efter belöningen. Det exempel som valts ut från distributionen av erbjudandet 2 har det högsta värdet. Detta är ett exempel på **prospektering**. När vi har visat erbjudandet 2 samlar vi in eventuell belöning (t.ex. konvertering/ingen konvertering) och uppdaterar posteriordistributionen av erbjudandet 2 med hjälp av Bayes Theorem enligt nedan.  Vi fortsätter med den här processen och uppdaterar efterhandsfördelningen varje gång ett erbjudande visas och belöningen samlas in. I den andra siffran väljs erbjudande 3 - trots att erbjudandet 1 har den högsta genomsnittliga belöningen (den posteriorbelöningsfördelningen ligger längst till höger) har provtagningsprocessen från varje distribution lett till att vi valt ett till synes ooptimalt erbjudande 3. På så sätt ger vi oss själva möjlighet att lära oss mer om den verkliga belöningsfördelningen i Erbjudande 3.

I takt med att fler prover samlas in ökar förtroendet och en mer korrekt uppskattning av den möjliga belöningen görs (motsvarande mindre belöningar). Processen med att uppdatera vår tro när fler bevis blir tillgängliga kallas **Bayersiska Inferensen**.

Om ett erbjudande (t.ex. erbjudande 1) är en tydlig vinnare kommer dess belöningsfördelning att separeras från andra. För varje beslut är den utvalda belöningen från erbjudande 1 troligtvis den högsta, och vi väljer den med större sannolikhet. Det här är **utnyttjande** - vi är övertygade om att erbjudande 1 är det bästa och därför väljs det för att maximera belöningarna.

![](../assets/ai-ranking-thompson-sampling.png)

**Figur 1**: *För varje beslut tar vi ett prov på en poäng från belöningsutdelningarna. Erbjudandet med det högsta samplingsvärdet (konverteringsgrad) kommer att väljas. I den inledande fasen har alla erbjudanden en enhetlig fördelning eftersom vi inte har några belägg för konverteringsgraden för erbjudandena från uppgifterna. Efterhandsdistributionen blir snävare och mer exakt när vi samlar in fler prover. I slutändan kommer det anbud som har högst konverteringsgrad att väljas ut varje gång.*

<!--
![](../assets/ai-ranking-thompson-sampling-initial.png)
![](../assets/ai-ranking-thompson-sampling-intermediate.png)
![](../assets/ai-ranking-thompson-sampling-ultimate.png)
-->

+++**Teknisk information**

För att beräkna/uppdatera distributioner använder vi **Bayes Theorem**. För varje erbjudande ***i*** vill vi beräkna deras ***P(??i | data)***, dvs. för varje erbjudande ***i***, hur sannolikt det är att belöningsvärdet **??i** med tanke på de uppgifter vi hittills har samlat in för detta erbjudande.

Från Bayes Theorem:

***Posterior = Sannolikhet * Tidigare***

The **tidigare sannolikhet** är den första gissningen om sannolikheten för att producera en utdata. Sannolikheten för att det ska gå att få fram vissa uppgifter kallas för **sannolikhet efter fel**. 

Automatisk optimering är utformat för att ta hänsyn till binära belöningar (klicka/klicka inte). I detta fall representerar sannolikheten antalet lyckade försök från N-prövningar och modelleras av en **Binomialfördelning**. För vissa sannolikhetsfunktioner, om du väljer en viss tidigare version, hamnar den bakre delen i samma fördelning som den föregående. En sådan tidigare version kallas då **konjugera föregående**. Den här typen av förhandsversioner gör det väldigt enkelt att beräkna posteriorfördelningen. The **Betadistribution** är ett konjugat före binomialsannolikheten (binära belöningar) och är därför ett bekvämt och vettigt val för tidigare och senare sannolikhetsfördelningar.Betafördelningen har två parametrar. ***α*** och ***β***. Dessa parametrar kan ses som antalet lyckade och misslyckade samt medelvärdet som ges av:

![](../assets/ai-ranking-beta-distribution.png)

Sannolikhetsfunktionen, som vi förklarade ovan, är baserad på en Binomial-distribution, med framgångar (konverteringar) och fel (inga konverteringar) och q är en [random-variabel](https://en.wikipedia.org/wiki/Random_variable){target="_blank"} with a [beta distribution](https://en.wikipedia.org/wiki/Beta_distribution){target="_blank"}.

Föregående modell baseras på betadistribution och den posteriala fördelningen har följande format:

![](../assets/ai-ranking-posterior-distribution.svg)

Den efterföljande beräkningen görs genom att antalet lyckade och misslyckade försök läggs till i de befintliga parametrarna ***α***, ***β***.

För automatisk optimering, som i exemplet ovan, börjar vi med en tidigare distribution ***Beta(1, 1)*** (enhetlig fördelning) för alla erbjudanden och efter att ha lyckats och misslyckats för ett visst erbjudande blir posteriorn en betadistribution med parametrar ***(s+α, f+β)*** för det erbjudandet.
+++

**Relaterade ämnen**:

Mer information om Thompson-provtagning finns i följande forskningsrapporter:
* [An Empirical Evaluation of Thompson Sampling](https://proceedings.neurips.cc/paper/2011/file/e53a0a2978c28872a4505bdb51db06dc-Paper.pdf){target="_blank"}
* [Analys av Thompson Sampling för det multiväpnade Bandit-problemet](https://proceedings.mlr.press/v23/agrawal12/agrawal12.pdf){target="_blank"}

## Problem med kallstart {#cold-start}

Problemet med&quot;kallstart&quot; uppstår när ett nytt erbjudande läggs till i en kampanj och det inte finns några tillgängliga uppgifter om det nya erbjudandets konverteringsgrad. Under den här perioden måste vi ta fram en strategi för hur ofta det nya erbjudandet väljs så att prestandasänkningen minimeras, samtidigt som vi samlar in information om konverteringsgraden för det nya erbjudandet. Det finns flera lösningar för att ta itu med det här problemet. Nyckeln är att hitta en balans mellan utforskandet av det nya erbjudandet, samtidigt som vi inte offrar exploateringen så mycket. För närvarande använder vi&quot;enhetlig fördelning&quot; som vår första gissning om det nya erbjudandets konverteringsgrad (tidigare distribution). I princip ger vi alla konverteringsgrader samma sannolikhet för förekomst.


![](../assets/ai-ranking-cold-start-strategies.png)

**Figur 2**: *Överväg en kampanj med 3 erbjudanden. Medan kampanjen är aktiv läggs erbjudande 4 till i kampanjen. Till att börja med har vi inga uppgifter om konverteringsgraden för erbjudande 4 och vi måste ta itu med problemet med kallstart. Vi använder enhetlig distribution som vår första gissning om konverteringsgraden i Erbjudande 4, medan vi samlar in data för det nya erbjudandet. Som förklaras i [Thompson sampling](#thompson-sampling) för att välja vilket erbjudande som ska visas för en användare, tar vi prov på punkter från offerternas efterhandsfördelningar och väljer det erbjudande som har det högsta exempelvärdet. I exemplet ovan väljs erbjudande 4 och senare baserat på den erhållna belöningen, uppdateras den senare distributionen av erbjudandet enligt anvisningarna i [Thompson sampling](#thompson-sampling) -avsnitt.*

## Lyft mätning {#lift}

&quot;Lyft&quot; är det mätvärde som används för att mäta resultatet för alla strategier som används i rangordningstjänsten, jämfört med baslinjestrategin (serbjudandena är bara slumpmässiga).

Om vi t.ex. är intresserade av att mäta resultatet för en Thompson Sampling-strategi (TS) som används i rangordningstjänsten och KPI är konverteringsgraden (CVR), definieras&quot;lyften&quot; i TS-strategin mot baslinjestrategin som:

![](../assets/ai-ranking-lift.png)
