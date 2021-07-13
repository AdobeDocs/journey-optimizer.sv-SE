---
title: E-postlive-rapport
description: Lär dig hur du använder data från e-postrapporten
feature: Rapportering
topic: Innehållshantering
role: User
level: Intermediate
source-git-commit: eba6ff87438325f58c453c12552c75c69dbdac0b
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 0%

---

# E-postlive-rapport {#email-live-report}

E-postmeddelandet **[!UICONTROL Live report]** avser bara en viss e-postleverans.

Välj **[!UICONTROL Live view]** på fliken **[!UICONTROL Executions]** på menyn **[!UICONTROL Messages]** och välj sedan **[!UICONTROL Live report]** på den avancerade menyn för den valda leveransen.

![](../assets/live_report.png)

E-postmeddelandet **[!UICONTROL Live report]** är uppdelat i olika widgetar som anger leveransens framgång och fel. Varje widget kan storleksändras och tas bort vid behov. Mer information finns i [avsnittet](live-report.md#modify-dashboard).

![](../assets/live_report_5.png)

**[!UICONTROL Email performance]** och  **[!UICONTROL Email summary]** widgetar visar huvudinformationen i förhållande till meddelandet med ett diagram och nyckeltal:

* **[!UICONTROL Sent]**: Totalt antal försändelser för leveransen.

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som sammanställts under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

* **[!UICONTROL Opens]**: Antal gånger ett meddelande öppnades i en leverans.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades i en leverans.

I **[!UICONTROL Sending Statistics]**-diagrammet visas leveransframgången:

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som sammanställts under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

![](../assets/live_report_6.png)

Med diagrammet och tabellen **[!UICONTROL Error Reasons]** kan du se vilket fel som uppstod under leveransen.

Widgetarna **[!UICONTROL Bounce Reasons]** och **[!UICONTROL Bounce categories]** innehåller tillgängliga data för studsade meddelanden, till exempel:

* **[!UICONTROL Hard bounce]**: Det totala antalet permanenta fel, t.ex. fel e-postadress. Detta inbegriper ett felmeddelande som uttryckligen anger att adressen är ogiltig, till exempel Okänd användare.

* **[!UICONTROL Soft bounce]**: Det totala antalet tillfälliga fel, t.ex. en fullständig inkorg.

* **[!UICONTROL Ignored]**: Det totala antalet tillfälliga, t.ex. frånvaro, eller ett tekniskt fel, t.ex. om avsändartypen är postmaster.
