---
solution: Journey Optimizer
product: journey optimizer
title: Global kampanjrapport
description: Lär dig använda data från rapporten Campaign Global
feature: Reporting
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
exl-id: ec1af88c-7b0a-4eaf-97e1-0d9676268fed
badge: label="Beta" type="Informative"
source-git-commit: b8d56578aae90383092978446cb3614a4a033f80
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 2%

---

# Global kampanjrapport {#objective-report}

Kampanjens globala rapport kan nås direkt från din kampanj med knappen **[!UICONTROL View report]**.

Campaign **[!UICONTROL Global report]** är uppdelad i olika widgetar som beskriver kampanjens framgångar och fel. Varje widget kan storleksändras och tas bort vid behov. Mer information finns i denna/detta <!--[section](../reports/global-report.md#modify-dashboard)-->.

En detaljerad lista över alla mätvärden som är tillgängliga i Adobe Journey Optimizer finns på <!--[this page](global-report.md#list-of-components-global.md)-->

## Fliken Kampanj {#campaign-global-objectives}

### Leverans {#delivery-global-objectives}

<!--
![](assets/campaign_report_global_1.png)
-->

Widgeten **[!UICONTROL Campaign's Statistics]** visar huvudinformationen i förhållande till din kampanj:

* **[!UICONTROL Entered profiles]**: Antal profiler som påbörjade resan.

* **[!UICONTROL Actions delivered]**: Totalt antal unika gånger en åtgärd i resan har levererats.

* **[!UICONTROL Actions failed in %]**: Totalt antal unika gånger en åtgärd misslyckades under resan jämfört med det totala antalet unika gånger en åtgärd har levererats.

### Målrapport {#objective-global}

>[!AVAILABILITY]
>
>Funktionen **Målrapport** är för närvarande bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant om du vill veta mer.

![](assets/performance_report.gif)

På fliken **[!UICONTROL Objectives]** kan du finjustera leveransrapporter bättre genom att ange ett specifikt mätvärde.

**[!UICONTROL Objectives]** i listan är länkad till **[!UICONTROL Datasets]** som definierar en anslutning till ett system för att hämta ytterligare information. En lista med inbyggda **[!UICONTROL Objectives]** är tillgänglig, men du kan lägga till egna genom att lägga till nya **[!UICONTROL Dataset]**. Detaljerade anvisningar finns i det här [avsnittet](../reports/reporting-configuration.md).

När du har valt de mål som du vill ha som mål på, kommer de två **[!UICONTROL Performance overview]**- och **[!UICONTROL Campaign objective]**-widgetarna att ge en detaljerad sammanfattning av leveransresultaten.

Med widgeten **[!UICONTROL Campaign objective]** kan du även välja att jämföra huvudmålet med ett annat mätvärde.

### Experimentationsrapport {#experimentation-global-objectives}

<!--
![](assets/experimentation_report_3.png)
-->

Fliken **[!UICONTROL Experimentation]** ger viktiga insikter om prestanda för varje variant och identifierar den som fungerar bäst.

Observera att det kan ta lite tid att definiera den bästa utföraren, men den representeras av den här ikonen ![](assets/experimentation_report_1.png).

+++Lär dig mer om de olika mätvärden och widgetar som är tillgängliga för rapporten Experimentation.

Widgeten **[!UICONTROL Experiment result]** visar prestanda för varje variant. Du kan ändra din baslinje genom att välja en av behandlingarna i listrutan **[!UICONTROL Baseline]**. Den bästa behandlingen visas med en stjärnikon.

Tabellen visar följande mått:

* **[!UICONTROL Lift over baseline]**: Mät den procentuella förbättringen av konverteringsgraden för en given behandling över baslinjen.

* **[!UICONTROL Confidence]**: Bevis på att en viss behandling är densamma som den initiala behandlingen. [Läs mer](../content-management/experiment-calculations.md#adobes-statistical-methodology-any-time-valid-confidence-sequences)

* **[!UICONTROL Unique outbound clicks]**: Totalt antal klick över utgående kanaler.

* **[!UICONTROL Profiles]**: Antal profiler som är avsedda för den här behandlingen.

* **[!UICONTROL Unique outbound clicks/profiles]**: Det totala värdet för resultatmåttet, som tidigare valdes när du skapade dina experiment, delat med antalet profiler.

Diagrammet **[!UICONTROL Confidence interval]** mäter osäkerheten kring förbättringen. Här anges den procentuella skillnaden i prestanda mellan baslinjen och den bästa behandlingen. [Läs mer](../content-management/experiment-calculations.md#adobes-statistical-methodology-any-time-valid-confidence-sequences).
+++

En djupdykning i dessa resultat och hur du tolkar dem finns på [den här sidan](../content-management/get-started-experiment.md#interpret-results).
