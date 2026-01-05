---
solution: Journey Optimizer
product: Journey Optimizer
title: Testa, validera och godkänn
description: Upptäck alla test- och godkännandefunktioner i Journey Optimizer. Förhandsgranska innehåll, simulera resor, validera e-postmeddelanden, kör experiment, identifiera konflikter och konfigurera arbetsflöden för godkännande före start.
feature: Get Started, Overview
role: User
level: Beginner, Intermediate
keywords: testa, validera, godkänna, godkänna, kvalitetssäkring, qa, testprofiler, personalisering, återgivning, skräppost, innehållstestning, a/b-test, konfliktidentifiering, utsädeslista, korrektur, exempeldata, godkännande-arbetsflöde, e-posttestning, valideringsarbetsflöde
redpen-status: CREATED_||_2025-08-11_20-30-59
exl-id: a770412f-2f80-459d-8cce-32212154d154
source-git-commit: d004bdaccab07110408860e67b52bf4c00c1fb15
workflow-type: tm+mt
source-wordcount: '2735'
ht-degree: 0%

---

# Testa, validera och godkänn{#section-overview}

I det här avsnittet beskrivs alla testnings- och godkännandefunktioner i Journey Optimizer. Du hittar verktyg för att förhandsgranska innehåll med testprofiler, validera reselogik, kontrollera e-poståtergivning och skräppostpoäng, köra A/B-experiment, identifiera konflikter och konfigurera arbetsflöden för godkännande.

Denna landningssida hjälper er att välja rätt testmetod baserat på vad ni bygger (kampanjer kontra resor), leder er genom rekommenderade testarbetsflöden och ger snabb tillgång till alla testnings- och godkännanderesurser. Börja med [Välj din testmetod](#choose-your-testing-approach) nedan för att identifiera vilka verktyg som gäller för ditt användningsfall.

## Varför det är viktigt att testa och godkänna

Testnings- och godkännandeprocesserna fungerar som viktiga kvalitetsgater som skyddar ert varumärke och säkerställer kampanjframgångar. Här är varför de betyder något:

* **Hitta fel innan de når kunder** - Identifiera brutna länkar, felaktig personalisering, återgivningsproblem och logiska fel i en kontrollerad miljö där korrigeringarna är snabba och riskfria.

* **Förbättra leveransen** - Testa skräppostpoängen, validera e-postautentiseringen och kontrollera återgivningen mellan e-postklienter för att maximera placeringen av inkorgen och engagemangsfrekvensen.

* **Säkerställ varumärkets enhetlighet** - Förhandsgranska innehåll med olika testprofiler för att verifiera att personaliseringen visas korrekt för olika kundsegment och upprätthåller varumärkesstandarder.

* **Validera komplexa resor** - Simulera flerstegsflöden för att bekräfta att utlösarna fungerar korrekt, villkoren utvärderas korrekt och att kunderna får rätt meddelanden vid rätt tidpunkt.

* **Upprätta ansvarsskyldighet** - Implementera formella godkännandearbetsflöden som kräver att intressenter godkänner avtalet, skapa tydligt ägarskap och minska oauktoriserade eller förtidiga kampanjstarter.

* **Spara tid och resurser** - Hitta problem tidigt i utvecklingscykeln när korrigeringarna är billigare och snabbare och förhindra kostsamma efterstartsändringar eller kundtjänsteskaleringar.

<!--## Testing capabilities overview

**Testing types available:**

* Content testing: Preview and validate message content before sending → [Choose your testing approach](#choose-your-testing-approach)
* Journey logic testing: Simulate customer progression through journey paths → [Choose your testing approach](#choose-your-testing-approach)
* Technical testing: Validate rendering, deliverability, and authentication → [Technical validation](#2-technical-validation)
* Performance testing: Compare content variations using A/B experiments → [Content Experiments & A/B Testing](#test--approve-content)
* Conflict testing: Detect campaign and journey overlaps → [Conflict Detection](#test--approve-content)
* Approval testing: Structured review workflows before activation → [Approval Workflows](#test--approve-content)

**Key capabilities by context:**

| Capability | Applies to | Channel restrictions | Prerequisites | Primary purpose |
|------------|-----------|---------------------|--------------|-----------------|
| [Test profiles](../using/content-management/test-profiles.md) | Campaigns, Journeys | All channels | Test profiles created | Preview personalized content |
| [Sample input data](../using/test-approve/simulate-sample-input.md) | Campaigns, Journeys | Email, SMS, Push, Web, Code-based, In-app, Content cards | CSV/JSON file | Test multiple personalization variants |
| [Test mode](../using/building-journeys/testing-the-journey.md) | Journeys only | N/A | Draft journey, namespace configured | Simulate profile progression |
| [Dry run](../using/building-journeys/journey-dry-run.md) | Journeys only | N/A | Journey created | Analyze execution paths |
| [Email rendering](../using/content-management/rendering.md) | Campaigns, Journeys | Email only | Litmus integration | Verify display across clients |
| [Spam score](../using/content-management/spam-report.md) | Campaigns, Journeys | Email only | None | Deliverability validation |
| [Seed lists](../using/configuration/seed-lists.md) | Campaigns, Journeys | Email only | Seed list configured | Stakeholder monitoring |
| [Content experiments](../using/content-management/get-started-experiment.md) | Campaigns only | All channels | None | A/B and multi-armed bandit testing |
| [Conflict detection](../using/conflict-prioritization/conflicts.md) | Campaigns, Journeys (limited) | All channels | None | Prevent customer over-messaging |
| [Approval workflows](../using/test-approve/gs-approval.md) | Campaigns, Journeys | All channels | Approval policy created | Structured review process |
| [Personalization playground](../using/personalization/personalize.md#playground) | All | All channels | None | Learn and test personalization syntax |

**Common testing workflows:**

1. Pre-development: Use [personalization playground](#test--approve-content) to learn syntax
2. During development: Preview with [test profiles](#choose-your-testing-approach), validate with [sample input data](#choose-your-testing-approach)
3. Pre-launch: Run [technical tests](#2-technical-validation) (rendering, spam), check [conflicts](#test--approve-content), submit for [approval](#test--approve-content)
4. Post-launch: Monitor with live reports (see [Monitoring & Troubleshooting](#test--approve-content)), iterate based on results

-->

## Nyckelterminologi

+++**Testprofiler**

Syntetiska kundprofiler (inte verkliga kunder) som används för att förhandsgranska personaliserat innehåll. Flaggas i Kundprofiltjänst i realtid. Krävs för testläge och förhandsgranskning av innehåll. [Läs mer](../using/content-management/test-profiles.md) | [Lär dig skapa testprofiler](../using/audience/creating-test-profiles.md)

+++

+++**Testläge**

Resesimuleringsfunktion som skickar testprofiler via resevägar. Begränsningar: Endast utkast, endast namnutrymme, endast testprofiler krävs. [Läs mer](../using/building-journeys/testing-the-journey.md)

+++

+++**Torr körning**

Reseanalysverktyg som spårar sökvägar utan att skicka meddelanden eller anropa API. Användningsfall: Validera logiken utan att behöva använda resurser. [Läs mer](../using/building-journeys/journey-dry-run.md)

+++

+++**Exempelindata**

CSV- eller JSON-filer som innehåller profilattributvärden för testning av personalisering. Stöder upp till 30 varianter. Alternativ för att skapa testprofiler. [Läs mer](../using/test-approve/simulate-sample-input.md)

+++

+++**Startlistor**

E-postadresser till interna intressenter som automatiskt ingår i faktiska leveranser (inte testmeddelanden). Endast e-postkanal. Användningsfall: Kvalitetsövervakning och efterlevnad. [Läs mer](../using/configuration/seed-lists.md)

+++

+++**Innehållsexperiment**

A/B-tester eller multiväpnade bandit-experiment där innehållsvariationer jämförs. Endast kampanjer, inte tillgängliga under resor. [Läs mer](../using/content-management/get-started-experiment.md) | [Skapa experiment ](../using/content-management/content-experiment.md)

+++

+++**Korrektur**

Testa e-postleveranser som skickas till specifika e-postadresser med hjälp av testprofildata. Olika utsädeslistor (korrektur är manuella testutskick, utsädeslistor är automatiska kopior av intressenter). [Läs mer](../using/content-management/proofs.md)

+++

+++**Konfliktidentifiering**

Verktyg som identifierar överlappande kampanjer och resor som riktar sig till samma målgrupper. Begränsat stöd för resor: endast typerna enhet, målgruppskvalitet och läsning av målgrupper. [Läs mer](../using/conflict-prioritization/conflicts.md) | [Lär dig mer om konflikthantering](../using/conflict-prioritization/gs-conflict-prioritization.md)

+++

+++**Arbetsflöden för godkännande**

Granskningsprocess i flera steg som kräver godkännande från berörda parter före aktivering. Kräver konfiguration av godkännandeprincip. [Läs mer](../using/test-approve/gs-approval.md) | [Skapa profiler](../using/test-approve/approval-policies.md)

+++

+++**Återgivningstester**

E-postvalidering för e-postklienter (Gmail, Outlook, Apple Mail) och enheter. Kräver integrering med Litmus. [Läs mer](../using/content-management/rendering.md)

+++

+++**Personalization playground**

Interaktiv utbildningsmiljö för att experimentera med personaliseringssyntax och testa uttryck med exempeldata. Inga livedatauppsättningar krävs. [Läs mer](../using/personalization/personalize.md#playground)

+++

## Beslutsträd för val av testmetod

Använd det här beslutsträdet för att snabbt identifiera rätt testverktyg för ditt specifika scenario. Svara på varje fråga baserat på ditt sammanhang (vad du bygger, vad du behöver validera och vilken kanal du använder) för att navigera direkt till relevanta funktioner och dokumentation.

+++ **Fråga 1: Vad testar du?**

* Campaign → [Välj testmetod](#choose-your-testing-approach)
* Resa → [Välj testmetod](#choose-your-testing-approach)
* Personalization-uttryck → [Personalization playground](#test--approve-content)
+++

+++**Fråga 2: Vilken aspekt behöver valideras?**

* Innehåll och personalisering → [Testa profiler](#choose-your-testing-approach) eller [exempelindata](#choose-your-testing-approach)
* E-postvisning → [Återgivningstest via e-post](#2-technical-validation)
* Leverans → [Spam score check](#2-technical-validation)
* Reselogik och -flöde → [Testläge](#choose-your-testing-approach) eller [torr körning](#test--approve-content)
* Prestandajämförelse → [Innehållsexperiment](#test--approve-content) (endast kampanjer)
* Tidskonflikter → [Konfliktidentifiering](#test--approve-content)
* Granskning av intressenter → [Arbetsflöde för godkännande](#test--approve-content)
+++

+++**Fråga 3: Vilken kanal?**

* E-post → Alla tillgängliga testmetoder (se [Välj testmetod](#choose-your-testing-approach))
* SMS, push → [Innehållstestning](#choose-your-testing-approach), [exempelindata](#choose-your-testing-approach), [arbetsflöden för godkännande](#test--approve-content)
* Webb, In-app, kodbaserad → [Innehållstestning](#choose-your-testing-approach), [exempelindata](#choose-your-testing-approach), [arbetsflöden för godkännande](#test--approve-content)
* Flera kanaler → Testa varje kanal separat
+++

+++**Fråga 4: När i arbetsflödet?**

* Innan du skapar → [Personalization playground](#test--approve-content) för lärande
* Under generering → [Testprofiler](#choose-your-testing-approach) och [exempelindata](#choose-your-testing-approach) för validering
* Innan du startar → [Återgivningstester](#2-technical-validation), [skräppostkontroller](#2-technical-validation), [konfliktidentifiering](#test--approve-content), [godkännanden](#test--approve-content)
* Efter start → [Live-rapporter](../using/building-journeys/report-journey.md) och [övervakning](#test--approve-content)
+++


## Välj testmetod

Rätt testmetod beror på vad du bygger och vad du behöver för att validera. Använd den här vägledningen när du vill identifiera de mest relevanta testverktygen för ditt scenario.

>[!BEGINTABS]

>[!TAB Testar kampanjer]

**För alla kampanjer:**

* Förhandsgranska och testa innehåll med [testprofiler](../using/content-management/test-profiles.md) eller [exempelindata](../using/test-approve/simulate-sample-input.md)
* Kontrollera [e-poståtergivning](../using/content-management/rendering.md) på enheter och klienter (endast e-postkanal)
* Kör [skräppostpoängskontroller](../using/content-management/spam-report.md) (endast e-postkanal)
* Granska [konflikter](../using/conflict-prioritization/conflicts.md) med andra kampanjer och resor
* Konfigurera [dirigerade listor](../using/configuration/seed-lists.md) för övervakning av intressenter (endast e-postkanal)
* Skicka för [godkännande](../using/test-approve/gs-approval.md) före aktivering

**För A/B-testning och optimering:**

* Skapa [innehållsexperiment](../using/content-management/get-started-experiment.md) för att testa flera behandlingar och mäta prestanda

**För API-utlösta kampanjer:**

* Använd [API:t för kampanjsimulering](https://developer.adobe.com/journey-optimizer-apis/references/simulations/){target="_blank"} om du vill utlösa korrekturjobb programmatiskt

>[!TAB Testar resor]

**För alla resor:**

* Använd [testläge](../using/building-journeys/testing-the-journey.md) för att simulera profilens förlopp (endast utkastresor, kräver namnutrymme) eller [torr körning](../using/building-journeys/journey-dry-run.md) för att analysera körningssökvägar utan att skicka meddelanden
* Testa enskilda meddelanden med [förhandsgranskning och korrektur](../using/content-management/preview-test.md)
* Kontrollera [konflikter](../using/conflict-prioritization/conflicts.md) med andra resor och kampanjer
* Skicka för [godkännande](../using/test-approve/gs-approval.md) före publicering

**För komplexa resor:**

* Använd testläget och kör torrt tillsammans för att noggrant validera förgreningslogik och körningsvägar
* Testa olika anmälningsvillkor och profilattribut systematiskt

**Obs!** Konfliktidentifiering och resefästning är endast tillgängliga för resor med enhetsbehörighet, målgruppskvalifikation och läsning av målgrupper.

>[!TAB Testar personalisering]

**Innan du skapar innehåll:**

* Experimentera i [personaliseringsuppspelningen](../using/personalization/personalize.md#playground) för att lära dig syntax och testa uttryck med exempeldata

**När innehåll skapas:**

* Förhandsgranska med [testprofiler](../using/content-management/test-profiles.md) för att validera återgivningar av personalisering korrekt
* Testa flera scenarier med [exempelindata](../using/test-approve/simulate-sample-input.md) från CSV-/JSON-filer (stöder upp till 30 varianter)

>[!ENDTABS]

## Testa bästa praxis

Följ de här rekommenderade arbetssätten för att maximera effekten av testningen:

1. **Testa tidigt och ofta** - Vänta inte tills en kampanj har skapats helt. Testa innehåll, personalisering och logik stegvis när ni utvecklar.

1. **Använd realistiska testprofiler** - [Skapa testprofiler](../using/audience/creating-test-profiles.md) som exakt motsvarar målgruppssegmenten, inklusive kantfall och olika personaliseringsscenarier.

1. **Testa mellan enheter och klienter** - Verifiera [e-poståtergivning](../using/content-management/rendering.md) på vanliga e-postklienter (Gmail, Outlook, Apple Mail) och enheter (skrivbord, mobil, surfplatta) för att se till att visningen är konsekvent (endast e-postkanal).

1. **Verifiera personalisering noggrant** - Testa med flera [testprofiler](../using/content-management/test-profiles.md) som har olika attributvärden för att bekräfta att personaliseringstoken återges korrekt och reservvärden fungerar. Använd [personaliseringsspelgrunden](../using/personalization/personalize.md#playground) om du vill experimentera med personaliseringsuttryck och testa kod med exempeldata innan du använder dem på dina kampanjer.

1. **Testa innehållsvariationer med exempeldata** - Använd [exempelindata](../using/test-approve/simulate-sample-input.md) från CSV- eller JSON-filer för att testa upp till 30 personaliseringsscenarier utan att skapa flera testprofiler, spara tid samtidigt som du får en heltäckande täckning. Stöder e-post, SMS, push, webb, kodbaserad upplevelse, kanaler i appen och innehållskort.

1. **Använd startlistor för övervakning av intressenter** - Konfigurera [startlistor](../using/configuration/seed-lists.md) för att automatiskt inkludera interna intressenter som tar emot kopior av alla leveranser vid körning för kvalitetsövervakning och kompatibilitetsverifiering (endast e-postkanal).

1. **Simulera resesökvägar** - För komplexa resor med flera förgreningar använder du [testläge](../using/building-journeys/testing-the-journey.md) för att testa olika postvillkor och profilattribut för att validera alla möjliga sökvägar. Tillgängligt för utkastresor som använder ett namnutrymme.

1. **Kontrollera leveransindikatorer** - Granska [skräppostpoäng](../using/content-management/spam-report.md), autentiseringsstatus och hälsomått för e-post före stora sändningar (endast e-postkanal).

1. **Dokumenttestresultat** - Registrera testresultat, problem och lösningar som kan förbättra framtida testprocesser och dela inlärningar med ditt team.

1. **Involvera intressenter tidigt** - Dela förhandsgranskningar och testresultat med intressenter före [formellt godkännande](../using/test-approve/gs-approval.md) för att samla in feedback och anpassa förväntningarna.

## Rekommenderat testarbetsflöde

Följ detta systematiska tillvägagångssätt för att säkerställa grundlig testning och smidiga godkännanden:

### &#x200B;1. Innehållsutveckling och förhandsgranskning

Börja med att skapa ditt innehåll och använda förhandsgranskningsfunktionerna för att verifiera den ursprungliga designen och personaliseringen:

* Utforma ditt [e-postmeddelande](../using/email/create-email.md), [SMS](../using/sms/create-sms.md), [push-meddelande](../using/push/create-push.md) eller annat kanalinnehåll

* Använd funktionen **[Simulera innehåll](../using/content-management/preview-test.md)** för att förhandsgranska med testprofiler

* Kontrollera [personaliseringstoken](../using/personalization/personalization-syntax.md), dynamiskt innehåll och reservvärden

* Experimentera med personaliseringsuttryck i **[personaliseringsuppspelningen](../using/personalization/personalize.md#playground)** för att testa och förfina koden med exempeldata innan den tillämpas på livematerial

* Testa flera variationer med **[exempelindata](../using/test-approve/simulate-sample-input.md)** från CSV-/JSON-filer för att validera personalisering i olika profilscenarier

* Verifiera [återgivning](../using/content-management/rendering.md) för olika skärmstorlekar och e-postklienter

### &#x200B;2. Teknisk validering

Validera tekniska aspekter som påverkar leveransen och funktionaliteten:

* Kör [skräppostpoängkontroller](../using/content-management/spam-report.md) för att identifiera potentiella leveransproblem

* Testa länkar för att säkerställa att de inte bryts och spåras korrekt

* Verifiera konfigurationen för [e-postautentisering](../using/configuration/dmarc-record.md) (SPF, DKIM, DMARC)

* Granska HTML-rendering och sök efter CSS-kompatibilitetsproblem

* Testa [responsiv design](../using/email/content-from-scratch.md) på mobila och stationära enheter

* Kontrollera om det finns [potentiella konflikter](../using/conflict-prioritization/conflicts.md) med andra kampanjer och resor för att förhindra problem med trötthet och timing i kundmeddelanden

### &#x200B;3. Reseprovning (endast resor)

Om du testar en resa, validera orkestreringslogiken:

* Aktivera **[testläge](../using/building-journeys/testing-the-journey.md)** för att simulera profilförloppet under resan

* Testa olika [anmälningsvillkor](../using/building-journeys/entry-management.md) och målgruppskvalifikationer

* Verifiera att [vänteaktiviteter](../using/building-journeys/wait-activity.md), [villkor](../using/building-journeys/condition-activity.md) och förgreningslogik fungerar korrekt

* Använd **[Torr körning](../using/building-journeys/journey-dry-run.md)** för komplexa resor för att analysera körningssökvägar utan att skicka meddelanden

* Kontrollera att [händelser](../using/event/about-events.md) utlöses korrekt och att [anpassade åtgärder](../using/action/about-custom-action-configuration.md) körs som förväntat

### &#x200B;4. Inlämning av godkännande

När testningen är klar och problemen är lösta:

* Skicka kampanjen eller resan för godkännande enligt din organisations [godkännandepolicy](../using/test-approve/approval-policies.md)

* Inkludera testresultat och dokumentation i [godkännandebegäran](../using/test-approve/request-approval.md)

* Åtgärda eventuella feedback- eller ändringsbegäranden från [godkännare](../using/test-approve/review-approve-request.md)

* Gör nödvändiga ändringar och försök igen om ändringarna är betydande

### &#x200B;5. Verifiering före start

Innan du aktiverar kampanjen eller resan:

* Utför en slutgiltig granskning av alla inställningar, målgrupper och [scheman](../using/building-journeys/journey-properties.md)

* Verifiera att alla godkännanden finns på plats och dokumenteras

* Bekräfta sändningstider och [tidszoner](../using/building-journeys/timezone-management.md) är korrekta

* Aktivera [övervakning och aviseringar](../using/reports/alerts.md) för att spåra prestanda efter start

### &#x200B;6. Övervaka och iterera

Efter start fortsätter du övervakningen för att upptäcka eventuella problem tidigt:

* Ställ in [systemvarningar](../using/reports/alerts.md) för resefel, hög avhoppsfrekvens eller lågt engagemang

* Granska [liverapporter](../using/building-journeys/report-journey.md) för att spåra prestanda i förhållande till förväntningarna

* Var redo att [pausa eller ändra ](../using/building-journeys/journey-pause.md) resor om allvarliga problem uppstår

* Dokumentlärdomar som kan förbättra framtida testprocesser

## Testning in action: Användningsexempel

Se hur testkoncept kan användas i verkliga scenarier:

| Användningsfall | Vad du kommer att lära dig | Viktigt fokus för testning |
|----------|-------------------|-------------------|
| **[Skicka flerkanalsmeddelanden](../using/building-journeys/journeys-uc.md)** | Testa en resa som kombinerar Läs publik, Reaktionshändelser och e-post/push-meddelanden. Validera hela flödet från målgruppsanpassning till meddelandeleverans. | Samordning i flera kanaler, reaktionshändelser, komplett flödesvalidering, test- och publiceringssteg |
| **[Skicka ett meddelande till prenumeranter](../using/building-journeys/message-to-subscribers-uc.md)** | Testa resor som avser prenumerationslistor med dynamisk e-postadress. Validera personaliseringsuttryck för korrekt målinriktning av prenumeranter. | Personalization-uttryck, dynamisk adressering, målinriktning för prenumerationslista |
| **[Skicka tidsbundna meddelanden](../using/building-journeys/weekday-email-uc.md)** | Testa resor med tidsbaserade villkor för att säkerställa att meddelanden skickas på specifika dagar. Validera vänteaktiviteter och schemaläggningslogik. | Tidsbaserade villkor, vänteaktiviteter, schemaläggningsvalidering |
| **[Utforska fler användningsexempel för resor](../using/building-journeys/jo-use-cases.md)** | Få tillgång till en omfattande samling praktiska exempel som omfattar upplevelsehändelser, flerkanalsmeddelanden och externa systemintegreringar. | Olika scenarier, avancerade mönster, integrationstestning |

## Testa och godkänna innehåll

:::: landing-cards-container
:::
![icon](https://cdn.experienceleague.adobe.com/icons/list-check.svg)

Förhandsgranska, testa och validera innehåll

Lär dig hur du förhandsgranskar, testar och validerar personaliserat innehåll med testprofiler, e-postrenderingstester, utvärderingar av skräppostpoäng med mera.

[Förhandsgranska och testa innehåll](preview-test-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/shield-halved.svg)

Arbetsflöden för godkännande av resor och kampanjer

Lär dig hur man skapar, hanterar och genomför godkännandeprocesser för att säkerställa kvalitetskontroll för resor och kampanjer.

[Läs mer om arbetsflöden för godkännande](approve-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg)

Testa din resa

Validera resan innan du publicerar den genom att testa den med specifika profiler för att säkerställa att händelser, villkor och åtgärder fungerar som förväntat. Tillgängligt för utkastresor som använder ett namnutrymme.

[Testa din resa](../using/building-journeys/testing-the-journey.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg)

Körning av resetorr

Utför en torr körning för att simulera och validera kundresan och identifiera potentiella problem innan du publicerar.

[Lär dig mer om körning av körning med resan](../using/building-journeys/journey-dry-run.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg)

Övervakning och felsökning

Få tillgång till omfattande felsökningsresurser, systemvarningar och felkoder för att lösa problem med kundresan och prestandan.

[Visa övervakning och felsökning](troubleshoot-journey-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code.svg)

Personalization Playground

Experimentera med personaliseringsuttryck i en säker miljö. Testa koden med exempeldata och förhandsgranska resultaten innan du lägger in dem i era kampanjer och resor.

[Läs mer om Personalization Playground](../using/personalization/personalize.md#playground)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/data.svg)

Content Experiments &amp; A/B Testing

Optimera era kampanjer genom att testa olika innehållsvariationer och mäta prestanda för att identifiera de mest effektiva behandlingarna. Endast tillgängligt för kampanjer (stöder A/B och multiväpnade banditexperiment).

[Lär dig mer om Content Experiments](../using/content-management/get-started-experiment.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/envelope.svg)

Utsändningslistor för övervakning av intressenter

Inkludera automatiskt interna intressentadresser i leveranser för att övervaka faktiska meddelanden som skickas till kunderna för kvalitetssäkring och efterlevnad. Endast tillgängligt för e-postkanaler.

[Konfigurera dirigeringslistor](../using/configuration/seed-lists.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bell.svg)

Konfliktidentifiering

Identifiera potentiella överlappningar mellan kampanjer och resor för att förhindra överväldigande kunder med för många samtidiga kommunikationer. Tillgängligt för kampanjer och för enhetsaktiviteter, målgruppskvalifikationer och för att läsa målgruppsresor.

[Identifiera konflikter](../using/conflict-prioritization/conflicts.md)
:::

::::

## Ytterligare resurser

>[!BEGINTABS]

>[!TAB Grundläggande stödlinjer]

* [Simulera innehållsvariationer](../using/test-approve/simulate-sample-input.md) - Testa upp till 30 personaliseringsscenarier med CSV- eller JSON-filer. Perfekt för testning av flerspråkigt innehåll utan att behöva skapa flera testprofiler. Har stöd för e-post, SMS, push, webb, kodbaserade kort, kort i appen och innehållskort.

* [Skapa testprofiler](../using/audience/creating-test-profiles.md) - Skapa och hantera testprofiler för att simulera kundscenarier. Lär dig hur du flaggar profiler för testning, anger attribut och organiserar testsegment.

* [Rapport om skräppost](../using/content-management/spam-report.md) - Kontrollera skräppostresultat innan du skickar iväg för att förbättra leveransen och placeringen av inkorgen. Få användbara rekommendationer för innehållsoptimering.

* [Vanliga frågor och svar om resan](../using/building-journeys/journey-faq.md) - Snabbreferens för vanliga frågor om resetestning, körning och felsökning.

>[!TAB Beroenden och relationer]

Lär dig hur testfunktionerna samverkar med varandra och med era större arbetsflöden i Journey Optimizer. I det här avsnittet mappas förutsättningar, överordnade och underordnade beroenden samt gemensamma funktionskombinationer.

+++**Förutsättningar (krävs före testning)**

* Testprofiler måste skapas innan du kan använda testläge eller innehållsförhandsgranskning
* Godkännandeprinciper måste konfigureras innan de skickas för godkännande
* Utsändningslistor måste skapas innan de läggs till i kampanjer/resor
* Litmusintegrering krävs för e-postrenderingstest
* Resan måste ha utkaststatus för att kunna använda testläge
* Resursen måste ha ett namnutrymme som är konfigurerat att använda testläge

+++

+++**Vilka tester som är beroende av (uppströms)**

* Skapa innehåll: Behöver kampanjer eller resor för att testa
* Testprofiler: Krävs för testläge och förhandsgranskning av innehåll
* Godkännandeprinciper: Krävs för godkännandearbetsflöden
* Konfiguration: Kanalkonfigurationer, e-postautentisering, domäninställningar

+++

+++**Vad är beroende av testning (nedåt)**

* Aktivering av kampanj/resa: Det går inte att aktivera utan att åtgärda fel
* Publicering: Godkännande kan krävas före publicering
* Live-övervakning: Övervakning och rapportering efter lansering
* Optimering: Använd testresultat för att förfina framtida kampanjer

+++

+++**Relaterade funktioner**

* Testning + Godkännandearbetsflöden = Kvalitetssäkringsprocess
* Testning + Konfliktidentifiering = Förhindra att kunderna överskickar meddelanden
* Testning + Innehållsexperiment = Prestandaoptimering
* Testning + rapportering = Kontinuerlig förbättringscykel
* Testprofiler + Personalization = Innehållsvalidering
* Torr körning + testläge = Omfattande validering av resan

+++

+++**Vanliga funktionskombinationer**

* Innehållstestning: Testprofiler + Exempelindata + Personalization playground
* E-postvalidering: Återgivningstester + skräppostpoäng + testprofiler + korrektur
* Resevalidering: Testläge + Torr körning + Testprofiler
* Checklista före start: Alla tekniska tester + Konfliktidentifiering + Arbetsflöden för godkännande

+++

>[!TAB Vanliga frågor]

+++**F: Vilken testning krävs innan en kampanj startas?**

**Minimum:** Förhandsgranska innehåll med testprofiler + kontroll av skräppostpoäng (e-post)
**Rekommenderas:** + Återgivning via e-post + Konfliktidentifiering + arbetsflöde för godkännande
**Bästa praxis:** + Datatestning med provindata + Seed-listor + A/B-experiment (vid optimering)

+++

+++**F: Hur testar jag personalisering utan att skapa många testprofiler?**

**Primär lösning:** Använd [exempelindata](../using/test-approve/simulate-sample-input.md) med CSV/JSON-filer (stöder upp till 30 varianter)
**Alternativ:** Skapa 3-5 representativa [testprofiler ](../using/audience/creating-test-profiles.md) som täcker nyckelsegment
**Utbildningsverktyg:** Experimentera först i [personaliseringspresentationen](../using/personalization/personalize.md#playground)

+++

+++**F: Vad är skillnaden mellan testläge och körning i torr riktning?**

**Testläge:** Skickar testprofiler genom resan, utlöser faktiska åtgärder och genererar testmeddelanden. Kräver utkast + namnutrymme.
**Torr körning:** Spårar körningssökvägar utan att skicka något. Fungerar på alla resestatus. Inga meddelanden har skickats, inga åtgärder har utförts.
**Använd tillsammans:** Testläge för meddelandetestning + Kör torr för logikvalidering = omfattande täckning.

+++

+++**F: Kan jag testa resor i produktions-/Live-status?**

**Testläge:** Nej - endast utkastresor
**Torr körning:** Ja - fungerar på alla resestatus
**Förhandsgranska innehåll:** Ja - förhandsgranska enskilda meddelanden när som helst
**Tillfällig lösning:** Duplicera live-resa till utkast för fullständig testlägesvalidering

+++

+++**F: Vilka testfunktioner kräver externa integreringar?**

**Återgivning via e-post:** Kräver integrering med Litmus (separat licens)
**Alla andra:** Inbyggt i Journey Optimizer, inga ytterligare integreringar krävs
**Obs!** Testprofiler kräver kundprofiltjänst i realtid (ingår)

+++

+++**F: Hur testar jag API-utlösta kampanjer?**

**Alternativ 1:** Använd [API för kampanjsimulering](https://developer.adobe.com/journey-optimizer-apis/references/simulations/){target="_blank"} för programmatisk testning
**Alternativ 2:** Förhandsgranska innehåll med testprofiler i användargränssnittet
**Alternativ 3:** Skicka korrektur för att testa e-postadresser
**Bästa praxis:** Kombinera alla tre för fullständig validering

+++

>[!ENDTABS]
