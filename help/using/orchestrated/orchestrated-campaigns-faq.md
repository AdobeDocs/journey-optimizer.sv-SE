---
solution: Journey Optimizer
product: journey optimizer
title: Vanliga frågor och svar om samordnade kampanjer
description: Frågor och svar om Journey Optimizer samordnade kampanjer
version: Campaign Orchestration
exl-id: 6a660605-5f75-4c0c-af84-9c19d82d30a0
source-git-commit: 9ae0d910f6246b87683b04db97bbdb7355beb349
workflow-type: tm+mt
source-wordcount: '1419'
ht-degree: 1%

---

# Vanliga frågor {#faq-oc}

Nedan hittar du Frågor och svar om Adobe Journey Optimizer samordnade kampanjer.

Behöver du mer information? Använd alternativen för feedback längst ned på den här sidan för att ställa din fråga eller kontakta [Adobe Journey Optimizer Community](https://experienceleaguecommunities.adobe.com/t5/adobe-journey-optimizer/ct-p/journey-optimizer?profile.language=en){target="_blank"}.

## Vad är Campaign-samordning? {#what-are-oc}

Kampanjsamordning är en funktion i Journey Optimizer som stöder enstegs- eller flerstegsarbetsflöden som utnyttjar Relational Datastore för att skapa och segmentera målgrupper för satsengagemang.

Det ger en ny typ av kampanjer till Journey Optimizer: **Orchestrerade-kampanjer**. Samordnade kampanjer hjälper varumärken att köra komplexa 1:N-kampanjer i stor skala. De är utformade för varumärkesinitierat engagemang, som kampanjer, säsongskampanjer eller kontobaserad kommunikation.

Jämfört med kampanjer för enstaka sändning/åtgärd för de **orkestrering och sekvensering** för utgående marknadsföring: målgrupperna rör sig genom ett flerstegsarbetsflöde tillsammans i stället för att få en engångsutsändning.

## Vad kan jag göra med en orkestrerad kampanj? {#what-can-i-do}

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

## Hur får jag åtkomst till kampanjsamordning? {#access-oc}

För att få åtkomst till kampanjsamordning måste din licens innehålla antingen paketet **Journey Optimizer - Campaigns &amp; Journeys** eller paketet **Journey Optimizer - Campaigns**. Kontakta din Adobe-representant för att bekräfta din licens och uppdatera vid behov.

Läs mer om licensieringsmodellen för kampanjsamordning i [Adobe Journey Optimizer produktbeskrivning](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"}.

## Hur skiljer sig Orchestrated-kampanjer från Journeys? {#oc-vs-journeys}

* **Samordnade kampanjer**: Passar bäst för **batch-, en-till-många**-kampanjer. Publiken gör satsvis, enligt ett schema.
* **Resor**: Passar bäst för **realtidsengagemang med en-till-en**. Varje kund rör sig genom resan i sin egen takt, triggad av beteende eller händelser.

>[!BEGINSHADEBOX]

**Bästa praxis**: Använd dem tillsammans - Resor för triggade, reaktiva upplevelser och samordnade kampanjer för planerade, kalenderbaserade initiativ.

>[!ENDSHADEBOX]

## Vad är segmentering av flera enheter? {#multi-entity}

Kampanjsamordning i Adobe Journey Optimizer använder en relationsdatabas. Den här typen av datamodell har separata scheman med data som är anslutna via 1:1- eller 1:many-relationer. Detta gör att användare kan starta en fråga i vilket schema som helst - inte bara på mottagarnivå - och sedan vända fram och tillbaka till andra relaterade scheman, som inköp, produkter, bokningar eller mottagarinformation, vilket ger stor flexibilitet i hur segment och målgrupper kan skapas och
förfinat.

>[!BEGINSHADEBOX]

**Exempel** - Rikta in dig på alla mottagare med prenumerationer som går ut inom 30 dagar. I Kampanjsamordning kan frågan börja med prenumerationsschemat, söka bara i kolumnen med förfallodatum i det schemat och returnera alla prenumerationer som förfaller. Sedan kan du samla in mottagardata som är relaterade till dessa specifika prenumerations-ID:n och returnera resultat snabbare och effektivare än datamodeller som påbörjar varje fråga på mottagarnivå.

>[!ENDSHADEBOX]


## Hur fungerar datamodellen? {#data-model}

Kampanjer använder en **relationsdatabas**. På så sätt kan ni söka efter olika datauppsättningar (t.ex. kunder, produkter, prenumerationer) och koppla dem flexibelt för avancerad segmentering.

>[!BEGINSHADEBOX]

**Bästa praxis**

* Ordna datauppsättningar så att **relationer (kopplingar)** återspeglar affärslogik.
* Undvik onödiga kopplingar för att få frågor att prestera.
* Validera exempelresultaten innan du kör storskaliga extraheringar.

>[!ENDSHADEBOX]

## Kan jag personalisera meddelanden med relationsdata? {#personalization}

Ja. I kampanjsamordning kan en mottagarprofil som kallas personentitet uppdateras och data som används för personalisering. Dessutom kan data från länkade entiteter i relationsdatabasen också användas för personalisering. Ni kan använda kundprofiler tillsammans med länkade data (som köp eller prenumerationer) för att anpassa innehåll i alla kanaler som stöds.

>[!BEGINSHADEBOX]

**Rekommendationer**

* Använd **transaktions- och beteendedata** för att göra erbjudanden relevanta.
* Kombinera **statiska attribut** (t.ex. lojalitetsnivå) med **dynamiska attribut** (t.ex. senaste inköpsdatum).
* Håll personaliseringen koncis - överlastning av meddelanden med data kan skada läsbarheten.

>[!ENDSHADEBOX]

<!--
## Do Orchestrated campaigns integrate with other Adobe solutions? {#integrations}

Yes. Campaign orchestration is natively integrated with:

* **Customer Journey Analytics**: Campaign orchestration reports are available.  
* **Real-Time CDP**: Audiences built in Campaigns can be read in Real-Time CDP.  
* **Federated Audience Composition (FAC)**: Available as an add-on.  -->

## Vilka kanaler stöds? {#channels}

Du kan skapa samordnade kampanjer för att skicka **e-post**, **SMS** och **push-meddelanden**.

## Kan flera kommunikationer och olika kanaler lanseras inom samma samordnade kampanj?

Ja, samordnade kampanjer har stöd för flerkanalsmarknadsföring.

## Finns det mallar för samordnade kampanjer?

Nej, du kan inte definiera eller använda kampanjmallar, men du kan använda innehållsmallar för din kommunikation.

## Är innehållsdesignern för meddelanden specifik för Orchestrated-kampanjer?

Nej, innehållsdesignern, inklusive Email Designer, är gemensam för alla Journey Optimizer-funktioner.

## Hur hänger de olika kanalerna ihop i samordnade kampanjer?

Kanalkomponenten och körningsmiljön är gemensamma för alla Journey Optimizer-kampanjer, men de kanaler som stöds skiljer sig åt.

## Kan samordnade kampanjer kopplas till utgående kanaler (webb, inApp)?

Nej, utgående kanaler stöds inte i Orchestrated-kampanjer.


## Vad gäller för tillstånd och samtycke? {#permissions}

Tillstånd och samtycke för samordnade kampanjer och resor hanteras centralt i Adobe Experience Platform. De här inställningarna används för båda lösningarna för varje mottagare innan de skickas.

>[!BEGINSHADEBOX]

**Bästa praxis**

* Använd **centraliserad styrning** - undvik att hantera samtycke separat på kampanjnivå.
* Granska regelbundet data om samtycke för att upptäcka inkonsekvenser.
* Respektera **kanalspecifika avanmälningar** - anta inte att globalt medgivande omfattar alla kanaler.

>[!ENDSHADEBOX]

## Kan jag segmentera enstaka bilder i samordnade kampanjer? {#ad-hoc}

I Campaign-orkestrering talar vi om ad hoc-segmentering som&quot;Live-segmentering&quot;, där ni kan komma åt alla data som finns i relationsarkivet i realtid, bygga en komplex fråga ovanpå den och få resultatet för omedelbar aktivering via utgående kanaler (t.ex. e-post + SMS).

>[!BEGINSHADEBOX]

**Tips**

* Använd ad hoc-segmentering för **tidskänsliga behov** (t.ex. Flash-kampanjer).
* Spara och dokumentera användbara frågor så att de kan återanvändas i framtida kampanjer.
* Validera antalet användare före aktivering för att förhindra att de skickas för mycket eller för lite.

>[!ENDSHADEBOX]

## Kommer Campaign Orchestration endast att få åtkomst till data som lästs in via batch, eller kan den även fråga efter uppdaterade realtidstabeller (som analysdata)?

Journey Optimizer Campaign-samordning kan först skapa ad hoc-frågor utöver Relational Schemas. Relationsscheman har endast stöd för batchkällor just nu. Dessutom har det stöd för läsare från alla typer av Adobe Experience Platform Audience.

## Har orkestrerade kampanjer stöd för beslut? {#decisioning}

Ja. Vid beslut kan relationsdata från samordnade kampanjer användas. När relationsschemat är kopplat till XDM-scheman kan XDM-data användas vid beslut.

## Hur fungerar driftsättningen i olika miljöer? {#deployment}

Objekt som skapas i samordnade kampanjer (t.ex. målgrupper, arbetsflöden) är kopplade till den sandlåda som de byggs i. Standardarbetsflöden för paketering och distribution i olika miljöer (dev, stage, prod) är för närvarande inte tillgängliga för samordnade kampanjer.

>[!BEGINSHADEBOX]

**Bästa praxis**

* Underhåll **separata sandlådor** för experiment, kvalitetskontroll och produktion.
* Dokumentkonfigurationer grundligt för att möjliggöra manuell replikering vid behov.
* Anpassa med styrningsteamen för att minska konfigurationsavbrottet mellan olika miljöer.

>[!ENDSHADEBOX]

<!--
## Are there recommended practices for running campaigns at scale? {#scale}

Yes, follow the best practices below:  

* **Plan campaigns around business calendars** (product launches, seasonal peaks) to align volume and resources.  
* Use **audience pre-views** before sending to confirm the expected size and avoid surprises.  
* Where possible, **stagger send times** to avoid overwhelming downstream systems (e.g., call centers, websites).  
* Establish a **monitoring routine**—track delivery logs, error rates, and opt-outs after each send.  
* Run **post-campaign analysis** in Customer Journey Analytics to refine targeting and orchestration for the next cycle.  
-->

## Vilken är relationen mellan mottagare och profilentiteter?

Segmentering utförs på mottagare när de skickar till Adobe Experience Platform-profilen. Måldimensionen för mottagaren utökar den enhetliga profilen med ytterligare data som används för segmentering inom samordnade kampanjer, medan mottagaren är inkompatibel med profilen vid körning för att skicka meddelanden och kontrollera samtyckespolicyn och affärsreglerna. Den här avstämningen är användbar för att sammanföra affärsregler och tillståndsansökningar på profilnivå

![](assets/recipients-and-profiles.png)


## I vilka fall rekommenderas du att använda Mottagare jämfört med Profilentiteter?

Om du svarar Ja föreslås det bästa datalagret, men du bör alltid bekräfta det bästa sättet baserat på ditt användningsfall och dina begränsningar med din Adobe-representant.

| Relationsarkiv | Kundprofil i realtid |
|---------|----------|
| Är källan redan datarelationen? | Är källan till dataströmningen? |
| Planerar ni att importera data som de är för användning i marknadsföringssyfte? | Är datadfrihet ett stort krav? |
| Finns det en stor mängd historiska data (`>` 2 månader) som behövs för att aktivera marknadsföring? | Finns det scenarier där åtgärder eller beslut kräver data just nu? |
| Finns det särskilda behov för att skapa, utvärdera och aktivera målgrupper? | Kan beteendedata begränsas till `<` 90 dagar med förberäknade aggregat? |
|  | Behövs data för att personalisera meddelanden i realtid? |


## Vilket är det högsta antalet aktiviteter per orkestrerad kampanj?

Antalet aktiviteter i en orkestrerad kampanj är begränsat till 500.

## Går det att utföra berikning för att lägga till ytterligare data?

Ja, ni kan utöka data från relationsbutiken och från Adobe Experience Platform målgrupper.

## Måste alla filter definieras via målgrupper eller kan någon typ av filter konfigureras?

Samordnade kampanjer har stöd för fördefinierade filter: du kan definiera och spara en fråga som ett filter och lägga till den i dina favoriter så att den kan återanvändas i andra segmenteringsuppgifter.



>[!MORELIKETHIS]
>
>* [Samordnade kampanjer, skyddsräcken och begränsningar](../orchestrated/guardrails.md)
>* [Kom igång med scheman och datauppsättningar i orkestrerade kampanjer](../orchestrated/gs-schemas.md)
>* [Skapa din första orkestrerade kampanj](../orchestrated/gs-campaign-creation.md)
>* [Journey Optimizer produktbeskrivning](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"}
