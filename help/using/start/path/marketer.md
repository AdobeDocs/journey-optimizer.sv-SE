---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer Get started for Marketers
description: Lär dig mer om hur du arbetar med Journey Optimizer som resehandledare
level: Beginner
feature: Get Started
Role: User
exl-id: 34304142-3ee8-4081-94b9-e914968c75ba
source-git-commit: ed3246d0bd552fee9c4df01babe18a5c1acd3b5f
workflow-type: tm+mt
source-wordcount: '1477'
ht-degree: 0%

---

# Kom igång med marknadsförare {#get-started-marketers}

Som **marknadsförare** eller **affärsadministratör** kan du utforma kundresor för att leverera personliga, sammanhangsbaserade upplevelser till kunder. Ni kan skapa och hantera alla de olika komponenterna i dessa personaliserade resor, inklusive e-post och push-meddelanden, erbjudanden och beslutskomponenter för att på ett intelligent sätt personalisera meddelandeinnehåll. Journey Optimizer ger en enhetlig användarupplevelse där man kan implementera hela användningen från början till slut på ett och samma ställe. Du kan börja arbeta med [!DNL Adobe Journey Optimizer] när [systemadministratören](administrator.md) och [datateknikern](data-engineer.md) har gett dig åtkomst och förberett din miljö.

## Kom igång med grunderna

Journey Optimizer sammanför kundinsikter i realtid, modern flerkanalsmarknadsföring och intelligent beslutsfattande i en enda applikation. Skapa personaliserade, sammankopplade kundupplevelser via e-post, SMS, push, i appen, webben, innehållskort med mera.

Journey Optimizer erbjuder två kraftfulla orkestreringsmetoder:

* **Resor**: Ett-till-ett-engagemang i realtid där varje kund går igenom i sin egen takt, triggas av beteende eller händelser
* **Samordnade kampanjer**: Komplexa gruppkampanjer i flera steg i stor skala där målgrupperna samverkar via arbetsflöden - perfekt för varumärkesinitierade kampanjer som säsongskampanjer, produktlanseringar eller kontobaserad kommunikation

Arbeta med dina [administratörer](administrator.md) för att få åtkomst och med [datatekniker](data-engineer.md) för att konfigurera målgrupper, data och relationsscheman för avancerad segmentering.

Så här börjar du med att skapa upplevelser:

1. **Skapa målgrupper**. Bygg målgrupper genom segmentdefinitioner, ladda upp CSV-filer eller använd målgruppskomposition. Journey Optimizer erbjuder flera sätt att inrikta sig på rätt kunder. Läs mer om [målgrupper](../../audience/about-audiences.md) och [att skapa segmentdefinitioner](../../audience/creating-a-segment-definition.md).

1. **Skapa innehåll**. Skapa övertygande budskap i alla kanaler, inklusive e-post, SMS, push, appar, webben och innehållskort:
   * Använd **AI-assistenten** för att generera e-postinnehåll, ämnesrader och bilder baserat på varumärkesriktlinjerna. [Läs mer om generering av AI-innehåll](../../content-management/gs-generative.md)
   * **Anpassa meddelanden** med kunddata, dynamiskt innehåll och villkorslogik. [Läs om personalisering](../../personalization/personalize.md)
   * **Iterera kontextdata** om du vill visa dynamiska listor från händelser, anpassade åtgärder och datauppsättningssökningar. [Lär dig mer om att iterera sammanhangsberoende data](../../personalization/iterate-contextual-data.md)
   * Skapa återanvändbara **innehållsmallar** och **fragment** för att upprätthålla varumärkets enhetlighet. [Arbeta med mallar](../../content-management/content-templates.md)
   * Leverera permanenta, icke-påträngande **innehållskort** i mobilappar och på webbplatser. Till skillnad från push-meddelanden förblir innehållskort synliga tills de stängs. [Lär dig mer om innehållskort](../../content-card/create-content-card.md)
   * Hantera resurser med **Adobe Experience Manager Assets**-integrering. [Läs om resurser](../../integrations/assets.md)

   ![](../assets/perso_ee2.png)

1. **Lägg till erbjudanden och beslut**. Leverera det bästa erbjudandet till varje kund vid rätt tidpunkt med hjälp av AI-styrda beslut. Lär dig mer om [Beslutshantering](../../offers/get-started/starting-offer-decisioning.md) och [Experience Decision](../../experience-decisioning/gs-experience-decisioning.md).

   ![](../assets/offers-e2e-offers-displayed.png)

1. **Testa och validera**. Förhandsgranska och testa innehållet innan du skickar:
   * Använd **testprofiler** för att förhandsgranska personalisering och kontrollera återgivning på olika enheter
   * Testa med **exempeldata** från CSV-/JSON-filer
   * Förhandsgranska **e-poståtergivning** för vanliga e-postklienter
   * Kör **A/B-tester och experiment** för att optimera innehållsvariationer. Använd multiväpnad bandit-experimenterande för att automatiskt tilldela mer trafik till vinnande variationer i realtid. [Lär dig mer om experiment](../../content-management/content-experiment.md)
   * Ställ in **arbetsflöden för godkännande** för kampanjer och resor (kräver ytterligare licens). [Läs om godkännanden](../../test-approve/gs-approval.md)

   Lär dig hur du [testar och validerar meddelanden](../../content-management/preview-test.md).

1. **Skapa kundresor**. Skapa personaliserade upplevelser i realtid med hjälp av arbetsytan:

   * Utlös resor med **händelser** (kundåtgärder) eller **målgrupper** (grupputskick)
   * Lägg till **villkor** för att skapa anpassade sökvägar baserat på kunddata
   * Använd **vänteaktiviteter** för att skapa perfekt timing mellan meddelanden
   * Skicka meddelanden över **flera kanaler** inom en resa
   * Använd **A/B-testning** och optimera sändningstider för att maximera engagemanget
   * Använd **datauppslagssökning** för att berika resor med realtidsdata från Adobe Experience Platform. [Lär dig mer om datauppsättningssökning](../../building-journeys/dataset-lookup.md)
   * Utnyttja **kompletterande identifierare** så att samma profil kan ange flera resesförekomster (t.ex. olika order eller bokningar). [Läs om ytterligare identifierare](../../building-journeys/supplemental-identifier.md)

   ![](../assets/journey-design.png)

   Lär dig hur du [utformar och kör resor](../../building-journeys/journey-gs.md) och utforskar [användningsexempel för resor](../../building-journeys/jo-use-cases.md). Förstå [villkor för in-/utträde](../../building-journeys/entry-exit-criteria-guide.md) för att styra profilflödet.

1. **Starta samordnade kampanjer**. Utforma komplexa flerstegskampanjer i stor skala med en visuell arbetsyta:

   * Bygg **on demand-målgrupper** direkt med relationsfrågor för att koppla kunddata till konton, inköp, prenumerationer och andra enheter
   * Skapa **segmentering för flera enheter** för exakt målgruppsanpassning (t.ex. &quot;kunder med prenumerationer som upphör om 30 dagar&quot; eller &quot;konton med nyligen gjorda värdefulla köp&quot;)
   * Få **synlighet före sändning** med korrekt antal målgrupper innan du startar
   * Utforma **flerstegsarbetsflöden** för säsongskampanjer, produktlanseringar, lojalitetserbjudanden eller kontobaserad marknadsföring
   * Schemalägg kampanjkörningar direkt, vid specifika tidpunkter eller i återkommande tidsplaner (varje dag, varje vecka, varje månad)
   * Bearbeta målgrupper i **gruppläge** där alla profiler sammanförs genom arbetsflödet

   Lär dig hur du [kommer igång med orkestrerade kampanjer](../../orchestrated/gs-orchestrated-campaigns.md) och förstår när du ska [använda kampanjer eller resor](../../orchestrated/orchestrated-campaigns-faq.md).

1. **Övervaka och optimera**. Spåra prestanda och förbättra resultaten över tid:
   * Övervaka **direktresan** och identifiera flaskhalsar
   * Analysera **leveransfrekvenser och interaktionsmått för**-meddelanden
   * Använd **rapportinstrumentpaneler** med Customer Journey Analytics-integrering
   * Spåra **konvertering** och affärsmässiga konsekvenser
   * Hantera **meddelandefrekvens och prioritering** med konflikthanteringsregler för att förhindra överkommunikation. [Läs om konflikthantering](../../conflict-prioritization/gs-conflict-prioritization.md)

   Lär dig [övervaka prestanda](../../reports/report-gs-cja.md).

## Bästa tillvägagångssätt för framgång

### Skapa innehåll

* **Börja med mallar**: Använd fördefinierade mallar och innehållsfragment för att snabba upp skapandet och upprätthålla konsekvensen
* **Testa tidigt, testa ofta**: Förhandsgranska alltid innehåll på olika enheter och använd testprofiler för att validera personaliseringen
* **Utnyttja AI på ett klokt sätt**: Använd AI Assistant för inledande utkast och variationer, men granska och förfina alltid för din varumärkesröst
* **Behåll det enkelt**: Tydliga, kortfattade meddelanden med starka uppmaningar att agera fungerar bättre än komplexa layouter

### Resedesign

* **Definiera tydliga mål**: Upprätta framgångsmått innan du skapar din resa
* **Mappa kundupplevelsen**: Visa hela kundresan innan implementering
* **Använd vänteaktiviteter strategiskt**: Ge kunderna tid att engagera innan de skickar uppföljningar
* **Planera strategier för att avsluta**: Definiera när och varför kunderna ska avsluta kundresan
* **Testa i utkastläge**: Verifiera reselogik med torr körning innan aktivering

[Lär dig de bästa sätten att få resan att fungera](../../building-journeys/entry-exit-criteria-guide.md#best-practices)

### Kampanjsamordning

* **Välj rätt metod**: Använd resor för upplevelser som triggas av beteenden i realtid; använd orkestrerade kampanjer för schemalagda gruppkampanjer
* **Definiera tydliga kampanjmål**: Upprätta mål innan du utformar flerstegsarbetsflöden
* **Börja med pilotmålgrupper**: Validera antal och segmenteringslogik före skalförändring
* **Utnyttja relationsdata**: Använd segmentering för flera enheter för att koppla kunddata till konton, inköp och prenumerationer för exakt målinriktning
* **Behåll segmenteringen enkelt**: Optimera prestanda och genomskinlighet med tydliga, underhållbara regler
* **Använd konsekvent namngivning**: Gör kampanjhanteringen enklare med tydliga namnkonventioner

### Målgruppsanpassning

* **Segmentera noggrant**: Skapa specifika, åtgärdbara målgruppssegment baserat på tydliga kriterier
* **Uppdatera regelbundet**: Se till att målgrupperna hålls uppdaterade genom att ställa in lämpliga utvärderingsscheman
* **Balansstorlek och precision**: Målgrupper som är tillräckligt stora för statistisk signifikans men tillräckligt specifika för relevans
* **Använd anrikningsattribut**: Utnyttja beräknade attribut och anrikningsdata för djupare personalisering

### Frekvenshantering

* **Respektera kundens preferenser**: Följ avanmälningarna och kommunikationsinställningarna
* **Ange frekvensgränser**: Använd regeluppsättningar för att förhindra meddelandetrötthet över kanaler
* **Koordinera kampanjer**: Använd konflikthantering för att se till att kunderna får rätt meddelande vid rätt tidpunkt
* **Övervaka engagemang**: Håll utkik efter tecken på trötthet (neka öppningsfrekvens, öka antalet prenumerationer)

[Läs mer om frekvensbegränsning](../../conflict-prioritization/channel-capping.md)

## Utforska användningsexempel

Ta del av praktiska exempel som demonstrerar Journey Optimizer funktioner:

**Användningsexempel på resan** (realtid, en-till-en):

* **Välkomstserie**: Ta in nya kunder med personaliserade flerstegsresor. [Visa användningsfall](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/use-cases/customer-onboarding)
* **Övergiven kundvagnsåterställning**: Engagera kunder som lämnat artiklar i kundvagnen igen. [Visa användningsfall](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/use-cases/abandoned-cart)
* **Händelsestyrda meddelanden**: Svara på kundåtgärder i realtid
* **Födelsedagskampanjer**: Skicka personaliserade födelsedagsmeddelanden som utlösts av profildatum
* **Produktrekommendationer**: Föreslå relevanta produkter baserat på bläddring och inköpshistorik

**Samordnade kampanjanvändningsfall** (batch, en-till-många):

* **Säsongskampanjer**: Starta samordnade kampanjer i olika kundsegment (t.ex. semesterförsäljning, skolstartsförsäljning)
* **Produktlanseringar**: Nu kommer nya produkter att visas för riktade målgrupper med sekvensmeddelanden
* **Lojalitetsprogram erbjuder**: Belöna värdefulla kunder med nivåindelade erbjudanden baserat på inköpshistorik
* **Kontobaserad marknadsföring**: Målkonton med specifika egenskaper och relaterade kontakter
* **Prenumerationsförnyelser**: Nå kunder med prenumerationer som snart går ut med hjälp av multientitetsfrågor
* **Återengagemangskampanjer**: Vinn inaktiva kunder med målinriktade erbjudanden i gruppläge. [Visa användningsfall](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/use-cases/personalization-insights-engagement/use-cases-luma)

**Resemönster:**

* [Skicka meddelanden till prenumeranter](../../building-journeys/message-to-subscribers-uc.md): Målprenumerationslistor med personaliserat innehåll
* [Flerkanalsmeddelanden](../../building-journeys/journeys-uc.md): Kombinera e-post och push med reaktionshändelser
* [E-postmeddelanden som endast är veckodag](../../building-journeys/weekday-email-uc.md): Schemalägg kommunikation med tidsbaserade villkor

Bläddra i det fullständiga biblioteket för [användningsfall för resan](../../building-journeys/jo-use-cases.md) och läs mer om [samordnade kampanjer](../../orchestrated/gs-orchestrated-campaigns.md).

## Samarbeta med andra roller

Marknadsföringsarbetet samverkar med andra team:

* **Arbeta med [datatekniker](data-engineer.md)**: Begär nya beräknade attribut, koordinera relationsscheman för orkestrerade kampanjer, ge feedback på målgruppskvaliteten och anpassa sig till datakraven för flera enheter för avancerad segmentering
* **Arbeta med [utvecklare](developer.md)**: Justera mot händelseutlösare, testa mobilimplementeringar och validera spårning
* **Arbeta med [administratörer](administrator.md)**: Begär kanalkonfigurationer, bekräfta licensåtkomst för orkestrerade kampanjer, rapportera problem med behörigheter och koordinera för aktivering av nya funktioner

## Håll dig uppdaterad

Håll dig à jour med de senaste funktionerna i Journey Optimizer och marknadsföringsfunktionerna:

* **[Versionsinformation](../../rn/release-notes.md)**: Granska nya funktioner, kanaluppdateringar och förbättringar som släpps varje månad
* **[Dokumentationsuppdateringar](../../rn/documentation-updates.md)**: Spåra senaste ändringar, inklusive nya användningsfall, bästa praxis och funktionsdokumentation
* **[Produktmeddelanden](../../rn/releases.md#staying-informed)**: Lär dig hur du prenumererar på e-postmeddelanden och produktmeddelanden för Journey Optimizer-uppdateringar, inklusive nya kanaler, kommande funktionsstarter och viktiga kampanjmeddelanden

## Nästa steg

1. **Start small**: Skapa en enkel välkomstresa eller kampanj med ett enda meddelande för att lära dig plattformen
2. **Utnyttja AI**: Använd AI Assistant för att ställa frågor och snabba upp skapandet av innehåll
3. **Gå med i communityn**: Anslut till andra Journey Optimizer-användare i [Experience League Community](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer/ct-p/journey-optimizer){target="_blank"}
4. **Utforska självstudiekurser**: Titta på stegvisa videor om [Experience League](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/overview.html){target="_blank"}
