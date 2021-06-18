---
title: Global rapport för push-meddelanden
description: Lär dig hur du använder data från den globala rapporten för push-meddelanden
feature: Rapportering
topic: Innehållshantering
role: User
level: Intermediate
source-git-commit: 42e5cdec54339f65cddd79df4deabbf28292d16b
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 1%

---

# Push Global rapport {#push-global-report}

Push-åtgärden **[!UICONTROL Global report]** avser endast en specifik push-leverans.

Välj **[!UICONTROL Global view]** på fliken **[!UICONTROL Executions]** på menyn **[!UICONTROL Messages]** och välj sedan **[!UICONTROL Global report]** på den avancerade menyn för den valda leveransen.

![](../assets/global_report_11.png)

Push-åtgärden **[!UICONTROL Global report]** är uppdelad i olika widgetar som anger leveransens framgång och fel. Varje widget kan storleksändras och tas bort vid behov. Mer information finns i [avsnittet](global-report.md#modify-dashboard).

![](../assets/push_global_report.png)

Widgeten **[!UICONTROL Push notification performance]** visar huvudinformationen i förhållande till dina push-meddelanden med KPI:er:

* **[!UICONTROL Sent]**: Totalt antal försändelser för leveransen.

* **[!UICONTROL Bounce Rate]**: Procentandel push-meddelanden som studsade jämfört med skickade push-meddelanden.

* **[!UICONTROL Error Rate]**: Procentandel fel som uppstod under en leverans och som förhindrar att den skickas jämfört med push-meddelanden som skickas.

* **[!UICONTROL Actions Rate]**: Procentandel åtgärder för push-meddelanden som levereras, t.ex. knappklickning eller avbruten.

* **[!UICONTROL Engagement Rate]**: Procentandel öppningar och åtgärder för det här push-meddelandet, dvs. om profilen öppnade push-meddelandet eller om någon klickade på en knapp.

Diagrammet **[!UICONTROL Push notification summary]** innehåller data som är tillgängliga för skickade push-meddelanden, som:

* **[!UICONTROL Opens]**: Antal gånger ett meddelande öppnades i en leverans.

* **[!UICONTROL Actions]**: Totalt antal åtgärder för push-meddelandet som levererats, t.ex. knappklickning eller avbruten.

* **[!UICONTROL Bounces]**: Totalt antal fel som sammanställts under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

Med diagrammet och tabellen **[!UICONTROL Error Reasons]** kan du se vilket fel som uppstod under leveransen.

![](../assets/push_global_report_2.png)

Diagram och tabeller för **[!UICONTROL Tracking by platform]**, **[!UICONTROL Sending by platform]** och **[!UICONTROL Breakdown by platform]** visar om push-meddelandet lyckades beroende på mottagarens operativsystem.