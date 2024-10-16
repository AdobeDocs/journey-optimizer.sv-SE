---
solution: Journey Optimizer
product: journey optimizer
title: Kampanjrapport
description: Lär dig hur du använder experimentdata från Campaign-rapporten
feature: Reporting
topic: Content Management
role: User
level: Intermediate
source-git-commit: 47482adb84e05fe41eb1c50479a8b50e00469ec4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Rapport om experimentkampanjer {#campaign-global-report-cja-experimentation}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment_click"
>title="Resultatmått"
>abstract="Det totala värdet för resultatmåttet, som tidigare valts när du skapade dina experiment, delat med antalet profiler."

## Experimentation {#experimentation}

Fliken **[!UICONTROL Experimentation]** ger viktiga insikter om prestanda för varje variant och identifierar den som fungerar bäst.

Observera att det kan ta en stund att definiera den bästa utföraren. Om ditt experiment inte lyckas ställs det in på **Ofullständig**.

![](assets/cja-experimentation-1.png)

### KPI:er för experiment {#experimentation-kpis}

![](assets/cja-experimentation-kpis.png)

**[!UICONTROL Experimentation]** KPI:er (Key Performance Indicators) fungerar som en heltäckande kontrollpanel som levererar en analys av viktiga mått som är kopplade till dina experiment.

+++ Läs mer om KPI:er för experiment

* **[!UICONTROL Lift]**: Mät den procentuella förbättringen av konverteringsgraden för en given behandling över baslinjen.

* **[!UICONTROL Confidence]**: Bevis på att en viss behandling är densamma som den initiala behandlingen. [Läs mer](../content-management/experiment-calculations.md#understand-confidence)

+++

### Variant efter inkommande klick {#variant-inbound}

![](assets/cja-experimentation-variants.png)

Widgeten **[!UICONTROL Variant by Inbound clicks]** visar prestanda för varje variant.
En djupdykning i dessa resultat och hur du tolkar dem finns på [den här sidan](../content-management/get-started-experiment.md#interpret-results).

+++ Läs mer om Mätvärden för inkommande klick för Variant

* **[!UICONTROL People]**: Antal användarprofiler som kvalificerar sig som målprofiler för dina meddelanden.

* **[!UICONTROL Inbound Clicks]**: Totalt antal klick över utgående kanaler.

* **[!UICONTROL Conversion rate]**: Det totala värdet för resultatmåttet, som tidigare valdes när du skapade dina experiment, delat med antalet profiler.

* **[!UICONTROL Lift]**: Mät den procentuella förbättringen av konverteringsgraden för en given behandling över baslinjen.

* **[!UICONTROL Confidence]**: Bevis på att en viss behandling är densamma som den initiala behandlingen. [Läs mer](../content-management/experiment-calculations.md#understand-confidence)

<!--
* **[!UICONTROL Confidence Upper bound]**:

* **[!UICONTROL Confidence Lower bound]**:
-->
+++

### Konverteringsgrad för inkommande klick {#conversion-rate}

![](assets/cja-experimentation-conversion.png)

Diagrammet **[!UICONTROL Confidence interval]** mäter osäkerheten kring förbättringen. Här anges den procentuella skillnaden i prestanda mellan baslinjen och den bästa behandlingen. [Läs mer](../content-management/experiment-calculations.md#confidence-intervals).
