---
solution: Journey Optimizer
product: journey optimizer
title: Resetyper och urvalsguide
description: Jämför olika typer av resor och välj rätt för ditt användningssätt med beslutsguider och matris för funktionskompatibilitet
feature: Journeys, Get Started, Overview
role: User
level: Beginner
keywords: resetyper, enhet, läsare, målgruppskvalifikation, affärshändelse, jämförelse, beslutshandbok, val, val, realtid, schemalagd, batch, händelseutlöst
version: Journey Orchestration
hide: true
hidefromtoc: true
exl-id: 0c894dc1-76b6-4b33-baf8-eaf6686f7d38
source-git-commit: 70653bafbbe8f1ece409e3005256d9dff035b518
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 1%

---

# Resetyper och urvalsguide {#journey-types-selection}

[!DNL Adobe Journey Optimizer] har stöd för fyra typer av resor, där var och en är utformad för olika startmekanismer och affärsscenarier. Den här guiden hjälper dig att förstå skillnaderna och välja rätt typ för ditt användningsfall.

## Översikt över resetyper {#journey-types}

>[!BEGINTABS]

>[!TAB Unitära resor]

**När:** Händelseutlösta upplevelser i realtid ska användas

**Unitära resor** aktiveras individuellt när en viss åtgärd inträffar (inköp, appinloggning, formuläröverföring). Profilerna anger en i taget i realtid, vilket gör detta idealiskt för omedelbara, beteendestyrda svar.

**Perfekt för:** Beställningsbekräftelser efter köp, välkomstmeddelanden när någon prenumererar, övergivna kundvagnar utlösta av surfning och meddelanden om lösenordsåterställning.

➡️ [Läs mer om händelser](../event/about-events.md) | [Meddelande till prenumeranter - användningsfall](message-to-subscribers-uc.md)

>[!TAB Läs målgruppsresor]

**När:** schemalagda kampanjer ska användas till målgruppssegment

**Läs målgruppsresor** börjar med en [!DNL Adobe Experience Platform]-målgrupp och skicka meddelanden gruppvis till alla profiler samtidigt. Den här typen av resa är perfekt för schemalagd, storskalig kommunikation.

**Perfekt för:** Månatliga nyhetsbrev, kampanjkampanjer för målsegment, produktmeddelanden och säsongskampanjer.

➡️ [Lär dig mer om att läsa målgrupp](read-audience.md) | [Kom igång med målgrupper](../audience/about-audiences.md)

>[!TAB Målgruppskvalificeringsresor]

**När ska användas:** Realtidssvar på ändringar av målgruppsmedlemskap

**Målgruppskvalificeringsresor** utlöser när profiler kvalificerar sig för (eller avslutar) en viss målgrupp. Profilerna läggs in individuellt när de uppfyller kriterierna i realtid, vilket ger ett omedelbart engagemang när kundbeteendet förändras.

**Perfekt för:** VIP-uppgraderingsmeddelanden, återengagemang när kunderna blir inaktiva, första besöksmeddelanden och geografisk anpassning när kunderna rör sig.

➡️ [Lär dig mer om Audience Qualification](audience-qualification-events.md) | [Skapa målgrupper](../audience/creating-a-segment-definition.md)

>[!TAB Affärshändelseresor]

**När:** Affärsvillkor som påverkar flera kunder

**Affärshändelseresor** utlöses av händelser på företagsnivå (stockuppdateringar, vädervarningar, prisförändringar) som påverkar flera profiler samtidigt. Dessa svarar mot mer allmänna affärsvillkor än enskilda åtgärder.

**Perfekt för:** Låga lagervarningar till intresserade kunder, meddelanden om flash-försäljning, väderbaserade kampanjer, meddelanden om prisfall och produktmeddelanden.

➡️ [Läs mer om affärshändelser](../event/about-creating-business.md) | [Anmälningshantering](entry-management.md)

>[!ENDTABS]

## Beslutsguide: Välj typ av resa {#decision-guide}

Följ det här beslutsträdet för att välja rätt resetyp för ditt användningsfall:

### Steg 1: Vad utlöser resan?

* **Kunden utför en specifik åtgärd** (köp, klicka, logga in) → Gå till steg 2
* **Tid/schema** (skicka vid en viss tidpunkt eller återkommande) → **Använd läsmålresan**
* **Kundstatus ändras** (leder/lämnar ett segment) → Gå till steg 3
* **Affärsvillkor** (börsnivå, prisförändring, väder) → **Använd affärshändelseresa**

### Steg 2: Enskilda kundåtgärdsutlösare

* **Krävs omedelbar realtidsrespons?**
   * Ja → **Använd enhetsresa**
   * Nej → Överväg att läsa målgruppsresan med schemalagd exekvering

### Steg 3: Kundstatusändringar

* **Behöver du svara när kunderna går in i eller avslutar ett segment?**
   * Ja → **Använd målgruppskompetensresa**
   * Nej, endast vid inträde → Överväg en enhetlig resa med event eller Läs målgrupp med målgruppsfilter

### Snabb markering med skiftläge

| Ditt mål | Rekommenderad resetyp | Varför |
|-----------|------------------------|-----|
| Skicka orderbekräftelse efter köp | Unitary | Omedelbar reaktion på individuella åtgärder |
| Skicka månatliga nyhetsbrev till prenumeranter | Läs målgrupp | Schemalagd batchkommunikation |
| Meddela kunderna när de når VIP-status | Målgruppskvalifikation | Realtidssvar på statusändring |
| Meddela kunder om begränsade lager på bevakade objekt | Affärshändelse | Affärsvillkor påverkar flera kunder |
| Välkomna nya appanvändare | Unitary | Utlöses av en signeringshändelse |
| Engagera inaktiva kunder på nytt | Målgruppskvalifikation | Svarar på inaktivitetssegmentpost |
| Säsongshöjning till målsegment | Läs målgrupp | Schemalagd kampanj till målgrupp |
| Flash-försäljningsmeddelande | Affärshändelse | Affärsbeslut påverkar flera kunder |

>[!NOTE]
>
>Vet du inte vilken typ du ska välja? Börja med **enhetliga resor** för händelsebaserade upplevelser eller **Läs målgruppsresor** för schemalagda kampanjer - de här omfattar de vanligaste användningsfallen.

## Detaljerad jämförelse av resetyper {#journey-types-comparison}

Använd den här tabellen om du snabbt vill jämföra olika typer av resor och välja rätt i ditt fall:

| Proportioner | Enhetsresor | Läs målgruppsresor | Målgruppskompetensresor | Affärshändelseresor |
|--------|------------------|------------------------|--------------------------------|------------------------|
| **Anmälningsmekanism** | Enskild händelseutlösare | Schemalagd batch | Ändring av målgruppsmedlemskap i realtid | Händelse på företagsnivå |
| **Anmälningstidpunkt** | Realtid, allt eftersom händelser inträffar | Schemalagd (en gång eller återkommande) | Realtid, allt eftersom kvalificering sker | Realtid, när affärshändelser utlöses |
| **Profilpost** | En åt gången | Alla samtidigt (batch) | En åt gången | Flera profiler samtidigt |
| **Utlösarkälla** | Kundåtgärd (köp, klicka, inloggning) | Tidsbaserat schema | Målgruppsmedlemskap (inträde/utträde) | Affärsvillkor (lager, väder, pris) |
| **Bäst för** | Transaktionsmeddelanden, beteenderespons | Marknadsföringskampanjer, nyhetsbrev | Lojalitetsprogram, livscykelfaser | Lagervarningar, kampanjer, affärsvillkor |
| **Använd när** | Omedelbar respons på enskilda åtgärder som behövs | Nå ut till stora målgruppssegment enligt tidsplanen | Svara på kundstatusändringar | Affärshändelser påverkar flera kunder |
| **Exempel** | Orderbekräftelse, lösenordsåterställning | Månatligt nyhetsbrev, säsongskampanj | Uppgradering av VIP, avisering om inaktivitet | Varning vid låg lagernivå, blixtförsäljning, prisfall |
| **Återinträde** | Konfigurerbar (tillåt flera poster per profil) | Varje profil anger en gång per körning | Konfigurerbar per kvalificeringshändelse | Flera profiler kan påverkas av samma händelse |
| **Datakrav** | Händelseschema med utlösardata | [!DNL Adobe Experience Platform] publik | Direktuppspelning eller gruppbearbetning | Affärshändelsens schema |

## Kompatibilitet per resetyp {#feature-compatibility}

Alla funktioner är inte tillgängliga för alla resetyper. Använd den här matrisen för att förstå vilka funktioner som fungerar med vilka resetyper:

| Funktion/funktioner | Unitary | Läs målgrupp | Målgruppskvalifikation | Affärshändelse |
|---------------------|:-------:|:-------------:|:----------------------:|:--------------:|
| **Ingångsmekanismer** |
| Händelseutlöst post | ✅ | ❌ | ❌ | ✅ |
| Schemalagd post | ❌ | ✅ | ❌ | ❌ |
| Målgruppsinlägg | ❌ | ✅ | ✅ | ❌ |
| **Orchestration-funktioner** |
| Vänta på aktiviteter | ✅ | ✅ | ✅ | ✅ |
| Villkorsaktiviteter | ✅ | ✅ | ✅ | ✅ |
| Anpassade åtgärder | ✅ | ✅ | ✅ | ✅ |
| Läsa målgruppsaktivitet (inre resa) | ✅ | ✅ | ✅ | ✅ |
| Verksamhet inom målgruppskvalifikation | ✅ | ✅ | ✅ | ✅ |
| Hoppaktivitet | ✅ | ✅ | ✅ | ✅ |
| **Profilhantering** |
| Återinträde av profil | ✅ kan konfigureras | ❌ En gång per körning | ✅ kan konfigureras | ✅ per händelse |
| Namnområdeskonfiguration | ✅ krävs | ✅ valfritt | ✅ krävs | ✅ krävs |
| Profilände | ✅ | ✅ | ✅ | ✅ |
| **Testning och optimering** |
| Testläge | ✅ | ✅ | ✅ | ✅ |
| Torr körning | ✅ | ✅ | ✅ | ✅ |
| Banexperiment (A/B-tester) | ✅ | ✅ | ✅ | ❌ |
| Optimering vid sändning | ✅ | ✅ | ✅ | ✅ |
| **Kanaler** |
| E-post | ✅ | ✅ | ✅ | ✅ |
| Push-meddelanden | ✅ | ✅ | ✅ | ✅ |
| SMS/MMS | ✅ | ✅ | ✅ | ✅ |
| Meddelanden i appen | ✅ | ✅ | ✅ | ✅ |
| Webb | ✅ | ✅ | ✅ | ✅ |
| Innehållskort | ✅ | ✅ | ✅ | ✅ |
| **Avancerade funktioner** |
| Inkrementell läsning | ❌ | ✅ | ❌ | ❌ |
| Exportera målgrupper | ✅ | ✅ | ✅ | ✅ |
| Hantering av tidszoner | ✅ | ✅ | ✅ | ✅ |
| Reaktionshändelser | ✅ | ✅ | ✅ | ✅ |
| Externa datakällor | ✅ | ✅ | ✅ | ✅ |
| Begränsning/begränsning | ✅ | ✅ | ✅ | ✅ |

**Förklaring:** ✅ = Stöds | ❌ = Stöds inte

## Nästa steg {#next-steps}

Nu när du förstår olika typer av resor är du redo att:

* **[Skapa din första resa](journey-gs.md)** - Steg för steg-guide
* **[Läs mer om resedesignern](using-the-journey-designer.md)** - Designa din arbetsyta
* **[Utforska resefunktioner](journey.md#capabilities)** - Upptäck avancerade funktioner
* **[Visa vanliga frågor om resan](journey-faq.md)** - Vanliga frågor besvarade

**Behöver du jämföra med kampanjer?**

* [Jämförelseguide för resor och kampanjer](../start/journeys-vs-campaigns.md) - Välj mellan resor, Action/API-kampanjer och samordnade kampanjer
