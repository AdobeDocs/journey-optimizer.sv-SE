---
title: Avgörande av skyddsräcken och begränsningar
description: Läs mer om hur du bestämmer skyddsprofiler och begränsningar.
feature: Decisioning
role: User
level: Intermediate
exl-id: 73548973-ff8d-4d6c-b383-dd3679fa159a
version: Journey Orchestration
source-git-commit: 3fa90fa707b562ecf2160ec980520bc8bc267a21
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 6%

---

# Avgörande av skyddsräcken och begränsningar {#decisioning-guardrails}

För att säkerställa optimal användning av beslut bör du tänka på följande skyddsräcken och begränsningar.

Den fullständiga listan med [!DNL Journey Optimizer] skyddsutkast och begränsningar finns i [det här avsnittet](../start/guardrails.md).

## Beslutsförfrågningar {#decision-requests}

| Guardrail | Gräns |
| ------- | ------- |
| Kodbaserad API-begäran för upplevelser med beslutspolicy med Edge segmentering | 1500 |
| Kodbaserad API-begäran för upplevelser med beslutspolicy som inte använder Edge-segmentering | 5000 |
| Max antal yt-URI:er per Edge-beslutsbegäran | 30 |

## Artikelsamlingar {#item-collections}

| Guardrail | Gräns |
| ------- | ------- |
| Objektsamlingar | 10 kB |
| Totalt antal erbjudandeartiklar per artikelsamling | 500 |

## Beslutspolitik {#decision-policy}

| Guardrail | Gräns |
| ------- | ------- |
| Antal urvalsstrategier och manuella poster per beslutspolicy | 10 |
| Max antal erbjudandeartiklar som returneras per beslutspolicy | 30 |

## Villkor för deltagande {#eligibility-rules}

| Guardrail | Gräns |
| ------- | ------- |
| Totalt antal beslutsregler och rangordningsformler | 10 000 kombinerade |
| Max antal profilattribut per regel | 25 |
| Max antal kontextdataattribut per regel | 30 |
| Maximal storlek för pql-regel | 15 kB (UTF-8) |
| Maximalt antal kapslingsnivåer | 30 |

## Rankningsformler {#ranking-formulas}

| Guardrail | Gräns |
| ------- | ------- |
| Maximal storlek för rankningsformeln PQL | 8K (UTF-8) |
| Max antal profilattribut | 25 |
| Max antal kontextdataattribut | 30 |
| Maximalt antal kapslingsnivåer | 30 |

## Övriga {#others}

| Guardrail | Gräns |
| ------- | ------- |
| Antal anpassade attribut per katalogschema för erbjudanden | 100 |
| Totalt antal erbjudanden | 10 kB |
| Totalt antal placeringar | 1 K |
| AI-rankningsmodell | 5 |
| Frekvensregler - maximalt antal regler per erbjudande | 10 |

## Konfigurationer {#configurations}

Det totala antalet konfigurationer som beslutsstöd stöder får inte överstiga 20 000.

Det totala antalet konfigurationer är det totala antalet [spärrregler](items.md#capping) som finns i din sandlåda.
