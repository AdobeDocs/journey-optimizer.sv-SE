---
solution: Journey Optimizer
product: journey optimizer
title: Journeys vs Campaigns - Välj rätt metod
description: Jämför resor, kampanjer och samordnade kampanjer för att välja rätt metod för era marknadsföringsbehov i Adobe Journey Optimizer
feature: Journeys, Campaigns, Get Started, Overview
role: User
level: Beginner
keywords: resa, kampanj, iscensatt, jämförelse, val, beslut, arbetsflöde, realtid, batch, orkestrering, flera steg, schemalagd, API-utlöst, händelsestyrd
hide: true
hidefromtoc: true
source-git-commit: c1efa56fc3f3c93bdc4b9c7a9f4e81b58cbcff72
workflow-type: tm+mt
source-wordcount: '1453'
ht-degree: 1%

---


# Resor jämfört med kampanjer: Välj rätt metod {#journeys-vs-campaigns}

Adobe Journey Optimizer erbjuder tre kraftfulla metoder för att nå ut till och engagera era kunder. Att förstå när de ska användas är avgörande för att skapa effektiva marknadsföringsupplevelser.

Den här guiden hjälper dig att välja mellan **Journeys**, **Åtgärdskampanjer**, **API-utlösta kampanjer** och **Orchestrerade-kampanjer** baserat på era specifika marknadsföringsbehov.

## Snabb jämförelse - översikt {#quick-overview}

| Metod | Bäst för | Körningsformat |
|----------|----------|-----------------|
| **Resor** | Flerstegs kundupplevelser i realtid med villkorlig logik | 1:1-samordning - varje profil i sin egen takt |
| **Åtgärdskampanjer** | Schemalagda eller återkommande sändningar till målgrupper | Batchkörning - målgruppen bearbetas tillsammans vid sändning |
| **API-utlösta kampanjer** | Händelsestyrda eller transaktionsstyrda meddelanden från externa system | On demand-körning - utlöses av API-anrop med nyttolast |
| **Samordnade kampanjer** | Komplexa batcharbetsflöden med segmentering av flera enheter | Batcharbetsyta - alla profiler bearbetas tillsammans |

## Detaljerad jämförelse {#detailed-comparison}

Använd den här omfattande tabellen för att förstå de viktigaste skillnaderna:

| Funktion | Resor | Åtgärdskampanjer | API-utlösta kampanjer | Samordnade kampanjer |
|---------|----------|------------------|------------------------|----------------------|
| **Huvudsyfte** | Flerstegs-1:1-samordning med kundkontext i realtid | Engångs- eller återkommande meddelandeleveranser till målgrupper | Transaktionella eller händelsestyrda meddelanden som initierats av externa system | Batchkampanjer i flera steg med komplexa segmenteringsarbetsflöden |
| **Arbetsytans typ** | 1:1 arbetsyta - varje profil rör sig i sin egen takt | Ingen arbetsyta - körning av en åtgärd | Ingen arbetsyta - körning av en åtgärd | Batcharbetsyta - alla profiler bearbetas tillsammans |
| **Körningsflöde** | Sekventiella åtgärder, profilen upprätthåller statusen under hela resan | Samtidig körning för hela målgruppen | Omedelbar körning per API-anrop | Batcharbetsflöde i flera steg med aktiviteter och övergångar |
| **Anmälningsmekanism** | Event, målgrupper, kvalifikationer, affärsevenemang | Manuell aktivering och schema | API-anrop från externt system | Schemalagd körning av batcharbetsflöde |
| **Datamodell** | Realtidsprofil + händelsedata | Profildata från Experience Platform målgrupper | API-nyttolastdata med valfri profilsökning | Relationsdata för flera enheter (profiler, produkter, butiker, bokningar) |
| **Segmentering** | Förbyggda målgrupper + realtidsförhållanden | Förbyggda målgrupper från Experience Platform | Belastningsstyrd målinriktning (ingen schemalagd målgrupp) | Målgrupper på arbetsytan med exakta antal |
| **Profilbearbetning** | Individuell, realtid (allteftersom händelser inträffar) | Gruppera, alla samtidigt | Per API-anrop, nyttolastdriven | Gruppera, allt tillsammans med stöd för flera enheter |
| **Personalization** | Kontextdata i realtid + profilattribut | Profilattribut | Nyttolastdata + valfria profilattribut | Multientitetsdata för precisionsanpassning |
| **Komplexitet** | Flera steg med förgreningar, väntetider och villkor | En åtgärd eller ett enkelt arbetsflöde | En åtgärd med nyttolastmappning | Batcharbetsflöden i flera steg med segmentering, berikning, delning |
| **Bäst för** | Kundlivscykelresor, introduktion, övergivna kundvagnar | Kampanjkampanjer, nyhetsbrev, meddelanden | Beställningsbekräftelser, leveransvarningar, lösenordsåterställningar | Komplexa säsongskampanjer, flerstegskampanjer, produktlanseringar |
| **Timing** | Kontinuerlig, alltid aktiv när den publicerats | Schemalagda start-/slutdatum | On-demand, händelsestyrd via API | Batchkörning enligt schema |
| **Tillståndshantering** | Underhåller kundens tillstånd för åtgärder i realtid | Tillståndslös körning | Tillståndslös exekvering per anrop | Batchbearbetning med arbetstabeller |
| **Använd när** | Flera kontaktytor krävs med beslutslogik i realtid | Enkelt budskap till en viss målgrupp vid en viss tidpunkt | Det externa systemet måste utlösa ett meddelande omedelbart | Kräver komplex segmentering, data för flera enheter eller exakta antal före sändning |
| **Unika funktioner** | Reaktioner i realtid, vänteaktiviteter, profilbaserad pacing | Schemaläggning, målgruppsanpassning, priskontroll | API-nyttolastmappning, system-till-system-utlösare | Relationsdatauppsättningar, segmentering av flera enheter, exakt antal, sändning på flera nivåer |

## Beslutsguide {#decision-guide}

Välj rätt metod genom att följa det här beslutsträdet:

### Steg 1: Vad är ditt krav på exekvering?

**Individuella svar i realtid på kundbeteende?**
→ **Använd resor**
* Profilerna måste flyttas i sin egen takt
* Villkorlig logik baserad på beteende
* Kontext i realtid är avgörande

**Enkel meddelandeleverans till en målgrupp vid en schemalagd tidpunkt?**
→ **Använd åtgärdskampanjer**
* Alla profiler får meddelanden samtidigt
* Schemalagda eller återkommande utskick
* Ingen komplex flerstegslogik behövs

**Omedelbart meddelande som utlöses av ett externt system?**
→ **Använd API-utlösta kampanjer**
* Utlöses på begäran via API-anrop
* Belastningsdriven personalisering
* Ingen komplex flerstegslogik behövs

**Komplext grupparbetsflöde med avancerad segmentering?**
→ **Använd samordnade kampanjer**
* Behöver data för flera enheter (produkter, butiker, bokningar)
* Kräv exakta antal före sändning
* Batchbearbetning i flera steg med delningar och berikning

### Steg 2: Validera ditt val

| Dina behov | Rekommenderad metod | Varför |
|-----------|---------------------|-----|
| Välkomna nya kunder med stegvis introduktion | Resor | Realtidsinmatning, flera kontaktytor, villkorsstyrda banor |
| Skicka månatliga nyhetsbrev till prenumeranter | Åtgärdskampanj | Enkelt schemalagt meddelande till målgruppen |
| Avbruten kundvagn med påminnelsesekvens | Resor | Utlösare i realtid, väntetider, villkorlig uppföljning |
| Kampanjannonsering till alla kunder | Åtgärdskampanj | Engångsmeddelande, direktleverans |
| Engagera inaktiva användare på nytt baserat på beteende | Resor | Utlöses av målgruppskvalifikationer, personaliserad kundresa |
| Flash-försäljning utlöses av en affärshändelse | Resor (affärshändelse) | Realtidsutlösare som påverkar flera kunder |
| Säsongskampanj med produktkatalogintegration | Samlad kampanj | Data för flera enheter, komplex segmentering, exakt antal |
| API-utlöst transaktionsmeddelande | API-utlöst kampanj | Extern systemutlösare, omedelbar leverans |
| Flernivåutskick per bokning | Samlad kampanj | Relationer för flera enheter, ett meddelande per bokning |

## Förklaring av viktiga distinktioner {#key-distinctions}

### Resor: 1:1 Orchestration i realtid

**Vad gör det unikt:**
* Varje profil bevarar individuellt läge och sammanhang
* Profilerna läggs in och utvecklas i sin egen takt
* beslutsfattande i realtid baserat på beteende och händelser
* Vänteaktiviteter skapar personaliserad timing
* Villkorlig förgreningslogik skapar unika sökvägar per profil

**Exempelflöde:**

```
Customer A: Abandoned cart → Wait 2 hours → No purchase? → Send reminder → Purchased? → End
Customer B: Abandoned cart → Wait 2 hours → Already purchased → End immediately
```

Varje kund upplever sin egen resetidslinje baserat på sina handlingar.

[Läs mer om Journeys](../building-journeys/journey.md)

### Kampanjer: Enkel batchleverans eller utlöst leverans

**Vad gör det unikt:**
* Alla profiler behandlas likadant och samtidigt
* Tillståndslös exekvering - inget sammanhang bevaras
* Enkel schemaläggning eller API-utlösning
* Idealiskt för tevekommunikation

**Exempelflöde:**

```
Monday 9 AM → Send newsletter to 100,000 subscribers → All receive simultaneously
```

Alla får samma meddelande samtidigt.

**Typer:**
* **Åtgärdskampanjer**: Schemalagd leverans till målgrupper (en gång eller återkommande)
* **API-utlösta kampanjer**: On demand-leverans utlöses av ett API-anrop med nyttolastdata

[Läs mer om kampanjer](../campaigns/get-started-with-campaigns.md)

### Samordnade kampanjer: Arbetsflöden för batcharbetsyta

**Vad gör det unikt:**
* Batcharbetsyta med aktiviteter och övergångar (liknande arbetsytan på resan men grupporienterad)
* Stöd för relationsdata för flera enheter (profiler + produkter + butiker + bokningar)
* On-demand-målgruppsuppbyggnad på arbetsytan
* Exakta antal innan de skickas (synlighet före sändning)
* Flernivåsändning (ett meddelande per enhet, t.ex. per bokning)
* Alla profiler som bearbetas tillsammans

**Exempelflöde:**

```
Query customers → Filter by purchase history → Split by region → 
Enrich with product data → Build segments → Send personalized offers → All in one batch execution
```

Kombinerar arbetsflödeskomplexitet med batchkörning av kampanjer.

[Läs mer om samordnade kampanjer](../orchestrated/gs-orchestrated-campaigns.md)

## Använd exempel på exempel {#use-cases}

### Användningsexempel på resa

* **Återställning av kundvagnsåsidosättning**: Utlöses av en händelse om kundvagn läggs till, vänta på utcheckning, skicka påminnelser om inget köp görs
* **Kundintroduktion**: Välkomstserie i flera steg med anpassat innehåll baserat på profildata
* **Bonusnivåuppgradering**: Utlöses när kunden når en ny nivå, skickar gratulationer och förmåner
* **Födelsedagskampanjer**: Anmälan baseras på födelsedatum, personaliserade erbjudanden
* **Återengagemang**: Utlöses av målgruppskvalifikation (inaktivitet), progressiv utåtriktad

### Användningsexempel för kampanj (åtgärd och API-utlösta)

**Åtgärdskampanjer:**
* **Månatliga nyhetsbrev**: Schemalagd batchleverans till prenumerantsegment
* **Kampanjmeddelanden**: Tidskänsliga erbjudanden för målgrupper
* **Produktlanseringar**: Koordinerat meddelande till alla kunder
* **Säsongshälsningar**: Helgdagsmeddelanden på vissa datum

**API-utlösta kampanjer:**
* **Beställningsbekräftelser**: Utlöses av e-handelssystemet efter köp
* **Leveransmeddelanden**: Utlöses av logistiksystemet
* **Kontovarningar**: Utlöses av system för upptäckt av bedrägeri
* **Lösenordsåterställning**: Utlöses av användaråtgärd i programmet

### Samordnade kampanjanvändningsfall

* **Säsongskampanj med katalogintegration**: Fråga efter produktkatalog, identifiera berättigade kunder, segmentera efter önskemål, skicka personaliserade produktrekommendationer
* **Butiksspecifika kampanjer**: Rikta kunderna mot specifika butiksplatser med lagerdata
* **Flerbokskommunikation**: Skicka ett meddelande per bokning (hotellbokningar, flygbokningar)
* **Komplex segmentsamordning**: Bygg målgrupper steg för steg med berikning från flera datakällor
* **Validering före sändning**: Få exakt antal mottagare innan du startar större kampanjer

## Tillgänglighet {#feature-availability}

### Kanaler

| Kanal | Resor | Åtgärdskampanjer | API-utlösta kampanjer | Samordnade kampanjer |
|---------|:--------:|:----------------:|:-----------------------:|:---------------------:|
| E-post | ✅ | ✅ | ✅ | ✅ |
| Push | ✅ | ✅ | ✅ | ✅ |
| SMS | ✅ | ✅ | ✅ | ✅ |
| I appen | ✅ | ✅ | ✅ | ❌ |
| Webb | ✅ | ✅ | ❌ | ❌ |
| Kodbaserad | ✅ | ✅ | ❌ | ❌ |
| Innehållskort | ✅ | ✅ | ❌ | ❌ |
| Direktmeddelande | ✅ | ✅ | ❌ | ❌ |

### Avancerade funktioner

| Funktion | Resor | Åtgärdskampanjer | API-utlösta kampanjer | Samordnade kampanjer |
|-----------|:--------:|:----------------:|:-----------------------:|:---------------------:|
| Flerstegsarbetsflöden | ✅ | ❌ | ❌ | ✅ |
| Utlösare i realtid | ✅ | ❌ | ✅ | ❌ |
| Vänta på aktiviteter | ✅ | ❌ | ❌ | ✅ |
| Villkorlig förgrening | ✅ | ❌ | ❌ | ✅ |
| Schemalagd körning | ✅ | ✅ | ✅ | ✅ |
| API-utlösare | ❌ | ❌ | ✅ | ❌ |
| Data för flera enheter | ❌ | ❌ | ❌ | ✅ |
| Exakt antal för-sändning | ❌ | ❌ | ❌ | ✅ |
| On-demand-segmentering | ❌ | ❌ | ❌ | ✅ |
| Optimering vid sändning | ✅ | ✅ | ✅ | ✅ |
| A/B-testning | ✅ | ✅ | ❌ | ❌ |
| Arbetsflöden för godkännande | ✅ | ✅ | ✅ | ❌ |

## Vanliga frågor {#common-questions}

+++ Kan jag kombinera resor och kampanjer i min marknadsföringsstrategi?

Absolut! De flesta organisationer använder alla tre metoder för olika scenarier:

* Resor för beteendeengagemang i realtid
* Åtgärdskampanjer för schemalagd sändningskommunikation
* API-utlösta kampanjer för transaktionsmeddelanden
* Samordnade kampanjer för komplexa, dataintensiva gruppkampanjer

+++

+++ Kan jag omvandla en kampanj till en resa eller vice versa?

Nej, du måste återskapa upplevelsen i rätt format. Men ni kan återanvända innehåll, målgrupper och logiska koncept.

+++

+++ Vilken metod är enklare att bygga?

Action Campaigns är oftast det enklaste (ett enda meddelande till en målgrupp), följt av API-utlösta kampanjer, resor (mer komplexa med flerstegslogik) och samordnade kampanjer (mest komplexa på grund av arbetsflöden på arbetsytan och funktioner för flera enheter).

+++

+++ Vilken skala passar bäst för stora målgrupper?

Alla tre kan skalas bra, men:

* **Läs målgrupper** och **Åtgärdskampanjer** är optimerade för stora grupper
* **Orchestrerade kampanjer** kan inte användas vid komplex segmentering med stora datamängder
* **Unitary Journeys** bearbetar profiler individuellt, så skalan beror på händelsens volym

+++

+++ Kan jag använda samma målgrupp på alla resor och i alla kampanjer?

Ja, målgrupper som skapats i Adobe Experience Platform kan användas på alla tre inriktningarna.

+++

## Nästa steg {#next-steps}

Vill du börja bygga? Utforska den detaljerade dokumentationen för det sätt du valt:

* **[Kom igång med resor](../building-journeys/journey.md)** - Lär dig mer om resetyper, designer och arbetsflöde
* **[Kom igång med kampanjer](../campaigns/get-started-with-campaigns.md)** - Utforska åtgärder och API-utlösta kampanjer
* **[Kom igång med samordnade kampanjer](../orchestrated/gs-orchestrated-campaigns.md)** - Upptäck arbetsflöden för arbetsytan i batch

**Behöver du mer hjälp med att bestämma dig?**
* [Jämförelse av resetyper](../building-journeys/journey.md#journey-types-comparison)
* [Jämförelse av kampanjtyper](../campaigns/get-started-with-campaigns.md#campaign-types)
* [Vanliga frågor om resor](../building-journeys/journey-faq.md)
* [Vanliga frågor om samordnade kampanjer](../orchestrated/orchestrated-campaigns-faq.md)

