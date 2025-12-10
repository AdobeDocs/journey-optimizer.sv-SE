---
solution: Journey Optimizer
product: journey optimizer
title: Förstå Journey Optimizer
description: Lär dig hur Adobe Journey Optimizer kan leverera personaliserade kundupplevelser med Adobe Experience Platform
feature: Get Started
role: Admin, Developer, User
level: Beginner
source-git-commit: a956684ab52f9045b5e1f84cc0b8d0071689873b
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 0%

---

# Förstå Journey Optimizer {#understanding-ajo}

Adobe Journey Optimizer (AJO) och Adobe Experience Platform (AEP) samarbetar för att möjliggöra datadriven personalisering i stor skala. På den här sidan beskrivs hur dessa system fungerar och hur deras viktigaste funktionsområden kombinerar för att leverera enastående kundupplevelser.

## Så här fungerar Journey Optimizer {#how-it-works}

Adobe Journey Optimizer fungerar som ett kontinuerligt flöde där data samlas in, analyseras och används för att skapa personaliserade kundresor.

![](assets/ajo-aep-architecture-diagram.png)

### Adobe Experience Platform: Grunden {#aep-foundation}

Adobe Experience Platform fungerar som ryggrad och gör det möjligt för varumärken att centralisera kunddata och aktivera dem för personaliserade upplevelser:

* **Dataplattform** - Centralt nav för att samla in, hantera och strukturera kunddata för att säkerställa konsekvens mellan system
* **Datainmatning (källor)** - Importera data från CRM-plattformar, webbplatser, mobilappar och molnlagring med fördefinierade anslutningar
* **Kundprofil i realtid** - Skapar enhetliga profiler genom att sammanfoga data från flera källor (e-postinteraktioner, butiksköp, webbbeteende)
* **Styrningslager** - Styr dataåtkomst, sekretessefterlevnad och säkerhet samtidigt som du följer regler

### Adobe Journey Optimizer: Orchestration Engine {#ajo-orchestration}

Adobe Journey Optimizer använder data och insikter från AEP för att leverera intelligenta, personaliserade kundupplevelser:

* **Kundförståelse** - Kundprofiler i realtid möjliggör segmentering i målgrupper för riktade meddelanden
* **Innehåll och erbjudanden** - Verktyg för att skapa, hantera och personalisera innehåll, logik i realtid för att välja det bästa erbjudandet för varje enskild person
* **Resurs- och kampanjhantering** - Automatiserar sekvenser av interaktioner (resor) eller schemalägger engångsinriktade meddelanden (kampanjer)
* **Leverans (anslutningar)** - Levererar meddelanden via kanaler som e-post, SMS, push-meddelanden och direktreklam. Exporterar data till externa system
* **Mätning och analys** - Håll koll på kundens engagemang och kampanjresultat med rapporter för kontinuerlig förbättring

### Kontinuerlig optimeringscykel {#optimization-cycle}

Det här ekosystemet fungerar som en kontinuerlig optimeringscykel. Data skapar förståelse för kunderna, vilket ger bättre underlag för personaliserat innehåll och beslut. Dessa är fördelade på resor, levereras över flera kanaler, mäts efter effektivitet och förfinas över tid.

![](../assets/do-not-localize/get-started-flow.png)

## Viktiga funktionsområden {#functional-areas}

Journey Optimizer har sju viktiga funktionsområden som fungerar ihop:

| Funktionsområde | Syfte | Viktiga aktiviteter |
|-----------------|---------|----------------|
| **Datahantering** | Organisera kunddata | Definiera scheman, skapa datauppsättningar, importera data från olika system |
| **Kundhantering** | Förstå vilka era kunder är | Bygg enhetliga profiler, lös identiteter, skapa målgrupper |
| **Innehållshantering** | Skapa personliga meddelanden | Designa e-postmeddelanden, hantera resurser, bygg mallar och fragment, personalisera innehåll |
| **Beslutshantering** | Välj det bästa erbjudandet i realtid | Hantera erbjudandebibliotek, definiera regler, tillämpa begränsningar, upprätta rankningslogik |
| **Resehantering** | Designa automatiserade kundupplevelser | Skapa resor med visuell designer, ange triggers, lägga till villkor och vänta steg |
| **Anslutningar** | Koppla samman datakällor och kanaler | Konfigurera källanslutningar, konfigurera kanaler, ansluta till externa plattformar |
| **Administration och sekretess** | Styr konfigurationen och regelefterlevnaden | Hantera användare, konfigurera sandlådor, konfigurera kanaler, hantera sekretessförfrågningar |

### Hur dessa områden fungerar tillsammans {#working-together}

Dessa funktionsområden fungerar i en kontinuerlig cykel:

1. **Datainmatning** - Dataflöden in i AEP, strukturerade med datahantering
2. **Kundförståelse** - Kundprofiler i realtid förenar data; Kundhantering skapar målgrupper
3. **Innehålls- och erbjudandestrategi** - Innehållshantering skapar meddelanden; Beslutshantering definierar erbjudandelogik
4. **Orchestration** - Resehantering mappar interaktioner över olika kanaler med kunddata, innehåll och beslut
5. **Leverans** - Anslutningar underlättar meddelandeleverans via kanaler eller delar data med externa system
6. **Mått** - Prestandadata ger tillbaka insikter för att förfina målgrupper, innehåll, beslut och resor
7. **Styrning** - Administrations- och sekretesskontroller säkerställer efterlevnad genom hela

## Arkitekturinformation {#architecture-details}

Här följer ett detaljerat arkitekturdiagram som visar hur Journey Optimizer kan integreras med Adobe Experience Platform:

![Adobe Journey Optimizer-arkitektur](assets/ajo-architecture.png)

Fyra program är inbyggda i Experience Platform: Adobe Real-Time Customer Data Platform, Journey Optimizer, Customer Journey Analytics och Adobe Mix Modeler. Journey Optimizer fungerar smidigt med dessa program men kan också fungera oberoende av varandra.

### Integrationspunkter {#integration-points}

Journey Optimizer kan integreras med Adobe Experience Platform på flera nivåer:

* **Datalager** - Delar samma kundprofil, identitetsdiagram och datauppsättningar i realtid
* **Tjänstlager** - Utnyttjar AEP styrning, sekretess och frågetjänster
* **Programlager** - Tillhandahåller resesamordning, beslutshantering och innehållshantering utöver AEP

Läs mer om [Adobe Journey Optimizer-ritningar](https://experienceleague.adobe.com/sv/docs/blueprints-learn/architecture/customer-journeys/journey-optimizer/journey-optimizer-overview){target="_blank"}.

## Integritet och säkerhet {#privacy-security}

Adobe Experience Cloud sekretess- och säkerhetspraxis gäller Adobe Journey Optimizer. Dessa åtgärder säkerställer efterlevnad av sekretessbestämmelser som GDPR, vilket gör att ni kan leverera personaliserade upplevelser samtidigt som ni behåller kundförtroendet.

[Läs mer om sekretess i Journey Optimizer](../privacy/get-started-privacy.md)

>[!MORELIKETHIS]
>
>* [Kom igång med Journey Optimizer](get-started.md)
>* [Nyckelterminologi](terminology.md)
>* [Användargränssnittshandbok](user-interface.md)
>* [Skyddsritningar och begränsningar](guardrails.md)

