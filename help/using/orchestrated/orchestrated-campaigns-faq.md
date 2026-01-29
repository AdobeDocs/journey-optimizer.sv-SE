---
solution: Journey Optimizer
product: journey optimizer
title: Vanliga frågor och svar om samordnade kampanjer
description: Frågor och svar om Journey Optimizer samordnade kampanjer
version: Campaign Orchestration
exl-id: 6a660605-5f75-4c0c-af84-9c19d82d30a0
source-git-commit: 478bd6df8a82c9e37ec9319dedb27d99c021ee99
workflow-type: tm+mt
source-wordcount: '1878'
ht-degree: 5%

---

# Vanliga frågor {#faq-oc}

Nedan hittar du Frågor och svar om Adobe Journey Optimizer samordnade kampanjer.

Behöver du mer information? Använd alternativen för feedback längst ned på den här sidan för att ställa din fråga eller kontakta [Adobe Journey Optimizer Community](https://experienceleaguecommunities.adobe.com/t5/adobe-journey-optimizer/ct-p/journey-optimizer?profile.language=sv){target="_blank"}.

+++ Vad är Campaign-samordning?

Kampanjsamordning är en funktion i Journey Optimizer som stöder enstegs- eller flerstegsarbetsflöden som utnyttjar Relational Datastore för att skapa och segmentera målgrupper för satsengagemang.

Det ger en ny typ av kampanjer till Journey Optimizer: **Orchestrerade-kampanjer**. Samordnade kampanjer hjälper varumärken att köra komplexa 1:N-kampanjer i stor skala. De är utformade för varumärkesinitierat engagemang, som kampanjer, säsongskampanjer eller kontobaserad kommunikation.

Jämfört med kampanjer för enstaka sändning/åtgärd för de **orkestrering och sekvensering** för utgående marknadsföring: målgrupperna rör sig genom ett flerstegsarbetsflöde tillsammans i stället för att få en engångsutsändning.

**Läs mer**

* [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)
* [Skapa din första samordnade kampanj](gs-campaign-creation.md)

+++

+++ Vad kan jag göra med en orkestrerad kampanj?

Viktiga funktioner:

* **On-Demand-målgrupper**: Bygg och förfina målgrupper direkt med hjälp av relationsfrågor.
* **Segmentering för flera enheter**: Skapa exakta målgrupper genom att koppla kunddata till relaterade entiteter (t.ex. konton, inköp, bokningar).
* **Synlighet före sändning**: Se rätt antal målgrupper innan du startar för att optimera målinriktningen.
* **Flerstegsarbetsflöden**: Kör sekventiella kampanjer, till exempel säsongskampanjer, produktlanseringar eller lojalitetserbjudanden.

**Bästa praxis**

* Definiera ett **tydligt kampanjmål** innan du utformar arbetsflöden.
* Börja med en **pilotmålgrupp** för att validera antal och logik innan skalning.
* Behåll segmenteringsreglerna **så enkla som möjligt** för att optimera prestanda och genomskinlighet.
* Använd **konsekventa namnkonventioner** för målgrupper och kampanjer för att underlätta hanteringen.

**Läs mer**

* [Skapa en orkestrerad kampanj](create-orchestrated-campaign.md)
* [Arbeta med kampanjaktiviteter](activities/about-activities.md)
* [Bygg din regel med frågemodelleraren](build-query.md)

+++

+++ Hur får jag tillgång till Campaign-samordning?

För att få åtkomst till kampanjsamordning måste din licens innehålla antingen paketet **Journey Optimizer - Campaigns &amp; Journeys** eller paketet **Journey Optimizer - Campaigns**. Kontakta din Adobe-representant för att bekräfta din licens och uppdatera vid behov.

**Läs mer**

* [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)
* [Adobe Journey Optimizer produktbeskrivning](https://helpx.adobe.com/se/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"}

+++

+++ Hur skiljer sig Orchestrated-kampanjer från Journeys?

* **Samordnade kampanjer**: Passar bäst för **batch-, en-till-många**-kampanjer. Publiken gör satsvis, enligt ett schema.
* **Resor**: Passar bäst för **realtidsengagemang med en-till-en**. Varje kund rör sig genom resan i sin egen takt, triggad av beteende eller händelser.

**Bästa praxis**: Använd dem tillsammans - Resor för triggade, reaktiva upplevelser och samordnade kampanjer för planerade, kalenderbaserade initiativ.

**Läs mer**

* [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)
* [Skapa den första resan](../building-journeys/journey-gs.md)
* [Kom igång med kampanjer](../campaigns/get-started-with-campaigns.md)

+++

+++ Vad är segmentering av flera enheter?

Kampanjsamordning i Adobe Journey Optimizer använder en relationsdatabas. Den här typen av datamodell har separata scheman med data som är anslutna via 1:1- eller 1:many-relationer. Detta gör att användare kan starta en fråga i vilket schema som helst - inte bara på mottagarnivå - och sedan vända fram och tillbaka till andra relaterade scheman, som inköp, produkter, bokningar eller mottagarinformation, vilket ger stor flexibilitet i hur segment och målgrupper kan skapas och finjusteras.

**Exempel** - Rikta in dig på alla mottagare med prenumerationer som går ut inom 30 dagar. I Kampanjsamordning kan frågan börja med prenumerationsschemat, söka bara i kolumnen med förfallodatum i det schemat och returnera alla prenumerationer som förfaller. Sedan kan du samla in mottagardata som är relaterade till dessa specifika prenumerations-ID:n och returnera resultat snabbare och effektivare än datamodeller som påbörjar varje fråga på mottagarnivå.

**Läs mer**

* [Kom igång med scheman och datauppsättningar](gs-schemas.md)
* [Konfigurera en måldimension](target-dimension.md)
* [Bygg din regel med frågemodelleraren](build-query.md)

+++

+++ Hur fungerar datamodellen?

Kampanjer använder en **relationsdatabas**. På så sätt kan ni söka efter olika datauppsättningar (t.ex. kunder, produkter, prenumerationer) och koppla dem flexibelt för avancerad segmentering.

**Bästa praxis**

* Ordna datauppsättningar så att **relationer (kopplingar)** återspeglar affärslogik.
* Undvik onödiga kopplingar för att få frågor att prestera.
* Validera exempelresultaten innan du kör storskaliga extraheringar.

**Läs mer**

* [Kom igång med scheman och datauppsättningar](gs-schemas.md)
* [Skapa ett schema manuellt](manual-schema.md)
* [Ingrediera data](ingest-data.md)

+++

+++ Kan jag personalisera meddelanden med relationsdata?

Ja. I kampanjsamordning kan en mottagarprofil som kallas personentitet uppdateras och data som används för personalisering. Dessutom kan data från länkade entiteter i relationsdatabasen också användas för personalisering. Ni kan använda kundprofiler tillsammans med länkade data (som köp eller prenumerationer) för att anpassa innehåll i alla kanaler som stöds.

**Rekommendationer**

* Använd **transaktions- och beteendedata** för att göra erbjudanden relevanta.
* Kombinera **statiska attribut** (t.ex. lojalitetsnivå) med **dynamiska attribut** (t.ex. senaste inköpsdatum).
* Håll personaliseringen koncis - överlastning av meddelanden med data kan skada läsbarheten.

**Läs mer**

* [Använd anrikningsaktiviteten](activities/enrichment.md)
* [Lägga till en kanalaktivitet i en orkestrerad kampanj](activities/channels.md)

+++

<!--
## Do Orchestrated campaigns integrate with other Adobe solutions? {#integrations}

Yes. Campaign orchestration is natively integrated with:

* **Customer Journey Analytics**: Campaign orchestration reports are available.  
* **Real-Time CDP**: Audiences built in Campaigns can be read in Real-Time CDP.  
* **Federated Audience Composition (FAC)**: Available as an add-on.  -->

+++ Kan jag återställa en live-orkestrerad kampanj till utkast?

Ja, i vissa situationer. Alternativet **[!UICONTROL Back to draft]** är utformat som en återställningsmekanism som avpublicerar och återställer en kampanj till utkaststatus.

Det här alternativet är tillgängligt för schemalagda kampanjer som väntar på att köras eller för direktkampanjer med körningsfel. [Lär dig hur du återställer en livekampanj till utkastet](start-monitor-campaigns.md#back-to-draft)

+++

+++ Vilka kanaler stöds?

Du kan skapa samordnade kampanjer för att skicka **e-post**, **SMS**, **push-meddelanden** och **direktmeddelanden**.

**Läs mer**

* [Lägga till en kanalaktivitet i en orkestrerad kampanj](activities/channels.md)
* [Arbeta med kampanjaktiviteter](activities/about-activities.md)

+++

+++ Kan flera kommunikationer och olika kanaler lanseras inom samma samordnade kampanj?

Ja, samordnade kampanjer har stöd för flerkanalsmarknadsföring. Ni kan kombinera e-post, SMS och push-meddelanden till en kampanjarbetsyta i flera steg för att skapa heltäckande kundupplevelser.

**Läs mer**

* [Lägga till en kanalaktivitet i en orkestrerad kampanj](activities/channels.md)
* [Arbeta med kampanjaktiviteter](activities/about-activities.md)

+++

+++ Finns det mallar för samordnade kampanjer?

Nej, du kan inte definiera eller använda kampanjmallar, men du kan använda innehållsmallar för din kommunikation.

**Läs mer**

* [Lägga till en kanalaktivitet i en orkestrerad kampanj](activities/channels.md)
* [Skapa en orkestrerad kampanj](create-orchestrated-campaign.md)

+++

+++ Är innehållsdesignern för meddelanden specifik för Orchestrated-kampanjer?

Nej, innehållsdesignern, inklusive Email Designer, är gemensam för alla Journey Optimizer-funktioner.

**Läs mer**

* [Lägga till en kanalaktivitet i en orkestrerad kampanj](activities/channels.md)
* [Använd anrikningsaktiviteten](activities/enrichment.md)

+++

+++ Hur hänger de olika kanalerna ihop i samordnade kampanjer?

Kanalkomponenten och körningsmiljön är gemensamma för alla Journey Optimizer-kampanjer, men de kanaler som stöds skiljer sig åt. Samordnade kampanjer har stöd för e-post, SMS och push-meddelanden.

**Läs mer**

* [Lägga till en kanalaktivitet i en orkestrerad kampanj](activities/channels.md)
* [Skyddsritningar och begränsningar](guardrails.md)

+++


+++ Kan samordnade kampanjer kopplas till utgående kanaler (webb, inApp)?

Nej, inkommande kanaler som webben och appar stöds inte i samordnade kampanjer. Endast utgående kanaler (e-post, SMS och push-meddelanden) stöds.

**Läs mer**

* [Skyddsritningar och begränsningar](guardrails.md)
* [Lägga till en kanalaktivitet i en orkestrerad kampanj](activities/channels.md)

+++

+++ Vad gäller för tillstånd och samtycke?

Tillstånd och samtycke för samordnade kampanjer och resor hanteras centralt i Adobe Experience Platform. De här inställningarna används för båda lösningarna för varje mottagare innan de skickas.

**Bästa praxis**

* Använd **centraliserad styrning** - undvik att hantera samtycke separat på kampanjnivå.
* Granska regelbundet data om samtycke för att upptäcka inkonsekvenser.
* Respektera **kanalspecifika avanmälningar** - anta inte att globalt medgivande omfattar alla kanaler.

**Läs mer**

* [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)
* [Skyddsritningar och begränsningar](guardrails.md)

+++


+++ Kan jag segmentera enstaka bilder i samordnade kampanjer?

I Campaign-orkestrering talar vi om ad hoc-segmentering som&quot;Live-segmentering&quot;, där ni kan komma åt alla data som finns i relationsarkivet i realtid, bygga en komplex fråga ovanpå den och få resultatet för omedelbar aktivering via utgående kanaler (t.ex. e-post + SMS).

**Tips**

* Använd ad hoc-segmentering för **tidskänsliga behov** (t.ex. Flash-kampanjer).
* Spara och dokumentera användbara frågor så att de kan återanvändas i framtida kampanjer.
* Validera antalet användare före aktivering för att förhindra att de skickas för mycket eller för lite.

**Läs mer**

* [Bygg din regel med frågemodelleraren](build-query.md)
* [Använd aktiviteten Skapa målgrupp](activities/build-audience.md)
* [Konfigurera en måldimension](target-dimension.md)

+++


+++ Kommer Campaign Orchestration endast att få åtkomst till data som lästs in via batch, eller kan den även fråga efter uppdaterade realtidstabeller (som analysdata)?

Journey Optimizer Campaign-samordning kan skapa ad hoc-frågor utöver relationsscheman. Relationsscheman har endast stöd för batchkällor just nu. Dessutom har programmet stöd för Läs publikaktiviteter från alla typer av Adobe Experience Platform Audience.

**Läs mer**

* [Kom igång med scheman och datauppsättningar](gs-schemas.md)
* [Ingrediera data](ingest-data.md)
* [Använda aktiviteten Läsa målgrupper](activities/read-audience.md)

+++

+++ Har orkestrerade kampanjer stöd för beslut?

Nej, samordnade kampanjer saknar stöd för beslutsfunktioner. Använd Journey Optimizer standardresor eller åtgärdskampanjer i stället för att bestämma vilka funktioner som ska användas.

**Läs mer**

* [Kom igång med Experience Decision](../experience-decisioning/gs-experience-decisioning.md)
* [Skapa den första resan](../building-journeys/journey-gs.md)
* [Kom igång med kampanjer](../campaigns/get-started-with-campaigns.md)

+++


+++ Hur fungerar driftsättningen i olika miljöer?

Objekt som skapas i samordnade kampanjer (t.ex. målgrupper, arbetsflöden) är kopplade till den sandlåda som de byggs i. Standardarbetsflöden för paketering och distribution i olika miljöer (dev, stage, prod) är för närvarande inte tillgängliga för samordnade kampanjer.

**Bästa praxis**

* Underhåll **separata sandlådor** för experiment, kvalitetskontroll och produktion.
* Dokumentkonfigurationer grundligt för att möjliggöra manuell replikering vid behov.
* Anpassa med styrningsteamen för att minska konfigurationsavbrottet mellan olika miljöer.

**Läs mer**

* [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)
* [Skyddsritningar och begränsningar](guardrails.md)

+++

<!--
## Are there recommended practices for running campaigns at scale? {#scale}

Yes, follow the best practices below:  

* **Plan campaigns around business calendars** (product launches, seasonal peaks) to align volume and resources.  
* Use **audience pre-views** before sending to confirm the expected size and avoid surprises.  
* Where possible, **stagger send times** to avoid overwhelming downstream systems (e.g., call centers, websites).  
* Establish a **monitoring routine**—track delivery logs, error rates, and opt-outs after each send.  
* Run **post-campaign analysis** in Customer Journey Analytics to refine targeting and orchestration for the next cycle.  
-->

+++ Vilken är relationen mellan mottagare och profilentiteter?

Segmentering utförs på mottagare när de skickar till Adobe Experience Platform-profilen. Måldimensionen för mottagaren utökar den enhetliga profilen med ytterligare data som används för segmentering inom samordnade kampanjer, medan mottagaren är inkompatibel med profilen vid körning för att skicka meddelanden och kontrollera samtyckespolicyn och affärsreglerna. Den här avstämningen är användbar för att sammanföra affärsregler och tillståndsansökningar på profilnivå.

![](assets/recipients-and-profiles.png)

**Läs mer**

* [Konfigurera en måldimension](target-dimension.md)
* [Kom igång med scheman och datauppsättningar](gs-schemas.md)
* [Bygg din regel med frågemodelleraren](build-query.md)

+++

+++ I vilka fall rekommenderas du att använda Mottagare jämfört med Profilentiteter?

Om du svarar Ja föreslås det bästa datalagret, men du bör alltid bekräfta det bästa sättet baserat på ditt användningsfall och dina begränsningar med din Adobe-representant.

| Relationsarkiv | Kundprofil i realtid |
|---------|----------|
| Är källan redan datarelationen? | Är källan till dataströmningen? |
| Planerar ni att importera data som de är för användning i marknadsföringssyfte? | Är datadfrihet ett stort krav? |
| Finns det en stor mängd historiska data (`>` 2 månader) som behövs för att aktivera marknadsföring? | Finns det scenarier där åtgärder eller beslut kräver data just nu? |
| Finns det särskilda behov för att skapa, utvärdera och aktivera målgrupper? | Kan beteendedata begränsas till `<` 90 dagar med förberäknade aggregat? |
|  | Behövs data för att personalisera meddelanden i realtid? |

**Läs mer**

* [Konfigurera en måldimension](target-dimension.md)
* [Kom igång med scheman och datauppsättningar](gs-schemas.md)
* [Bygg din regel med frågemodelleraren](build-query.md)

+++

+++ Vilket är det högsta antalet aktiviteter per orkestrerad kampanj?

Antalet aktiviteter i en orkestrerad kampanj är begränsat till 500.

**Läs mer**

* [Skyddsritningar och begränsningar](guardrails.md)
* [Arbeta med kampanjaktiviteter](activities/about-activities.md)

+++

+++ Går det att utföra berikning för att lägga till ytterligare data?

Ja, ni kan utöka data från relationsbutiken och från Adobe Experience Platform målgrupper. Använd Enrichment-aktiviteten för att förbättra era målgruppsdata med ytterligare attribut från relaterade scheman.

**Läs mer**

* [Använd anrikningsaktiviteten](activities/enrichment.md)
* [Använd avstämningsaktiviteten](activities/reconciliation.md)

+++

+++ Måste alla filter definieras via målgrupper eller kan någon typ av filter konfigureras?

Samordnade kampanjer har stöd för fördefinierade filter: du kan definiera och spara en fråga som ett filter, lägga till den i dina favoriter och återanvända den i andra segmenteringsuppgifter. Fördefinierade filter kan innehålla parametrar så att du kan ange värden när du använder dem. [Lär dig arbeta med fördefinierade filter](predefined-filters.md).

**Läs mer**

* [Bygg din regel med frågemodelleraren](build-query.md)
* [Använd aktiviteten Skapa målgrupp](activities/build-audience.md)
* [Arbeta med fördefinierade filter](orchestrated-rule-builder.md)

+++


## Ytterligare resurser

Utforska följande resurser om du vill ha mer information och uppdateringar:

* [Samordnade kampanjer skyddar mot detaljer och begränsningar](guardrails.md)
* [Kom igång med scheman och datauppsättningar i samordnade kampanjer](gs-schemas.md)
* [Skapa din första samordnade kampanj](gs-campaign-creation.md)
* [Journey Optimizer produktbeskrivning](https://helpx.adobe.com/se/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"}
