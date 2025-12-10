---
solution: Journey Optimizer
product: journey optimizer
title: Nyckelterminologi
description: Grundläggande termer och begrepp i Adobe Journey Optimizer
feature: Get Started
role: Admin, Developer, User
level: Beginner
source-git-commit: 4ae9e908d259dbd266417242cf9e65d693227061
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 7%

---

# Nyckelterminologi {#key-terminology}

Den här referenshandboken definierar de viktigaste termer du kommer att stöta på när du använder Adobe Journey Optimizer. Genom att förstå dessa koncept kan du tryggt navigera på plattformen och samarbeta effektivt med teamet.

>[!TIP]
>
>Detaljerade förklaringar av funktioner och arbetsflöden finns i de specifika dokumentationsavsnitten som är länkade i den här handboken.

## Villkor för kärnplattform {#core-terms}

| Villkor | Definition |
|------|------------|
| **Adobe Journey Optimizer** | En applikation för att skapa och leverera personaliserade meddelanden till kunder över alla kanaler (e-post, SMS, push-meddelanden, webb). Det gör det möjligt för er att utforma kundresor som svarar på kundåtgärder i realtid. |
| **Adobe Experience Platform** | Grunden till Adobe Journey Optimizer som samlar in och organiserar alla kunddata på ett och samma ställe. Det skapar enhetliga kundprofiler som Journey Optimizer använder för personalisering. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html){target="_blank"} |
| **Kundprofil i realtid** | En enhetlig realtidsvy över varje kund som kombinerar data från flera kanaler, inklusive online-, offline-, CRM- och tredjepartsdata. Varje profil uppdateras dynamiskt när kunderna interagerar med ert varumärke. [Läs mer](../audience/get-started-profiles.md) |
| **Sandbox** | En separat arbetsyta för testning och experimenterande utan att påverka kundkommunikationen. Adobe Journey Optimizer innehåller flera sandlådor för utvecklings-, testnings- och produktionsmiljöer. [Läs mer](../administration/sandboxes.md) |

## Resevillkor och kampanjvillkor {#journey-campaign-terms}

| Villkor | Definition |
|------|------------|
| **Resa** | En serie sammankopplade steg som vägleder kunderna genom upplevelser med ert varumärke över tid. Varje steg är baserat på kundåtgärder eller tidsutlösare, vilket möjliggör sekventiell, personaliserad interaktion. [Läs mer](../building-journeys/journey.md) |
| **Campaign** | En enda kommunikation eller en uppsättning meddelanden som skickas till en viss målgrupp. Till skillnad från resor som utvecklas över tid levererar kampanjer meddelanden enligt ett schema eller en utlösare, antingen direkt eller vid en viss tidpunkt. [Läs mer](../campaigns/get-started-with-campaigns.md) |
| **Händelse** | En åtgärd eller händelse som utlöser eller främjar en resa. Händelser kan vara kundåtgärder (att göra ett köp, överge en kundvagn) eller systemhändelser (datum/tid, dataändring). [Läs mer](../event/about-events.md) |
| **Kanal** | Den metod som används för att kommunicera med kunderna: e-post, SMS, push-meddelanden, meddelanden i appen, webben eller direktreklam. Varje kanal kräver en specifik konfiguration. [Läs mer](../configuration/get-started-configuration.md) |

## Kund- och målgruppsvillkor {#customer-audience-terms}

| Villkor | Definition |
|------|------------|
| **Målgrupp** | En grupp kunder som delar gemensamma egenskaper eller beteenden, t.ex.&quot;kunder som köpt under de senaste 30 dagarna&quot; eller&quot;lojalitetsprogram&quot;. Målgrupperna används för att inrikta sig på specifika kundsegment. [Läs mer](../audience/about-audiences.md) |
| **Målgruppskvalifikation** | Den automatiska process som inträffar när en kund går med eller lämnar en målgrupp. Journey Optimizer kan utlösa åtgärder när någon kommer in eller lämnar en viss målgrupp och säkerställa att relevant kommunikation sker i rätt tid. [Läs mer](../building-journeys/audience-qualification-events.md) |
| **Engagerbar målgrupp** | Antalet kundprofiler som du aktivt kan kontakta via Adobe Journey Optimizer baserat på ditt licensavtal. Detta avser vanligtvis profiler som använts under de senaste 12 månaderna. |
| **Testa profil** | Fantastiska profiler som används för att testa och förhandsgranska meddelanden innan de skickas till verkliga kunder. Testprofiler hjälper till att verifiera personalisering, innehåll och reslogik. [Läs mer](../audience/creating-test-profiles.md) |

## Innehåll och Personalization villkor {#content-terms}

| Villkor | Definition |
|------|------------|
| **Personalization** | Processen att skräddarsy innehåll för enskilda kunder med hjälp av profildata, preferenser och beteenden. Du kan till exempel infoga en kunds namn eller visa produktrekommendationer baserat på webbläsarhistorik. [Läs mer](../personalization/personalize.md) |
| **Innehållsmall** | En återanvändbar meddelandedesign som kan användas i flera kampanjer och resor för att upprätthålla varumärkets enhetlighet och snabba upp innehållsskapandet. [Läs mer](../content-management/content-templates.md) |
| **Fragment** | Ett återanvändbart innehållsblock (t.ex. ett sidhuvud, en sidfot eller en reklambanderoll) som kan användas i flera meddelanden för att säkerställa konsekvens och möjliggöra centraliserade uppdateringar. [Läs mer](../content-management/fragments.md) |
| **Startsida** | En fristående webbsida där kunderna kan välja bort eller avanmäla sig från kommunikation, prenumerera på tjänster eller tillhandahålla information via onlineformulär. [Läs mer](../landing-pages/get-started-lp.md) |

## Villkor för beslut och erbjudande {#decision-terms}

| Villkor | Definition |
|------|------------|
| **Beslutshantering** | En funktion som automatiskt väljer det bästa innehållet eller det bästa erbjudandet för varje kund baserat på profildata, kontext och affärsregler i realtid. [Läs mer](../offers/get-started/starting-offer-decisioning.md) |
| **Erbjudande** | Ett marknadsföringsmeddelande, en rabatt eller en kampanj som kan presenteras för kunderna. Erbjudandena innehåller regler för behörighet som avgör vilka kunder som kan få dem. [Läs mer](../offers/offer-library/creating-personalized-offers.md) |
| **Beslutspolicy** | En uppsättning regler och strategier som avgör vilket erbjudande som ska visas för vilken kund vid vilken tidpunkt, baserat på begränsningar som behörighet, prioritet och regler för begränsning. [Läs mer](../experience-decisioning/create-decision.md) |

## Data- och konfigurationsvillkor {#data-config-terms}

| Villkor | Definition |
|------|------------|
| **Schema** | Den struktur som definierar hur data ordnas i Adobe Experience Platform, inklusive fältnamn, datatyper och relationer. Scheman säkerställer att data är konsekventa över alla system. [Läs mer](../data/get-started-schemas.md) |
| **Datauppsättning** | En samling data (vanligtvis en tabell) som följer ett specifikt schema. Datauppsättningar lagrar kunddata, interaktionshändelser och annan information som används för personalisering. [Läs mer](../data/get-started-datasets.md) |

>[!NOTE]
>
>En omfattande ordlista med Adobe Experience Platform-termer finns i [Adobe Experience Platform-ordlistan](https://experienceleague.adobe.com/docs/experience-platform/landing/glossary.html){target="_blank"}.

## Relaterade ämnen {#related-topics}

* [Så här fungerar Journey Optimizer](understanding-ajo.md)
* [Kom igång med användargränssnittet](user-interface.md)
* [Välj roll och utbildningsväg](quick-start.md)

