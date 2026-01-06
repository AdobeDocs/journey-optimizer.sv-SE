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
source-git-commit: 670503f9aedcd3008b3cd63c0ec6e59fac3dc31a
workflow-type: tm+mt
source-wordcount: '2328'
ht-degree: 0%

---

# Testa, validera och godkänn{#section-overview}

I det här avsnittet beskrivs alla testnings- och godkännandefunktioner i Journey Optimizer. Du hittar verktyg för att förhandsgranska innehåll med testprofiler, validera reselogik, kontrollera e-poståtergivning och skräppostpoäng, köra A/B-experiment, identifiera konflikter och konfigurera arbetsflöden för godkännande.

Denna landningssida hjälper er att välja rätt testmetod baserat på vad ni bygger (kampanjer kontra resor), leder er genom rekommenderade testarbetsflöden och ger snabb tillgång till alla testnings- och godkännanderesurser. Börja med [Välj din testmetod](#choose-your-testing-approach) nedan för att identifiera vilka verktyg som gäller för ditt användningsfall. Definitioner av nyckeltesttermer finns i [Nyckelterminologi](#key-terminology).

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

<!--
## Decision tree for testing method selection

Use this decision tree to quickly identify the right testing tools for your specific scenario. Answer each question based on your context (what you're building, what you need to validate, and which channel you're using) to navigate directly to the relevant capabilities and documentation.

+++ **Question 1: What are you testing?**

* Campaign → [Choose your testing approach](#choose-your-testing-approach)
* Journey → [Choose your testing approach](#choose-your-testing-approach)
* Personalization expressions → [Personalization playground](#test--approve-content)
+++

+++**Question 2: What aspect needs validation?**

* Content and personalization → [Test profiles](#choose-your-testing-approach) or [sample input data](#choose-your-testing-approach)
* Email display → [Email rendering tests](#2-technical-validation)
* Deliverability → [Spam score checks](#2-technical-validation)
* Journey logic and flow → [Test mode](#choose-your-testing-approach) or [dry run](#test--approve-content)
* Performance comparison → [Content experiment](#test--approve-content) (campaigns only)
* Timing conflicts → [Conflict detection](#test--approve-content)
* Stakeholder review → [Approval workflow](#test--approve-content)
+++

+++**Question 3: What channel?**

* Email → All testing methods available (see [Choose your testing approach](#choose-your-testing-approach))
* SMS, Push → [Content testing](#choose-your-testing-approach), [sample input data](#choose-your-testing-approach), [approval workflows](#test--approve-content)
* Web, In-app, Code-based → [Content testing](#choose-your-testing-approach), [sample input data](#choose-your-testing-approach), [approval workflows](#test--approve-content)
* Multiple channels → Test each channel separately
+++

+++**Question 4: When in the workflow?**

* Before building → [Personalization playground](#test--approve-content) for learning
* During building → [Test profiles](#choose-your-testing-approach) and [sample input data](#choose-your-testing-approach) for validation
* Before launch → [Rendering tests](#2-technical-validation), [spam checks](#2-technical-validation), [conflict detection](#test--approve-content), [approvals](#test--approve-content)
* After launch → [Live reports](../using/building-journeys/report-journey.md) and [monitoring](#test--approve-content)
+++

-->

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

* Använd [API:t för kampanjsimulering](https://developer.adobe.com/journey-optimizer-apis/references/simulations/){target-&quot;_blank&quot;} för att starta korrekturjobb programmatiskt

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

Följ den här 4-stegsmetoden för att validera era kampanjer och resor före lansering:

| Fas | Testa | Viktiga åtgärder |
|-------|-------------|-------------|
| **1. Innehållsvalidering** | Personalization, design, rendering | [Förhandsgranska med testprofiler](../using/content-management/preview-test.md), testa [flera varianter](../using/test-approve/simulate-sample-input.md) med CSV/JSON, verifiera [återgivning](../using/content-management/rendering.md) på olika enheter |
| **2. Tekniska kontroller** | Leverans, länkar, konflikter | Kör [skräppostpoängkontroller](../using/content-management/spam-report.md), validera länkar, kontrollera om det finns [konflikter](../using/conflict-prioritization/conflicts.md) med andra kampanjer |
| **3. Reselogik** (endast resor) | Ingångsvillkor, flöde, förgrening | Använd [testläge](../using/building-journeys/testing-the-journey.md) för att simulera förloppet, kör [torr körning](../using/building-journeys/journey-dry-run.md) för komplexa banor |
| **4. Förstart** | Inställningar, godkännanden, övervakning | Skicka för [godkännande](../using/test-approve/gs-approval.md), verifiera scheman och målgrupper, aktivera [aviseringar](../using/reports/alerts.md) |

**Pro-tips:** Börja med [personaliseringsuppspelningen](../using/personalization/personalize.md#playground) om du vill testa uttryck innan du skapar innehåll, och kontrollera alltid [konfliktidentifiering](../using/conflict-prioritization/conflicts.md) innan du startar programmet för att förhindra överskjutande meddelanden.

## Testning in action: Användningsexempel

Se hur testkoncept kan användas i verkliga scenarier:

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="../using/building-journeys/journeys-uc.md">
<img alt="Skicka flerkanalsmeddelanden" src="../using/assets/do-not-localize/start-journey.jpeg">
</a>
<div>
<a href="../using/building-journeys/journeys-uc.md"><strong>Skicka flerkanalsmeddelanden</strong></a>
</div>
<p>
Testa en resa som kombinerar Läs publik, Reaktionshändelser och e-post/push-meddelanden. Validera hela flödet från målgruppsanpassning till meddelandeleverans. Fokusera på flerkanalskoordinering, reaktionshändelser, komplett flödesvalidering och test-/publiceringssteg.
</p>
</td>
<td>
<a href="../using/building-journeys/message-to-subscribers-uc.md">
<img alt="Skicka ett meddelande till prenumeranter" src="../using/assets/do-not-localize/start-quick.png">
</a>
<div>
<a href="../using/building-journeys/message-to-subscribers-uc.md"><strong>Skicka ett meddelande till prenumeranter</strong></a>
</div>
<p>
Testa resor som avser prenumerationslistor med dynamisk e-postadress. Validera personaliseringsuttryck för korrekt målinriktning av prenumeranter. Fokusera på personaliseringsuttryck, dynamisk adressering och målinriktning på prenumerationslistor.
</p>
</td>
<td>
<a href="../using/building-journeys/weekday-email-uc.md">
<img alt="Skicka tidsbundna meddelanden" src="../using/assets/do-not-localize/icon-first-journey.svg">
</a>
<div>
<a href="../using/building-journeys/weekday-email-uc.md"><strong>Skicka tidsbundna meddelanden</strong></a>
</div>
<p>
Testa resor med tidsbaserade villkor för att säkerställa att meddelanden skickas på specifika dagar. Validera vänteaktiviteter och schemaläggningslogik. Fokusera på tidsbaserade villkor, vänteaktiviteter och tidsplaneringsvalidering.
</p>
</td>
</tr></table>

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="../using/building-journeys/jo-use-cases.md">
<img alt="Utforska fler användningsexempel för resor" src="../using/assets/do-not-localize/icon-quick-start.svg">
</a>
<div>
<a href="../using/building-journeys/jo-use-cases.md"><strong>Utforska fler användningsexempel för resor</strong></a>
</div>
<p>
Få tillgång till en omfattande samling praktiska exempel som omfattar upplevelsehändelser, flerkanalsmeddelanden och externa systemintegreringar. Utforska olika scenarier, avancerade mönster och integrationstestningsmetoder.
</p>
</td>
</tr></table>

## Nyckelterminologi

Bekanta dig med dessa viktiga testkoncept för att bättre förstå Journey Optimizer testnings- och godkännandefunktioner. Varje term länkar till detaljerad dokumentation.

**[Testa profiler](../using/content-management/test-profiles.md)** - Syntetiska kundprofiler (inte verkliga kunder) som används för att förhandsgranska personaliserat innehåll. Flaggas i Kundprofiltjänst i realtid. Krävs för testläge och förhandsgranskning av innehåll. [Lär dig skapa testprofiler](../using/audience/creating-test-profiles.md)

**[Testläge](../using/building-journeys/testing-the-journey.md)** - Resesimuleringsfunktion som skickar testprofiler via resebanor. Begränsningar: Endast utkast, endast namnutrymme, endast testprofiler krävs. [Se testlägesdokumentation](../using/building-journeys/testing-the-journey.md)

**[Torr körning](../using/building-journeys/journey-dry-run.md)** - Resekörningsanalysverktyg som spårar sökvägar utan att skicka meddelanden eller göra API-anrop. Användningsfall: Validera logiken utan att behöva använda resurser. [Lär dig mer om torr körning](../using/building-journeys/journey-dry-run.md)

**[Exempelindata](../using/test-approve/simulate-sample-input.md)** - CSV- eller JSON-filer som innehåller profilattributvärden för testning av personalisering. Stöder upp till 30 varianter. Alternativ för att skapa testprofiler. [Så här simulerar du innehållsvariationer](../using/test-approve/simulate-sample-input.md)

**[Startlistor](../using/configuration/seed-lists.md)** - E-postadresser till interna intressenter inkluderas automatiskt i faktiska leveranser (inte testmeddelanden). Endast e-postkanal. Användningsfall: Kvalitetsövervakning och efterlevnad. [Konfigurera dirigerade listor](../using/configuration/seed-lists.md)

**[Innehållsexperiment](../using/content-management/get-started-experiment.md)** - A/B-testning eller multiväpnade bandit-experiment där innehållsvariationer jämförs. Endast kampanjer, inte tillgängliga under resor. [Kom igång med experiment](../using/content-management/get-started-experiment.md) | [Skapa experiment &#x200B;](../using/content-management/content-experiment.md)

**[Korrektur](../using/content-management/proofs.md)** - Testa e-postleveranser som skickas till specifika e-postadresser med hjälp av testprofildata. Olika utsädeslistor (korrektur är manuella testutskick, utsädeslistor är automatiska kopior av intressenter). [Skicka korrektur](../using/content-management/proofs.md)

**[Konfliktidentifiering](../using/conflict-prioritization/conflicts.md)** - Verktyg som identifierar överlappande kampanjer och resor som riktar sig till samma målgrupper. Begränsat stöd för resor: endast typerna enhet, målgruppskvalitet och läsning av målgrupper. [Läs om konflikthantering](../using/conflict-prioritization/gs-conflict-prioritization.md)

**[Arbetsflöden för godkännande](../using/test-approve/gs-approval.md)** - Granskningsprocess i flera steg som kräver godkännande av berörda parter före aktivering. Kräver konfiguration av godkännandeprincip. [Konfigurera godkännanden](../using/test-approve/gs-approval.md) | [Skapa profiler](../using/test-approve/approval-policies.md)

**[Återgivningstest](../using/content-management/rendering.md)** - E-postvisningsvalidering för e-postklienter (Gmail, Outlook, Apple Mail) och enheter. Kräver integrering med Litmus. [Testa e-poståtergivning](../using/content-management/rendering.md)

**[Personalization playground](../using/personalization/personalize.md#playground)** - Interaktiv utbildningsmiljö för att experimentera med personaliseringssyntax och testa uttryck med exempeldata. Inga livedatauppsättningar krävs. [Åtkomst till uppspelningsmiljön](../using/personalization/personalize.md#playground)

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

* Testning + Godkännandearbetsflöden - Kvalitetssäkringsprocess
* Testning + konfliktidentifiering - Förhindra att kunderna överskickar meddelanden
* Testning + Innehållsexperiment - Prestandaoptimering
* Testning + rapportering - kontinuerlig förbättringscykel
* Testprofiler + Personalization - validering av innehåll
* Torr körning + testläge - Omfattande validering av resan

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
**Alternativ:** Skapa 3-5 representativa [testprofiler &#x200B;](../using/audience/creating-test-profiles.md) som täcker nyckelsegment
**Utbildningsverktyg:** Experimentera först i [personaliseringspresentationen](../using/personalization/personalize.md#playground)

+++

+++**F: Vad är skillnaden mellan testläge och körning i torr riktning?**

**Testläge:** Skickar testprofiler genom resan, utlöser faktiska åtgärder och genererar testmeddelanden. Kräver utkast + namnutrymme.
**Torr körning:** Spårar körningssökvägar utan att skicka något. Fungerar på alla resestatus. Inga meddelanden har skickats, inga åtgärder har utförts.
**Använd tillsammans:** Testläge för meddelandetestning + Torr körning för logikvalidering - omfattande täckning.

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

**Alternativ 1:** Använd [API för kampanjsimulering](https://developer.adobe.com/journey-optimizer-apis/references/simulations/){target-&quot;_blank&quot;} för programmatisk testning
**Alternativ 2:** Förhandsgranska innehåll med testprofiler i användargränssnittet
**Alternativ 3:** Skicka korrektur för att testa e-postadresser
**Bästa praxis:** Kombinera alla tre för fullständig validering

+++

>[!ENDTABS]
