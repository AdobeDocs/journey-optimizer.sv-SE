---
solution: Journey Optimizer
product: journey optimizer
title: Kampanjrapport
description: Lär dig hur du använder data från Campaign-rapporten
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 925494b6-e08a-4bd3-8a2f-96a5d9cbc387
source-git-commit: 4112ac79a1f21fb369119ccd801dcbceac3c1e58
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 1%

---

# Kampanjrapport {#campaign-live-report}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_report"
>title="Kampanjrapport"
>abstract="Med rapporten Campaign live kan ni i realtid mäta och visualisera effekten och resultatet av era kampanjer bara under de senaste 24 timmarna. Din rapport är uppdelad i olika widgetar som detaljerat beskriver kampanjens framgångar och fel. Varje rapportkontrollpanel kan ändras genom att widgetar storleksändras eller tas bort."

Live-rapporter, som du kommer åt från fliken Senaste 24 timmarna, visar händelser som har inträffat under de senaste 24 timmarna, med ett tidsintervall på minst två minuter från händelseförekomsten. Som jämförelse fokuserar Global-rapporter på händelser som inträffade för minst två timmar sedan och täcker händelser under en vald tidsperiod.

Kampanjens live-rapport kan nås direkt från kampanjen med **[!UICONTROL Live view]** -knappen.

Kampanjen **[!UICONTROL Live report]** visas med följande flikar:

* [Campaign](#campaign-live)
* [E-post](#email-live)
* [I appen](#inapp-live)
* [Push](#push-live)
* [SMS](#sms-live)
* [Webb](#web-tab)
* [Direktmeddelande](#direct-mail-tab)

Kampanjen **[!UICONTROL Live report]** är uppdelat i olika widgetar som detaljerat beskriver kampanjens framgångar och fel. Varje widget kan storleksändras och tas bort vid behov. Mer information finns i [section](../reports/live-report.md#modify-dashboard).

En detaljerad lista över alla mätvärden som är tillgängliga i Adobe Journey Optimizer finns på [den här sidan](live-report.md#list-of-components-live).

## Fliken Kampanj {#campaign-global}

### Leverans {#delivery-global}

The **[!UICONTROL Campaign Statistics]** widgetinformation om huvudinformationen i förhållande till kampanjen:

* **[!UICONTROL Entered profiles]**: Antal profiler som påbörjade resan.

<!--
### Experimentation tab (#experimentation-live)

From your Campaign **[!UICONTROL Live report]**, the **[!UICONTROL Experimentation]** tab details the main information relative to how each variant is performing and if there is was winner during the test.
-->

## Fliken E-post {#email-live}

Från er kampanj **[!UICONTROL Live report]**, **[!UICONTROL Email]** -fliken innehåller huvudinformationen om de e-postleveranser som skickas i kampanjen.

![](assets/campaign_report_live_1.png)

+++Läs mer om de olika mätvärden och widgetar som är tillgängliga för e-postrapporten.

The **[!UICONTROL Email Sending Statistics]** widgeten innehåller information om den viktigaste informationen i förhållande till ditt meddelande:

* **[!UICONTROL Delivered]**: Antal meddelanden som skickats.

* **[!UICONTROL Bounces]**: Totalt antal fel som ackumulerats under leverans och automatisk returbearbetning.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

The **[!UICONTROL Sending metrics by Email]** tabell och **[!UICONTROL Email Summary]** diagram visar hur framgångsrik leveransen är:

* **[!UICONTROL Sent]**: Totalt antal försändelser för leveransen.

* **[!UICONTROL Delivered]**: Antal meddelanden som skickats.

* **[!UICONTROL Bounces]**: Totalt antal fel som ackumulerats under leverans och automatisk returbearbetning.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

* **[!UICONTROL Opens]**: Antal gånger ett meddelande öppnades i en leverans.

* **[!UICONTROL Clicks]**: Antal gånger ett innehåll klickades i en leverans.

* **[!UICONTROL Unsubscribe]**: Antal klick på länken för att avbryta prenumerationen.

* **[!UICONTROL Spam complaints]**: Antal gånger ett meddelande har deklarerats som skräppost eller skräppost.

The **[!UICONTROL Bounce Reasons]**, **[!UICONTROL Bounce categories]** och **[!UICONTROL Hard and bounce - by Email]** widgetar innehåller tillgängliga data som är relaterade till studsade meddelanden, som:

* **[!UICONTROL Hard bounce]**: Det totala antalet permanenta fel, t.ex. fel e-postadress. Detta inbegriper ett felmeddelande som uttryckligen anger att adressen är ogiltig, till exempel Okänd användare.

* **[!UICONTROL Soft bounce]**: Det totala antalet tillfälliga fel, till exempel en fullständig inkorg.

* **[!UICONTROL Ignored]**: Det totala antalet tillfälliga, t.ex. frånvaro, eller ett tekniskt fel, t.ex. om avsändartypen är postmaster.

The **[!UICONTROL Error Reasons]** och **[!UICONTROL Exclude Reasons]** Med diagram och tabeller kan du se vilka fel och undantag som inträffade under leveransen.

The **[!UICONTROL Email - Top recipient domain]** diagram och tabeller visar vilka domäner som är de mest använda av mottagarna för att öppna e-postmeddelandet.
+++

## Fliken I appen {#inapp-live}

Från er kampanj **[!UICONTROL Live report]**, **[!UICONTROL In-app]** -fliken innehåller huvudinformationen om de leveranser i appen som skickas i kampanjen.

+++Läs mer om de olika mätvärden och widgetar som är tillgängliga för rapporten i appen.

The **[!UICONTROL In-app performance]** Nyckeltal anger den viktigaste informationen i relation till besökarnas engagemang i era meddelanden i appen, till exempel:

* **[!UICONTROL Unique impressions]**: antal unika användare som meddelandet i appen levererades till.

* **[!UICONTROL Impressions]**: totalt antal meddelanden i appen som levereras till alla användare.

The **[!UICONTROL In-app summary]** diagram visar hur dina visningar i appen har utvecklats för den aktuella perioden.

The **[!UICONTROL Clicks by button]** diagram och tabell innehåller tillgängliga data för mottagarnas beteende per knapp:

* **[!UICONTROL Clicks]**: totalt antal mottagare som interagerat med knapparna i meddelandet i appen.

+++

## Fliken Push-meddelanden {#push-live}

Från er kampanj **[!UICONTROL Live report]**, **[!UICONTROL Push notification]** -fliken innehåller huvudinformationen i förhållande till push-leveranser som skickas i kampanjen.

![](assets/campaign_report_live_2.png)

+++Läs mer om de olika mätvärden och widgetar som är tillgängliga för rapporten Push.

**[!UICONTROL Push notification sending performance]**, **[!UICONTROL Push notification summary]** och **[!UICONTROL Sending metrics - by Push]** widgetar anger huvudinformationen i förhållande till ditt meddelande:

* **[!UICONTROL Sent]**: Totalt antal försändelser för leveransen.

* **[!UICONTROL Delivered]**: Antal meddelanden som skickats.

* **[!UICONTROL Bounces]**: Totalt antal fel som ackumulerats under leverans och automatisk returbearbetning.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

* **[!UICONTROL Opens]**: Antal gånger ett meddelande öppnades i en leverans.

* **[!UICONTROL Actions]**: Totalt antal åtgärder för push-meddelandet som levererats, t.ex. knappklickning eller avvisning.

* **[!UICONTROL Engagements]**: Totalt antal öppningar och åtgärder för detta push-meddelande, dvs. om profilen öppnade push-meddelandet eller om någon klickade på en knapp.

The **[!UICONTROL Error Reasons]** och **[!UICONTROL Exclude Reasons]** Med diagram och tabeller kan du se vilka fel och undantag som inträffade under leveransen.

The **[!UICONTROL Sending statistics - Failed]** kan du se hur många fel och studsar som har inträffat.

The **[!UICONTROL Tracking by platform]**, **[!UICONTROL Sending by platform]** och **[!UICONTROL Breakdown by platform]** diagram och tabeller visar hur bra push-meddelandena är beroende på vilket operativsystem som används.
+++

## fliken SMS {#sms-live}

Från er kampanj **[!UICONTROL Live report]**, **[!UICONTROL SMS]** -fliken innehåller huvudinformationen om SMS-leveranser som skickas i kampanjen.

![](assets/campaign_report_live_3.png)

+++Läs mer om de olika mätvärden och widgetar som är tillgängliga för SMS-rapporten.

The **[!UICONTROL SMS - Statistics]** tabellen visar hur framgångsrik leveransen är:

* **[!UICONTROL Targeted]**: Antal användarprofiler som kvalificerar sig som målprofiler för den här leveransen.

* **[!UICONTROL Excluded]**: Antal användarprofiler, exkluderade från målprofilerna, som inte fick meddelandet.

* **[!UICONTROL Sent]**: Totalt antal försändelser för leveransen.

* **[!UICONTROL Bounces]**: Totalt antal fel som ackumulerats under leverans och automatisk returbearbetning.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

* **[!UICONTROL Clicks]**: Totalt antal URL-besök.

The **[!UICONTROL SMS Performance by date]** widgeten visar huvudinformationen i förhållande till meddelandet med ett diagram:

* **[!UICONTROL Sent]**: Totalt antal försändelser för leveransen.

* **[!UICONTROL Bounces]**: Totalt antal fel som ackumulerats under leverans och automatisk returbearbetning.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

The **[!UICONTROL Exclude Reasons]**, **[!UICONTROL Bounces Reasons]** och **[!UICONTROL Error Reasons]** Med diagram och tabeller kan du se vilka fel och undantag som inträffade under leveransen.
+++

## Fliken Webb {#web-tab}

Från er kampanj **[!UICONTROL Global report]**, **[!UICONTROL Web]** -fliken anger huvudinformationen för dina webbsidor.

+++Läs mer om de olika mätvärden och widgetar som finns för webbrapporten.

The **[!UICONTROL Web performance]** Nyckeltal anger den viktigaste informationen i relation till besökarnas engagemang i era webbupplevelser, till exempel:

* **[!UICONTROL Unique impressions]**: antal unika användare som webbupplevelsen levererades till.

* **[!UICONTROL Impressions]**: totalt antal webbupplevelser som levereras till alla användare.

* **[!UICONTROL Clicks]**: totalt antal URL-besök.

The **[!UICONTROL Web summary]** diagram visar hur webbupplevelserna har utvecklats (visningar, unika intryck och klickningar) under den aktuella perioden.

The **[!UICONTROL Clicks by element]** tabellen innehåller huvudinformationen om besökarnas engagemang för de olika elementen på webbsidorna.
+++

## Fliken Direktreklam {#direct-mail-tab}

Från er kampanj **[!UICONTROL Global report]**, **[!UICONTROL Direct mail]** -fliken anger huvudinformationen i förhållande till dina Direct-postleveranser.

+++Läs mer om de olika mätvärden och widgetar som finns för rapporten Direct mail.

The **[!UICONTROL Direct Mail - Sending statistics]** tabellen visar hur framgångsrik leveransen är:

* **[!UICONTROL Targeted]**: Antal användarprofiler som kvalificerar sig som målprofiler för den här leveransen.

* **[!UICONTROL Sent]**: Totalt antal försändelser för leveransen.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.

* **[!UICONTROL Excluded]**: Antal användarprofiler, exkluderade från målprofilerna, som inte fick leveransen.

The **[!UICONTROL Direct Mail - Excluded reasons]** och **[!UICONTROL Direct Mail - Error reasons]** Med diagram och tabeller kan du se vilka fel och undantag som inträffade under leveransen.
+++

## Ytterligare resurser

* [Kom igång med kampanjer](../campaigns/get-started-with-campaigns.md)
* [Skapa en kampanj](../campaigns/create-campaign.md)
* [Skapa API-utlösta kampanjer](../campaigns/api-triggered-campaigns.md)
* [Ändra eller stoppa en kampanj](../campaigns/modify-stop-campaign.md)
* [Global kampanjrapport](campaign-global-report.md)
