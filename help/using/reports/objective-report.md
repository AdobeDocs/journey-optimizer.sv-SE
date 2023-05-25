---
solution: Journey Optimizer
product: journey optimizer
title: Global kampanjrapport
description: Lär dig hur du använder data från rapporten Campaign Global
feature: Reporting
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
source-git-commit: 6b8983d3f3fa989bd7190fc6a8b51fa8989b2293
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 1%

---

# Global kampanjrapport {#objective-report}

Kampanjens globala rapport kan nås direkt från er Campaign via **[!UICONTROL View report]** -knappen.

Kampanjen **[!UICONTROL Global report]** är uppdelat i olika widgetar som detaljerat beskriver kampanjens framgångar och fel. Varje widget kan storleksändras och tas bort vid behov. Mer information finns i [section](../reports/global-report.md#modify-dashboard).

En detaljerad lista över alla mätvärden som är tillgängliga i Adobe Journey Optimizer finns på [den här sidan](global-report.md#list-of-components-global.md)

## Fliken Kampanj {#campaign-global-objectives}

### Leverans {#delivery-global-objectives}

![](assets/campaign_report_global_1.png)

The **[!UICONTROL Campaign's Statistics]** widgetinformation om huvudinformationen i förhållande till kampanjen:

* **[!UICONTROL Entered profiles]**: Antal profiler som påbörjade resan.

* **[!UICONTROL Actions delivered]**: Totalt antal unika gånger som en åtgärd i resan har utförts.

* **[!UICONTROL Actions failed in %]**: Totalt antal unika gånger en åtgärd misslyckades under resan jämfört med det totala antalet unika gånger en åtgärd har levererats.

### Målrapport {#objective-global}

>[!AVAILABILITY]
>
>The **Målrapport** är för närvarande bara tillgängligt för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant om du vill ha mer information.

![](assets/performance_report.gif)

The **[!UICONTROL Objectives]** kan du finjustera leveransrapporter bättre genom att ange ett specifikt mätvärde.

The **[!UICONTROL Objectives]** listade är länkade till **[!UICONTROL Datasets]** som definierar en anslutning till ett system för att hämta ytterligare information. En lista med inbyggda **[!UICONTROL Objectives]** är tillgängligt, men du kan lägga till egna genom att lägga till nya **[!UICONTROL Dataset]**. För det detaljerade förfarandet, se [section](../campaigns/reporting-configuration.md).

När du har valt de mål som du vill ha som mål för **[!UICONTROL Performance overview]** och **[!UICONTROL Campaign objective]** -widgetar ger en detaljerad sammanfattning av leveransresultatet.

Med **[!UICONTROL Campaign objective]** kan du också välja att jämföra huvudmålet med ett annat mätvärde.

### Experimentationsrapport {#experimentation-global-objectives}

![](assets/experimentation_report_3.png)

The **[!UICONTROL Experimentation]** ger viktiga insikter om prestanda för varje variant och identifierar den mest framgångsrika.

Observera att det kan ta en stund att definiera den bästa utföraren, men den representeras av den här ikonen ![](assets/experimentation_report_1.png).

+++Läs mer om de olika mätvärden och widgetar som är tillgängliga för rapporten Experimentation.

The **[!UICONTROL Experiment result]** widgeten anger prestanda för varje variant. Du kan ändra din baslinje genom att välja en av behandlingarna i **[!UICONTROL Baseline]** listrutan. Den bästa behandlingen visas med en stjärnikon.

Tabellen visar följande mått:

* **[!UICONTROL Lift over baseline]**: Mät den procentuella förbättringen av konverteringsgraden för en viss behandling jämfört med baslinjen.

* **[!UICONTROL Confidence]**: Bevis på att en viss behandling är densamma som den initiala behandlingen. [Läs mer](../campaigns/experiment-calculations.md#understand-confidence)

* **[!UICONTROL Unique outbound clicks]**: Totalt antal klick i utgående kanaler.

* **[!UICONTROL Profiles]**: Antal profiler som är avsedda för denna behandling.

* **[!UICONTROL Unique outbound clicks/profiles]**: Totalt värde för framgångsmåttet, som tidigare valts när du skapade dina experiment, delat med antalet profiler.

The **[!UICONTROL Confidence interval]** graf mäter osäkerheten kring förbättringen. Här anges den procentuella skillnaden i prestanda mellan baslinjen och den bästa behandlingen. [Läs mer](../campaigns/experiment-calculations.md#confidence-intervals).
+++

En djupdykning i dessa resultat och hur du tolkar dem finns i [den här sidan](../campaigns/get-started-experiment.md#interpret-results).

