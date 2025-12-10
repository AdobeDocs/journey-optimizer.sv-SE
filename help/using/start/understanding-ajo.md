---
solution: Journey Optimizer
product: journey optimizer
title: Förstå Journey Optimizer
description: Lär dig hur Adobe Journey Optimizer kan leverera personaliserade kundupplevelser med Adobe Experience Platform
feature: Get Started
role: Admin, Developer, User
level: Beginner
source-git-commit: 87f714e380957b40df196652ac37d1e6cd611925
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 2%

---

# Förstå Journey Optimizer {#understanding-ajo}

Adobe Journey Optimizer och Adobe Experience Platform samarbetar för att möjliggöra datadriven personalisering i stor skala. På den här sidan beskrivs hur dessa system fungerar och hur deras viktigaste funktionsområden kombinerar för att leverera enastående kundupplevelser. [Lär dig mer om nyckelfunktioner](get-started.md) | [ Utforska nyckelterminologi ](terminology.md)

## Så här fungerar Journey Optimizer {#how-it-works}

Adobe Journey Optimizer fungerar som ett kontinuerligt flöde där data samlas in, analyseras och används för att skapa personaliserade kundresor.

![](assets/ajo-aep-architecture-diagram.png)

### Adobe Experience Platform: Grunden {#aep-foundation}

Adobe Experience Platform fungerar som ryggrad och gör det möjligt för varumärken att centralisera kunddata och aktivera dem för personaliserade upplevelser:

* **Dataplattform** - Centralt nav för att samla in, hantera och strukturera kunddata för att säkerställa konsekvens mellan system. [Läs om scheman och datauppsättningar](../data/get-started-schemas.md)
* **Datainmatning (källor)** - Importera data från CRM-plattformar, webbplatser, mobilappar och molnlagring med hjälp av färdiga anslutningar. [Utforska datakällor](get-started-sources.md)
* **Kundprofil i realtid** - Skapar enhetliga profiler genom att sammanfoga data från flera källor (e-postinteraktioner, butiksköp, webbbeteende). [Läs om profiler](../audience/get-started-profiles.md)
* **Styrningslager** - Styr dataåtkomst, sekretessefterlevnad och säkerhet samtidigt som du följer regler. [Visa sekretessdokumentation](../privacy/get-started-privacy.md)

### Adobe Journey Optimizer: Orchestration Engine {#ajo-orchestration}

Adobe Journey Optimizer använder data och insikter från Adobe Experience Platform för att leverera intelligenta, personaliserade kundupplevelser:

* **Kundförståelse** - Kundprofiler i realtid möjliggör segmentering i målgrupper för riktade meddelanden. [Skapa målgrupper](../audience/about-audiences.md)
* **Innehåll och erbjudanden** - Verktyg för att skapa, hantera och personalisera innehåll, logik i realtid för att välja det bästa erbjudandet för varje individ. [Designa innehåll](../../rp_landing_pages/content-management-landing-page.md) | [Hantera erbjudanden](../offers/get-started/starting-offer-decisioning.md)
* **Resurs- och kampanjhantering** - Automatiserar sekvenser av interaktioner (resor) eller schemalägger engångsinriktade meddelanden (kampanjer). [Skapa resor](../building-journeys/journey-gs.md) | [Skapa kampanjer](../campaigns/get-started-with-campaigns.md)
* **Leverans (anslutningar)** - Levererar meddelanden via kanaler som e-post, SMS, push-meddelanden och direktreklam. Exporterar data till externa system. [Konfigurera kanaler](../configuration/get-started-configuration.md)
* **Mätning och analys** - Håll koll på kundens engagemang och kampanjresultat med rapporter för kontinuerlig förbättring. [Visa rapporter](../reports/campaign-global-report-cja.md)

### Kontinuerlig optimeringscykel {#optimization-cycle}

Det här ekosystemet fungerar som en kontinuerlig optimeringscykel. Data skapar förståelse för kunderna, vilket ger bättre underlag för personaliserat innehåll och beslut. Dessa är fördelade på resor, levereras över flera kanaler, mäts efter effektivitet och förfinas över tid.

![](../assets/do-not-localize/get-started-flow.png)

## Viktiga funktionsområden {#functional-areas}

Journey Optimizer har sju viktiga funktionsområden som fungerar ihop:

| Funktionsområde | Syfte | Viktiga aktiviteter |
|-----------------|---------|----------------|
| **Datahantering** | Organisera kunddata | Definiera scheman, skapa datauppsättningar och importera data från olika system. [Läs mer](../data/get-started-schemas.md) |
| **Kundhantering** | Förstå vilka era kunder är | Skapa enhetliga profiler, lös identiteter, skapa målgrupper. [Läs mer](../audience/get-started-profiles.md) |
| **Innehållshantering** | Skapa personliga meddelanden | Designa e-postmeddelanden, hantera resurser, bygg mallar och fragment, personalisera innehåll. [Läs mer](../../rp_landing_pages/content-management-landing-page.md) |
| **Beslutshantering** | Välj det bästa erbjudandet i realtid | Hantera erbjudandebiblioteket, definiera regler, tillämpa begränsningar och upprätta rangordningslogik. [Läs mer](../offers/get-started/starting-offer-decisioning.md) |
| **Resehantering** | Designa automatiserade kundupplevelser | Skapa resor med visuell designer, ställ in triggers, lägg till villkor och vänta steg. [Läs mer](../building-journeys/journey-gs.md) |
| **Anslutningar** | Koppla samman datakällor och kanaler | Konfigurera källanslutningar, konfigurera kanaler, ansluta till externa plattformar. [Läs mer](../configuration/get-started-configuration.md) |
| **Administration och sekretess** | Styr konfigurationen och regelefterlevnaden | Hantera användare, konfigurera sandlådor, konfigurera kanaler och hantera sekretessförfrågningar. [Läs mer](../administration/permissions.md) |

### Hur dessa områden fungerar tillsammans {#working-together}

Dessa funktionsområden fungerar i en kontinuerlig cykel:

1. **Datainmatning** - Dataflöden in i Adobe Experience Platform, strukturerade med datahantering
2. **Kundförståelse** - Kundprofiler i realtid förenar data; Kundhantering skapar målgrupper
3. **Innehålls- och erbjudandestrategi** - Innehållshantering skapar meddelanden; Beslutshantering definierar erbjudandelogik
4. **Orchestration** - Resehantering mappar interaktioner över olika kanaler med kunddata, innehåll och beslut
5. **Leverans** - Anslutningar underlättar meddelandeleverans via kanaler eller delar data med externa system
6. **Mått** - Prestandadata ger tillbaka insikter för att förfina målgrupper, innehåll, beslut och resor
7. **Styrning** - Administrations- och sekretesskontroller säkerställer efterlevnad genom hela

## Arkitekturinformation {#architecture-details}

Här följer ett detaljerat arkitekturdiagram som visar hur Journey Optimizer kan integreras med Adobe Experience Platform. [Navigera i gränssnittet](user-interface.md) för att utforska de här komponenterna i praktiken.

![Adobe Journey Optimizer-arkitektur](assets/ajo-architecture.png)

Fyra program är inbyggda i Experience Platform: Adobe Real-Time Customer Data Platform, Journey Optimizer, Customer Journey Analytics och Adobe Mix Modeler. Journey Optimizer fungerar smidigt med dessa program men kan också fungera oberoende av varandra. [Granska säkerhetsutkast och begränsningar](guardrails.md) för implementeringsfrågor.

### Integrationspunkter {#integration-points}

Journey Optimizer kan integreras med Adobe Experience Platform på flera nivåer:

* **Datalager** - Delar samma kundprofil, identitetsdiagram och datauppsättningar i realtid
* **Tjänstlager** - Utnyttjar Adobe Experience Platform styrning, sekretess och frågetjänster
* **Programlager** - Tillhandahåller resesamordning, beslutshantering och innehållshantering utöver Adobe Experience Platform

Läs mer om [Adobe Journey Optimizer-ritningar](https://experienceleague.adobe.com/en/docs/blueprints-learn/architecture/customer-journeys/journey-optimizer/journey-optimizer-overview){target="_blank"}.

## Integritet och säkerhet {#privacy-security}

Adobe Experience Cloud sekretess- och säkerhetspraxis gäller Adobe Journey Optimizer. Dessa åtgärder säkerställer efterlevnad av sekretessbestämmelser som GDPR, vilket gör att ni kan leverera personaliserade upplevelser samtidigt som ni behåller kundförtroendet. [Läs mer om sekretess i Journey Optimizer](../privacy/get-started-privacy.md)
