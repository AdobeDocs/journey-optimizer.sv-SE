---
solution: Journey Optimizer
product: Journey Optimizer
title: Testa och godkänn
description: Testa och godkänn
redpen-status: CREATED_||_2025-08-11_20-30-59
exl-id: a770412f-2f80-459d-8cce-32212154d154
source-git-commit: dd3d91266c0edea562f75ceb1f75974c7242ee1a
workflow-type: tm+mt
source-wordcount: '1296'
ht-degree: 0%

---

# Testa och godkänn{#section-overview}

Kvalitetssäkring är avgörande för att kunna leverera enastående kundupplevelser. Adobe Journey Optimizer erbjuder omfattande testnings- och godkännandefunktioner som hjälper er att validera innehållet, verifiera kundens logik och säkerställa att kampanjerna uppfyller kvalitetsstandarderna innan ni når ut till er målgrupp. Med dessa verktyg kan ni identifiera och lösa problem tidigt, minska riskerna och upprätthålla varumärkets integritet - från förhandsgranskning av personaliserade meddelanden med testprofiler till simulering av komplexa kundfärdsflöden. Vare sig du testar e-poståtergivning på olika enheter, validerar flerstegsresor eller etablerar formella arbetsflöden för godkännande vägleder det här avsnittet dig genom bästa praxis och steg-för-steg-processer för att bygga upp förtroendet för kampanjer och resor. Genom att implementera grundliga tester och strukturerade godkännanden minimerar ni antalet fel, förbättrar leveransmöjligheterna och skapar smidiga upplevelser som får genklang hos era kunder.

## Varför det är viktigt att testa och godkänna

Testnings- och godkännandeprocesserna fungerar som viktiga kvalitetsgater som skyddar ert varumärke och säkerställer kampanjframgångar. Här är varför de betyder något:

* **Hitta fel innan de når kunder** - Identifiera brutna länkar, felaktig personalisering, återgivningsproblem och logiska fel i en kontrollerad miljö där korrigeringarna är snabba och riskfria.

* **Förbättra leveransen** - Testa skräppostpoängen, validera e-postautentiseringen och kontrollera återgivningen mellan e-postklienter för att maximera placeringen av inkorgen och engagemangsfrekvensen.

* **Säkerställ varumärkets enhetlighet** - Förhandsgranska innehåll med olika testprofiler för att verifiera att personaliseringen visas korrekt för olika kundsegment och upprätthåller varumärkesstandarder.

* **Validera komplexa resor** - Simulera flerstegsflöden för att bekräfta att utlösarna fungerar korrekt, villkoren utvärderas korrekt och att kunderna får rätt meddelanden vid rätt tidpunkt.

* **Upprätta ansvarsskyldighet** - Implementera formella godkännandearbetsflöden som kräver att intressenter godkänner avtalet, skapa tydligt ägarskap och minska oauktoriserade eller förtidiga kampanjstarter.

* **Spara tid och resurser** - Hitta problem tidigt i utvecklingscykeln när korrigeringarna är billigare och snabbare och förhindra kostsamma efterstartsändringar eller kundtjänsteskaleringar.

## Testa bästa praxis

Följ de här rekommenderade arbetssätten för att maximera effekten av testningen:

1. **Testa tidigt och ofta** - Vänta inte tills en kampanj har skapats helt. Testa innehåll, personalisering och logik stegvis när ni utvecklar.

1. **Använd realistiska testprofiler** - [Skapa testprofiler](../using/audience/creating-test-profiles.md) som exakt motsvarar målgruppssegmenten, inklusive kantfall och olika personaliseringsscenarier.

1. **Testa olika enheter och klienter** - Verifiera [e-poståtergivning](../using/content-management/rendering.md) på vanliga e-postklienter (Gmail, Outlook, Apple Mail) och enheter (skrivbord, mobil, surfplatta) för att se till att visningen blir konsekvent.

1. **Verifiera personalisering noggrant** - Testa med flera [testprofiler](../using/content-management/test-profiles.md) som har olika attributvärden för att bekräfta att personaliseringstoken återges korrekt och reservvärden fungerar.

1. **Simulera resesökvägar** - För komplexa resor med flera förgreningar använder du [testläge](../using/building-journeys/testing-the-journey.md) för att testa olika postvillkor och profilattribut för att validera alla möjliga sökvägar.

1. **Kontrollera leveransindikatorer** - Granska [skräppostpoäng](../using/content-management/spam-report.md), autentiseringsstatus och hälsomått för e-post innan stora sändningar skickas.

1. **Dokumenttestresultat** - Registrera testresultat, problem och lösningar som kan förbättra framtida testprocesser och dela inlärningar med ditt team.

1. **Involvera intressenter tidigt** - Dela förhandsgranskningar och testresultat med intressenter före [formellt godkännande](../using/test-approve/gs-approval.md) för att samla in feedback och anpassa förväntningarna.

## Rekommenderat testarbetsflöde

Följ detta systematiska tillvägagångssätt för att säkerställa grundlig testning och smidiga godkännanden:

### &#x200B;1. Innehållsutveckling och förhandsgranskning

Börja med att skapa ditt innehåll och använda förhandsgranskningsfunktionerna för att verifiera den ursprungliga designen och personaliseringen:

* Utforma ditt [e-postmeddelande](../using/email/create-email.md), [SMS](../using/sms/create-sms.md), [push-meddelande](../using/push/create-push.md) eller annat kanalinnehåll
* Använd funktionen **[Simulera innehåll](../using/content-management/preview-test.md)** för att förhandsgranska med testprofiler
* Kontrollera [personaliseringstoken](../using/personalization/personalization-syntax.md), dynamiskt innehåll och reservvärden
* Verifiera [återgivning](../using/content-management/rendering.md) för olika skärmstorlekar och e-postklienter

### &#x200B;2. Teknisk validering

Validera tekniska aspekter som påverkar leveransen och funktionaliteten:

* Kör [skräppostpoängkontroller](../using/content-management/spam-report.md) för att identifiera potentiella leveransproblem
* Testa länkar för att säkerställa att de inte bryts och spåras korrekt
* Verifiera konfigurationen för [e-postautentisering](../using/configuration/dmarc-record.md) (SPF, DKIM, DMARC)
* Granska HTML-rendering och sök efter CSS-kompatibilitetsproblem
* Testa [responsiv design](../using/email/content-from-scratch.md) på mobila och stationära enheter

### &#x200B;3. Resetester

Validera orkestreringslogiken för resor:

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
* Var redo att [pausa eller ändra &#x200B;](../using/building-journeys/journey-pause.md) resor om allvarliga problem uppstår
* Dokumentlärdomar som kan förbättra framtida testprocesser

## Testning in action: Användningsexempel

Se hur testkoncept kan användas i verkliga scenarier:

* **[Skicka flerkanalsmeddelanden](../using/building-journeys/journeys-uc.md)** - Det här användningsexemplet visar hur du testar en resa som kombinerar Läs publik, Reaktionshändelser och e-post/push-meddelanden. Lär dig validera hela flödet från målgruppsanpassning till meddelandeleverans och se hur testning och publicering fungerar i praktiken.

* **[Skicka ett meddelande till prenumeranter](../using/building-journeys/message-to-subscribers-uc.md)** - Upptäck hur du testar resor som är avsedda för prenumerationslistor med dynamisk e-postadress. I det här exemplet visas hur du validerar personaliseringsuttryck och ser till att meddelandena når rätt prenumeranter.

* **[Skicka tidsbundna meddelanden](../using/building-journeys/weekday-email-uc.md)** - Lär dig hur du testar resor med tidsbaserade villkor för att säkerställa att meddelanden skickas på specifika dagar. Se hur du validerar vänteaktiviteter och schemaläggningslogik.

* **[Utforska fler användningsexempel för resor](../using/building-journeys/jo-use-cases.md)** - Få tillgång till en omfattande samling praktiska exempel som omfattar upplevelsehändelser, flerkanalsmeddelanden och externa systemintegreringar.

## Testa och godkänna innehåll

:::: landing-cards-container
:::
![icon](https://cdn.experienceleague.adobe.com/icons/list-check.svg?lang=sv-SE)

Förhandsgranska, testa och validera innehåll

Lär dig hur du förhandsgranskar, testar och validerar personaliserat innehåll med testprofiler, e-postrenderingstester, utvärderingar av skräppostpoäng med mera.

[Förhandsgranska och testa innehåll](preview-test-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/shield-halved.svg?lang=sv-SE)

Arbetsflöden för godkännande av resor och kampanjer

Lär dig hur man skapar, hanterar och genomför godkännandeprocesser för att säkerställa kvalitetskontroll för resor och kampanjer.

[Läs mer om arbetsflöden för godkännande](approve-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg?lang=sv-SE)

Testa din resa

Validera resan innan du publicerar den genom att testa den med specifika profiler för att säkerställa att händelser, villkor och åtgärder fungerar som förväntat.

[Testa din resa](../using/building-journeys/testing-the-journey.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg?lang=sv-SE)

Körning av resetorr

Utför en torr körning för att simulera och validera kundresan och identifiera potentiella problem innan du publicerar.

[Lär dig mer om körning av körning med resan](../using/building-journeys/journey-dry-run.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg?lang=sv-SE)

Övervakning och felsökning

Få tillgång till omfattande felsökningsresurser, systemvarningar och felkoder för att lösa problem med kundresan och prestandan.

[Visa övervakning och felsökning](troubleshoot-journey-landing-page.md)
:::

::::

## Ytterligare resurser

### Grundläggande riktlinjer för testning och validering

* [Live-rapport i din resa](../using/building-journeys/report-journey.md) - Övervaka resemätningar i realtid för att spåra prestanda och identifiera problem under körningen. Få tillgång till detaljerade uppdelningar av profilens förlopp, händelseutlösare och antalet slutförda åtgärder.

* [Skapa testprofiler](../using/audience/creating-test-profiles.md) - Skapa och hantera testprofiler för att simulera verkliga kundscenarier och validera personaliseringen. Lär dig hur du flaggar profiler för testning, anger attributvärden och organiserar testprofilsegment.

* [Rapport om skräppost](../using/content-management/spam-report.md) - Kontrollera skräppostresultatet innan du skickar iväg det för att förbättra leveransen och placeringen av inkorgen. Förstå hur skräppostfilter utvärderar ditt innehåll och får rekommendationer om förbättringar.

* [Vanliga frågor och svar om resor](../using/building-journeys/journey-faq.md) - Hitta svar på vanliga frågor om att skapa, testa, köra och felsöka resor. Snabb referens för att lösa vanliga problem och förstå resebeteende.

### Relaterade ämnen

* [Innehållshantering](content-management-landing-page.md) - Lär dig hur du utformar, förhandsgranskar och hanterar innehåll med hjälp av mallar, fragment och e-post-Designer. Bästa tillvägagångssätt för att skapa enhetligt innehåll.

* [Rapportering och analys](reporting-landing-page.md) - Analysera kampanjer och kundresan med omfattande rapporter, instrumentpaneler och mätvärden. Fatta databaserade beslut för att optimera kundupplevelserna.

* [Resekonfiguration](configure-journeys-landing-page.md) - Konfigurera datakällor, händelser och anpassade åtgärder för att aktivera sofistikerad resesamordning. Skapa en teknisk grund för att skapa en resa.

* [Kampanjhantering](../using/campaigns/get-started-with-campaigns.md) - Utforska olika kampanjtyper och lär dig hur du skapar, schemalägger och optimerar batch- och realtidskampanjer för maximal effekt.
