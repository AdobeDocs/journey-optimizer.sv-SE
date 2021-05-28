---
title: Rapport om resebesök
description: Lär dig använda data från reserapporten
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 0%

---

# Direktfärdsrapport {#journey-live-report}

![](../assets/do-not-localize/badge.png)

Du kan komma åt liverapporten för resan direkt från din resa med knappen **[!UICONTROL Live report]**.

![](../assets/report_1.png)

Sidan **[!UICONTROL Live report]** för resan visas med följande flikar:

* [Resa](#journey-live)
* [E-post](#email-live)
* [Tryck](#push-live)

Resan **[!UICONTROL Live report]** är uppdelad i olika widgetar som anger hur framgångsrik och felfri din resa är. Varje widget kan storleksändras och tas bort vid behov. Mer information finns i [avsnittet](live-report.md#modify-dashboard).

## Reseflik {#journey-live}

Från din resa **[!UICONTROL Live report]** ger fliken **[!UICONTROL Journey]** en tydlig bild av de viktigaste spårningsdata som rör din resa.

![](../assets/report_journey_2.png)

**[!UICONTROL Journey`s performance]** gör att du kan se vägen för dina målprofiler steg för steg under hela kundresan.

Widgeten **[!UICONTROL Journey`s statistics]** visar följande KPI:er:

* **[!UICONTROL Entered profiles]**: Totalt antal personer som har nått resans inträde.

* **[!UICONTROL Exited profiles]**: Totalt antal personer som avbrutit resan.

* **[!UICONTROL Failed individual journey]**: Totalt antal enskilda resor som inte har slutförts.

![](../assets/report_journey_3.png)

Med widgetarna **[!UICONTROL Event executed over the last 24 hours]**, **[!UICONTROL Events executed]** och **[!UICONTROL Events]** kan du se vilken av dina händelser som utfördes med sammanfattningsnummer, diagram och tabell.

![](../assets/report_journey_4.png)

**[!UICONTROL Action executed over the last 24 hours]** och  **[!UICONTROL Actions executed and errors]** widgetar är de mest framgångsrika åtgärderna och felen som inträffade när åtgärderna utlöstes. Åtgärdsdiagrammet, tabellen och sammanfattningsnumren innehåller de data som är tillgängliga för åtgärder, till exempel:

* **[!UICONTROL Actions successfully executed]**: Totalt antal genomförda åtgärder för en resa.

* **[!UICONTROL Error in action]**: Totalt antal fel som uppstått för åtgärder.

## Fliken E-post {#email-live}

Från din resa **[!UICONTROL Live report]** anger fliken **[!UICONTROL Email]** huvudinformationen i relation till e-postleveranserna som skickas under din resa.

En detaljerad rapport om en viss e-postleverans finns i avsnittet [E-postlive rapport](email-live-report.md).

![](../assets/report_email_1.png)

Widgetarna **[!UICONTROL Sending Statistics]** och **[!UICONTROL Sending metrics by Email]** visar hur bra leveransen är:

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som sammanställts under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

<!--Hard and bounce - by Email-->

Diagrammet **[!UICONTROL Email summary]** visar huvudinformationen i förhållande till meddelandet:

* **[!UICONTROL Sent]**: Totalt antal försändelser för leveransen.

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som sammanställts under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

* **[!UICONTROL Opens]**: Antal gånger ett meddelande öppnades i en leverans.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades i en leverans.

![](../assets/report_email_2.png)

Widgetarna **[!UICONTROL Bounce Reasons]** och **[!UICONTROL Bounce categories]** innehåller tillgängliga data för studsade meddelanden, till exempel:

* **[!UICONTROL Hard bounce]**: Det totala antalet permanenta fel, t.ex. fel e-postadress. Detta inbegriper ett felmeddelande som uttryckligen anger att adressen är ogiltig, till exempel Okänd användare.

* **[!UICONTROL Soft bounce]**: Det totala antalet tillfälliga fel, t.ex. en fullständig inkorg.

* **[!UICONTROL Ignored]**: Det totala antalet tillfälliga, t.ex. frånvaro, eller ett tekniskt fel, t.ex. om avsändartypen är postmaster.

Med diagrammet och tabellen **[!UICONTROL Error Reasons]** kan du se vilket fel som uppstod under leveransen.

## Skjut fliken {#push-live}

Från din resa **[!UICONTROL Live report]** anger fliken **[!UICONTROL Push]** huvudinformationen i relation till push-leveranserna som skickas under din resa.

En detaljerad rapport om en viss push-leverans finns i avsnittet [Push live report](push-live-report.md).

![](../assets/report_push_1.png)

**[!UICONTROL Push notification sending performance]**,  **[!UICONTROL Push notification summary]** och  **[!UICONTROL Sending metrics - by Push]** widgetar visar huvudinformationen i relation till ditt meddelande:

* **[!UICONTROL Sent]**: Totalt antal försändelser för leveransen.

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som sammanställts under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

* **[!UICONTROL Opens]**: Antal gånger ett meddelande öppnades i en leverans.

* **[!UICONTROL Actions]**: Totalt antal åtgärder för push-meddelandet som levererats, t.ex. knappklickning eller avbruten.

* **[!UICONTROL Engagements]**: Totalt antal öppningar och åtgärder för det här push-meddelandet, dvs om profilen öppnade push-meddelandet eller om någon klickade på en knapp.

Med diagrammet och tabellen **[!UICONTROL Error Reasons]** kan du se vilket fel som uppstod under leveransen.

![](../assets/report_push_2.png)

Diagram och tabeller för **[!UICONTROL Tracking by platform]**, **[!UICONTROL Sending by platform]** och **[!UICONTROL Breakdown by platform]** visar om push-meddelandet är klart beroende på vilket operativsystem som används.

Med widgeten **[!UICONTROL Sending statistics - Failed]** kan du se hur många fel och studs.
