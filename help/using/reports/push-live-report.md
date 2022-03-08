---
title: Direktrapport om push-meddelanden
description: Lär dig hur du använder data från push-meddelanderapporten
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: cab7c6da-aba7-439d-a638-79eb0c949837
source-git-commit: 51254efaab08a572def118d475dc18f74c9d29b7
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# Publicera live-rapport {#push-live-report}

The push **[!UICONTROL Live report]** endast för en viss push-leverans.

Från **[!UICONTROL Executions]** -fliken i **[!UICONTROL Messages]** meny, välja **[!UICONTROL Live view]** väljer du på den avancerade menyn för den valda leveransen **[!UICONTROL Live report]**.

![](../assets/live_report_2.png)

The push **[!UICONTROL Live report]** är uppdelat i olika widgetar som detaljerat beskriver leveransens framgångar och fel. Varje widget kan storleksändras och tas bort vid behov. Mer information finns i [section](live-report.md#modify-dashboard).

![](../assets/live_report_3.png)

**[!UICONTROL Push notification performance]** och **[!UICONTROL Push notification summary]** widgetar detaljerar huvudinformationen i förhållande till meddelandet med diagram och KPI:er:

* **[!UICONTROL Sent]**: Totalt antal försändelser för leveransen.

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som sammanställts under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

* **[!UICONTROL Opens]**: Antal gånger ett meddelande öppnades i en leverans.

* **[!UICONTROL Actions]**: Totalt antal åtgärder för push-meddelandet som levererats, t.ex. knappklickning eller avbruten.

* **[!UICONTROL Engagements]**: Totalt antal öppningar och åtgärder för det här push-meddelandet, dvs om profilen öppnade push-meddelandet eller om någon klickade på en knapp.

The **[!UICONTROL Sending metrics - by push]** tabellen visar hur framgångsrik leveransen är:

* **[!UICONTROL Targeted]**: Antal användarprofiler som kvalificerar sig som målprofiler för den här leveransen.

* **[!UICONTROL Excluded]**: Antal användarprofiler, exkluderade från målprofilerna, som inte fick meddelandet.

* **[!UICONTROL Sent]**: Totalt antal försändelser för leveransen.

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som sammanställts under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

* **[!UICONTROL Opens]**: Antal gånger ett meddelande öppnades i en leverans.

![](../assets/live_report_4.png)

The **[!UICONTROL Tracking by platform]**, **[!UICONTROL Sending by platform]** och **[!UICONTROL Breakdown by platform]** diagram och tabeller visar hur bra push-meddelandena är beroende på vilket operativsystem som används.

The **[!UICONTROL Sending statistics - Failed]** kan du se hur många fel och studs.

The **[!UICONTROL Error Reasons]** Med diagram och tabeller kan du se vilket fel som inträffade under leveransen.
