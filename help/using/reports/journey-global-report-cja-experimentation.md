---
solution: Journey Optimizer
product: journey optimizer
title: Rapport om reseexperiment
description: Lär dig hur du använder Experimentationsdata från reserapporten
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: a2b4ef74-96a9-4907-ba70-7aee69e45f20
source-git-commit: 45ebae048a748429a1918326526f3756a3e93c4c
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 1%

---

# Rapport om experimenterad resa {#campaign-global-report-cja-experimentation}

I din reserapport får du en fullständig bild av hur ditt experiment fungerar, tillsammans med de nyckeltal du behöver för att förstå hur det påverkar.

I Journey Optimizer delas reseexperimenterande in i två typer:

* [Innehållsexperiment](../content-management/content-experiment.md)

  Observera att tabeller och KPI:er som är detaljerade för ditt Content-experiment är desamma som för ett Path-experiment. Läs [dokumentationen nedan](#experimentation) om du har konfigurerat ett innehållsexperiment.

* [Banexperiment](../building-journeys/optimize.md)

## Banexperiment {#experimentation}

### KPI:er för experiment {#experimentation-kpis}

![](assets/journey-report-experiment-1.png)

**Experimentationssammanfattningen** ger viktiga insikter i hur ditt experiment fungerar och identifierar den som fungerar bäst. Observera att det kan ta en stund att definiera den bästa utföraren. Om ditt experiment inte lyckas ställs det in på **Ofullständig**.

**Prestandaindikatorerna för experimentnyckeltal** fungerar som en övergripande instrumentpanel och levererar en analys av viktiga mått som är kopplade till dina experiment.

+++ Läs mer om KPI:er för experiment

* **[!UICONTROL Lift]**: Mät den procentuella förbättringen av konverteringsgraden för en given behandling över baslinjen.

* **[!UICONTROL Confidence]**: Bevis på att en viss behandling är densamma som den initiala behandlingen. [Läs mer](../content-management/experiment-calculations.md#understand-confidence)

+++



### Variant efter framgångsmått {#variant-inbound}

![](assets/cja-experimentation-variants.png)

Tabellen **Variant efter framgångsmått** visar hur varje variant fungerar baserat på det framgångsmått som valts när du konfigurerade experimentet.
En djupdykning i dessa resultat och hur du tolkar dem finns på [den här sidan](../content-management/get-started-experiment.md#interpret-results).

+++ Läs mer om Variant med Success Metric

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina meddelanden.

* **[!UICONTROL Inbound Clicks]**: Det totala värdet för resultatmåttet, som tidigare valdes när du skapade dina experiment.

* **[!UICONTROL Conversion rate]**: Det totala värdet för resultatmåttet, som tidigare valdes när du skapade dina experiment, delat med antalet profiler.

* **[!UICONTROL Lift]**: Mät den procentuella förbättringen av konverteringsgraden för en given behandling över baslinjen.

* **[!UICONTROL Confidence Lower bound]**: Det lägsta uppskattade värdet av konverteringsskillnaden mellan behandlingen och baslinjen, inom det valda konfidensintervallet.

* **[!UICONTROL Confidence]**: Bevis på att en viss behandling är densamma som den initiala behandlingen. [Läs mer](../content-management/experiment-calculations.md#understand-confidence)

* **[!UICONTROL Confidence Upper bound]**: Det högsta uppskattade värdet av konverteringsskillnaden mellan behandlingen och baslinjen, inom det valda konfidensintervallet.

+++

### Konverteringsgrad för framgångsmått {#conversion-rate}

![](assets/cja-experimentation-conversion.png)

Diagrammet **[!UICONTROL Confidence interval]** visar intervallet av möjliga förbättringar, som jämför baslinjen med den bästa behandlingen för det valda framgångsmåttet. [Läs mer](../content-management/experiment-calculations.md#confidence-intervals).
