---
solution: Journey Optimizer
product: journey optimizer
title: AI och intelligenta funktioner
description: Läs om hur AI och maskininlärning förbättrar Adobe Journey Optimizer funktioner
feature: Overview
topic: Content Management
role: User
level: Beginner
source-git-commit: b48a8fa89605ac18c6db85751bf71d2ccec08f63
workflow-type: tm+mt
source-wordcount: '1469'
ht-degree: 1%

---

# AI och intelligenta funktioner {#ai-features}

Adobe Journey Optimizer utnyttjar kraften i artificiell intelligens och maskininlärning för att hjälpa er att skapa, optimera och leverera enastående kundupplevelser. Med AI-funktionerna kan du effektivisera arbetsflödet och maximera påverkan, från att skapa personaliserat innehåll till att förutsäga optimala sändningstider. Använd fallspelsböcker som innehåller färdiga mallar för att snabbt implementera vanliga marknadsföringsscenarier.

## AI-assistenten {#ai-assistant}

AI Assistant är en guide till Adobe Journey Optimizer. Använd det för att få svar på produktfunktioner, driftsinsikter om era resor och hjälp med att navigera på plattformen.

### Få tillgång till AI-assistenten

Klicka på ikonen AI-assistenten i det övre fältet för att öppna assistentpanelen till höger på skärmen.

![](assets/do-not-localize/ai-assistant-open.png)

>[!IMPORTANT]
>
>Du måste godkänna [Adobe Experience Cloud Generative AI User Guidelines](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/home){target="_blank"} innan du kan använda AI Assistant.

### Vad AI-assistenten kan göra

**Produktkunskap** - Ställ frågor om Adobe Journey Optimizer funktioner och begrepp:

* &quot;Hur skapar jag en kampanj i Adobe Journey Optimizer?&quot;
* &quot;Hur skapar jag en anpassad åtgärd som ska användas under resor?&quot;
* &quot;Hur många aktiva aktiviteter kan jag ha i en sandlåda?&quot;

**Operational Insights (Beta)** - Få information i realtid om dina resor:

* &quot;Hur många direktresor har jag?&quot;
* &quot;Ge mig en lista över alla schemalagda resor&quot;
* &quot;Hur många resor har skapats de senaste 7 dagarna?&quot;

>[!NOTE]
>
>Driftsinsikter är för närvarande bara tillgängliga för **Resor** och speglar data från din aktuella sandlåda.

### Använda AI Assistant

1. Skriv din fråga i textfältet längst ned på panelen
2. Tryck på Retur för att skicka frågan
3. Granska det AI-genererade svaret
4. Klicka på **Visa källor** för att få åtkomst till relaterad dokumentation
5. Använd reglagen uppåt/nedåt för att mäta svarskvaliteten

![](assets/do-not-localize/ai-assistant-answer.png){width="40%" align="left"}

[Läs mer om AI Assistant i Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/home){target="_blank"}

## Avancerade AI-agenter för reseoptimering {#ai-agents}

Adobe Journey Optimizer bygger på AI Assistants konversationsfunktioner och erbjuder specialiserade AI-agenter som ger djupgående analyser och användbara rekommendationer för optimering och experimenterande av resor.

### Reseanalysagent {#journey-agent}

Med agenten [Reseanalys](https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/ajo-agent-analyze){target="_blank"} kan du optimera resan genom naturlig språkanalys:

+++**Nyckelfunktioner**

* **Resebortfallsanalys** - Identifiera var och varför kunder faller bort under resor, identifiera bortfallsmönster
* **Identifiering av målgruppsöverlappning** - Analysera målgruppsöverlappning över flera resor för att förhindra trötthet från övermålning
* **Schemalägg konfliktidentifiering** - Identifiera tidskonflikter mellan schemalagda resor med samma målgrupp
* **Driftsinsikter** - Få snabba insikter som&quot;visa mig alla live-resor&quot; eller&quot;vilka målgrupper som används på fler än X resor&quot;

+++

+++**Exempelfrågor**

* &quot;Utför en bortfallsanalys för resan \[resenamn\]&quot;
* &quot;Finns det några schemaläggningskonflikter för resan \[Resenamn\]?&quot;
* &quot;Visa mig att målgruppen överlappar konflikter för resan \[resenamn\]&quot;
* &quot;Vilka målgrupper används på fler än fem resor?&quot;

+++

+++**Behörigheter krävs**

* **Visa resor** - Visa insikter om resor direkt i AI Assistant
* **Hantera resor** - Skapa nya resor direkt i AI Assistant
* **Visa segment** - Visa insikter om målgrupper
* **Hantera segment** - Skapa nya målgrupper direkt i AI Assistant

+++

### Experimentationsagent {#experimentation-agent}

[Experimentationsagenten](https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/agent-experiment){target="_blank"} moderniserar hur du kör och hanterar digitala experiment på webbplatser, i e-postmeddelanden, push-meddelanden och i program:

+++**Nyckelfunktioner**

* **Prestandaanalys** - Tydlig vy över vad som hänt i försök
* **Insights Generation** - Förklaring av varför resultatet inträffade
* **Affärsmöjlighetsidentifiering** - Vägledning om nästa åtgärd som ska vidtas
* **Innehållsanalys** - Undersök meddelandeelement för att förstå varför vissa behandlingar överträffade andra
* **Rekommendationsgenerering** - Föreslå nya behandlingar eller justeringar baserat på insikter

+++

+++**Exempelfrågor**

* &quot;Vilka experiment körs för \[Campaign Name\]?&quot;
* &quot;För min \[Experimentnamn\], vilken behandling leder?&quot;
* &quot;Vad lärde vi oss av \[Experimentnamn\]?&quot;
* &quot;Vad rekommenderar du att jag gör efter detta experiment?&quot;
* &quot;Vilka vanliga mönster kommer från de senaste testerna?&quot;

+++

+++**Behörigheter krävs**

* **Visa experiment** - Visa insikter i experiment i AI Assistant
* **Hantera experimentmetadata** - Skapa nya experiment i AI Assistant

**Obs!** Finns med Journey Optimizer Experimentation Accelerator-licens.

+++

### Ytterligare AI-agenter

**Audience Agent** - För prospektering och hantering av konversationer i hela Adobe Experience Platform, inklusive identifiering av dubbletter och storleksspårning. [Läs mer om Audience Agent](https://experienceleague.adobe.com/sv/docs/experience-cloud-ai/experience-cloud-ai/agents/audience){target="_blank"}

**Agent Orchestrator** - koordinerar flera specialiserade agenter för att lösa komplexa, flerstegsutmaningar inom marknadsföring. Orchestrator bestämmer automatiskt vilka agenter som ska involveras och sekventierar deras arbete effektivt. [Läs mer om Agent Orchestrator](https://experienceleague.adobe.com/sv/docs/experience-cloud-ai/experience-cloud-ai/agents/agent-orchestrator){target="_blank"}

## AI-driven generering av innehåll {#content-generation}

Använd generativ AI för att skapa och personalisera innehåll i flera kanaler, vilket snabbar upp processen för att skapa innehåll samtidigt som varumärkets enhetlighet bibehålls. AI-assistenten för innehållsgenerering är tillgänglig för [e-post](../email/get-started-email.md), [push-meddelanden](../push/get-started-push.md), [SMS](../sms/get-started-sms.md) och [webb](../web/get-started-web.md) - vilket hjälper dig att generera ämnesrader, brödtext, bilder och fullständiga meddelandevarianter.

### Viktiga funktioner

* **Textgenerering** - Skapa övertygande text baserat på din varumärkesröst och dina mål. [Generera text med AI](../content-management/generative-text.md)
* **Bildgenerering** - Generera anpassade bilder med Adobe Firefly. [Generera bilder med AI](../content-management/generative-image.md)
* **Innehållsvariationer** - Skapa flera variationer för A/B-testning. [Experimentera med AI](../content-management/generative-experimentation.md)
* **Märkesjustering** - Kontrollera att det genererade innehållet matchar varumärkesriktlinjerna. [Utvärdera varumärkesjustering](../content-management/brands-score.md)
* **Mallsupport** - Utnyttja dina befintliga e-postmallar. [Arbeta med innehållsmallar](../content-management/content-templates.md)

### Bästa praxis

* **Var specifik** - Ange tydliga, detaljerade anvisningar för bättre resultat
* **Överför varumärkesresurser** - Använd PDF-filer, bilder eller ZIP-filer (högst 50 MB) för att upprätthålla varumärkets enhetlighet
* **Använd egna mallar** - Använd varumärkesspecifika mallar med upp till 8-10 bilder
* **Ge feedback** - Rate-utdata hjälper till att förbättra AI-modellerna
* **Granska allt innehåll** - Granska alltid AI-genererat innehåll för precision innan publicering

[Läs mer om generering av AI-innehåll](../content-management/gs-generative.md)

## Sändningsoptimering {#send-time-optimization}

Använd AI för att förutsäga den optimala tidpunkten för att skicka varje meddelande baserat på individuella kundbeteendemönster, vilket maximerar engagemanget.

### Så här fungerar det

Sändningsoptimering analyserar historiska engagemangsdata (öppningar och klick) för att förutse när varje kund är mest benägen att interagera med era meddelanden. Systemet schemalägger automatiskt leveransen inom det angivna tidsfönstret.

### När ska den användas

| Bäst för | Rekommenderas inte för |
|----------|---------------------|
| Marknadsföringskampanjer och nyhetsbrev | Tidskänsliga operativa meddelanden (orderbekräftelser, lösenordsåterställningar) |
| Kampanjmeddelanden | Akuta meddelanden (flygförseningar, larm om nödsituationer) |
| Utbildningsmaterial | Händelsebaserade meddelanden med specifika timingkrav |
| Engagerande kampanjer | |

[Läs mer om optimering av sändningstid](../building-journeys/send-time-optimization.md)

## AI-modeller för beslut {#ai-decisioning}

Skapa intelligenta rangordningsmodeller som automatiskt optimerar vilka erbjudanden som ska visas för varje kund och maximerar affärsmålen.

### Modelltyper

**Automatisk optimering** - lär dig av kundinteraktioner för att automatiskt förbättra erbjudandets prestanda över tid

**Anpassad optimering** - Använder attribut och beteenden för kundprofiler för att förutsäga det bästa erbjudandet för varje enskild person

### Krav

* Minst två erbjudanden med tillräckliga interaktionsdata:
   * 100+ skärmhändelser
   * 5+ klickningshändelser
   * Under de senaste 14 dagarna
* Max 5 AI-rankningsmodeller per organisation

[Läs mer om AI-modeller för beslut](../experience-decisioning/ranking/ai-models.md) | [Skapa AI-rankningsmodeller](../experience-decisioning/ranking/create-ai-models.md)

## Experimentera med AI {#experimentation}

**Med Experiment Accelerator** kan du köra experiment snabbare med AI-baserade insikter och rekommendationer och identifiera vinnande innehållsvariationer snabbare.

Viktiga funktioner:

* Generera flera innehållsvariationer automatiskt
* Få AI-rekommendationer för experimentell design
* Få tidiga indikationer på resultattrender
* Snabba upp tiden till statistisk signifikans

[Läs mer om Experiment Accelerator](../content-management/experiment-accelerator-gs.md)

## Use Case Playbooks {#playbooks}

Case Playbooks är färdiga arbetsflöden som hjälper er att implementera vanliga marknadsföringsscenarier snabbt. Varje spelbok innehåller färdiga resor, meddelanden, scheman och segment.

![Använd gränssnittet för fallspelningsböcker](assets/playbooks-filter.png)

### Så här fungerar Playbooks

1. **Bläddra** i spelboksbiblioteket för att hitta användningsfall som matchar dina mål
2. **Aktivera** en spelbok för att automatiskt generera alla nödvändiga resurser
3. **Anpassa** de genererade resurserna så att de matchar ditt varumärke och dina krav
4. **Distribuera** till produktion eller testa i en utvecklingssandlåda

### Tillgängliga spelböcker

Bläddra bland Journey Optimizer spelböcker efter vanliga scenarier som:

* Återvinning av övergiven kundvagn
* Välkomstserie för nya kunder
* Inköp efter inköp
* Födelsedag
* Återengagemangskampanjer

+++**Förhandskrav**

* Sandlåda med lämpliga behörigheter
* Kanalkonfigurationer för e-post, push och/eller SMS
* Användarbehörigheter för att skapa resor och meddelanden

+++

[Visa alla tillgängliga spelningsböcker](https://experienceleague.adobe.com/docs/experience-platform/use-case-playbooks/playbooks/playbooks-list.html){target="_blank"} | [Läs mer i Experience Platform-dokumentationen &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/use-case-playbooks/playbooks/overview.html){target="_blank"}

## Ytterligare AI-funktioner {#additional-capabilities}

### Image to HTML Converter

Omvandla statiska bilddesigner (JPEG, PNG) till redigerbara HTML e-postmallar med AI-baserad konverteringsteknik.

[Läs mer om Image to HTML](../email/image-to-html.md)

### Klassificering av varumärkesjustering

Utvärdera hur väl innehållet överensstämmer med varumärkesriktlinjerna med hjälp av AI-baserad poängsättning som mäter tonen, rösten och meddelandets enhetlighet.

[Läs mer om varumärkesjustering](../content-management/brands-score.md)

## Vanliga frågor {#faq}

+++**Vilka behörigheter behöver jag för AI-funktioner?**

* **[AI-assistenten för innehållsgenerering](#content-generation)** - Kräver behörigheten Generera innehåll
* **[AI Assistant](#ai-assistant)** produktkunskap - Kräver godkännande av Adobe Generative AI User Guidelines
* **[Reseanalysagent](#journey-agent)** - Kräver behörighet för att visa/hantera resor och visa/hantera segment
* **[Experimenteringsagent](#experimentation-agent)** - Kräver behörighet för att visa och hantera experimentella metadata

Alla AI-agenter kräver åtkomst till AI Assistant och godkännande av Adobe Experience Cloud Generative AI User Guidelines.

[Läs mer om behörigheter](../administration/ootb-permissions.md)

+++

+++**Är AI-genererat innehåll alltid korrekt?**

Nej. Granska alltid [AI-genererat innehåll](#content-generation) för att se om det är korrekt och lämpligt för varumärket. Använd feedbackverktygen (dra upp/ned) för att förbättra modellerna.

+++

+++**Vilka är de huvudsakliga begränsningarna?**

* **[Tidsoptimering vid sändning](#send-time-optimization)** - Endast tillgängligt för e-post och push-resor; kräver 30-dagars utbildningsperiod
* **[Generering av AI-innehåll](#content-generation)** - Inte tillgängligt för direktreklam, innehållskort, LINE eller whatsApp
* **[AI-rangordningsmodeller](#ai-decisioning)** - Högst 5 modeller per organisation; kräver minimala interaktionsdata

+++

+++**Hur får jag åtkomst till de här funktionerna?**

De flesta AI-funktioner ingår i Adobe Journey Optimizer. Vissa funktioner som [Send-Time Optimization](#send-time-optimization) eller [AI Agents](#ai-agents) kan kräva aktivering av Adobe. Kontakta din Adobe-representant för att få information om din specifika licens och tillgängliga funktioner.

+++
