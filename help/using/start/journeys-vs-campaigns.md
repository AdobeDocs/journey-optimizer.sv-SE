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
source-git-commit: 8ea2a0fe685678d41004d549443a1757eb30c765
workflow-type: tm+mt
source-wordcount: '1344'
ht-degree: 1%

---


# Resor jämfört med kampanjer: Välj rätt metod {#journeys-vs-campaigns}

Adobe Journey Optimizer erbjuder tre kraftfulla metoder för att nå ut till och engagera era kunder. Att förstå när de ska användas är avgörande för att skapa effektiva marknadsföringsupplevelser.

Den här guiden hjälper dig att välja mellan **Journeys**, **Campaigns** (Action &amp; API-utlösta) och **Orchestrated Campaigns** baserat på era specifika marknadsföringsbehov.

## Snabb jämförelse - översikt {#quick-overview}

| Metod | Bäst för | Körningsformat |
|----------|----------|-----------------|
| **Resor** | Flerstegs kundupplevelser i realtid med villkorlig logik | 1:1-samordning - varje profil i sin egen takt |
| **Kampanjer (Action &amp; API)** | Enkel, schemalagd eller utlöst meddelandeleverans | Batch- eller API-utlösta - alla profiler samtidigt |
| **Samordnade kampanjer** | Komplexa batcharbetsflöden med segmentering av flera enheter | Batcharbetsyta - alla profiler bearbetas tillsammans |

## Detaljerad jämförelse {#detailed-comparison}

Använd den här omfattande tabellen för att förstå de viktigaste skillnaderna:

| Funktion | Resor | Kampanjer (åtgärd och API-utlösta) | Samordnade kampanjer |
|---------|----------|-----------------------------------|----------------------|
| **Huvudsyfte** | Flerstegs-1:1-samordning med kundkontext i realtid | Engångs- eller återkommande meddelandeleveranser till målgrupper | Batchkampanjer i flera steg med komplexa segmenteringsarbetsflöden |
| **Arbetsytans typ** | 1:1 arbetsyta - varje profil rör sig i sin egen takt | Ingen arbetsyta - körning av en åtgärd | Batcharbetsyta - alla profiler bearbetas tillsammans |
| **Körningsflöde** | Sekventiella åtgärder, profilen upprätthåller statusen under hela resan | Samtidig körning för hela målgruppen | Batcharbetsflöde i flera steg med aktiviteter och övergångar |
| **Anmälningsmekanism** | Event, målgrupper, kvalifikationer, affärsevenemang | Manuell aktivering, schemalagd eller API-utlösare | Schemalagd körning av batcharbetsflöde |
| **Datamodell** | Realtidsprofil + händelsedata | Profildata + API-nyttolast | Relationsdata för flera enheter (profiler, produkter, butiker, bokningar) |
| **Segmentering** | Förbyggda målgrupper + realtidsförhållanden | Förbyggda målgrupper från Experience Platform | Målgrupper på arbetsytan med exakta antal |
| **Profilbearbetning** | Individuell, realtid (allteftersom händelser inträffar) | Gruppera, alla samtidigt | Gruppera, allt tillsammans med stöd för flera enheter |
| **Personalization** | Kontextdata i realtid + profilattribut | Profilattribut + API-nyttolastdata | Multientitetsdata för precisionsanpassning |
| **Komplexitet** | Flera steg med förgreningar, väntetider och villkor | En åtgärd eller ett enkelt arbetsflöde | Batcharbetsflöden i flera steg med segmentering, berikning, delning |
| **Bäst för** | Kundlivscykelresor, introduktion, övergivna kundvagnar | Kampanjkampanjer, nyhetsbrev, meddelanden, transaktionsmeddelanden | Komplexa säsongskampanjer, flerstegskampanjer, produktlanseringar |
| **Timing** | Kontinuerlig, alltid aktiv när den publicerats | Schemalagda start-/slutdatum eller API-utlösta | Batchkörning enligt schema |
| **Tillståndshantering** | Underhåller kundens tillstånd för åtgärder i realtid | Tillståndslös körning | Batchbearbetning med arbetstabeller |
| **Använd när** | Flera kontaktytor krävs med beslutslogik i realtid | Enkelt budskap till målgruppen vid en viss tidpunkt | Kräver komplex segmentering, data för flera enheter eller exakta antal före sändning |
| **Unika funktioner** | Reaktioner i realtid, vänteaktiviteter, profilbaserad pacing | Enkel schemaläggning, API-utlösare, tariffkontroll | Relationsdatauppsättningar, segmentering av flera enheter, exakt antal, sändning på flera nivåer |

## Beslutsguide {#decision-guide}

Välj rätt metod genom att följa det här beslutsträdet:

### Steg 1: Vad är ditt krav på exekvering?

**Individuella svar i realtid på kundbeteende?**
→ **Använd resor**
- Profilerna måste flyttas i sin egen takt
- Villkorlig logik baserad på beteende
- Kontext i realtid är avgörande

**Enkel meddelandeleverans till en publik?**
→ **Använd Action- eller API-utlösta kampanjer**
- Alla profiler får meddelanden samtidigt
- Schemalagd eller utlöst via API
- Ingen komplex flerstegslogik behövs

**Komplext grupparbetsflöde med avancerad segmentering?**
→ **Använd samordnade kampanjer**
- Behöver data för flera enheter (produkter, butiker, bokningar)
- Kräv exakta antal före sändning
- Batchbearbetning i flera steg med delningar och berikning

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
- Varje profil bevarar individuellt läge och sammanhang
- Profilerna läggs in och utvecklas i sin egen takt
- beslutsfattande i realtid baserat på beteende och händelser
- Vänteaktiviteter skapar personaliserad timing
- Villkorlig förgreningslogik skapar unika sökvägar per profil

**Exempelflöde:**

```
Customer A: Abandoned cart → Wait 2 hours → No purchase? → Send reminder → Purchased? → End
Customer B: Abandoned cart → Wait 2 hours → Already purchased → End immediately
```

Varje kund upplever sin egen resetidslinje baserat på sina handlingar.

[Läs mer om Journeys](../building-journeys/journey.md)

### Kampanjer: Enkel batchleverans eller utlöst leverans

**Vad gör det unikt:**
- Alla profiler behandlas likadant och samtidigt
- Tillståndslös exekvering - inget sammanhang bevaras
- Enkel schemaläggning eller API-utlösning
- Idealiskt för tevekommunikation

**Exempelflöde:**

```
Monday 9 AM → Send newsletter to 100,000 subscribers → All receive simultaneously
```

Alla får samma meddelande samtidigt.

**Typer:**
- **Åtgärdskampanjer**: Schemalagd leverans (en gång eller återkommande)
- **API-utlösta kampanjer**: Utlöses via API-anrop från externa system

[Läs mer om kampanjer](../campaigns/get-started-with-campaigns.md)

### Samordnade kampanjer: Arbetsflöden för batcharbetsyta

**Vad gör det unikt:**
- Batcharbetsyta med aktiviteter och övergångar (liknande arbetsytan på resan men grupporienterad)
- Stöd för relationsdata för flera enheter (profiler + produkter + butiker + bokningar)
- On-demand-målgruppsuppbyggnad på arbetsytan
- Exakta antal innan de skickas (synlighet före sändning)
- Flernivåsändning (ett meddelande per enhet, t.ex. per bokning)
- Alla profiler som bearbetas tillsammans

**Exempelflöde:**

```
Query customers → Filter by purchase history → Split by region → 
Enrich with product data → Build segments → Send personalized offers → All in one batch execution
```

Kombinerar arbetsflödeskomplexitet med batchkörning av kampanjer.

[Läs mer om samordnade kampanjer](../orchestrated/gs-orchestrated-campaigns.md)

## Använd exempel på exempel {#use-cases}

### Användningsexempel på resa

&#x200B;* **Återställning av kundvagnsåsidosättning**: Utlöses av en händelse om kundvagn läggs till, vänta på utcheckning, skicka påminnelser om inget köp görs
&#x200B;* **Kundintroduktion**: Välkomstserie i flera steg med anpassat innehåll baserat på profildata
&#x200B;* **Bonusnivåuppgradering**: Utlöses när kunden når en ny nivå, skickar gratulationer och förmåner
&#x200B;* **Födelsedagskampanjer**: Anmälan baseras på födelsedatum, personaliserade erbjudanden
&#x200B;* **Återengagemang**: Utlöses av målgruppskvalifikation (inaktivitet), progressiv utåtriktad

### Användningsexempel för kampanj (åtgärd och API-utlösta)

**Åtgärdskampanjer:**
&#x200B;* **Månatliga nyhetsbrev**: Schemalagd batchleverans till prenumerantsegment
&#x200B;* **Kampanjmeddelanden**: Tidskänsliga erbjudanden för målgrupper
&#x200B;* **Produktlanseringar**: Koordinerat meddelande till alla kunder
&#x200B;* **Säsongshälsningar**: Helgdagsmeddelanden på vissa datum

**API-utlösta kampanjer:**
&#x200B;* **Beställningsbekräftelser**: Utlöses av e-handelssystemet efter köp
&#x200B;* **Leveransmeddelanden**: Utlöses av logistiksystemet
&#x200B;* **Kontovarningar**: Utlöses av system för upptäckt av bedrägeri
&#x200B;* **Lösenordsåterställning**: Utlöses av användaråtgärd i programmet

### Samordnade kampanjanvändningsfall

&#x200B;* **Säsongskampanj med katalogintegration**: Fråga efter produktkatalog, identifiera berättigade kunder, segmentera efter önskemål, skicka personaliserade produktrekommendationer
&#x200B;* **Butiksspecifika kampanjer**: Rikta kunderna mot specifika butiksplatser med lagerdata
&#x200B;* **Flerbokskommunikation**: Skicka ett meddelande per bokning (hotellbokningar, flygbokningar)
&#x200B;* **Komplex segmentsamordning**: Bygg målgrupper steg för steg med berikning från flera datakällor
&#x200B;* **Validering före sändning**: Få exakt antal mottagare innan du startar större kampanjer

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

**F: Kan jag kombinera resor och kampanjer i min marknadsföringsstrategi?**

S: Absolut! De flesta organisationer använder alla tre metoder för olika scenarier:
- Resor för beteendeengagemang i realtid
- Åtgärdskampanjer för schemalagd sändningskommunikation
- API-utlösta kampanjer för transaktionsmeddelanden
- Samordnade kampanjer för komplexa, dataintensiva gruppkampanjer

**F: Kan jag konvertera en kampanj till en resa eller vice versa?**

S: Nej, du måste återskapa upplevelsen i rätt format. Men ni kan återanvända innehåll, målgrupper och logiska koncept.

**F: Vilken metod är enklare att bygga?**

S: Åtgärdskampanjer är oftast de enklaste (enskilda meddelanden till målgrupper), följt av API-utlösta kampanjer, resor (mer komplexa med flerstegslogik) och samordnade kampanjer (mest komplexa på grund av arbetsytans arbetsflöde och funktioner för flera enheter).

**Q: Vilken skala passar bäst för stora målgrupper?**

S: Alla tre kan skalas bra, men:
- **Läs målgrupper** och **Åtgärdskampanjer** är optimerade för stora grupper
- **Orchestrerade kampanjer** kan inte användas vid komplex segmentering med stora datamängder
- **Unitary Journeys** bearbetar profiler individuellt, så skalan beror på händelsens volym

**F: Kan jag använda samma målgrupp på resor och i kampanjer?**

S: Ja, målgrupper som skapats i Adobe Experience Platform kan användas på alla tre inriktningarna.

## Nästa steg {#next-steps}

Vill du börja bygga? Utforska den detaljerade dokumentationen för det sätt du valt:

&#x200B;* **[Kom igång med resor](../building-journeys/journey.md)** - Lär dig mer om resetyper, designer och arbetsflöde
&#x200B;* **[Kom igång med kampanjer](../campaigns/get-started-with-campaigns.md)** - Utforska åtgärder och API-utlösta kampanjer
&#x200B;* **[Kom igång med samordnade kampanjer](../orchestrated/gs-orchestrated-campaigns.md)** - Upptäck arbetsflöden för arbetsytan i batch

**Behöver du mer hjälp med att bestämma dig?**
- [Jämförelse av resetyper](../building-journeys/journey.md#journey-types-comparison)
- [Jämförelse av kampanjtyper](../campaigns/get-started-with-campaigns.md#campaign-types)
- [Vanliga frågor om resor](../building-journeys/journey-faq.md)
- [Vanliga frågor om samordnade kampanjer](../orchestrated/orchestrated-campaigns-faq.md)

