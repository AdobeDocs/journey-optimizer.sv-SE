---
title: Garantier och begränsningar för beslutshantering
description: Läs mer om avtalsutkast och begränsningar.
feature: Decisioning
role: User
level: Intermediate
exl-id: d2872bd3-42f8-4744-bb5b-41c49340098a
source-git-commit: 70543fc2b70b388934c1b3f45e5405f02895a3af
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 5%

---

# Garantier och begränsningar för beslutshantering {#decision-management-guardrails}

För att säkerställa en optimal användning av beslutsprocessen bör du tänka på följande säkerhetsförslag och begränsningar.

Den fullständiga listan med [!DNL Journey Optimizer] skyddsutkast och begränsningar finns i [det här avsnittet](../start/guardrails.md).

## Beslutsförfrågningar

Leveransflödet motsvarar antalet beslutssvar som kan levereras av beslutsstyrningsapptjänsten under en angiven tidsperiod.

| Guardrail | Gräns |
| ------- | ------- |
| API-begäranden för beslut per sekund | 500 per organisation |
| Edge Decisioning API-begäranden per sekund med Edge Segmentering | 1 500 per organisation |
| Edge Decisionering API-begäranden per sekund utan Edge-segmentering | 5 000 per organisation |
| Returnerade erbjudanden per svar | Upp till 30 per beslutsomfattning eller totalt 100 |
| Maximalt antal regler för erbjudanden per förfrågan | 100 |

## Beslut

| Guardrail | Gräns |
| ------- | ------- |
| Totalt antal beslut | 10 kB |
| Live-beslut | 1 K |
| Placeringar per beslut | 30 |

## Samlingar

| Guardrail | Gräns |
| ------- | ------- |
| Erbjudanden per samling | 500 |
| Samlingar | 10 kB |
| Samlingar per beslut | 30 |

## Samlingskvalificerare

| Guardrail | Gräns |
| ------- | ------- |
| Samlingskvalificerare per erbjudande eller samling | 20 |
| Totalt antal samlingskvalificerare | 1 000 |

## Erbjudanden

| Guardrail | Gräns |
| ------- | ------- |
| Totalt antal erbjudanden | 10 kB |
| Maximalt antal **aktiva** erbjudanden per sandlåda | 10 kB |
| Maximal storlek på erbjudanden inklusive attribut (1 kB), maximalt 30 attribut | 1 kB |
| Maximal representationsstorlek för erbjudande (totalt för alla ersättningar) | 1 kB |

## Villkor för deltagande

| Guardrail | Gräns |
| ------- | ------- |
| Sammanlagda beslutsregler och rangordningstexter | 10 000 kombinerade |
| Max antal profilattribut per regel | 25 |
| Max antal kontextdataattribut per regel | 30 |
| Maximal storlek för PQL-regel | 15 kB (UTF-8) |
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
| Placeringar | 1000 |
| AI-rankningsmodell | 5 |
| Frekvensbegränsning - maximalt antal regler per erbjudande | 10 |
