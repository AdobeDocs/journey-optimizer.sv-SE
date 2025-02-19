---
title: Avgörande av skyddsräcken och begränsningar
description: Läs mer om hur du bestämmer skyddsprofiler och begränsningar.
feature: Decisioning
role: User
level: Intermediate
source-git-commit: b6c31528784c0c8576e3200e7611a6b6cd43d7a7
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 6%

---


# Avgörande av skyddsräcken och begränsningar {#decisioning-guardrails}

För att säkerställa optimal användning av beslut bör du tänka på följande skyddsräcken och begränsningar.

Den fullständiga listan med [!DNL Journey Optimizer] skyddsutkast och begränsningar finns i [det här avsnittet](../start/guardrails.md).

## Beslutsförfrågningar

| Guardrail | Gräns |
| ------- | ------- |
| Kodbaserad API-begäran för upplevelser med beslutspolicy som använder Edge-segmentering | 1500 |
| Kodbaserad API-begäran för upplevelser med beslutspolicy som inte använder Edge-segmentering | 5000 |

## Artikelsamlingar

| Guardrail | Gräns |
| ------- | ------- |
| Objektsamlingar | 10 kB |
| Totalt antal erbjudandeartiklar per artikelsamling | 500 |

## Beslutspolitik

| Guardrail | Gräns |
| ------- | ------- |
| Antal urvalsstrategier och manuella poster per beslutspolicy | 10 |
| Max antal erbjudandeartiklar som returneras per beslutspolicy | 30 |

## Villkor för deltagande

| Guardrail | Gräns |
| ------- | ------- |
| Totalt antal beslutsregler och rangordningsformler | 10 000 kombinerade |
| Max antal profilattribut per regel | 25 |
| Max antal kontextdataattribut per regel | 30 |
| Maximal storlek för pql-regel | 15 kB (UTF-8) |
| Maximalt antal kapslingsnivåer | 30 |

## Rankningsformler

| Guardrail | Gräns |
| ------- | ------- |
| Maximal storlek för rankningsformeln PQL | 8K (UTF-8) |
| Max antal profilattribut | 25 |
| Max antal kontextdataattribut | 30 |
| Maximalt antal kapslingsnivåer | 30 |

## Övriga

| Guardrail | Gräns |
| ------- | ------- |
| Antal anpassade attribut per katalogschema för erbjudanden | 100 |
| Totalt antal erbjudanden | 10 kB |
| Totalt antal placeringar | 1 K |
| AI-rankningsmodell | 5 |
| Frekvensregler - maximalt antal regler per erbjudande | 10 |
