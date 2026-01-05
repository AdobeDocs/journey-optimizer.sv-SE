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
source-git-commit: 57f32088aa9cef55ed68729995326d3eae401bd5
workflow-type: tm+mt
source-wordcount: '3103'
ht-degree: 0%

---

# Testa, validera och godkänn{#section-overview}

I det här avsnittet beskrivs alla testnings- och godkännandefunktioner i Journey Optimizer. Du hittar verktyg för att förhandsgranska innehåll med testprofiler, validera reselogik, kontrollera e-poståtergivning och skräppostpoäng, köra A/B-experiment, identifiera konflikter och konfigurera arbetsflöden för godkännande.

Denna landningssida hjälper er att välja rätt testmetod baserat på vad ni bygger (kampanjer kontra resor), leder er genom rekommenderade testarbetsflöden och ger snabb tillgång till alla testnings- och godkännanderesurser. Börja med [Välj din testmetod](#choose-your-testing-approach) nedan för att identifiera vilka verktyg som gäller för ditt användningsfall.

## Översikt över testfunktioner

**Testtyper finns:**

* Innehållstestning: Förhandsgranska och validera meddelandeinnehåll innan du skickar → [Testa kampanjer](#testing-campaigns), [Testa personalisering](#testing-personalization)
* Reselogiktestning: Simulera kundens utveckling genom resan → [Testa resorna](#testing-journeys)
* Teknisk testning: Verifiera återgivning, leverans och autentisering → [Teknisk validering](#2-technical-validation)
* Prestandatestning: Jämför innehållsvariationer med A/B-experiment → [Innehållsexperiment](#content-experiments--ab-testing)
* Konflikttestning: Identifiera kampanjer och resor överlappar → [Konfliktidentifiering](#conflict-detection)
* Godkännandeprovning: Strukturerade granskningsarbetsflöden före aktivering → [Arbetsflöden för godkännande](#approval-workflows-for-journeys-and-campaigns)

**Nyckelfunktioner efter kontext:**

| Funktion | Gäller för | Kanalbegränsningar | Förhandskrav | Primärt syfte | Dokumentation |
|------------|-----------|---------------------|--------------|-----------------|---------------|
| [Testprofiler](../using/content-management/test-profiles.md) | Kampanjer, resor | Alla kanaler | Testprofiler har skapats | Förhandsgranska personaliserat innehåll | [Guide](#testing-campaigns) |
| [Exempelindata](../test-approve/simulate-sample-input.md) | Kampanjer, resor | E-post, SMS, push, webb, kodbaserad, i appen, innehållskort | CSV/JSON-fil | Testa flera personaliseringsvarianter | [Guide](#simulate-content-variations) |
| [Testläge](../using/building-journeys/testing-the-journey.md) | Endast resor | N/A | Utkastresa, namnområde konfigurerat | Simulera profilförlopp | [Kort](#test-your-journey) |
| [Torr körning](../using/building-journeys/journey-dry-run.md) | Endast resor | N/A | Resan skapad | Analysera körningssökvägar | [Kort](#journey-dry-run) |
| [E-poståtergivning](../using/content-management/rendering.md) | Kampanjer, resor | Endast e-post | Litmus-integrering | Verifiera visning mellan klienter | [Arbetsflöde](#2-technical-validation) |
| [Spam score](../using/content-management/spam-report.md) | Kampanjer, resor | Endast e-post | Ingen | Validering av slutprodukt | [Arbetsflöde](#2-technical-validation) |
| [Startlistor](../using/configuration/seed-lists.md) | Kampanjer, resor | Endast e-post | Startlista konfigurerad | Intressentövervakning | [Kort](#seed-lists-for-stakeholder-monitoring) |
| [Innehållsexperiment](../using/content-management/get-started-experiment.md) | Endast kampanjer | Alla kanaler | Ingen | A/B-tester och multiväpnad bankutprövning | [Kort](#content-experiments--ab-testing) |
| [Konfliktidentifiering](../using/conflict-prioritization/conflicts.md) | Kampanjer, resor (begränsat) | Alla kanaler | Ingen | Förhindra att kundens meddelanden blir för många | [Kort](#conflict-detection) |
| [Arbetsflöden för godkännande](../using/test-approve/gs-approval.md) | Kampanjer, resor | Alla kanaler | Godkännandeprincip har skapats | Strukturerad granskningsprocess | [Kort](#approval-workflows-for-journeys-and-campaigns) |
| [Personalization playground](../using/personalization/personalize.md#playground) | Alla | Alla kanaler | Ingen | Lär dig mer om och testa personaliseringssyntax | [Kort](#personalization-playground) |

**Vanliga arbetsflöden för testning:**

1. Förutveckling: Använd [personaliseringsuppspelning](#testing-personalization) för att lära dig syntax
2. Under utvecklingen: Förhandsgranska med [testprofiler](#testing-campaigns), validera med [exempelindata](#simulate-content-variations)
3. Förstart: Kör [tekniska tester](#2-technical-validation) (återgivning, skräppost), kontrollera [konflikter](#conflict-detection), skicka för [godkännande](#approval-workflows-for-journeys-and-campaigns)
4. Efter start: Övervaka med live-rapporter (se [Övervakning och felsökning](#monitoring--troubleshooting)), iterera baserat på resultat


## Varför det är viktigt att testa och godkänna

Testnings- och godkännandeprocesserna fungerar som viktiga kvalitetsgater som skyddar ert varumärke och säkerställer kampanjframgångar. Här är varför de betyder något:

* **Hitta fel innan de når kunder** - Identifiera brutna länkar, felaktig personalisering, återgivningsproblem och logiska fel i en kontrollerad miljö där korrigeringarna är snabba och riskfria.

* **Förbättra leveransen** - Testa skräppostpoängen, validera e-postautentiseringen och kontrollera återgivningen mellan e-postklienter för att maximera placeringen av inkorgen och engagemangsfrekvensen.

* **Säkerställ varumärkets enhetlighet** - Förhandsgranska innehåll med olika testprofiler för att verifiera att personaliseringen visas korrekt för olika kundsegment och upprätthåller varumärkesstandarder.

* **Validera komplexa resor** - Simulera flerstegsflöden för att bekräfta att utlösarna fungerar korrekt, villkoren utvärderas korrekt och att kunderna får rätt meddelanden vid rätt tidpunkt.

* **Upprätta ansvarsskyldighet** - Implementera formella godkännandearbetsflöden som kräver att intressenter godkänner avtalet, skapa tydligt ägarskap och minska oauktoriserade eller förtidiga kampanjstarter.

* **Spara tid och resurser** - Hitta problem tidigt i utvecklingscykeln när korrigeringarna är billigare och snabbare och förhindra kostsamma efterstartsändringar eller kundtjänsteskaleringar.

## Nyckelterminologi

**[Testa profiler](../using/content-management/test-profiles.md)** = Syntetiska kundprofiler (inte verkliga kunder) som används för att förhandsgranska personaliserat innehåll. Flaggas i Kundprofiltjänst i realtid. Krävs för testläge och förhandsgranskning av innehåll. [Lär dig skapa testprofiler](../using/audience/creating-test-profiles.md)

**[Testläge](../using/building-journeys/testing-the-journey.md)** = Funktion för resesimulering som skickar testprofiler via resebanor. Begränsningar: Endast utkast, endast namnutrymme, endast testprofiler krävs. [Se testlägesdokumentation](../using/building-journeys/testing-the-journey.md)

**[Torr körning](../using/building-journeys/journey-dry-run.md)** = Resekörningsanalysverktyg som spårar sökvägar utan att skicka meddelanden eller anropa API. Användningsfall: Validera logiken utan att behöva använda resurser. [Lär dig mer om torr körning](../using/building-journeys/journey-dry-run.md)

**[Exempelindata](../test-approve/simulate-sample-input.md)** = CSV- eller JSON-filer som innehåller profilattributvärden för testning av personalisering. Stöder upp till 30 varianter. Alternativ för att skapa testprofiler. [Så här simulerar du innehållsvariationer](../test-approve/simulate-sample-input.md)

**[Utsändningslistor](../using/configuration/seed-lists.md)** = E-postadresser till interna intressenter som automatiskt inkluderas i faktiska leveranser (inte testmeddelanden). Endast e-postkanal. Användningsfall: Kvalitetsövervakning och efterlevnad. [Konfigurera dirigerade listor](../using/configuration/seed-lists.md)

**[Innehållsexperiment](../using/content-management/get-started-experiment.md)** = A/B-testning eller multiväpnade bandit-experiment där innehållsvariationer jämförs. Endast kampanjer, inte tillgängliga under resor. [Kom igång med experiment](../using/content-management/get-started-experiment.md) | [Skapa experiment ](../using/content-management/content-experiment.md)

**[Korrektur](../using/content-management/proofs.md)** = Testa e-postleveranser som skickas till specifika e-postadresser med hjälp av testprofildata. Olika utsädeslistor (korrektur är manuella testutskick, utsädeslistor är automatiska kopior av intressenter). [Skicka korrektur](../using/content-management/proofs.md)

**[Konfliktidentifiering](../using/conflict-prioritization/conflicts.md)** = Verktyg som identifierar överlappande kampanjer och resor som riktar sig till samma målgrupper. Begränsat stöd för resor: endast typerna enhet, målgruppskvalitet och läsning av målgrupper. [Läs om konflikthantering](../using/conflict-prioritization/gs-conflict-prioritization.md)

**[Arbetsflöden för godkännande](../using/test-approve/gs-approval.md)** = Granskningsprocess i flera steg som kräver godkännande av berörda parter före aktivering. Kräver konfiguration av godkännandeprincip. [Konfigurera godkännanden](../using/test-approve/gs-approval.md) | [Skapa profiler](../using/test-approve/approval-policies.md)

**[Återgivningstester](../using/content-management/rendering.md)** = Verifiering av e-postvisning för e-postklienter (Gmail, Outlook, Apple Mail) och enheter. Kräver integrering med Litmus. [Testa e-poståtergivning](../using/content-management/rendering.md)

**[Personalization playground](../using/personalization/personalize.md#playground)** = Interaktiv utbildningsmiljö för att experimentera med personaliseringssyntax och testa uttryck med exempeldata. Inga livedatauppsättningar krävs. [Åtkomst till uppspelningsmiljön](../using/personalization/personalize.md#playground)

## Beslutsträd för val av testmetod

Använd det här beslutsträdet för att snabbt identifiera rätt testverktyg för ditt specifika scenario. Svara på varje fråga baserat på ditt sammanhang (vad du bygger, vad du behöver validera och vilken kanal du använder) för att navigera direkt till relevanta funktioner och dokumentation.

+++ **Fråga 1: Vad testar du?**

* Kampanj → [Testar kampanjer](#testing-campaigns)
* Resa → [Testar resor](#testing-journeys)
* Personalization-uttryck → [Personalization playground](#testing-personalization)
+++

+++**Fråga 2: Vilken aspekt behöver valideras?**

* Innehåll och personalisering → [Testa profiler](#testing-campaigns) eller [exempelindata](#simulate-content-variations)
* E-postvisning → [Återgivningstest via e-post](#2-technical-validation)
* Leverans → [Spam score check](#2-technical-validation)
* Reselogik och -flöde → [Testläge](#testing-journeys) eller [torr körning](#journey-dry-run)
* Prestandajämförelse → [Innehållsexperiment](#content-experiments--ab-testing) (endast kampanjer)
* Tidskonflikter → [Konfliktidentifiering](#conflict-detection)
* Granskning av intressenter → [Arbetsflöde för godkännande](#approval-workflows-for-journeys-and-campaigns)
+++

+++**Fråga 3: Vilken kanal?**

* E-post → Alla testmetoder är tillgängliga (se [Testa kampanjer](#testing-campaigns))
* SMS, push → [Innehållstestning](#testing-campaigns), [exempelindata](#simulate-content-variations), [arbetsflöden för godkännande](#approval-workflows-for-journeys-and-campaigns)
* Webb, In-app, kodbaserad → [Innehållstestning](#testing-campaigns), [exempelindata](#simulate-content-variations), [arbetsflöden för godkännande](#approval-workflows-for-journeys-and-campaigns)
* Flera kanaler → Testa varje kanal separat
+++

+++**Fråga 4: När i arbetsflödet?**

* Innan du skapar → [Personalization playground](#personalization-playground) för lärande
* Under generering → [Testprofiler](#testing-campaigns) och [exempelindata](#simulate-content-variations) för validering
* Innan du startar → [Återgivningstester](#2-technical-validation), [skräppostkontroller](#email-spam-report), [konfliktidentifiering](#conflict-detection), [godkännanden](#approval-workflows-for-journeys-and-campaigns)
* Efter start → [Live-rapporter](../using/building-journeys/report-journey.md) och [övervakning](#monitoring--troubleshooting)
+++


## Välj testmetod

Rätt testmetod beror på vad du bygger och vad du behöver för att validera. Använd den här vägledningen när du vill identifiera de mest relevanta testverktygen för ditt scenario.

### Testa kampanjer

**För alla kampanjer:**

* Förhandsgranska och testa innehåll med [testprofiler](../using/content-management/test-profiles.md) eller [exempelindata](../test-approve/simulate-sample-input.md)
* Kontrollera [e-poståtergivning](../using/content-management/rendering.md) på enheter och klienter (endast e-postkanal)
* Kör [skräppostpoängskontroller](../using/content-management/spam-report.md) (endast e-postkanal)
* Granska [konflikter](../using/conflict-prioritization/conflicts.md) med andra kampanjer och resor
* Konfigurera [dirigerade listor](../using/configuration/seed-lists.md) för övervakning av intressenter (endast e-postkanal)
* Skicka för [godkännande](../using/test-approve/gs-approval.md) före aktivering

**För A/B-testning och optimering:**

* Skapa [innehållsexperiment](../using/content-management/get-started-experiment.md) för att testa flera behandlingar och mäta prestanda

**För API-utlösta kampanjer:**

* Använd [API:t för kampanjsimulering](https://developer.adobe.com/journey-optimizer-apis/references/simulations/){target="_blank"} om du vill utlösa korrekturjobb programmatiskt

### Testa resor

**För alla resor:**

* Använd [testläge](../using/building-journeys/testing-the-journey.md) för att simulera profilens förlopp (endast utkastresor, kräver namnutrymme) eller [torr körning](../using/building-journeys/journey-dry-run.md) för att analysera körningssökvägar utan att skicka meddelanden
* Testa enskilda meddelanden med [förhandsgranskning och korrektur](../using/content-management/preview-test.md)
* Kontrollera [konflikter](../using/conflict-prioritization/conflicts.md) med andra resor och kampanjer
* Skicka för [godkännande](../using/test-approve/gs-approval.md) före publicering

**För komplexa resor:**

* Använd testläget och kör torrt tillsammans för att noggrant validera förgreningslogik och körningsvägar
* Testa olika anmälningsvillkor och profilattribut systematiskt

**Obs!** Konfliktidentifiering och resefästning är endast tillgängliga för resor med enhetsbehörighet, målgruppskvalifikation och läsning av målgrupper.

### Testa personalisering

**Innan du skapar innehåll:**

* Experimentera i [personaliseringsuppspelningen](../using/personalization/personalize.md#playground) för att lära dig syntax och testa uttryck med exempeldata

**När innehåll skapas:**

* Förhandsgranska med [testprofiler](../using/content-management/test-profiles.md) för att validera återgivningar av personalisering korrekt
* Testa flera scenarier med [exempelindata](../test-approve/simulate-sample-input.md) från CSV-/JSON-filer (stöder upp till 30 varianter)

## Testa bästa praxis

Följ de här rekommenderade arbetssätten för att maximera effekten av testningen:

1. **Testa tidigt och ofta** - Vänta inte tills en kampanj har skapats helt. Testa innehåll, personalisering och logik stegvis när ni utvecklar.

1. **Använd realistiska testprofiler** - [Skapa testprofiler](../using/audience/creating-test-profiles.md) som exakt motsvarar målgruppssegmenten, inklusive kantfall och olika personaliseringsscenarier.

1. **Testa mellan enheter och klienter** - Verifiera [e-poståtergivning](../using/content-management/rendering.md) på vanliga e-postklienter (Gmail, Outlook, Apple Mail) och enheter (skrivbord, mobil, surfplatta) för att se till att visningen är konsekvent (endast e-postkanal).

1. **Verifiera personalisering noggrant** - Testa med flera [testprofiler](../using/content-management/test-profiles.md) som har olika attributvärden för att bekräfta att personaliseringstoken återges korrekt och reservvärden fungerar. Använd [personaliseringsspelgrunden](../using/personalization/personalize.md#playground) om du vill experimentera med personaliseringsuttryck och testa kod med exempeldata innan du använder dem på dina kampanjer.

1. **Testa innehållsvariationer med exempeldata** - Använd [exempelindata](../test-approve/simulate-sample-input.md) från CSV- eller JSON-filer för att testa upp till 30 personaliseringsscenarier utan att skapa flera testprofiler, spara tid samtidigt som du får en heltäckande täckning. Stöder e-post, SMS, push, webb, kodbaserad upplevelse, kanaler i appen och innehållskort.

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

* Testa flera variationer med **[exempelindata](../test-approve/simulate-sample-input.md)** från CSV-/JSON-filer för att validera personalisering i olika profilscenarier

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

### Grundläggande riktlinjer för testning och validering

* [Simulera innehållsvariationer](../test-approve/simulate-sample-input.md) - Testa upp till 30 personaliseringsscenarier med CSV- eller JSON-filer. Perfekt för testning av flerspråkigt innehåll utan att behöva skapa flera testprofiler. Har stöd för e-post, SMS, push, webb, kodbaserade kort, kort i appen och innehållskort.

* [Skapa testprofiler](../using/audience/creating-test-profiles.md) - Skapa och hantera testprofiler för att simulera kundscenarier. Lär dig hur du flaggar profiler för testning, anger attribut och organiserar testsegment.

* [Rapport om skräppost](../using/content-management/spam-report.md) - Kontrollera skräppostresultat innan du skickar iväg för att förbättra leveransen och placeringen av inkorgen. Få användbara rekommendationer för innehållsoptimering.

* [Vanliga frågor och svar om resan](../using/building-journeys/journey-faq.md) - Snabbreferens för vanliga frågor om resetestning, körning och felsökning.

### Beroenden och relationer

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

### Vanliga frågor

+++**F: Vilken testning krävs innan en kampanj startas?**

**Minimum:** Förhandsgranska innehåll med testprofiler + kontroll av skräppostpoäng (e-post)
**Rekommenderas:** + Återgivning via e-post + Konfliktidentifiering + arbetsflöde för godkännande
**Bästa praxis:** + Datatestning med provindata + Seed-listor + A/B-experiment (vid optimering)

+++

+++**F: Hur testar jag personalisering utan att skapa många testprofiler?**

**Primär lösning:** Använd [exempelindata](../test-approve/simulate-sample-input.md) med CSV/JSON-filer (stöder upp till 30 varianter)
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


### Relaterade ämnen

* [Innehållshantering](content-management-landing-page.md) - Lär dig hur du utformar, förhandsgranskar och hanterar innehåll med hjälp av mallar, fragment och e-post-Designer. Bästa tillvägagångssätt för att skapa enhetligt innehåll.

* [Rapportering och analys](reporting-landing-page.md) - Analysera kampanjer och kundresan med omfattande rapporter, instrumentpaneler och mätvärden. Fatta databaserade beslut för att optimera kundupplevelserna.

* [Resekonfiguration](configure-journeys-landing-page.md) - Konfigurera datakällor, händelser och anpassade åtgärder för att aktivera sofistikerad resesamordning. Skapa en teknisk grund för att skapa en resa.

* [Kampanjhantering](../using/campaigns/get-started-with-campaigns.md) - Utforska olika kampanjtyper och lär dig hur du skapar, schemalägger och optimerar batch- och realtidskampanjer för maximal effekt.
