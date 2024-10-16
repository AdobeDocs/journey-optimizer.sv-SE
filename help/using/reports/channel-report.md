---
solution: Journey Optimizer
product: journey optimizer
title: Kanalnivårapporter
description: Lär dig hur du använder data från kanalrapporter
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: ead9359b-cdab-43ed-a469-d98b0ca19a17
source-git-commit: 47482adb84e05fe41eb1c50479a8b50e00469ec4
workflow-type: tm+mt
source-wordcount: '3492'
ht-degree: 0%

---

# Kanalrapporter {#channel-report}

>[!CONTEXTUALHELP]
>id="ajo_channel_level_report"
>title="Rapport på kanalnivå"
>abstract="Kanalrapporterna ger en omfattande översikt över trafik- och engagemangsmätningar i alla kanaler. Dina rapporter är uppdelade i olika widgetar som detaljerat beskriver er kampanj och dina kundresor och fel. Varje rapportkontrollpanel kan ändras genom att widgetar storleksändras eller tas bort."

>[!AVAILABILITY]
>
>Den nuvarande rapportupplevelsen kommer att upphöra i januari 2025. Efter detta datum kommer den nya rapportupplevelsen att bli standard. Vi rekommenderar att du behärskar de nya funktionerna så att övergången blir smidig. [Kom igång med Journey Optimizer nya rapporteringsgränssnitt.](report-gs-cja.md)

>[!IMPORTANT]
>
> Om du vill få åtkomst till menyn **Rapport** måste du ha behörigheten **[!UICONTROL View Channel Reports]**. [Läs mer](channel-report-gs.md#before-starting-manage-reports-prereq)

Kanalrapporterna ger användarna en heltäckande översikt över trafik- och engagemangsmätningar på kanalnivå. Mätvärdena sammanställs för att presentera konsoliderade värden för åtgärder som kommer från den valda kanalen och som omfattar olika kampanjer och resor.

Du kommer åt kanalrapporterna genom att gå till menyn **Rapporter** i avsnittet **Resehantering** . Den är helt anpassningsbar, du kan filtrera dina data beroende på rapportdatumet eller åtgärden. [Läs mer](channel-report-gs.md)

Rapportsidan visas med följande flikar:

* [E-post](#email)
* [Push-meddelanden](#push)
* [SMS](#sms)
* [I appen](#inapp)
* [Webb](#web)
* [Direktmeddelande](#direct-mail)

➡️ [Upptäck den här funktionen i videon](#channel-report-video)

## E-post {#email}

Från kanalrapporter visar e-postmenyn huvudinformationen om e-postmeddelanden som skickas i kampanjer och resor. Mätvärdena anges nedan.

### E-post - total sändningsstatistik {#email-total-sending}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_sending_statistics"
>title="E-post - total sändningsstatistik"
>abstract="KPI:erna för sändning av statistik för e-post - totalt sammanfattar viktiga data om dina e-postmeddelanden, som riktade eller levererade meddelanden."

![](assets/channel_email_total_sending.png)

Widgeten **[!UICONTROL Email Total Sending Statistics]** ger en omfattande översikt över din e-postprestanda och visar nyckeltal (KPI) som sammanfattar viktiga data om dina e-postmeddelanden.

+++ Läs mer om statistik för sändning via e-post

* **[!UICONTROL Targeted]**: Totalt antal bearbetade e-postmeddelanden.

* **[!UICONTROL Sent]**: Totalt antal skickade meddelanden.

* **[!UICONTROL Delivered]**: Antal e-postmeddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

* **[!UICONTROL Delivery Rate]**: Procentandel e-postmeddelanden har skickats.

* **[!UICONTROL Bounces]**: Totalt antal kumulerade fel och automatisk returbearbetning i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Bounce Rate]**: Procentandel e-postmeddelanden som studsade jämfört med skickade e-postmeddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som har inträffat som förhindrar att den skickas till profiler.

* **[!UICONTROL Error Rate]**: Procentandel fel som inträffade som förhindrade att det skickades jämfört med skickade e-postmeddelanden.

* **[!UICONTROL Excluded]**: Antal profiler som har undantagits av Adobe Journey Optimizer.

* **[!UICONTROL Exclude rate]**: Procentandel profiler som har undantagits av Adobe Journey Optimizer.

+++

### E-post - Total spårningsstatistik {#email-total-tracking}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_tracking_statistics"
>title="E-post - Total spårningsstatistik"
>abstract="KPI:erna för e-post - total spårningsstatistik tillhandahåller data om profilaktiviteten för dina e-postmeddelanden."

![](assets/channel_email_total_tracking.png)

Widgeten **[!UICONTROL Email Total Tracking statistics]** erbjuder en detaljerad ögonblicksbild av profilaktivitet som är kopplad till dina e-postmeddelanden, och ger viktiga insikter om engagemang och e-posteffektivitet.

+++ Läs mer om statistik för uppföljning av totalt e-postmeddelande

* **[!UICONTROL Opens]**: Antal gånger som meddelandet öppnades.

* **[!UICONTROL Open Rate]**: Totalt antal öppnade e-postmeddelanden jämfört med antalet levererade e-postmeddelanden.

* **[!UICONTROL Clicks]**: Antal gånger ett innehåll klickades i ett meddelande.

* **[!UICONTROL Click rate]**: Procentandel användare som interagerade med e-postmeddelandet.

* **[!UICONTROL Spam complaints]**: Antal gånger ett meddelande har deklarerats som skräppost eller skräppost.

* **[!UICONTROL Spam complaint rate]**: Procentandel av meddelandet som deklarerats som skräppost eller skräppost jämfört med antalet skickade e-postmeddelanden.

* **[!UICONTROL Unsubscribes]**: Antal klick på prenumerationslänken.

* **[!UICONTROL Unsubscribe rate]**: Procentandel för avprenumeration jämfört med antalet skickade e-postmeddelanden.

+++

### E-post - skicka statistik över tid {#email-sending-statistics-overtime}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_sending_statistics_overtime"
>title="E-post - skicka statistik över tid"
>abstract="Diagrammet E-post - skicka statistik över tid visar data om skickade e-postmeddelanden, uppdelade per timme, dag, vecka eller månad."

![](assets/channel_email_sending_statistics.png)

Diagrammet **[!UICONTROL Email - Sending Statistics over time]** innehåller en dynamisk representation som visar en analys av din e-postaktivitet. Den grafiska representationen ger en omfattande beskrivning av skickade e-postmeddelanden, så att du kan följa trender och mönster på en tim-, daglig-, vecko- eller månadsnivå.

+++ Läs mer om e-post - Skicka statistik över tidsvärden

* **[!UICONTROL Sent]**: Totalt antal skickade meddelanden.

* **[!UICONTROL Delivered]**: Antal e-postmeddelanden som har skickats, i relation till det totala antalet skickade e-postmeddelanden.

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats och automatisk returbehandling i relation till totalt antal skickade e-postmeddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som har inträffat som förhindrar att den skickas till profiler.

+++

### E-post - Spårningsstatistik över tid {#email-tracking-statistics-overtime}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_tracking_statistics_overtime"
>title="E-post - Spårningsstatistik över tid"
>abstract="Diagrammet E-post - Spårningsstatistik över tid visar data om profilaktiviteten för dina e-postmeddelanden, uppdelade per timme, dag, vecka eller månad."

![](assets/channel_email_tracking_overtime.png)

Diagrammet **[!UICONTROL Email - Tracking statistics over time]** innehåller en detaljerad översikt över profilaktivitet som är relaterad till dina e-postmeddelanden. Den grafiska representationen delar upp informationen varje timme, dag, vecka eller månad, och ger värdefulla insikter om hur mottagarengagemanget utvecklas över olika tidsintervall.

+++ Läs mer om e-post - Spåra statistik över tidsvärden

* **[!UICONTROL Opens]**: Antal gånger som meddelandet öppnades.

* **[!UICONTROL Clicks]**: Antal gånger ett innehåll klickades i ett meddelande.

+++

### E-post - studskategorier och orsaker {#bounce-categories}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_bounce_categories"
>title="Studskategorier"
>abstract="Diagram och tabell för studskategorier innehåller data om både temporära och permanenta fel."

>[!CONTEXTUALHELP]
>id="ajo_channel_email_bounce_reasons"
>title="Brytningsorsaker"
>abstract="Diagram över studentorsaker och tabellen innehåller tillgängliga data om studsade meddelanden."

![](assets/channel_email_bounce_categories.png)

Widgetarna **[!UICONTROL Bounce categories]** och **[!UICONTROL Bounce reasons]** kapslar in data som är kopplade till studsade meddelanden, vilket ger en omfattande översikt över de olika kategorierna och specifika orsaker bakom meddelandegränser

Mer information om studsar finns på sidan [Suppressionslista](../reports/suppression-list.md).

+++ Läs mer om statistik för studskategorier

* **[!UICONTROL Hard bounce]**: Det totala antalet permanenta fel, till exempel en felaktig e-postadress. Detta inbegriper ett felmeddelande som uttryckligen anger att adressen är ogiltig, till exempel Okänd användare.

* **[!UICONTROL Soft bounce]**: Det totala antalet tillfälliga fel, till exempel en fullständig inkorg.

* **[!UICONTROL Ignored]**: Det totala antalet tillfälliga, till exempel frånvaro, eller ett tekniskt fel, till exempel om avsändartypen är postmaster.

+++

### Felorsaker {#error-reasons}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_error_reasons"
>title="Felorsaker"
>abstract="Med hjälp av diagrammen och tabellen Felorsaker kan du identifiera de specifika fel som uppstod under sändningsprocessen."

![](assets/channel_email_error.png)

Med diagrammen och tabellen **[!UICONTROL Error Reasons]** kan du identifiera de exakta fel som uppstod under sändningsprocessen, vilket ger en tydlig förståelse för eventuella problem som har uppstått.

### Undantagna orsaker {#excluded-reasons}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_excluded_reasons"
>title="Undantagna orsaker"
>abstract="I diagrammen och tabellen Exkluderade orsaker visas de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen och inte fick meddelandet."

![](assets/channel_email_excluded.png)

Diagrammen och tabellen **[!UICONTROL Excluded reasons]** innehåller en heltäckande bild av de olika faktorer som har lett till att användarprofiler har tagits bort från målgruppen, vilket leder till att meddelandet inte tas emot.

Se [den här sidan](exclusion-list.md) för en utförlig lista över orsaker till undantag.

### Skickat och levererat av domäner {#sent-delivered-domains}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_sending_delivered_domains"
>title="Skickat och levererat av domäner"
>abstract="Diagrammet och tabellen för Skickat och levererat per domän representerar domännivåuppdelning av alla viktiga e-postmeddelanden som skickar data."

![](assets/channel_email_sent_domains.png)

Tabellen och diagrammet **[!UICONTROL Sent & delivered by domains]** innehåller en detaljerad beskrivning av e-postleveranser på domännivå, med omfattande insikter om hur dina e-postmeddelanden fungerar.

+++ Läs mer om Sänd och levererad via domänmått

* **[!UICONTROL Sent]**: Totalt antal skickade meddelanden för din e-post.

* **[!UICONTROL Delivered]**: Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.

+++

### Begränsningar och fel per domäner {#bounces-errors-domains}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_bounces_errors_domains"
>title="Begränsningar och fel per domäner"
>abstract="Diagram och tabell över studsar och fel per domän representerar domännivåuppdelning av specifika fel som inträffade under sändningsprocessen."

![](assets/channel_email_bounces_domain.png)

Diagrammet och tabellen **[!UICONTROL Bounces & errors by domains]** innehåller en beskrivning på domännivå av specifika fel som påträffats under sändningsprocessen, vilket ger en detaljerad analys av problem som uppstått.

+++ Läs mer om studsar och fel per domänmått

* **[!UICONTROL Bounces]**: Totalt antal fel som har ackumulerats under sändningsprocessen och automatisk returbearbetning i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.

+++

### Öppna och klicka efter domäner {#open-clicks-domains}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_open_clicks_domains"
>title="Öppna och klicka efter domäner"
>abstract="Grafen och tabellen Öppna och klicka per domän visar en domännivåuppdelning av besökarnas engagemang i e-postmeddelandet."

![](assets/channel_email_open_domains.png)

Diagrammet och tabellen **[!UICONTROL Open & clicks by domains]** visar en uppdelning på domännivå av besökarnas engagemang i ditt e-postmeddelande, vilket ger värdefulla insikter om hur olika domäner interagerar med ditt innehåll.

+++ Läs mer om Öppna och klickningar efter domänstatistik

* **[!UICONTROL Opens]**: Antal gånger som e-postmeddelandet öppnades.

* **[!UICONTROL Clicks]**: Antal gånger ett innehåll klickades i ett e-postmeddelande.

+++

### Studsa orsaker efter domän {#bounce-reasons-domains}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_bounce_reasons_domains"
>title="Studsa orsaker efter domän"
>abstract="Studsorsaker per domän per domändiagram och tabell representerar domännivåuppdelning av data för både temporära och permanenta fel."

![](assets/channel_email_bounce_domain.png)

Diagrammet och tabellen **[!UICONTROL Bounce reasons by domain]** erbjuder en uppdelning på domännivå av data som gäller både tillfälliga och permanenta fel, vilket ger detaljerad information om orsakerna bakom studsade meddelanden.

Mer information om studsar finns på sidan [Suppressionslista](../reports/suppression-list.md).

## Push-meddelande {#push}

Från kanalrapporter visar menyn **Push Notification** huvudinformationen i relation till push-meddelanden som skickas i dina kampanjer och resor. Mätvärdena anges nedan.

### Push-meddelanden - totalt antal utskicksstatistik {#push-total-sending}

>[!CONTEXTUALHELP]
>id="ajo_channel_push_sending_statistics"
>title="Push-meddelanden - totalt antal utskicksstatistik"
>abstract="Push-meddelanden - Totalt antal KPI:er för sändning av statistik sammanfattar viktiga data om dina push-meddelanden, som Target eller Delivery."

![](assets/channel_push_total_sending.png)

KPI:erna för **[!UICONTROL Push notifications - Total sending statistics]** fungerar som en omfattande sammanfattning, som kapslar in viktiga data relaterade till dina push-meddelanden. Dessa mätvärden inkluderar detaljerade insikter om målgruppen och leveransstatus, vilket ger en detaljerad bild av hur effektiva och omfattande push-meddelandena är.

+++ Lär dig mer om push-meddelanden - statistik för totalt skickade meddelanden

* **[!UICONTROL Targeted]**: Totalt antal push-meddelanden som bearbetats.

* **[!UICONTROL Sent]**: Totalt antal skickade push-meddelanden.

* **[!UICONTROL Delivered]**: Antal push-meddelanden som har skickats, i relation till det totala antalet skickade push-meddelanden.

* **[!UICONTROL Delivery Rate]**: Procentandel push-meddelanden har skickats.

* **[!UICONTROL Bounces]**: Totalt antal kumulerade fel och automatisk returbearbetning i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Bounce Rate]**: Procentandel push-meddelanden som studsade jämfört med skickade push-meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som har inträffat som förhindrar att den skickas till profiler.

* **[!UICONTROL Error Rate]**: Procentandel fel som inträffade som förhindrade att det skickades jämfört med skickade push-meddelanden.

* **[!UICONTROL Excluded]**: Antal profiler som har undantagits av Adobe Journey Optimizer.

* **[!UICONTROL Exclude rate]**: Procentandel profiler som har undantagits av Adobe Journey Optimizer.

+++

### Push-meddelande - Total spårningsstatistik {#push-total-tracking}

>[!CONTEXTUALHELP]
>id="ajo_channel_push_tracking_statistics"
>title="Push-meddelande - Total spårningsstatistik"
>abstract="Push-meddelandet - Total spårningsstatistik innehåller data om profilaktivitet för dina push-meddelanden."

Widgeten **[!UICONTROL Push notification - Total tracking statistics]** erbjuder en detaljerad ögonblicksbild av profilaktivitet som är kopplad till dina push-meddelanden, vilket ger viktiga insikter om engagemang och push-meddelandenas effektivitet.

+++ Läs mer om push-meddelanden - statistik för total spårning

* **[!UICONTROL Opens]**: Antal gånger ett push-meddelande öppnades.

* **[!UICONTROL Open Rate]**: Procentandel öppna push-meddelanden.

* **[!UICONTROL Actions]**: Totalt antal åtgärder för det skickade push-meddelandet, t.ex. knappklickning eller avbruten.

* **[!UICONTROL Action rate]**: Procentandel åtgärder för levererade push-meddelanden jämfört med skickade push-meddelanden.

+++

### Push-meddelanden - skicka statistik över tid {#push-sending-overtime}

>[!CONTEXTUALHELP]
>id="ajo_channel_push_sending_statistics_overtime"
>title="Push-meddelanden - skicka statistik över tid"
>abstract="I diagrammet Push Notification Sending för tid visas data om skickade push-meddelanden, uppdelade per timme, dag, vecka eller månad."

![](assets/channel_push_sending_statistics.png)

Diagrammet **[!UICONTROL Push notifications - Sending statistics over time]** innehåller en dynamisk representation som visar en analys av din push-meddelandeaktivitet. Denna grafiska representation ger en omfattande beskrivning av skickade push-meddelanden, så att du kan observera trender och mönster varje timme, dag, vecka eller månad.

+++ Läs mer om push-meddelanden - Skicka statistik över tid

* **[!UICONTROL Sent]**: Totalt antal skickade push-meddelanden.

* **[!UICONTROL Delivered]**: Antal push-meddelanden som har skickats, i relation till det totala antalet skickade push-meddelanden.

* **[!UICONTROL Bounces]**: Totalt antal kumulerade fel och automatisk returbearbetning i relation till totalt antal skickade meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som har inträffat som förhindrar att den skickas till profiler.

+++

### Push-meddelanden - Spåra statistik över tid {#push-tracking-overtime}

>[!CONTEXTUALHELP]
>id="ajo_channel_push_tracking_statistics_overtime"
>title="Push-meddelanden - Spåra statistik över tid"
>abstract="Push-meddelandena - Spårningsstatistik över tid-diagrammet ger data om profilaktiviteten för dina push-meddelanden, uppdelade per timme, dag, vecka eller månad."

Diagrammet **[!UICONTROL Push notifications - Tracking statistics over time]** innehåller en detaljerad översikt över profilaktivitet som är relaterad till dina push-meddelanden. Den grafiska representationen delar upp informationen varje timme, dag, vecka eller månad, och ger värdefulla insikter om hur mottagarengagemanget utvecklas över olika tidsintervall.

+++ Läs mer om push-meddelanden - Spåra statistik över tid

* **[!UICONTROL Opens]**: Antal gånger ditt push-meddelande öppnades.

* **[!UICONTROL Actions]**: Totalt antal åtgärder för det skickade push-meddelandet, t.ex. knappklickning eller avbruten.

+++

### Push-meddelanden - Undantagna orsaker {#push-excluded-reasons}

>[!CONTEXTUALHELP]
>id="ajo_channel_push_excluded_reasons"
>title="Undantagna orsaker"
>abstract="I diagrammen och tabellen Exkluderade orsaker visas de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen och inte fick meddelandet."

![](assets/channel_push_excluded.png)

Diagrammet och tabellen **[!UICONTROL Excluded reasons]** visar olika orsaker som hindrade användarprofiler, som exkluderats från målprofilerna, från att ta emot push-meddelanden.

Se [den här sidan](exclusion-list.md) för en utförlig lista över orsaker till undantag.

### Push-meddelanden - felorsaker {#push-error-reasons}

>[!CONTEXTUALHELP]
>id="ajo_channel_push_error_reasons"
>title="Felorsaker"
>abstract="Med hjälp av diagrammen och tabellen Felorsaker kan du identifiera de specifika fel som uppstod under sändningsprocessen."

![](assets/channel_push_error.png)

Diagrammen och tabellen **[!UICONTROL Error Reasons]** ger dig möjlighet att identifiera de specifika fel som uppstod under sändningsprocessen för dina push-meddelanden, och ger dig detaljerade insikter om eventuella problem som påträffas längs vägen.

### Push-meddelanden - Spårning per plattform {#push-tracking-platform}

>[!CONTEXTUALHELP]
>id="ajo_channel_push_tracking_statistics_platform"
>title="Spårningsstatistik per plattform"
>abstract="Spårningsstatistiken per plattform - diagram och tabell visar data om profilaktiviteten för dina push-meddelanden beroende på vilken profil du har."

Diagram och tabeller från **[!UICONTROL Push notifications - Tracking by platform]** visar mottagaraktiviteten för push-meddelandet beroende på vilken profil du har.

### Push-meddelanden - Skicka efter plattform {#push-sending-platform}

>[!CONTEXTUALHELP]
>id="ajo_channel_push_sending_statistics_platform"
>title="Skicka statistik per plattform"
>abstract="Diagram och tabell för att skicka statistik per plattform visar data om skickade push-meddelanden."

![](assets/channel_push_sending_platform.png)

Diagrammet och tabellerna **[!UICONTROL Push notifications - Sending by platform]** innehåller en omfattande beskrivning av om push-meddelandena lyckades i förhållande till profilernas operativsystem. Denna grundliga analys ger värdefulla insikter om hur effektiva era push-meddelanden är på olika plattformar.

## SMS {#sms}

Från dina **Channel**-rapporter visar SMS-menyn huvudinformationen i förhållande till SMS som skickas i dina kampanjer och resor. Mätvärdena anges nedan.

### SMS - Total sändningsstatistik {#sms-sending-statistics}

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_sending_statistics"
>title="SMS - Total sändningsstatistik"
>abstract="SMS - Totalt antal KPI:er för sändning av statistik sammanfattar viktiga data om dina SMS-meddelanden, som Riktat eller Levererat."

![](assets/channel_sms_total_sending.png)

KPI:erna för **[!UICONTROL SMS - Total sending statistics]** fungerar som en omfattande sammanfattning som kapslar in viktiga data relaterade till ditt SMS. Dessa mätvärden inkluderar detaljerade insikter om målgruppen och leveransstatus, vilket ger en detaljerad bild av effektiviteten och räckvidden i era SMS-meddelanden.

+++ Lär dig mer om push-meddelanden - statistik för totalt skickade meddelanden

* **[!UICONTROL Targeted]**: Antal användarprofiler som kvalificerar sig som målprofiler för SMS-kanal.

* **[!UICONTROL Sent]**: Totalt antal skickade SMS-meddelanden.

* **[!UICONTROL Delivered]**: Antal SMS-meddelanden som har skickats, i relation till det totala antalet skickade SMS-meddelanden.

* **[!UICONTROL Delivery Rate]**: Procentandel SMS-meddelanden har skickats.

* **[!UICONTROL Bounces]**: Totalt antal kumulerade fel och automatisk returbearbetning i relation till totalt antal skickade SMS-meddelanden.

* **[!UICONTROL Bounce Rate]**: Procentandel SMS-meddelanden som studsade jämfört med skickade SMS-meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som har inträffat som förhindrar att den skickas till profiler.

* **[!UICONTROL Error Rate]**: Procentandel fel som inträffade som förhindrade att det skickades jämfört med skickade SMS-meddelanden.

* **[!UICONTROL Excluded]**: Antal användarprofiler, exkluderade från målprofilerna, som inte fick meddelandet.

* **[!UICONTROL Exclude rate]**: Procentandel profiler som har undantagits av Adobe Journey Optimizer.

+++

### SMS - Total spårningsstatistik {#sms-tracking-statistics}

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_tracking_statistics"
>title="SMS - Total spårningsstatistik"
>abstract="SMS - Total spårningsstatistik ger data om profilaktivitet för dina SMS-meddelanden."

![](assets/channel_sms_tracking.png)

Widgeten **[!UICONTROL SMS - Total tracking statistics]** ger en detaljerad översikt över viktig information som rör besökarnas interaktion med dina URL:er, och ger insikter om hur effektiva dina SMS-meddelanden är:

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades i SMS-meddelandet.

### SMS - Skicka statistik över tid {#sms-sending-statistics-overtime}

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_sending_statistics_overtime"
>title="SMS - Skicka statistik över tid"
>abstract="Diagrammet SMS - Skicka statistik över tid visar data om skickade SMS-meddelanden, uppdelade per timme, dag, vecka eller månad."

![](assets/channel_sms_sending_overtime.png)

Diagrammet **[!UICONTROL SMS - Sending statistics over time]** ger en heltäckande bild av skickade SMS-meddelanden och ger data uppdelade per timme, dag, vecka eller månad. Med den här grafiska representationen kan du spåra och analysera trender i SMS-meddelandeaktiviteten över olika tidsintervall.

+++ Läs mer om SMS - Skicka statistik över tidsvärden

* **[!UICONTROL Sent]**: Totalt antal skickade SMS-meddelanden.

* **[!UICONTROL Bounces]**: Totalt antal kumulerade fel och automatisk returbearbetning i relation till totalt antal skickade SMS-meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som har inträffat som förhindrar att den skickas till profiler.

+++

### SMS - Spårningsstatistik över tid {#sms-tracking-statistics-overtime}

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_tracking_statistics_overtime"
>title="SMS - Spårningsstatistik över tid"
>abstract="Diagrammet SMS - Spårningsstatistik över tid visar data om profilaktiviteten för dina SMS-meddelanden, uppdelat per timme, dag, vecka eller månad."

![](assets/channel_sms_tracking_overtime.png)

Diagrammet **[!UICONTROL SMS - Tracking statistics over time]** innehåller data om profilaktiviteter som är relaterade till dina SMS-meddelanden, med detaljerad information om varje timme, dag, vecka eller månad. Denna grafiska representation gör att ni kan analysera och förstå mönster i användarinteraktionen över olika tidsintervall.

* **[!UICONTROL Clicks]**: Antal gånger som ett innehåll klickades i SMS-meddelandet.

### Undantagna orsaker {#sms-excluded-reasons}

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_excluded_reasons"
>title="Undantagna orsaker"
>abstract="I diagrammen och tabellen Exkluderade orsaker visas de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen och inte fick meddelandet."

![](assets/channel_sms_excluded.png)

Diagrammen och tabellen **[!UICONTROL Excludes Reasons]** visar visuellt de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen, vilket förhindrar dem från att ta emot SMS-meddelanden.

Se [den här sidan](exclusion-list.md) för en utförlig lista över orsaker till undantag.

### Brytningsorsaker {#sms-bounce-reasons}

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_bounce_reasons"
>title="Brytningsorsaker"
>abstract="Diagram över studentorsaker och tabellen innehåller tillgängliga data om studsade meddelanden."

![](assets/channel_sms_bounce_reasons.png)

Diagrammen och tabellen **[!UICONTROL Bounces Reasons]** ger en omfattande översikt över data som är relaterade till studsade SMS-meddelanden och ger värdefulla insikter om de specifika orsakerna bakom instanser av SMS-meddelandegränser.

### Felorsaker {#sms-error-reasons}

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_error_reasons"
>title="Felorsaker"
>abstract="Med hjälp av diagrammen och tabellen Felorsaker kan du identifiera de specifika fel som uppstod under sändningsprocessen."

Med diagrammen och tabellen **[!UICONTROL Error Reasons]** kan du identifiera de specifika fel som uppstod under sändningsprocessen för SMS-meddelanden, vilket underlättar en grundlig analys av eventuella problem som påträffats.

## Direktmeddelande {#direct-mail}

Från dina **kanalrapporter** visar menyn **Direktutskick** huvudinformationen i relation till direktutskick som skickas i dina **kampanjer** och **resor**. Metrucs anges nedan.

### Direktutskick - totalt utskicksstatistik {#direct-mail-total-sending}

>[!CONTEXTUALHELP]
>id="ajo_channel_direct_sending_statistics"
>title="Direktutskick - totalt utskicksstatistik"
>abstract="KPI:er för direktutskick - Totalt antal utskickande av statistik sammanfattar viktiga data om dina direktutskick, till exempel riktad eller levererad."

![](assets/channel_direct_sending.png)

Widgeten **[!UICONTROL Direct mail - Total sending statistics]** ger en omfattande översikt över hur dina direktutskick fungerar och visar nyckeltal (KPI) som sammanfattar viktiga data om dina direktutskick.

+++ Läs mer om direktreklam - statistik som skickas totalt

* **[!UICONTROL Targeted]**: Antal användarprofiler som kvalificerar som målprofiler för dina Direct-postmeddelanden.

* **[!UICONTROL Sent]**: Totalt antal skickade meddelanden.

* **[!UICONTROL Errors]**: Totalt antal fel som har inträffat som förhindrar att den skickas till profiler.

* **[!UICONTROL Error Rate]**: Procentandel fel som inträffade som förhindrade att det skickades jämfört med skickade push-meddelanden.

* **[!UICONTROL Excluded]**: Antal användarprofiler, exkluderade från målprofilerna, som inte fick meddelandet.

* **[!UICONTROL Exclude rate]**: Procentandel profiler som har undantagits av Adobe Journey Optimizer.

+++

### Undantagna orsaker {#direct-mail-excluded-reasons}

>[!CONTEXTUALHELP]
>id="ajo_channel_direct_excluded_reasons"
>title="Undantagna orsaker"
>abstract="I diagrammen och tabellen Exkluderade orsaker visas de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen och inte fick meddelandet."

![](assets/channel_direct_excluded.png)

Diagrammen och tabellen **[!UICONTROL Direct Mail - Excluded reasons]** illustrerar visuellt de olika faktorer som resulterade i att användarprofiler exkluderades från målgruppen, vilket förhindrar dem från att ta emot dina direktutskick.

Se [den här sidan](exclusion-list.md) för en utförlig lista över orsaker till undantag.

### Felorsaker {#direct-mail-error-reasons}

>[!CONTEXTUALHELP]
>id="ajo_channel_direct_error_reasons"
>title="Felorsaker"
>abstract="Med hjälp av diagrammen och tabellen Felorsaker kan du identifiera de specifika fel som uppstod under sändningsprocessen."

![](assets/channel_direct_error.png)

**[!UICONTROL Direct Mail - Error reasons]** ger möjlighet att identifiera specifika fel som uppstod under sändningsprocessen för dina direktmeddelanden, vilket gör det möjligt att göra en detaljerad analys av eventuella problem som påträffats.

## I appen {#in-app}

Från kanalrapporterna visar menyn i appen huvudinformationen i förhållande till meddelanden i appen som skickas i era kampanjer och resor. Mätvärdena anges nedan.

### Totalt engagemang i appar {#inapp-total-engagement}

>[!CONTEXTUALHELP]
>id="ajo_channel_inapp_engagement"
>title="Intern användning - totalt engagemang"
>abstract="KPI:erna för engagemang i appen - totalt ger omfattande information om besökarnas engagemang i era meddelanden i appen, inklusive mått som Impressions och Interactions."

![](assets/channel_inapp_engagement.png)

KPI:erna för **[!UICONTROL In-app total engagement]** ger omfattande insikter om besökarnas engagemang i dina meddelanden i appen, med nyckeltal som **Impressions** och **Interactions**.

+++ Läs mer om totala engagemangsmått i appar

* **[!UICONTROL Impressions]**: Totalt antal meddelanden i appen som levereras till alla användare.

* **[!UICONTROL Interactions]**: Totalt antal ärenden i ditt meddelande i appen. Detta inkluderar alla åtgärder som användaren utför, t.ex. klickningar, uppsägningar eller annan interaktion.

+++

### Interaktionsövertid i appen {#inapp-engagement-overtime}

>[!CONTEXTUALHELP]
>id="ajo_channel_inapp_engagement_overtime"
>title="Intern aktivering - övertid"
>abstract="I appen - Engagement-övertidsdiagram kan man se intryck och interaktioner i appen, vilket ger fördelning per timme, dag, vecka och månad."

![](assets/channel_inapp_engagement_overtime.png)

Diagrammet **[!UICONTROL In-app engagement overtime]** visar hur dina visningar och interaktioner i appen har utvecklats under den aktuella perioden genom att spåra alla visningar, avvisningar eller interaktioner.

+++ Läs mer om interaktionsövertidstatistik i appen

* **[!UICONTROL Impressions]**: Totalt antal meddelanden i appen som levereras till alla användare.

* **[!UICONTROL Interactions]**: Totalt antal ärenden i ditt meddelande i appen. Detta inkluderar alla åtgärder som användaren utför, t.ex. klickningar, uppsägningar eller annan interaktion.

+++

## Webb {#web}

Från dina **kanalrapporter** visar webbmenyn huvudinformationen i förhållande till webbsidorna som ingår i dina **kampanjer** och **resor**. Mätvärdena anges nedan.

### Webb - Totalt engagemang {#web-engagement-total}

>[!CONTEXTUALHELP]
>id="ajo_channel_web_engagement"
>title="Webb - Totalt engagemang"
>abstract="Webben - Total engagemangs-KPI:er ger omfattande information om besökarnas interaktion med era webbsidor, inklusive mått som Impressions och Interactions."

![](assets/channel_web_engagement.png)

KPI:erna för **[!UICONTROL Web total engagement]** ger omfattande insikter om besökarnas engagemang på dina webbsidor, med nyckeltal som Impressions och Interactions.

+++ Läs mer om totala engagemangsmått på webben

* **[!UICONTROL Impressions]**: Totalt antal webbupplevelser som levereras till alla användare.

* **[!UICONTROL Interactions]**: Totalt antal ärenden på din webbsida. Detta inkluderar alla åtgärder som användaren utför, t.ex. klickningar eller andra interaktioner.

+++

### Webb - Total engagemangsövertid {#web-engagement-total-overtime}

>[!CONTEXTUALHELP]
>id="ajo_channel_web_engagement_overtime"
>title="Webb - Total engagemangsövertid"
>abstract="Webben - Engagement overtime-diagram visar hur webbsidorna ser ut och hur de interagerar. Du kan dela upp dem varje timme, dag, vecka och månad."

![](assets/channel_web_engagement_overtime.png)

Diagrammet **[!UICONTROL Web engagement overtime]** övervakar **Impressions** och **Interactions** för dina webbsidor och ger detaljerade uppdelningar per timme, dag, vecka och månad.

+++ Läs mer om mätvärden för webbengagemang

* **[!UICONTROL Impressions]**: Totalt antal webbupplevelser som levereras till alla användare.

* **[!UICONTROL Interactions]**: Totalt antal ärenden på din webbsida. Detta inkluderar alla åtgärder som användaren utför, t.ex. klickningar eller andra interaktioner.

+++

## Kanalrapport (video) {#channel-report-video}

Lär dig hur du får åtkomst till, navigerar och exporterar rapporter på kanalnivå i den här videon

>[!VIDEO](https://video.tv.adobe.com/v/3424537?quality=12)
