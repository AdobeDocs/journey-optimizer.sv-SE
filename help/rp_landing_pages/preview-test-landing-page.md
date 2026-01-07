---
solution: Journey Optimizer
product: Journey Optimizer
title: Förhandsgranska och testa innehåll
description: Verifiera meddelandets exakthet före start. Förhandsgranska personaliserat innehåll med testprofiler, skicka korrektur till intressenter, kontrollera e-poståtergivning över klienter, utvärdera spamresultat och testa olika innehållsvariationer effektivt.
redpen-status: CREATED_||_2025-08-11_20-30-05
exl-id: bd78e0af-573b-4880-a9f1-44467c9db159
source-git-commit: 6b83b015dfd74da9eb58bd06958d0963d81c6489
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 0%

---

# Förhandsgranska och testa innehåll{#section-overview}

>[!BEGINSHADEBOX]

**Syfte:** Valideringsverktyg före start för kampanjer och resor\
**Primära användare:** Kampanjhanterare, e-postmarknadsförare, innehållsskapare\
**Nyckelresultat:** Fånga upp fel före kundleverans

>[!ENDSHADEBOX]

Säkerställ felfri meddelandeleverans genom att hitta fel innan de når kunderna. Förhandsgranska innehåll validerar personaliseringen i olika kundprofiler, medan testverktygen avslöjar renderingsproblem, spamrisker och innehållsvariationer som kan påverka engagemanget. Få tillgång till omfattande funktioner för att skicka korrektur till intressenter, simulera personalisering med exempeldata, kontrollera e-poståtergivning mellan kunder och utvärdera leveransstatistik - allt före aktivering. Lär dig dessa valideringstekniker för att skydda varumärket, maximera placeringen av inkorgen och leverera enhetliga och utmärkta kundupplevelser.

## Förhandsgranska och testa innehåll

:::: landing-cards-container
:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg)

Förhandsgranska och testa ditt innehåll

Lär dig hur du använder testprofiler och exempelindata för att förhandsgranska och testa innehåll, skicka korrektur och säkerställa att personaliseringen är korrekt.

[Kom igång med förgranskning och test](../using/content-management/preview-test.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/list-check.svg)

Så här väljer du testprofiler

Lär dig hur du väljer och hanterar testprofiler för att förhandsgranska och testa personaliserat innehåll effektivt.

[Lär dig välja testprofiler](../using/content-management/test-profiles.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg)

Förhandsgranska ditt innehåll med testprofiler

Stegvisa anvisningar för att förhandsgranska personaliserat innehåll med testprofiler och simulera innehållsvariationer.

[Förhandsgranska innehåll med testprofiler](../using/content-management/preview.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/envelope.svg)

Skicka korrektur med testprofildata

Testa och validera dina e-postmeddelanden genom att skicka korrektur med testprofildata för att säkerställa att innehållet är korrekt.

[Lär dig hur du skickar korrektur](../using/content-management/proofs.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/eye.svg)

Testa e-poståtergivning med Litmus

Integrera Litmus för att förhandsgranska e-poståtergivning i olika e-postklienter och se till att de visas korrekt.

[Testa e-poståtergivning med Litmus](../using/content-management/rendering.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg)

Simulera och testa innehållsvariationer

Simulera innehållsvariationer med exempeldata för att testa personaliserat innehåll och säkerställa exakthet.

[Simulera innehållsvariationer](../using/test-approve/simulate-sample-input.md)
:::

::::

## Snabbguide

**Kontext:** Den här tabellen mappar testmål till specifika verktyg i Adobe Journey Optimizer.

Välj testmetod baserat på ditt mål:

| **Om du behöver..** | **Använd det här verktyget** |
|----------------------|-------------------|
| Verifiera att personalisering visas korrekt | [Testprofiler](../using/content-management/test-profiles.md) |
| Testa 10+ innehållsvariationer snabbt | [Exempelindata](../using/test-approve/simulate-sample-input.md) |
| Låt intressenter godkänna innan de skickar | [Skicka korrektur](../using/content-management/proofs.md) |
| Kontrollera e-postvisningen i Gmail, Outlook, Apple Mail | [Litmus-återgivning](../using/content-management/rendering.md) |
| Förbättra placeringen av inkorgen | [Spam-rapport](../using/content-management/spam-report.md) |
| Förhandsgranska alla variationer samtidigt | [Förhandsgranskningsläge](../using/content-management/preview.md) |

## Kontrollista för testarbetsflöde

**Kontext:** Rekommenderad testsekvens i fem steg som gäller för alla kanaler (e-post, SMS, push, webb, i appen).

Följ den här sekvensen för fullständig validering:

1. **Förhandsgranska** - Använd testprofiler för att kontrollera personaliseringsrenderingar korrekt
2. **Testa variationer** - Överför exempeldata CSV/JSON för att validera flera scenarier
3. **Kontrollera levererbarhet** (e-post) - Kör skräppostrapport och renderingstest
4. **Skicka korrektur** - Dela med intressenter för granskning och godkännande
5. **Slutlig kontroll** - Verifiera att alla länkar, bilder och CTA fungerar som de ska

**Pro-tips:** Testa med minst tre profiler som representerar olika kundsegment (högt värde, nytt, inaktivt) för att fånga upp kantärenden.

## Vanliga scenarier

**Kontext:** Exempel från verkligheten som visar hur du använder testverktyg i vanliga fall.

**Scenario 1: Testa personliga e-postmeddelanden för en kampanj i flera segment**
→ Använd [&#x200B; exempelindata &#x200B;](../using/test-approve/simulate-sample-input.md) för att testa 20-30 variationer utan att skapa individuella testprofiler. Ladda upp en CSV-fil med olika kundattribut och förhandsgranska alla samtidigt.

**Scenario 2: Verifierar e-poståtergivning före en större sändning**
→ Kör [&#x200B; Litmus-tester &#x200B;](../using/content-management/rendering.md) för att kontrollera visningen över de vanligaste e-postklienterna och kontrollera sedan [skräppostrapporten](../using/content-management/spam-report.md) för att se till att inkorgen är placerad.

**Scenario 3: Få berörda parter att godkänna**
→ [Skicka korrektur](../using/content-management/proofs.md) till interna granskare med testprofildata så att de ser exakt vad kunderna får.

## Viktiga uppgifter

- **Testprofiler** är viktiga för förhandsgranskning av anpassat innehåll. Använd exempelindata för att testa över 10 variationer effektivt
- **E-postspecifika verktyg** innehåller återgivningstester (Litmus), skräppostrapporter och korrektur
- **Rekommenderad sekvens:** Förhandsgranska → Testa variationer → Kontrollera levererbarhet → Skicka korrektur → Slutlig kontroll
- **Tidsbesparande:** Överför CSV/JSON med kundattribut i stället för att skapa individuella testprofiler

## Ytterligare resurser

- **[Så här använder du skräppostrapporten](../using/content-management/spam-report.md)** - Utvärdera skräppostresultatet för e-postinnehåll med funktionen Skräppostrapport för att förbättra leveransen.

**Relaterade ämnen:** [Testa och godkänn landningssida](test-landing-page.md) | [Arbetsflöden för godkännande](approve-landing-page.md) | [Skapa testprofiler](../using/audience/creating-test-profiles.md)
