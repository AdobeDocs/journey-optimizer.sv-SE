---
title: E-postlive-rapport
description: Lär dig hur du använder data från e-postrapporten
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 1ddfbf1a-3cd5-446a-b0fb-76b81b88c1b4
source-git-commit: f0e34e040dd0e0ba2fa8293f4290ab55e1781426
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 0%

---

# E-postlive-rapport {#email-live-report}

E-postmeddelandet **[!UICONTROL Live report]** avser endast en viss e-postleverans.

Från **[!UICONTROL Executions]** -fliken i **[!UICONTROL Messages]** meny, välja **[!UICONTROL Live view]** väljer du på den avancerade menyn för den valda leveransen **[!UICONTROL Live report]**.

![](../assets/live_report.png)

E-postmeddelandet **[!UICONTROL Live report]** är uppdelat i olika widgetar som detaljerat beskriver leveransens framgångar och fel. Varje widget kan storleksändras och tas bort vid behov. Mer information finns i [section](live-report.md#modify-dashboard).

![](../assets/live_report_5.png)

**[!UICONTROL Email performance]** och **[!UICONTROL Email summary]** widgetar detaljerar huvudinformationen i förhållande till meddelandet med ett diagram och KPI:er:

* **[!UICONTROL Targeted]**: Antal användarprofiler som kvalificerar sig som målprofiler för den här leveransen.

* **[!UICONTROL Sent]**: Totalt antal försändelser för leveransen.

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Opens]**: Antal gånger ett meddelande öppnades i en leverans.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades i en leverans.

* **[!UICONTROL Bounces]**: Totalt antal fel som sammanställts under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

* **[!UICONTROL Spam complaints]**: Antal meddelanden som klassificerats som skräppost.

* **[!UICONTROL Unsubscriptions]**: Antal klick på länken för att avbryta prenumerationen.

* **[!UICONTROL Excluded]**: Antal användarprofiler, exkluderade från målprofilerna, som inte fick meddelandet.

The **[!UICONTROL Sending Statistics]** widgeten visar hur framgångsrik leveransen är:

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som sammanställts under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

![](../assets/live_report_6.png)

The **[!UICONTROL Error Reasons]** Med diagram och tabeller kan du se vilket fel som inträffade under leveransen.

The **[!UICONTROL Bounce Reasons]** och **[!UICONTROL Bounce categories]** widgetar innehåller tillgängliga data som är relaterade till studsade meddelanden, som:

* **[!UICONTROL Hard bounce]**: Det totala antalet permanenta fel, t.ex. fel e-postadress. Detta inbegriper ett felmeddelande som uttryckligen anger att adressen är ogiltig, till exempel Okänd användare.

* **[!UICONTROL Soft bounce]**: Det totala antalet tillfälliga fel, t.ex. en fullständig inkorg.

* **[!UICONTROL Ignored]**: Det totala antalet tillfälliga, t.ex. frånvaro, eller ett tekniskt fel, t.ex. om avsändartypen är postmaster.

![](../assets/live_report_8.png)

>[!NOTE]
>
>Widgetarna och mätvärdena för erbjudanden är bara tillgängliga om ett beslut har infogats i ett e-postmeddelande. Mer information om beslutsförvaltning finns i denna [page](../offers/get-started/starting-offer-decisioning.md).

The **[!UICONTROL Offers statistic]** och **[!UICONTROL Offers statistics]** med tidswidgetar mäter hur väl erbjudandet lyckats och påverkat er målgrupp. Den innehåller detaljerad huvudinformation om meddelandet med nyckeltal:

* **[!UICONTROL Offer sent]**: Totalt antal utskick för erbjudandet.

* **[!UICONTROL Offer impression]**: Antal gånger som erbjudandet öppnades i en leverans.

* **[!UICONTROL Offer clicks]**: Antal gånger som man klickat på ett erbjudande i en leverans.

>[!NOTE]
>
>Profilerna med **[!UICONTROL Suppressed]** eller **[!UICONTROL Not allowed]** status utelämnas under meddelandesändningsprocessen. Därför är **Reserapporter** visar att dessa profiler har flyttats genom resan ([Läs segment](../building-journeys/read-segment.md) och [Meddelande](../building-journeys/journeys-message.md) verksamhet), **E-postrapporter** kommer inte att inkludera dem i **[!UICONTROL Sent]** mätvärden när de filtreras ut innan e-postmeddelanden skickas.
>
>Läs mer på [Undertryckningslista](../suppression-list.md) och [Tillåtelselista](../allow-list.md). Om du vill ta reda på orsaken till alla undantagsfall kan du använda [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html){target=&quot;_blank&quot;}.
