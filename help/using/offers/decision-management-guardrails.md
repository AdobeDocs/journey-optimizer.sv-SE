---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: Garantier och begränsningar för beslutshantering
description: Läs mer om avtalsutkast och begränsningar.
badge: label="Äldre" type="Informative"
feature: Decision Management
role: User
level: Intermediate
exl-id: d2872bd3-42f8-4744-bb5b-41c49340098a
version: Journey Orchestration
source-git-commit: 8732a73118b807eaa7f57cfdad60355b535282ff
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 5%

---

# Garantier och begränsningar för beslutshantering {#decision-management-guardrails}

>[!TIP]
>
>Beslutsfattandet, [!DNL Adobe Journey Optimizer]s nya beslutsfunktion, är nu tillgängligt via den kodbaserade upplevelsen och e-postkanalerna! [Läs mer](../experience-decisioning/gs-experience-decisioning.md)

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

## Konfigurationer {#configurations}

Det totala antalet konfigurationer som stöds av beslutshanteringen får inte överstiga 20 000.

Det totala antalet konfigurationer är det totala antalet [spärrregler](offer-library/add-constraints.md#capping) som finns i din sandlåda. För varje begränsningsregel som tillämpas på alla [placements](offer-library/creating-placements.md) måste regeln multipliceras med alla placeringar som är associerade med det angivna erbjudandet.
