---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med innehållsoptimering
description: Lär dig hur ni kan använda innehållsoptimering för att leverera personaliserat och optimerat innehåll i era kampanjer och resor.
feature: Experimentation, Targeting
topic: Content Management
role: User
level: Beginner
keywords: optimering, målinriktning, experiment, A/B-testning, kampanjer, resor, personalisering
exl-id: 0f563d61-7a9e-46bf-adfb-5a26e63505b9
source-git-commit: 27de3d2171e6f6575eb66ada20f951f6cb3abc98
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 2%

---

# Kom igång med innehållsoptimering {#message-optimization}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_optimization"
>title="Innehållsoptimering"
>abstract="Med innehållsoptimering i Journey Optimizer kan du testa olika versioner av ditt innehåll och avgöra vilka som fungerar bäst. Ni kan använda målinriktning för att leverera personaliserat innehåll till specifika segment, experimentera för att testa flera variationer eller kombinera båda metoderna för sofistikerade optimeringsstrategier."

Innehållsoptimering ger er de verktyg ni behöver för att leverera rätt budskap till rätt målgrupp vid rätt tidpunkt. Genom att kombinera datadrivna insikter med kraftfulla personaliseringsfunktioner kan ni maximera engagemanget och konverteringarna i era kampanjer och resor.

Innehållsoptimering är tillgängligt i både [kampanjer](../campaigns/create-campaign.md) och [resor](../building-journeys/journey-gs.md), vilket gör att du kan använda samma optimeringsstrategier för alla kundkontaktytor.

➡️ [Lär dig hur du kan utnyttja innehållsoptimering i en kampanj i den här videon](#video)

## Optimeringsfunktioner {#capabilities}

Med innehållsoptimering i Journey Optimizer kan man

* [Använd målinriktning](optimization-targeting.md) för att leverera personaliserat innehåll till specifika målgruppssegment baserat på profilattribut, kontextuella data eller målgruppsmedlemskap.

* [Kör experiment](optimization-experimentation.md) för att testa flera innehållsvariationer och identifiera vilka som fungerar bäst baserat på dina framgångsmått.

* [Kombinera båda metoderna](optimization-combination.md) för att skapa sofistikerade optimeringsstrategier där du testar olika variationer för varje målsegment.

## Målinriktning jämfört med experimenterande {#targeting-vs-experimentation}

Genom att förstå skillnaden mellan målinriktning och experimenterande kan ni välja rätt optimeringsmetod för era mål.

**Målinriktning** använder deterministiska regler för att leverera personaliserat innehåll till specifika segment baserat på kända profilattribut, kontext eller målgruppsmedlemskap. Det ser till att rätt budskap når rätt målgrupp.

**Experimentationen** använder slumpmässig tilldelning för att testa flera innehållsvariationer och identifiera vilka som fungerar bäst. Det hjälper er att lära er vad som får flest gensvar hos er målgrupp genom datadriven testning.

Tabellen nedan sammanfattar de viktigaste skillnaderna:

| Funktion | Målinriktning | Experimentation |
|--------|-----------|-----------------|
| **Tilldelningsmetod** | Deterministisk - baserat på regler | Slumpmässigt - baserat på trafikallokering |
| **Baserat på** | Profilattribut, sammanhang, målgrupper | Slumpmässig fördelning |
| **Användningsfall** | Leverera relevant innehåll till kända segment | Identifiera vilket innehåll som fungerar bäst |
| **Exempel** | Visa olika kampanjer per plats | Testa två ämnesrader för att se vilka som blir fler |
| **Bäst för** | Personalization i stor skala | Optimering och inlärning |

![](../campaigns/assets/msg-optimization-experiment-vs-targeting.png){width="110%" zoomable="yes"}

## Vanliga användningsfall {#use-cases}

Här är några typiska scenarier där innehållsoptimering kan hjälpa dig att få bättre resultat:

Målinriktning:

* **Geografisk anpassning** - Skicka platsspecifika erbjudanden baserat på var kunderna finns. Du kan till exempel främja vinterkattor i kallare områden och badkläder i varmare klimat.

* **Enhetsoptimering** - Leverera enhetsspecifikt innehåll, till exempel skrivbordsoptimerade layouter för skrivbordsanvändare och mobiloptimerade layouter för smarttelefonanvändare.

Experimentation:

* **A/B-testning** - Testa olika ämnesrader, call-to-action-knappar eller kampanjerbjudanden för att ta reda på vilka som driver flest konverteringar.

* **Livscykelmarknadsföring** - Testa olika introduktionsmeddelanden för nya kunder jämfört med erbjudanden för befintliga kunder.

Kombination:

* **Avancerad segmentering** - Rikta kunderna efter lojalitetsnivå och testa olika belöningsmeddelanden inom varje nivå för att maximera engagemanget inom alla segment.

## Kom igång {#get-started}

Så här börjar du optimera ditt innehåll:

1. **Skapa en kampanj eller resa**: Konfigurera din [kampanj](../campaigns/create-campaign.md) eller [resa](../building-journeys/journey-gs.md) och lägg till minst en åtgärd.

1. **Välj optimeringsmetod**:
   * [Använd målinriktning](optimization-targeting.md) för att anpassa innehåll för specifika segment.
   * [Använd experimentering](optimization-experimentation.md) för att testa flera variationer.
   * [Kombinera båda](optimization-combination.md) för avancerad optimering.

1. **Definiera ditt innehåll**: Skapa olika innehållsvariationer för din optimeringsstrategi.

1. **Aktivera och övervaka**: Starta den optimerade kampanjen eller resan och spåra resultatet i [rapporterna](../reports/campaign-global-report-cja.md).

## Så fungerar det {#how-it-works}

När resan eller kampanjen är live utvärderas profiler utifrån de kriterier du har definierat. Baserat på dessa utvärderingar får varje profil den lämpligaste innehållsversionen:

1. **Profilutvärdering** - När en profil kommer in i din kampanj eller resa utvärderar Journey Optimizer deras attribut och kontext.

1. **Innehållstilldelning** - Baserat på din optimeringskonfiguration:
   * För **mål** får profiler som matchar specifika villkor motsvarande personaliserat innehåll.
   * För **experiment** tilldelas profiler slumpmässigt till olika innehållsvariationer baserat på dina inställningar för trafikallokering.
   * För **kombinationer** matchar profiler först en målningsregel och tilldelas sedan slumpmässigt till en av experimentvariationerna för det segmentet.

1. **Prestandaspårning** - Journey Optimizer spårar automatiskt engagemangsmått och konverteringsdata så att du kan identifiera vilket innehåll som fungerar bäst.

## Instruktionsvideo {#video}

Lär dig hur ni kan utnyttja innehållsoptimering i praktiken eller API-utlösta kampanjer. Ni får se hur ni kan rikta in er på undergrupper, skapa meddelandevarianter efter plats, aktivera reservinnehåll och köra flera experiment inom en och samma kampanj. Den här självstudiekursen handlar också om hur du hanterar flerkanalskampanjer samtidigt som du bibehåller meddelandets enhetlighet.

>[!VIDEO](https://video.tv.adobe.com/v/3470372?captions=swe&quality=12)

**Relaterade ämnen**

* [Skapa en kampanj](../campaigns/create-campaign.md)
* [Skapa en resa](../building-journeys/journey-gs.md)
* [Innehållsexperiment](../content-management/get-started-experiment.md)
