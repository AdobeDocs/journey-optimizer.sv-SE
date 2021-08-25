---
title: E-postlive-rapport
description: Lär dig hur du använder data från e-postrapporten
feature: Reporting
topic: Content Management
role: User
level: Intermediate
source-git-commit: 9408a93deecfb12f28a0a87c19fa0074c66844a9
workflow-type: tm+mt
source-wordcount: '397'
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

>[!NOTE]
>
>Profilerna med **[!UICONTROL Suppressed]**- eller **[!UICONTROL Not allowed]**-status exkluderas när meddelandet skickas. Samtidigt som **reseservrapporterna** visar dessa profiler som om de har flyttats genom resan ([Läs segment](../building-journeys/read-segment.md) och [Meddelande](../building-journeys/journeys-message.md)-aktiviteter), kommer **e-postrapporterna** inte att inkludera dem i **[!UICONTROL Sent]**-måtten eftersom de filtreras ut innan e-postmeddelandet skickas.
>
>Läs mer i [Suppressionslistan](../suppression-list.md) och [Tillåtelselista](../allow-list.md). Om du vill ta reda på orsaken till alla undantagsfall kan du använda [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html){target=&quot;_blank&quot;}.
