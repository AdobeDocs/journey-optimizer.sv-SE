---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med resor
description: Kom igång med resor - Lär dig mer om resetyper, arbetsflöde, funktioner och bästa praxis för att skapa personaliserade kundupplevelser i Adobe Journey Optimizer
feature: Journeys, Get Started, Overview
role: User
level: Beginner, Intermediate
keywords: resa, upptäck, komma-start, unitär, läsare, målgruppskvalifikation, affärshändelse, realtid, schemalagd, batch, händelseutlöst, arbetsflöde, orkestration, personalisering, flerkanalsmarknadsföring
exl-id: 73cfd48b-72e6-4b72-bbdf-700a32a34bda
version: Journey Orchestration
source-git-commit: 8ea2a0fe685678d41004d549443a1757eb30c765
workflow-type: tm+mt
source-wordcount: '1465'
ht-degree: 0%

---


# Kom igång med resor{#jo-general-principle}

Adobe Journey Optimizer ger er möjlighet att skapa personaliserade kundresor i flera steg som i realtid anpassar sig efter målgruppens beteende och behov. Med en intuitiv dra-och-släpp-arbetsyta kan ni samordna meddelanden och åtgärder i flera kanaler och utnyttja sammanhangsberoende data och målgruppsanpassning för maximal effekt.

Den här guiden ger en tydlig färdplan för att hjälpa er att förstå viktiga delar av kundresan, välja rätt resetyp för ert användningsfall och utforma tryggt kundresor som levererar meningsfulla, aktuella kundupplevelser.

## Vad är resor?

**Resor** är automatiserade, flerstegskunderna kundupplevelser som koordinerar personaliserade interaktioner över olika kanaler som svar på kundbeteende, affärshändelser eller schemalagda kampanjer.

Använd [!DNL Journey Optimizer] för att:

* Bygg **realtidskoordinering** med kontextuella data lagrade i händelser eller datakällor
* Utforma **avancerade flerstegsscenarier** som dynamiskt svarar på kundbeteende och affärshändelser
* Leverera **1:1 personaliserade upplevelser** i stor skala via e-post, push, SMS, appar, webben med mera

![Resedesignerns gränssnitt med palett, arbetsyta och egenskapspanelen](assets/journey38.png)

➡️ **Vill du börja bygga?** [Skapa din första resa](journey-gs.md) på 5 minuter.

### Journeys vs Campaigns: När ska man använda varje {#journeys-vs-campaigns-intro}

Adobe Journey Optimizer erbjuder tre metoder för att nå kunder: **Journeys** (1:1 realtidssamordning), **Campaigns** (enkel batchleverans eller API-utlöst leverans) och **Orchestrerade Campaigns** (batcharbetsytearbetsflöden med multientitetsdata).

**Snabbt beslut:**

* Använd **Resor** för beteendestyrda upplevelser i flera steg där varje kund utvecklas i sin egen takt
* Använd **Action/API-kampanjer** för enkel, schemalagd eller utlöst meddelandeleverans till målgrupper
* Använd **samordnade kampanjer** för komplexa batcharbetsflöden som kräver segmentering av flera enheter och exakt antal före sändning

<!-- waiting for DOCAC-13912
➡️ **[View detailed comparison: Journeys vs Campaigns](../start/journeys-vs-campaigns.md)** - Includes decision guide, use cases, and feature availability-->

## Välj typ av resa {#journey-types}

Adobe Journey Optimizer har stöd för fyra olika typer av resor, var och en utformade för olika ingångs- och affärsscenarier:

* **Enhetliga resor**: Händelseutlösta upplevelser i realtid (orderbekräftelser, välkomstmeddelanden)
* **Läs målgruppsresor**: Schemalagda gruppmeddelanden till målgruppssegment (nyhetsbrev, kampanjkampanjer)
* **Målgruppskvalificeringsresor**: Realtidssvar på ändringar av målgruppsmedlemskap (VIP-uppgraderingar, återengagemang)
* **Affärshändelseresor**: Affärsvillkor som påverkar flera kunder (lagervarningar, flash-försäljning)

➡️ **[Resetyper och urvalsguide](journey-types-selection.md)** - Detaljerad jämförelse, beslutsträd och kompatibilitetsmatris för funktioner

## Bygg med resedesignern {#journey-designer}

**[Resedesignern](using-the-journey-designer.md)** är den visuella arbetsytan för att skapa kundupplevelser. Med ett intuitivt dra-och-släpp-gränssnitt kan ni samordna alla steg i resan utan att behöva skriva kod.

![Resedesignerns gränssnitt med palett, arbetsyta och egenskapspanelen](assets/journey38.png)

### Vad du kan göra i designern:

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg)

**Definiera startpunkter**

Välj hur kunderna ska delta: via en händelse, ett målgruppssegment eller en målgruppskompetens.

[Läs mer om hantering av inträde](entry-management.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/envelope.svg)

**Skicka meddelanden**

Använd de inbyggda kanalåtgärderna för e-post, push, SMS/MMS, i appen, på webben med mera - allt som tagits fram i Journey Optimizer.

[Skicka meddelanden under resor](journeys-message.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg)

**Lägg till logik och villkor**

Förse er resa utifrån profilattribut, målgruppsmedlemskap eller realtidsevenemang.

[Användningsvillkor](condition-activity.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/database.svg)

**Utnyttja data**

Använd sammanhangsbaserade data från händelser, Adobe Experience Platform eller API-tjänster från tredje part.

[Arbeta med datakällor](../datasource/about-data-sources.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg)

**Anslut externa system**

Skapa anpassade åtgärder för att integrera tredjepartssystem för att skicka meddelanden eller aktivera arbetsflöden.

[Konfigurera anpassade åtgärder](../action/about-custom-action-configuration.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/puzzle-piece.svg)

**Lägg till koordinationsaktiviteter**

Använd väntetider, hopp, profiluppdateringar och målgruppshantering för att skapa avancerade flöden.

[Utforska alla aktiviteter](about-journey-activities.md)
:::

::::

➡️ **Praktisk inlärning:** [Titta på resedesignervideon](#video) eller [utforska användningsexempel från början till slut](jo-use-cases.md)

## Arbetsflöde för att skapa resan {#workflow}

Att skapa framgångsrika resor följer en tydlig och upprepningsbar process. Här är ditt stegvisa arbetsflöde:

**1. Planera** → **2. Design** → **3. Test** → **4. Publicera** → **5. Monitor** → **6. Optimera**

### &#x200B;1. Planera din resa {#plan}

Förtydliga målen innan du öppnar designern:

* **Vad är målet?** (t.ex. introducera nya kunder, engagera inaktiva användare igen)
* **Vem är målgruppen?** (specifikt segment, händelsestyrda individer)
* **Vilken resetyp passar?** (Se [resetyper](#journey-types) ovan)
* **Vilka kanaler ska du använda?** (e-post, push, SMS osv.)

### &#x200B;2. Designa på arbetsytan {#design}

Använd resedesignern för att bygga upp ditt flöde:

1. **Ange anmälningsvillkor** - Definiera hur profiler ska anges (händelse, målgrupp, kvalificering)
2. **Lägg till orkestreringslogik** - Inkludera väntetider, villkor och beslutspunkter
3. **Konfigurera meddelanden** - Designa dina meddelanden eller utnyttja befintliga mallar
4. **Konfigurera åtgärder** - Konfigurera inbyggda eller anpassade åtgärder som ska köras
5. **Definiera avslutningskriterier** - Ange när och hur profiler slutför resan

[Lär dig använda resedesignern →](using-the-journey-designer.md)

### &#x200B;3. Testa innan du publicerar {#test}

Testa alltid kundresan för att fånga upp problem innan kunderna upplever dem:

* Använd **testläge** för att simulera resan med testprofiler
* Använd **torr körning** om du vill förhandsgranska körningen utan att påverka verkliga data eller skicka meddelanden
* Verifiera att alla villkor, meddelanden och åtgärder fungerar som förväntat
* Kontrollera timing, dataflöden och personalisering

[Testa din resa →](testing-the-journey.md) | [Lär dig mer om torr körning → &#x200B;](journey-dry-run.md)

### &#x200B;4. Publicera din resa {#publish}

När testningen är klar publicerar du för att göra din resa levande:

* Granska de slutliga inställningarna och egenskaperna
* Publicera för att aktivera för riktiga kunder
* Obs! Live-resor kan stoppas men inte redigeras (du måste skapa en ny version)

[Publicera din resa →](publish-journey.md)

### &#x200B;5. Bildskärmsprestanda {#monitor}

Spåra hur din resa fungerar i verkligheten:

* Visa reserapporter och analyser
* Övervaka antalet inmatningar, slutföranden och fel
* Ställ in aviseringar för kritiska problem

[Övervaka och rapportera →](report-journey.md) | [Konfigurera aviseringar →](../reports/alerts.md)

### &#x200B;6. Optimera och iterera {#optimize}

Använd insikter för att förbättra:

* Analysera engagemangsmått och konverteringsgrader
* Testa optimering vid sändning
* Skapa nya versioner av resan med förbättringar
* Använd AI-baserade rekommendationer

[Optimera dina resor →](optimize.md) | [Tidsoptimering →](send-time-optimization.md)

➡️ **Vill du börja?** [Skapa din första resa nu →](journey-gs.md)

## Användningsexempel i verkligheten {#use-cases}

Lär dig av praktiska exempel som visar hur man använder resekoncept för att lösa vanliga marknadsföringsutmaningar:

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/envelope.svg)

**Välkommen nya prenumeranter**

När en kund prenumererar på din tjänst kan du utlösa en välkomstresa som uppmuntrar dem att slutföra introduktionsstegen.

[Visa användningsfall →](message-to-subscribers-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/calendar-alt.svg)

**Tidsoptimering vid sändning**

Använd AI för att leverera e-postmeddelanden när varje kund är mest benägen att engagera sig och maximera öppnings- och klickfrekvensen.

[Visa användningsfall →](send-time-optimization.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg)

**Dra upp leveranser**

Öka volymen för meddelanden gradvis för att värma upp ert anseende och undvika leveransproblem.

[Visa användningsfall →](ramp-up-deliveries-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg)

**Mål efter veckodag**

Skicka olika innehåll baserat på vilken veckodag kunderna är på er resa för att få bättre relevans.

[Visa användningsfall →](weekday-email-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/puzzle-piece.svg)

**Flerkanalskampanjer**

Samordna smidiga upplevelser över e-post, push, SMS och webbkanaler under en enda resa.

[Visa användningsfall →](journeys-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/book.svg)

**Alla användningsfall**

Utforska hela biblioteket med användningsexempel för resor med stegvisa implementeringar.

[Bläddra bland alla →](jo-use-cases.md) | [Använd fallbibliotek →](/help/rp_landing_pages/journey-use-cases-landing-page.md)
:::

::::

## Utforska resefunktioner {#capabilities}

När ni blir mer bekväma med att bygga kundresor kan ni utforska dessa kraftfulla funktioner för att skapa sofistikerade kundupplevelser:

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg)

**Avancerade uttryck**

Bygg dynamiska villkor och personalisering med uttrycksredigeraren för datahantering och komplex logik.

[Läs mer om uttryck](/help/rp_landing_pages/building-advanced-conditions-journeys-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/clock.svg)

**Hantering av tidszoner**

Hantera globala målgrupper med automatiska tidszonsjusteringar och optimala sändningstider.

[Hantera tidszoner](timezone-management.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/shield-halved.svg)

**Testläge och torr körning**

Validera resor med testprofiler innan du publicerar och förhandsgranska körningen utan att påverka verkliga data.

[Använd torr körning](journey-dry-run.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/database.svg)

**Kopiera till sandlåda**

Duplicera resor mellan sandlådor för att effektivisera arbetsflödena för testning och driftsättning.

[Kopiera resor](copy-to-sandbox.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/book.svg)

**Taggar och organisation**

Använd taggar för att kategorisera och filtrera resor för bättre hantering i stor skala.

[Ordna med taggar](tags.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg)

**Genomströmningskontroll**

Begränsa meddelandets genomströmning för att hantera sändningens rykte och undvika överväldigande system.

[Styr genomströmning](limit-throughput.md)
:::

::::

[Se alla funktioner för resan →](/help/rp_landing_pages/manage-journey-landing-page.md)

## Lär dig mer genom att titta {#video}

Få en visuell introduktion till resekomponenterna och lär dig grunderna för att bygga resor på arbetsytan:

>[!VIDEO](https://video.tv.adobe.com/v/3424996?quality=12)

➡️ **Vill du ha fler videoklipp?** [Utforska självstudiekurser om resan &#x200B;](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/journeys/journey-designer-overview){target="_blank"}

## Vanliga frågor {#common-questions}

**F: Vad är skillnaden mellan en resa och en kampanj?**

S: Adobe Journey Optimizer erbjuder tre strategier:

* **Resor**: :1 realtidssamordning där varje profil färdas genom steg i sin egen takt. Passar bäst för beteendestyrda flerstegsupplevelser med villkorsstyrd logik (t.ex. onboarding, cart abonment).

* **Kampanjer (Action &amp; API-utlösta)**: Enkel meddelandeleverans till målgrupper, som körs samtidigt till alla profiler antingen enligt schema eller via API-utlösare. Bäst för kampanjkampanjer, nyhetsbrev och transaktionsmeddelanden.

* **Samordnade kampanjer**: Batcharbetsflöden i flera steg med komplex segmentering med hjälp av relationsdata (profiler + produkter/butiker/bokningar). Alla profiler har bearbetats tillsammans med exakt antal före sändning. Bäst för säsongskampanjer, produktlanseringar och kampanjer som kräver data från flera enheter.

**Viktig skillnad**: Resor behåller enskilda kundtillstånd för åtgärder i realtid. Action/API-kampanjer levererar enkla meddelanden i batch. Orchestrerade-kampanjer erbjuder arbetsflödesyta i batch med segmenteringsfunktioner för flera enheter.

&#x200B;<!-- waiting for DOCAC-13912 [See detailed comparison](#journeys-vs-campaigns) | -->[Läs om samordnade kampanjer](../orchestrated/gs-orchestrated-campaigns.md)

<!-- Waiting for DOCAC-13912
**Q: Which journey type should I use?**

A: Use the [decision guide](#decision-guide) or [comparison table](#journey-types-comparison) to choose between Unitary, Read Audience, Audience Qualification, and Business Event journeys based on your trigger mechanism and use case.
-->

**F: Kan jag redigera en direktresa?**

S: Du kan redigera begränsade element (namn, meddelandeinnehåll), men för strukturella ändringar måste du skapa en ny version. [Läs mer om reseversioner](publish-journey.md#journey-versions)

➡️ **Fler frågor?** [Visa frågor och svar om hela resan](journey-faq.md) med över 40 detaljerade svar

## Behöver du hjälp? {#help}

### Snabblänkar för vanliga uppgifter

* **[Skapa din första resa](journey-gs.md)** - Steg för steg-guide för nybörjare
* **[Vanliga frågor om resan](journey-faq.md)** - Vanliga frågor besvarade
* **[Felsökning](/help/rp_landing_pages/troubleshoot-journey-landing-page.md)** - Diagnostisera och åtgärda problem
* **[Felkodsreferens](error-codes-reference.md)** - Förstå felmeddelanden
* **[Garantier och begränsningar](../start/guardrails.md)** - Tekniska gränser och bästa praxis

### Få meddelanden om problem

Konfigurera **[resemeddelanden](../reports/alerts.md)** för att ta emot meddelanden i realtid när resor stöter på fel eller ovanliga mönster.

### Ytterligare resurser

* **[Nav för resehantering](/help/rp_landing_pages/manage-journey-landing-page.md)** - Verktyg för filtrering, optimering och profilhantering
* **[Reseaktiviteter, referens](/help/rp_landing_pages/about-journey-building-landing-page.md)** - Fullständig guide till alla aktivitetstyper
* **[Felsöka körningsproblem](troubleshooting-execution.md)** - Felsöka körningsproblem för resan
* **[Felsöka inkommande aktiviteter](troubleshooting-inbound.md)** - Åtgärda problem med inträde och kvalificering

**Vill du skapa din första resa?** [Kom igång nu →](journey-gs.md)
