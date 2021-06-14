---
title: E-posta global rapport
description: Lär dig hur du använder data från den globala e-postrapporten
feature: Rapportering
topic: Innehållshantering
role: User
level: Intermediate
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# E-posta global rapport {#email-global-report}

![](../assets/do-not-localize/badge.png)

E-postmeddelandet **[!UICONTROL Global report]** avser bara en viss e-postleverans.

Välj **[!UICONTROL Global view]** på fliken **[!UICONTROL Executions]** på menyn **[!UICONTROL Messages]** och välj sedan **[!UICONTROL Global report]** på den avancerade menyn för den valda leveransen.

![](../assets/global_report_3.png)

E-postmeddelandet **[!UICONTROL Global report]** är uppdelat i olika widgetar som anger leveransens framgång och fel. Varje widget kan storleksändras och tas bort vid behov. Mer information finns i [avsnittet](global-report.md#modify-dashboard).

![](../assets/global_report_4.png)

**[!UICONTROL Email performance]** anger huvudinformationen i förhållande till meddelandet med KPI:er:

* **[!UICONTROL Sent]**: Totalt antal försändelser för leveransen.

* **[!UICONTROL Delivery Rate]**: Procentandel meddelanden som har skickats.

* **[!UICONTROL Bounce Rate]**: Procentandel e-postmeddelanden som studsade jämfört med skickade e-postmeddelanden.

* **[!UICONTROL Error Rate]**: Procentandel fel som uppstod under en leverans och som förhindrar att den skickas jämfört med skickade e-postmeddelanden.

* **[!UICONTROL Open Rate]**: Procentandel öppnade meddelanden.

* **[!UICONTROL Click Rate]**: Procentandel klick i en leverans.

* **[!UICONTROL Spam Complaint Rate]**: Procentandel e-postmeddelanden som har markerats som skräppost av mottagare jämfört med levererade meddelanden. Mer information om klagomål finns på den här [sidan](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/complaints.html#metrics-for-deliverability).

* **[!UICONTROL Unsubscribe Rate]**: Antal unika avprenumerationer jämfört med levererade meddelanden.

I **[!UICONTROL Sending Statistics]**-diagrammet visas leveransframgången:

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som sammanställts under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

Widgetarna **[!UICONTROL Bounce Reasons]** och **[!UICONTROL Bounce categories]** innehåller tillgängliga data för studsade meddelanden, till exempel:

* **[!UICONTROL Hard bounce]**: Det totala antalet permanenta fel, t.ex. fel e-postadress. Detta inbegriper ett felmeddelande som uttryckligen anger att adressen är ogiltig, till exempel Okänd användare.

* **[!UICONTROL Soft bounce]**: Det totala antalet tillfälliga fel, t.ex. en fullständig inkorg.

* **[!UICONTROL Ignored]**: Det totala antalet tillfälliga, t.ex. frånvaro, eller ett tekniskt fel, t.ex. om avsändaren är postmaster.

Mer information om studsar finns på sidan [Suppressionslista](../suppression-list.md).

![](../assets/global_report_5.png)

Med diagrammet och tabellen **[!UICONTROL Error Reasons]** kan du se vilket fel som uppstod under leveransen.

Diagrammet och tabellen **[!UICONTROL Email - Best recipient domain]** visar vilka domäner som är de mest använda av mottagarna för att öppna e-postmeddelandet.

![](../assets/global_report_6.png)

Tabellen **[!UICONTROL Email - Tracking statistics]** innehåller tillgängliga data för mottagaraktivitet för leveransen:

* **[!UICONTROL Opens]**: Antal gånger som leveransen öppnades i en leverans.

* **[!UICONTROL Unique Opens]**: Antal mottagare som öppnade leveransen.

* **[!UICONTROL Open Rate]**: Procentandel öppnade meddelanden.

* **[!UICONTROL Clicks]**: Antal gånger ett innehåll klickades i ett e-postmeddelande.

* **[!UICONTROL Unique Clicks]**:Antal mottagare som klickat på ett innehåll i ett e-postmeddelande.

* **[!UICONTROL Click through rate]**: Procentandel klick i en leverans.

**[!UICONTROL Open vs Click]** identifierar mottagarnas interaktion med leveransen:

* **[!UICONTROL Unique Clicks]**:Antal mottagare som klickat på ett innehåll i ett e-postmeddelande.

* **[!UICONTROL Unique Opens]**: Antal mottagare som öppnade leveransen.

Diagrammet och tabellen **[!UICONTROL Email - Top Url]** visar vilka URL:er från din leverans som är mest besökta.
