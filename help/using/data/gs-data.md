---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med datahantering i Journey Optimizer
description: Lär dig hur data flödar in i och ut från Adobe Journey Optimizer, inklusive viktiga koncept, konfigurationssteg och skyddsprofiler.
feature: Data Management
role: Developer, Admin, User
level: Beginner, Intermediate
exl-id: 25519acb-a017-446a-992b-653d3a8a3d96
source-git-commit: 7094cb2717f36042fa0aec1c6442f8d00c593823
workflow-type: tm+mt
source-wordcount: '2442'
ht-degree: 0%

---


# Kom igång med datahantering {#about-data}

Data är grunden för varje resa, beslut och meddelande som du levererar med [!DNL Adobe Journey Optimizer].

På den här sidan får du en praktisk utgångspunkt för att förstå:

* Journey Optimizer kärndatabyggningsblock (scheman, datamängder, identiteter, profiler)
* Hur Journey Optimizer använder Adobe Experience Platform-data
* Vilka datainställningssteg teamet måste slutföra innan de kan skapa resor och kampanjer
* Här följer en översikt över konfiguration och bästa praxis

Använd den här guiden tillsammans med datatekniker, administratörer och marknadsförare så att alla kan få en gemensam bild av hur data flödar in i och ut från Journey Optimizer.

>[!TIP]
>Har du inte använt datahanteringen i Journey Optimizer förut? Titta på självstudiekursen [Konfigurera dataöversikt](https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-management/set-up-data-overview){target="_blank"} för en praktisk, nybörjarvänlig genomgång av scheman, datauppsättningar och källor.

## Hur Journey Optimizer använder Adobe Experience Platform-data {#aep-data}

[!DNL Adobe Journey Optimizer] är byggt på [!DNL Adobe Experience Platform]. Den har inte ett separat, isolerat datalager. I stället används samma grund som andra Experience Cloud-program.

Scheman och datauppsättningar finns i Adobe Experience Platform. Identiteter och [Real-Time Customer Profile](../audience/get-started-profiles.md) hanteras av identitetstjänsten och profiltjänsten. Journey Optimizer läser profil- och händelsedata från Adobe Experience Platform för att utvärdera resevillkor, personalisera meddelanden och utvalda erbjudanden. Här skrivs interaktionsdata - som skicka, öppna, klicka och studsa händelser och kundstegshändelser - tillbaka till Experience Platform datauppsättningar. Det kan även söka efter ytterligare datauppsättningar vid körning utan att kopiera dessa data till profilen.

>[!TIP]
>Se Adobe Experience Platform som ert centrala datalager och Journey Optimizer som en tillämpning som ordnar resor och meddelanden med denna gemensamma datamgrund.

➡️ [Läs mer om Journey Optimizer-arkitektur](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/get-started/essentials/understanding-ajo#architecture-details){target="_blank"}

## Viktiga databegrepp i Journey Optimizer {#key-concepts}

När du arbetar med data i Journey Optimizer kommer du att stöta på flera närliggande begrepp. Tabellen nedan ger dig en snabb översikt. I avsnitten som följer beskrivs varje koncept mer ingående.

| Koncept | Vad det är | Primär användning i Journey Optimizer |
|---|---|---|
| XDM-schema | Regler som representerar, validerar och formaterar data (skapade från en klass + fältgrupper) | Modellprofilattribut och beteendehändelser |
| Datauppsättning | Lagringstabell för data som överensstämmer med ett schema | Håll kvar profil, händelse och systemgenererade data |
| Source Connector | Direktuppspelar eller batchbearbetar data från externa system till AEP | Ingest CRM, analyser och webbdata |
| Datakälla | Visar AEP eller externa fält inom resorna | Stärk resevillkoren och personalisering av meddelanden |
| Identitet | Identifierare som unikt representerar en enskild kund | Fästa profiler över flera kanaler |
| Sök datauppsättning | Körningsreferens till AEP-data utan profillagring | Förbättra meddelanden med live-referensdata |

### Schema (XDM-schema) {#schema}

Ett schema är en uppsättning regler som representerar, validerar och formaterar dina data. Den består av en **klass** (som definierar basbeteendet: post- eller tidsserie) och valfria **fältgrupper** (som lägger till specifika fält). Scheman definieras med XDM-standarder (Experience Data Model) och finns i Adobe Experience Platform.

XDM löser ett verkligt problem: samma koncept - en kund, ett inköp, en produkt - namnges och struktureras på olika sätt i olika källsystem. XDM är ett delat språk som förenar dessa begrepp i en enda definition, oavsett var informationen kommer från. Detta gör att Journey Optimizer kan arbeta enhetligt med data från CRM, er webbplats, er mobilapp och ert datalager samtidigt.

I Journey Optimizer arbetar du vanligtvis med **XDM Individual Profile**-scheman för kundattribut (namn, inställningar, medgivande) och **XDM ExperienceEvent**-scheman för beteendehändelser (inköp, sidvisningar, registreringar).

➡️ [Läs mer om scheman](get-started-schemas.md)

### Datauppsättning {#dataset}

En datauppsättning är en lagrings- och hanteringskonstruktion för data som följer ett schema - tänk på det som en tabell med en definierad uppsättning kolumner och rader. Alla data som används av Journey Optimizer lagras i Adobe Experience Platform datamängder. Dessa kan vara profildatauppsättningar (som bidrar till kundprofilen i realtid), händelsedatamängder (som lagrar beteendedata för resor och analys) eller systemdatauppsättningar som automatiskt skapas av Journey Optimizer för spårning, feedback och kundstegshändelser.

➡️ [Läs mer om datauppsättningar](get-started-datasets.md)

### Source Connector {#source-connector}

En källanslutning (kallas även **källa**) hjälper dig att importera data från flera system - som Adobe Analytics, Adobe Experience Platform Web SDK, molnlagring (S3, Azure Blob) eller CRM-databaser - till Adobe Experience Platform. Förutom råmaterialsanvändning möjliggör kopplingar strukturering, märkning och förbättring av data med hjälp av Experience Platform tjänster, inklusive fältmappning till XDM-scheman och datastyrningsetiketter.

➡️ [Läs mer om källanslutningar](../start/get-started-sources.md)

### Datakälla (Journey Optimizer) {#data-source}

En datakälla i Journey Optimizer definierar vilka fält från Adobe Experience Platform (eller externa API:er) som exponeras inuti resor och meddelanden. Datakällor som konfigureras i Journey Optimizer-gränssnittet innehåller vanligtvis den inbyggda Adobe Experience Platform-datakällan (som visar kundprofilattribut i realtid) och externa eller anpassade datakällor som anropas under körningen för ytterligare berikning. De används för resevillkor, anpassade åtgärder och personalisering av meddelanden.

➡️ [Läs mer om datakällor](../datasource/about-data-sources.md)

>[!NOTE]
>[Adobe Experience Platform-ordlistan](https://experienceleague.adobe.com/sv/docs/experience-platform/landing/glossary){target="_blank"} definierar&quot;datakälla&quot; i allmänhet som datas ursprung (en CRM, mobilapp osv.). I Journey Optimizer har **datakällan** en specifik betydelse: en gränssnittskonfiguration som styr vilka fält som visas i resor och meddelanden.

### Identitet och kundprofil i realtid {#identity}

En identitet är en identifierare som unikt representerar en enskild kund, till exempel ett cookie-ID, ett enhets-ID, en e-postadress eller ett CRM-ID. Identiteter ordnas i namnutrymmen (e-post, ECID, CRMID), och flera identiteter för samma person sammanfogas i ett enhetligt identitetsdiagram. Kundprofilen i realtid använder det diagrammet för att få en helhetsbild av varje enskild kund genom att kombinera data från flera kanaler, inklusive online-, offline-, CRM- och tredjepartskällor.

Ett nyckelkoncept för nybörjare är **profilfragmentmodellen**. Varje gång en kund interagerar med ert varumärke på en viss enhet eller kanal - på er webbplats, i en mobilapp eller i en butik - registreras den interaktionen som ett profilfragment: en partiell bild av kunden baserat på den specifika kontaktytan. Kundprofilen i realtid sammanfogar dessa fragment kontinuerligt baserat på delade identitetsvärden och skapar en komplett, aktuell profil. Journey Optimizer läser från den här sammansatta profilen för att utvärdera villkoren, välja erbjudanden och personalisera meddelanden i realtid.

➡️ [Läs mer om identiteter i Journey Optimizer](../audience/get-started-identity.md)

### Sök datauppsättning {#lookup-dataset}

Med en uppslagsdatauppsättning kan Journey Optimizer hämta referens- eller transaktionsdata vid körning från en Adobe Experience Platform-datauppsättning, utan att lagra dessa data i kundprofilen i realtid. Detta är användbart för ofta ändrade referensdata (priser, lager, lagertimmar) eller transaktionsdata som behövs vid meddelandetillfället men som inte hör till profilen. Journey Optimizer utför sökningen under resan eller meddelandekörningen baserat på en nyckel som ett produkt-ID.

➡️ [Läs mer om uppslagsdatauppsättningar](lookup-aep-data.md)

## Checklista för databeredskap {#checklist}

Innan marknadsförarna börjar bygga resor och kampanjer bör organisationen slutföra en uppsättning databeredskapsåtgärder. Detta garanterar att Journey Optimizer kan använda rätt data vid rätt tidpunkt och på ett kompatibelt sätt.

>[!NOTE]
>Stegen nedan har flera roller: datatekniker, administratörer och marknadsförare. Använd checklistan som en delad plan för att förbereda din miljö. Steg 1-4 slutförs i Adobe Experience Platform; steg 5-6 konfigureras i Journey Optimizer.

I de sex stegen nedan går du igenom hela datakonfigurationsprocessen, från identitetskonfiguration till verifiering av att data flödar korrekt till Journey Optimizer:

1. Definiera din identitetsstrategi
1. Utforma scheman för profil- och händelsedata
1. Skapa profilaktiverade datauppsättningar
1. Hämta in data från era källor
1. Konfigurera datakällor i Journey Optimizer
1. Verifiera spårning, feedback och resedatauppsättningar

+++ Definiera din identitetsstrategi

Välj en primär identitet för dina kunder (till exempel ECID, e-post eller CRMID) och konfigurera motsvarande namnutrymmen i Adobe Experience Platform Identity Service. Kontrollera att det finns identitetsfält i profilaktiverade scheman och validera att profilerna är korrekt sammanfogade i identitetsdiagrammet.

➡️ [Läs mer om identiteter i Journey Optimizer](../audience/get-started-identity.md)

+++

+++ Utforma scheman för profil- och händelsedata

Skapa **XDM-scheman för enskild profil** om du vill samla in kundattribut som namn och kontaktinformation, inställningar och intressen samt livscykelstadium eller medgivandetillstånd. Skapa **XDM ExperienceEvent**-scheman för att hämta beteendedata och transaktionsdata, till exempel webb- och apphändelser, köp och offlineinteraktioner. Markera de rätta fälten som identiteter och profilattribut där så är lämpligt.

➡️ [Läs mer om scheman](get-started-schemas.md)

+++

+++ Skapa profilaktiverade datauppsättningar

I Adobe Experience Platform skapar du datauppsättningar baserade på dina XDM-scheman och aktiverar profil på alla datauppsättningar som ska bidra till kundprofilen i realtid. Kontrollera att systemgenererade datauppsättningar som skapats av Journey Optimizer visas på arbetsytan Datauppsättningar.

➡️ [Läs mer om datauppsättningar](get-started-datasets.md)

+++

+++ Hämta in data från era källor

Konfigurera källkopplingar för företagssystem - som Adobe Analytics, Adobe Experience Platform Web SDK eller dina CRM- och POS-plattformar - och mappa inkommande fält till XDM-scheman. Verifiera att data får plats i rätt datauppsättningar och visas i kundprofilen i realtid där det förväntas.

➡️ [Läs mer om källanslutningar](../start/get-started-sources.md)

➡️ [Självstudiekurs: Skapa datauppsättningar och importera data](https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-management/create-datasets-and-ingest-data){target="_blank"}

+++

+++ Konfigurera datakällor i Journey Optimizer

Datakällor är ett Journey Optimizer-specifikt koncept: de är inte där dina data finns, men där du deklarerar vilka fält som Journey Optimizer får läsa under resan och meddelandekörningen. Innan en resa kan utvärdera ett villkor som&quot;är kunden en lojalitetsmedlem?&quot; Om du vill anpassa ett meddelande med ett förnamn måste de relevanta profilfälten visas via en datakällkonfiguration.

Journey Optimizer innehåller en inbyggd [Adobe Experience Platform-datakälla](../datasource/adobe-experience-platform-data-source.md) som ger direktåtkomst till kundprofilattribut i realtid. Detta omfattar de flesta användningsfall: läsprofilattribut för personalisering eller kontroll av samtycke och inställningsfält. Du kan också konfigurera [externa datakällor](../datasource/external-data-sources.md) så att externa API:er anropas vid körning, till exempel för att hämta en kundlojalitetspoäng i realtid, en produktrekommendation eller en lagerlagernivå som inte lagras i Adobe Experience Platform.

>[!NOTE]
>Direktåtkomst till händelsedata för upplevelser via den inbyggda Adobe Experience Platform-datakällan är föråldrad och inaktiveras stegvis. [Läs mer](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/orchestrate-journeys/journey-use-cases/exp-event-lookup){target="_blank"}.

Att konfigurera datakällor är en administrativ uppgift som låser upp hela datalagret för reseförfattare och marknadsförare. När ett fält exponeras via en datakälla blir det tillgängligt i transportvillkorsbyggaren, i redigeringsprogram för meddelandeanpassning och i regler för beslut om erbjudanden - utan att det krävs något ytterligare konstruktionsarbete vid resans byggtid.

➡️ [Läs mer om konfiguration av datakälla](../datasource/about-data-sources.md)

+++

+++ Verifiera spårning, feedback och resedatauppsättningar

Kontrollera att systemgenererade Journey Optimizer-datauppsättningar är tillgängliga på arbetsytan Datauppsättningar. Kör testresor och -kampanjer och använd sedan Frågeredigeraren för att verifiera att skicka-, öppna-, klicknings- och studshändelser registreras och att steg-händelser och lägen för resan fångas in korrekt. Använd dessa datauppsättningar för kontinuerlig övervakning, felsökning och optimering av kundresan.

➡️ [Läs mer om frågor i Journey Optimizer](get-started-queries.md)

+++

## Skyddsritningar och datadesignöverväganden {#guardrails}

Vissa skyddsmekanismer och begränsningar kan påverka hur du utformar din datamodell och dina resor. Granska dessa tidigt för att undvika omarbetningar senare.

>[!IMPORTANT]
>Se alltid sidan [Journey Optimizer-skyddsförslag och begränsningar](../start/guardrails.md) för den senaste informationen. Sammanfattningarna nedan markerar viktiga objekt, men kan förändras över tid.

### Journey Optimizer systemdatauppsättningar och TTL {#datasets-ttl}

Journey Optimizer skapar flera systemgenererade datauppsättningar för spårning, feedback och steg för kundresan. Från och med februari 2025 introduceras ett TTL-skydd (time-to-live) för vissa av dessa datauppsättningar, vilket kan påverka hur länge data lagras för analys och felsökning.

➡️ [Läs mer om TTL-skyddsräcken för datauppsättningar](datasets-ttl.md)

### Direktuppspelningssegmentering och Journey Optimizer-event {#streaming-segmentation}

Från och med 1 november 2024 har direktuppspelningssegmentering inte längre stöd för skicka och öppna händelser från Journey Optimizer spårnings- och feedbackdatauppsättningar. Använd [Affärsregler](../conflict-prioritization/rule-sets.md) i stället för att direktuppspela segment baserat på skicka/öppna händelser för användningsfall som till exempel frekvensbegränsning och trötthetshantering.

➡️ [Läs mer om datauppsättningar](get-started-datasets.md)

### Uppslag och beslut för datauppsättningar {#lookup-guardrails}

Datauppslagning är idealiskt för attribut som ofta ändras (lager, priser, väder) eller data som inte behöver lagras i kundprofilen i realtid. Granska produktspecifika utkast som storleksbegränsningar för datauppsättningar och frågetak i relevant dokumentation innan du utformar din sökstrategi.

➡️ [Läs mer om uppslagsdatauppsättningar](lookup-aep-data.md)

## Exempel: förbereda data för en välkomstresa {#example}

I följande exempel visas hur koncepten på den här sidan fungerar tillsammans i ett enkelt scenario.

1. En datatekniker skapar ett [XDM Individual Profile-schema](get-started-schemas.md) för kundattribut (namn, e-post, lojalitetsnivå, medgivande) och ett XDM ExperienceEvent-schema för webbregistreringshändelser.
1. [Profilaktiverade datauppsättningar](get-started-datasets.md) skapas för varje schema: en för CRM-attribut och en för registreringshändelser.
1. Registreringshändelser direktuppspelas via Adobe Experience Platform Web SDK. CRM-data hämtas via en [källanslutning](../start/get-started-sources.md).
1. En administratör konfigurerar datakällan [Adobe Experience Platform](../datasource/adobe-experience-platform-data-source.md) i Journey Optimizer och visar fält som `profile.person.name.firstName`, `profile.personalEmail.address` och `profile.loyaltyTier`.
1. En marknadsförare [skapar en välkomstresa](../building-journeys/journey-gs.md) som lyssnar efter en registreringshändelse och använder dessa profilattribut för att [anpassa välkomstmeddelandet](../personalization/personalize.md). Journey Optimizer skriver skicka och öppna händelser för att spåra datauppsättningar och loggar reseförloppet i händelsedatamängder för kundsteg.
1. En utvecklare använder [Frågeredigeraren](get-started-queries.md) för att verifiera att händelser flödar korrekt och analyserar prestanda (öppnar, klickar, går att skicka). Teamet anpassar kundresan och innehållet baserat på dessa insikter.

Det här flödet visar hur scheman, datauppsättningar, källor, datakällor och frågor fungerar tillsammans i ett komplett, nybörjarvänligt användningsfall.

## Relaterade resurser {#related-resources}

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg?lang=sv-SE)

**Kom igång med scheman**

Lär dig hur du skapar XDM-scheman i Adobe Experience Platform, väljer rätt klass och fältgrupper och modellerar profilattribut och beteendehändelser.

[Läs mer](get-started-schemas.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/database.svg?lang=sv-SE)

**Arbeta med datauppsättningar**

Lär dig hur du skapar profilaktiverade data och händelsedatamängder, övervakar datainmatning och utforskar de systemgenererade datauppsättningar som Journey Optimizer skapar automatiskt för spårning, feedback och steg i kundresan.

[Läs mer](get-started-datasets.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg?lang=sv-SE)

**Konfigurera datakällor**

Stegvisa anvisningar om hur du konfigurerar den inbyggda Adobe Experience Platform-datakällan och valfria externa datakällor för att visa profilfält och externa API-svar på dina resor.

[Läs mer](../datasource/about-data-sources.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/puzzle-piece.svg?lang=sv-SE)

**Använd Adobe Experience Platform-data (sökning)**

Upptäck hur ni förbättrar meddelanden under körning med referens- eller transaktionsdata från AEP datauppsättningar, utan att lagra dessa data i kundprofilen i realtid.

[Läs mer](lookup-aep-data.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg?lang=sv-SE)

**Kom igång med frågor**

Använd frågetjänsten för att analysera Journey Optimizer-datauppsättningar, verifiera att händelser flödar korrekt och skapa rapporteringsfrågor vid sändning, öppna, klicka och studsa data.

[Läs mer](get-started-queries.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg?lang=sv-SE)

**Kom igång med profiler**

Se hur kundprofilen i realtid fungerar i Journey Optimizer och hur du bläddrar bland, inspekterar och validerar enskilda kundprofiler i användargränssnittet för plattformen.

[Läs mer](../audience/get-started-profiles.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg?lang=sv-SE)

**Ställa in en översikt**

En nybörjarvänlig videogenomgång av datainställningar i Journey Optimizer som omfattar scheman, datauppsättningar och källor från början till slut.

[Titta på självstudiekursen](https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-management/set-up-data-overview){target="_blank"}
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg?lang=sv-SE)

**Skapa datauppsättningar och importera data, genomgång**

En praktisk självstudiekurs som visar hur du skapar datauppsättningar i Adobe Experience Platform och importerar data med hjälp av källanslutningar, med stegvisa instruktioner som du kan följa i din egen sandlåda.

[Titta på självstudiekursen](https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/data-management/create-datasets-and-ingest-data){target="_blank"}
:::

::::
