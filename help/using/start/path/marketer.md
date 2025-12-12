---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer Get started for Marketers
description: Lär dig mer om hur du arbetar med Journey Optimizer som resehandledare
level: Beginner
feature: Get Started
Role: User
exl-id: 34304142-3ee8-4081-94b9-e914968c75ba
source-git-commit: 5ff7987c00afda3263cb97654967c5b698f726c2
workflow-type: tm+mt
source-wordcount: '1192'
ht-degree: 0%

---

# Kom igång med marknadsförare {#get-started-marketers}

Som **marknadsförare** eller **resenär** ansvarar du för att skapa erbjudanden och resor och utforma innehåll. Du kan börja arbeta med [!DNL Adobe Journey Optimizer] när [systemadministratören](administrator.md) och [datateknikern](data-engineer.md) har gett dig åtkomst och förberett din miljö.

## Kom igång med grunderna

Journey Optimizer ger er möjlighet att skapa personaliserade, sammankopplade kundupplevelser via e-post, SMS, push, i appen, webben, innehållskort med mera. Arbeta med dina [administratörer](administrator.md) för att få åtkomst och med [datatekniker](data-engineer.md) för att konfigurera målgrupper och data.

Så här börjar du med att skapa upplevelser:

1. **Skapa målgrupper**. Bygg målgrupper genom segmentdefinitioner, ladda upp CSV-filer eller använd målgruppskomposition. Journey Optimizer erbjuder flera sätt att inrikta sig på rätt kunder. Läs mer om [målgrupper](../../audience/about-audiences.md) och [att skapa segmentdefinitioner](../../audience/creating-a-segment-definition.md).

1. **Skapa innehåll**. Skapa övertygande budskap i alla kanaler:
   * Använd **AI-assistenten** för att generera e-postinnehåll, ämnesrader och bilder baserat på varumärkesriktlinjerna. [Läs mer om generering av AI-innehåll](../../content-management/gs-generative.md)
   * **Anpassa meddelanden** med kunddata, dynamiskt innehåll och villkorslogik. [Läs om personalisering](../../personalization/personalize.md)
   * **Iterera kontextdata** om du vill visa dynamiska listor från händelser, anpassade åtgärder och datauppsättningssökningar. [Lär dig mer om att iterera sammanhangsberoende data](../../personalization/iterate-contextual-data.md)
   * Skapa återanvändbara **innehållsmallar** och **fragment** för att upprätthålla varumärkets enhetlighet. [Arbeta med mallar](../../content-management/content-templates.md)
   * Hantera resurser med **Adobe Experience Manager Assets**-integrering. [Läs om resurser](../../integrations/assets.md)

   ![](../assets/perso_ee2.png)

1. **Lägg till erbjudanden och beslut**. Leverera det bästa erbjudandet till varje kund vid rätt tidpunkt med hjälp av AI-styrda beslut. Lär dig mer om [Beslutshantering](../../offers/get-started/starting-offer-decisioning.md) och [Experience Decision](../../experience-decisioning/gs-experience-decisioning.md).

   ![](../assets/offers-e2e-offers-displayed.png)

1. **Testa och validera**. Förhandsgranska och testa innehållet innan du skickar:
   * Använd **testprofiler** för att förhandsgranska personalisering och kontrollera återgivning på olika enheter
   * Testa med **exempeldata** från CSV-/JSON-filer
   * Förhandsgranska **e-poståtergivning** för vanliga e-postklienter
   * Ställ in **arbetsflöden för godkännande** för kampanjer och resor (kräver ytterligare licens)

   Lär dig hur du [testar och validerar meddelanden](../../content-management/preview-test.md).

1. **Skapa kundresor**. Skapa personaliserade upplevelser i realtid med hjälp av arbetsytan:

   * Utlös resor med **händelser** (kundåtgärder) eller **målgrupper** (grupputskick)
   * Lägg till **villkor** för att skapa anpassade sökvägar baserat på kunddata
   * Använd **vänteaktiviteter** för att skapa perfekt timing mellan meddelanden
   * Skicka meddelanden över **flera kanaler** inom en resa
   * Använd **A/B-testning** för att optimera resans effektivitet
   * Använd **datauppslagssökning** för att berika resor med realtidsdata från Adobe Experience Platform. [Lär dig mer om datauppsättningssökning](../../building-journeys/dataset-lookup.md)
   * Utnyttja **kompletterande identifierare** så att samma profil kan ange flera resesförekomster (t.ex. olika order eller bokningar). [Läs om ytterligare identifierare](../../building-journeys/supplemental-identifier.md)

   ![](../assets/journey-design.png)

   Lär dig hur du [utformar och kör resor](../../building-journeys/journey-gs.md) och utforskar [användningsexempel för resor](../../building-journeys/jo-use-cases.md). Förstå [villkor för in-/utträde](../../building-journeys/entry-exit-criteria-guide.md) för att styra profilflödet.

1. **Övervaka och optimera**. Spåra prestanda och förbättra resultaten över tid:
   * Övervaka **direktresan** och identifiera flaskhalsar
   * Analysera **leveransfrekvenser och interaktionsmått för**-meddelanden
   * Använd **rapportinstrumentpaneler** med Customer Journey Analytics-integrering
   * Spåra **konvertering** och affärsmässiga konsekvenser

   Lär dig [övervaka prestanda](../../reports/report-gs-cja.md).

## Utnyttja de senaste funktionerna

Journey Optimizer utvecklas kontinuerligt med nya funktioner för att förbättra er marknadsföring:

* **Innehållskort**: Leverera permanenta, icke-påträngande meddelanden i mobilappar och på webbplatser som användarna kan interagera med när de vill. Till skillnad från push-meddelanden förblir innehållskort synliga tills de stängs. [Lär dig mer om innehållskort](../../content-card/get-started-content-card.md)

* **Konflikthantering och prioritering**: Kontrollera meddelandefrekvens och förhindra överkommunikation med avancerade regler för begränsning. Ange prioritetspoäng för att säkerställa att de viktigaste meddelandena når kunderna först. [Läs om konflikthantering](../../conflict-prioritization/gs-conflict-prioritization.md)

* **AI-driven Send-Time Optimization**: Låt AI förutse den optimala sändningstiden för varje kund utifrån deras historiska engagemangsmönster, öka öppnings- och klickfrekvensen med upp till 10 %. [Läs om optimering vid sändning](../../building-journeys/send-time-optimization.md)

* **Multi-Armed Bandit Experimentation**: Allokera automatiskt mer trafik till vinnande variationer i realtid medan du testar, maximera resultaten utan att vänta på att testet ska slutföras. [Lär dig mer om experiment](../../content-management/content-experiment.md)

* **Arbetsflöden för godkännande**: Implementera granskningsprocesser för kampanjer och resor innan de publiceras (tillgängligt med ytterligare licens). [Läs om godkännanden](../../test-approve/gs-approval.md)

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

**Populära användningsfall:**

* **Välkomstserie**: Ta in nya kunder med personaliserade flerstegsresor. [Visa användningsfall](https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/use-cases/customer-onboarding)
* **Övergiven kundvagnsåterställning**: Engagera kunder som lämnat artiklar i kundvagnen igen. [Visa användningsfall](https://experienceleague.adobe.com/sv/docs/journey-optimizer-learn/tutorials/use-cases/abandoned-cart)
* **Återengagemangskampanjer**: Vinn inaktiva kunder med riktade erbjudanden. [Visa användningsfall](https://experienceleague.adobe.com/sv/docs/experience-platform/rtcdp/use-cases/personalization-insights-engagement/use-cases-luma)
* **Födelsedagskampanjer**: Skicka personliga födelsedagsmeddelanden med specialerbjudanden
* **Produktrekommendationer**: Föreslå relevanta produkter baserat på bläddring och inköpshistorik
* **Händelsestyrda meddelanden**: Svara på kundåtgärder i realtid

**Resemönster:**

* [Skicka meddelanden till prenumeranter](../../building-journeys/message-to-subscribers-uc.md): Målprenumerationslistor med personaliserat innehåll
* [Flerkanalsmeddelanden](../../building-journeys/journeys-uc.md): Kombinera e-post och push med reaktionshändelser
* [E-postmeddelanden som endast är veckodag](../../building-journeys/weekday-email-uc.md): Schemalägg kommunikation med tidsbaserade villkor

Bläddra i det fullständiga biblioteket för [resans användningsfall](../../building-journeys/jo-use-cases.md) om du vill ha fler mönster och implementeringar.

## Samarbeta med andra roller

Marknadsföringsarbetet samverkar med andra team:

* **Arbeta med [datatekniker](data-engineer.md)**: Begär nya beräknade attribut, ge feedback om målgruppens kvalitet och koordinera för datakrav
* **Arbeta med [utvecklare](developer.md)**: Justera mot händelseutlösare, testa mobilimplementeringar och validera spårning
* **Arbeta med [administratörer](administrator.md)**: Begär kanalkonfigurationer, rapportera problem med behörigheter och koordinera för aktivering av nya funktioner

## Håll dig uppdaterad

Håll dig à jour med de senaste funktionerna i Journey Optimizer och marknadsföringsfunktionerna:

* **[Versionsinformation](../../rn/release-notes.md)**: Granska nya funktioner, kanaluppdateringar och förbättringar som släpps varje månad
* **[Dokumentationsuppdateringar](../../rn/documentation-updates.md)**: Spåra senaste ändringar, inklusive nya användningsfall, bästa praxis och funktionsdokumentation
* **Produktmeddelanden**: Aktivera aviseringar i din [Adobe Experience Cloud-profil](https://experience.adobe.com/preferences){target="_blank"} för att få aviseringar om:
   * Nya kanaler och funktioner som är tillgängliga
   * Kommande funktionslanseringar och betaprogram
   * Bästa praxis och utbildningsmöjligheter
   * Viktiga meddelanden som påverkar era kampanjer

  Om du vill aktivera meddelanden klickar du på din profilikon i det övre högra hörnet av Adobe Experience Cloud, går till **Inställningar > Meddelanden** och konfigurerar Journey Optimizer meddelandeinställningar.

## Nästa steg

1. **Start small**: Skapa en enkel välkomstresa eller kampanj med ett enda meddelande för att lära dig plattformen
2. **Utnyttja AI**: Använd AI Assistant för att ställa frågor och snabba upp skapandet av innehåll
3. **Gå med i communityn**: Anslut till andra Journey Optimizer-användare i [Experience League Community](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer/ct-p/journey-optimizer){target="_blank"}
4. **Utforska självstudiekurser**: Titta på stegvisa videor om [Experience League](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/overview.html?lang=sv-SE){target="_blank"}
