---
solution: Journey Optimizer
product: journey optimizer
title: Vanliga frågor och svar om samordnade kampanjer
description: Frågor och svar om Journey Optimizer samordnade kampanjer
hide: true
hidefromtoc: true
exl-id: 6a660605-5f75-4c0c-af84-9c19d82d30a0
source-git-commit: f850cb5573c321d479fe956e8c9b9bf377e78dfc
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 1%

---

# Vanliga frågor {#faq-oc}

Nedan hittar du Vanliga frågor om Adobe Journey Optimizer samordnade kampanjer.

Behöver du mer information? Använd alternativen för feedback längst ned på den här sidan för att ta upp din fråga.

## Vad är samordnade kampanjer? {#what-are-oc}

Samordnade kampanjer i Adobe Journey Optimizer hjälper varumärken att köra komplexa 1:N-kampanjer i stor skala. De är utformade för varumärkesinitierat engagemang, som kampanjer, säsongskampanjer eller kontobaserad kommunikation.

Jämfört med kampanjer för enstaka sändning för de med **orkestrering och sekvensering** till utgående marknadsföring: målgrupperna rör sig genom ett flerstegsarbetsflöde tillsammans i stället för att få en engångskarta.

## Vad kan jag göra med orkestrerade kampanjer? {#what-can-i-do}

Viktiga funktioner:

* **On-Demand-målgrupper**: Bygg och förfina målgrupper direkt med hjälp av relationsfrågor.
* **Segmentering för flera enheter**: Skapa exakta målgrupper genom att koppla kunddata till relaterade entiteter (t.ex. konton, inköp, bokningar).
* **Synlighet före sändning**: Se rätt antal målgrupper innan du startar för att optimera målinriktningen.
* **Flerstegsarbetsflöden**: Kör sekventiella kampanjer, till exempel säsongskampanjer, produktlanseringar eller lojalitetserbjudanden.

>[!BEGINSHADEBOX]

**Bästa praxis**

* Definiera ett **tydligt kampanjmål** innan du utformar arbetsflöden.
* Börja med en **pilotmålgrupp** för att validera antal och logik innan skalning.
* Behåll segmenteringsreglerna **så enkla som möjligt** för att optimera prestanda och genomskinlighet.
* Använd **konsekventa namnkonventioner** för målgrupper och kampanjer för att underlätta hanteringen.

>[!ENDSHADEBOX]


## Vilka kanaler stöds? {#channels}

Orchestrated Campaigns har stöd för **e-post-, SMS- och push-meddelanden**.

>[!BEGINSHADEBOX]

**Rekommendationer**

* Matcha kanalen med **typen av meddelande** (t.ex. brådskande = SMS, personaliserade erbjudanden = e-post, sammanhangsberoende = push).
* Validera alltid samtycke och prenumerationsinställningar innan du aktiverar en kanal.
* Testa meddelandeåtergivning på flera enheter och klienter för att säkerställa en enhetlig upplevelse.

>[!ENDSHADEBOX]

## Hur skiljer sig Orchestrated Campaigns från Journeys? {#oc-vs-journeys}

* **Samordnade kampanjer**: Bäst för **batch-, en-till-många**-kampanjer. Hela målgrupper rör sig genom kampanjarbetsytan tillsammans.
* **Resor**: Passar bäst för **realtidsengagemang med en-till-en**. Varje kund rör sig genom resan i sin egen takt, triggad av beteende eller händelser.

>[!BEGINSHADEBOX]

**Tips** - Många organisationer använder **båda tillsammans** - resor för triggade, reaktiva upplevelser och samordnade kampanjer för planerade, kalenderbaserade initiativ.

>[!ENDSHADEBOX]

## Vad är segmentering av flera enheter? {#multi-entity}

Kampanjsamordning i Adobe Journey Optimizer använder en relationsdatabas. Den här typen av datamodell har separata scheman med data som är anslutna via 1:1- eller 1:many-relationer. Detta gör att användare kan starta en fråga i vilket schema som helst - inte bara på mottagarnivå - och sedan vända fram och tillbaka till andra relaterade scheman, som inköp, produkter, bokningar eller mottagarinformation, vilket ger stor flexibilitet i hur segment och målgrupper kan skapas och
förfinat.

>[!BEGINSHADEBOX]

**Exempel** - Rikta in dig på alla mottagare med prenumerationer som upphör att gälla inom de kommande 3-h0 dagarna: I Campaign-samordning kan frågan börja med prenumerationsschemat, söka bara i kolumnen för förfallodatum i det schemat och returnera alla prenumerationer som förfaller, och sedan samla in mottagardata som är relaterade till dessa specifika prenumerations-ID:n och returnera resultat snabbare och effektivare än datamodeller som påbörjar varje fråga på mottagarnivå.

>[!ENDSHADEBOX]


## Hur fungerar datamodellen? {#data-model}

Kampanjer använder en **relationsdatabas**. På så sätt kan ni söka efter olika datauppsättningar (t.ex. kunder, produkter, prenumerationer) och koppla dem flexibelt för avancerad segmentering.

>[!BEGINSHADEBOX]

**Bästa praxis**

* Ordna datauppsättningar så att **relationer (kopplingar)** återspeglar affärslogik.
* Undvik onödiga kopplingar för att få frågor att prestera.
* Validera exempelresultaten innan du kör storskaliga extraheringar.

>[!ENDSHADEBOX]

## Kan jag personalisera meddelanden med dessa data? {#personalization}

Ja. I kampanjsamordning kan en mottagarprofil som kallas personentitet uppdateras och data som används för personalisering. Dessutom kan data från länkade entiteter i relationsdatabasen också användas för personalisering. Ni kan använda kundprofiler tillsammans med länkade data (som köp eller prenumerationer) för att anpassa innehåll i alla kanaler som stöds.

>[!BEGINSHADEBOX]

**Rekommendationer**

* Använd **transaktions- och beteendedata** för att göra erbjudanden relevanta.
* Kombinera **statiska attribut** (t.ex. lojalitetsnivå) med **dynamiska attribut** (t.ex. senaste inköpsdatum).
* Håll personaliseringen koncis - överlastning av meddelanden med data kan skada läsbarheten.

>[!ENDSHADEBOX]


## Kan programmet integreras med andra Adobe-lösningar? {#integrations}

Ja. Kampanjsamordning är integrerad med:

* **Customer Journey Analytics**: Det finns rapporter om kampanjsamordning.
* **Real-Time CDP**: Publiker som skapats i kampanjer kan läsas i Real-Time CDP.
* **FFAC (Federated Audience Composition)**: Tillgängligt som tillägg.

## Vad gäller för tillstånd och samtycke? {#permissions}

Tillstånd och samtycke för samordnade kampanjer och resor hanteras centralt i Adobe Experience Platform. De här inställningarna används för båda lösningarna för varje mottagare innan de skickas.

>[!BEGINSHADEBOX]

**Bästa praxis**

* Använd **centraliserad styrning** - undvik att hantera samtycke separat på kampanjnivå.
* Granska regelbundet data om samtycke för att upptäcka inkonsekvenser.
* Respektera **kanalspecifika avanmälningar** - anta inte att globalt medgivande omfattar alla kanaler.

>[!ENDSHADEBOX]

## Kan jag göra ad hoc-segmentering? {#ad-hoc}

I Campaign-orkestrering talar vi om ad hoc-segmentering som&quot;Live-segmentering&quot;, där ni kan komma åt alla data som finns i relationsarkivet i realtid, bygga en komplex fråga ovanpå den och få resultatet för omedelbar aktivering via utgående kanaler (t.ex. e-post + SMS).

>[!BEGINSHADEBOX]

**Tips**

* Använd ad hoc-segmentering för **tidskänsliga behov** (t.ex. Flash-kampanjer).
* Spara och dokumentera användbara frågor så att de kan återanvändas i framtida kampanjer.
* Validera antalet användare före aktivering för att förhindra att de skickas för mycket eller för lite.

>[!ENDSHADEBOX]


## Stöder detta beslut? {#decisioning}

För närvarande används inte relationsdata från Orchestrated Campaigns vid beslut.

## Hur fungerar driftsättningen i olika miljöer? {#deployment}

Objekt som skapas i samordnade kampanjer (t.ex. målgrupper, arbetsflöden) är kopplade till den sandlåda som de byggs i. Standardarbetsflöden för paketering och distribution i olika miljöer (dev, stage, prod) är för närvarande inte tillgängliga för Orchestrated Campaigns.

>[!BEGINSHADEBOX]

**Bästa praxis**

* Underhåll **separata sandlådor** för experiment, kvalitetskontroll och produktion.
* Dokumentkonfigurationer grundligt för att möjliggöra manuell replikering vid behov.
* Anpassa med styrningsteamen för att minska konfigurationsavbrottet mellan olika miljöer.

>[!ENDSHADEBOX]

## Finns det rekommendationer för att köra kampanjer i stor skala? {#scale}

Ja, följ god praxis nedan:

* **Planera kampanjer runt affärskalendrar** (produktlanseringar, säsongstopp) för att anpassa volym och resurser.
* Använd **målgruppens förhandsvisningar** innan du skickar för att bekräfta den förväntade storleken och undvika överraskningar.
* Om möjligt **stagger-sändningstider** för att undvika överväldigande system längre fram i kedjan (till exempel callcenters, webbplatser).
* Upprätta en **övervakningsrutin** - spåra leveransloggar, felfrekvens och avanmälan efter varje sändning.
* Kör **efterkampanjanalys** i Customer Journey Analytics för att förfina målinriktning och samordning inför nästa cykel.



>[!MORELIKETHIS]
>
>* [Samordnade kampanjer, skyddsräcken och begränsningar](../orchestrated/guardrails.md)
>* [Kom igång med scheman och datauppsättningar i orkestrerade kampanjer](../orchestrated/gs-schemas.md)
>* [Skapa din första orkestrerade kampanj](../orchestrated/gs-campaign-creation.md)
>* [Journey Optimizer produktbeskrivning](https://helpx.adobe.com/se/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"}
