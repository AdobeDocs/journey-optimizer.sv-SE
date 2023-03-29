---
solution: Journey Optimizer
product: journey optimizer
title: Live-rapport
description: Lär dig använda data från liverapporten
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 8dd48bb2-a805-4c46-a16c-c68173a9ac08
source-git-commit: 4f3d22c9ce3a5b77969a2a04dafbc28b53f95507
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 2%

---

# Kom igång med Live Report {#live-report}

Använd **[!UICONTROL Live report]** att i realtid mäta och visualisera påverkan och resultat av era resor och era meddelanden i en inbyggd kontrollpanel.
Data finns i **[!UICONTROL Live report]** så snart leveransen har skickats eller din resa har körts från **[!UICONTROL Last 24hrs]** -fliken.

* Om du vill rikta in dig på en resa i samband med en resa, från **[!UICONTROL Journeys]** -menyn, få åtkomst till din resa och klicka på **[!UICONTROL View report]** -knappen.

   ![](assets/report_journey.png)

* Om du vill rikta in en kampanj går du till **[!UICONTROL Campaigns]** öppnar du kampanjen och klickar på **[!UICONTROL Reports]** -knappen.

   ![](assets/report_campaign.png)

* Om du vill växla från **[!UICONTROL Global report]** till **[!UICONTROL Live report]** för leverans klickar du **[!UICONTROL Last 24hrs]** i flikväxlaren.

   ![](assets/report_3.png)

En detaljerad lista över alla mätvärden som är tillgängliga i Adobe Journey Optimizer finns på [den här sidan](#list-of-components-live).

## Anpassa kontrollpanelen {#modify-dashboard}

Varje rapportkontrollpanel kan ändras genom att widgetar storleksändras eller tas bort. Om du ändrar widgetarna påverkas bara den aktuella användarens kontrollpanel. Andra användare ser sina egna kontrollpaneler eller de som har angetts som standard.

1. Från **[!UICONTROL Actions]** väljer du om du vill rapportera en viss åtgärd på dina resor.

1. Välj om du vill utesluta testhändelser från dina rapporter med hjälp av alternativfältet. Mer information om testhändelser finns i [den här sidan](../building-journeys/testing-the-journey.md).

   Observera att **[!UICONTROL Exclude test events]** alternativet är bara tillgängligt för reserapporter.

   ![](assets/report_modify_6.png)

1. Om du vill ändra storlek på eller ta bort widgetar klickar du på **[!UICONTROL Modify]**.

   ![](assets/report_modify_7.png)

1. Justera widgetarnas storlek genom att dra i det nedre högra hörnet.

   ![](assets/report_modify_8.png)

1. Klicka **[!UICONTROL Remove]** för att ta bort widgetar du inte behöver.

   ![](assets/report_modify_9.png)

1. När du är nöjd med visningsordningen och widgetarnas storlek klickar du på **[!UICONTROL Save]**.

1. Om du vill anpassa hur data visas kan du växla mellan olika visualiseringsalternativ, som diagram, tabeller och dondiagram.

   ![](assets/report_modify_11.png)

Instrumentpanelen har nu sparats. Dina olika ändringar kommer att tillämpas på nytt för senare användning av dina liverapporter. Använd **[!UICONTROL Reset]** för att återställa standardordningen för widgetar och widgetar.

## Lista över komponenter {#list-of-components-live}

Tabellerna nedan ger dig en lista över de mätvärden som används i rapporter och deras definitioner beroende på leveranstyp.

### Resemått {#journey-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Mått<br/> </th> 
   <th> Definition<br/> </th> 
</tr>
 </thead> 
 <tbody> 
  <tr> 
   <td>Åtgärderna har körts<br/> </td> 
   <td> Totalt antal slutförda åtgärder för en resa.<br/> </td> 
</tr> 
  <tr> 
   <td> Angivna profiler<br/> </td> 
   <td> Totalt antal personer som har nått resans inträde.<br/> </td> 
</tr>
  <tr> 
   <td> Fel i åtgärd<br/> </td> 
   <td>Totalt antal fel som uppstått för åtgärder.<br/> </td> 
</tr> 
  <tr> 
   <td> Avslutade profiler<br/> </td> 
   <td> Totalt antal personer som avbrutit resan.<br/> </td> 
</tr> 
  <tr> 
   <td> Misslyckad enskild resa<br/> </td> 
   <td> Totalt antal enskilda resor som inte har slutförts.<br/> </td> 
</tr> 
 </tbody> 
</table>

### Dimensioner och mått för e-post och SMS {#email-and-sms-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Mått<br/> </th> 
   <th> Definition<br/> </th> 
</tr>
 </thead> 
 <tbody>
  <tr> 
   <td> Studsar<br/> </td> 
   <td> Totalt antal fel som ackumulerats under leverans och automatisk returbearbetning.<br/> </td> 
</tr> 
  <tr> 
   <td> Studsfrekvens<br/> </td> 
   <td> Procentandel e-postmeddelanden som studsade jämfört med skickade e-postmeddelanden.<br/> </td> 
</tr>
  <tr> 
   <td> Klickningar<br/> </td> 
   <td> Antal gånger ett innehåll klickades i ett e-postmeddelande.<br/> </td> 
</tr> 
  <tr> 
   <td> Levererat <br/> </td> 
   <td> Antal meddelanden som har skickats.<br/></td> 
</tr> 
  <tr> 
   <td> Leveransnivå<br/> </td> 
   <td> Procentandel meddelanden som har skickats.<br/> </td> 
</tr>
  <tr> 
   <td> Fel<br/> </td> 
   <td> Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.<br/> </td> 
</tr> 
  <tr> 
   <td> Felfrekvens<br/> </td> 
   <td> Procentandel fel som uppstod under en leverans och som förhindrar att den skickas jämfört med skickade e-postmeddelanden.<br/> </td> 
</tr>
  <tr> 
   <td> Exkluderad<br/> </td> 
   <td> Antal profiler som har uteslutits av Adobe Journey Optimizer.<br/> </td> 
</tr>
  <tr> 
   <td> Hård studs<br/> </td> 
   <td> Det totala antalet permanenta fel, t.ex. fel e-postadress. Detta inbegriper ett felmeddelande som uttryckligen anger att adressen är ogiltig, till exempel Okänd användare.<br/> </td>
</tr>
  <tr> 
   <td> Ignorerad<br/> </td> 
   <td> Det totala antalet tillfälliga, t.ex. frånvaro, eller ett tekniskt fel, t.ex. om avsändartypen är postmaster.<br/> </td> 
</tr>
   <tr> 
   <td>Erbjud klickfrekvens<br/> </td> 
   <td>Procentandel användare som interagerade med erbjudandet.<br/> </td> 
</tr>
   <tr> 
   <td>Erbjud tittarfrekvens<br/> </td> 
   <td>Procentandel öppnade erbjudanden jämfört med antalet skickade erbjudanden.<br/> </td> 
</tr>
   <tr> 
   <td>Namn på erbjudande<br/> </td> 
   <td> Namn på erbjudandet som lagts till i leveransen. Mer information om placering finns i <a href="../offers/offer-library/creating-personalized-offers.md">page</a>.<br/> </td> 
</tr>
   <tr> 
   <td>Erbjudandet har skickats<br/> </td> 
   <td>Totalt antal utskick för erbjudandet.<br/> </td> 
</tr> 
  <tr>
   <td>Öppnar<br/> </td> 
   <td> Antal gånger som meddelandet öppnades.<br/> </td> 
</tr> 
  <tr> 
   <td> Öppen kurs<br/> </td> 
   <td> Totalt antal öppnade e-postmeddelanden jämfört med antalet levererade e-postmeddelanden.<br/> </td> 
</tr>
  <tr> 
   <td>Placeringsnamn<br/> </td> 
   <td> Namn på den placering som användes för att visa ditt erbjudande. Mer information om placering finns i <a href="../offers/offer-library/creating-placements.md">page</a>. </td> 
</tr> 
  <tr> 
   <td> Återförsök<br/> </td> 
   <td> Antal e-postmeddelanden i kön för återförsök.<br/> </td> 
</tr> 
  <tr> 
   <td> Skickat<br/> </td> 
   <td> Totalt antal försändelser för leveransen.<br/> </td> 
</tr>
  <tr> 
   <td> Mjuk studsa<br/> </td> 
   <td> Totalt antal tillfälliga fel, t.ex. en fullständig inkorg.<br/> </td> 
</tr>
  <tr> 
   <td> Skräppost<br/> </td> 
   <td> Antal gånger ett meddelande har deklarerats som skräppost eller skräppost.<br/> </td> 
</tr>
  <tr> 
   <td> Målinriktad<br/> </td> 
   <td> Totalt antal meddelanden som bearbetats under leveransanalysen.<br/> </td> 
</tr> 
  <tr> 
   <td> Unika klick<br/> </td> 
   <td> Antal mottagare som klickat på ett innehåll i ett e-postmeddelande.<br/> </td> 
</tr> 
  <tr> 
   <td>Unik klickfrekvens<br/> </td> 
   <td> Procentandel användare som interagerade med leveransen.<br/> </td> 
</tr>
  <tr> 
   <td> Unika öppningar<br/> </td> 
   <td>Antal mottagare som öppnade leveransen.<br/> </td> 
</tr> 
  <tr> 
   <td> Avprenumerationer<br/> </td> 
   <td> Antal klick på länken för att avbryta prenumerationen.<br/> </td> 
</tr> 
 </tbody> 
</table>

### Mätvärden för landningssida {#landing-page-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Mått<br/> </th> 
   <th> Definition<br/> </th> 
</tr>
 </thead> 
 <tbody>
 <tr> 
  <td>Studsar<br/> </td> 
   <td>Antal personer som inte interagerade med landningssidan och inte slutförde prenumerationsåtgärden.<br/> </td> 
</tr>
 <tr>
  <tr> 
   <td>Klickningar<br/> </td> 
   <td>Antal gånger som ett innehåll klickades på på landningssidan.<br/> </td> 
</tr>
<tr>
<td>Konvertering<br/> </td> 
   <td>Antal personer som interagerat med landningssidan, t.ex. prenumererat på ett formulär.<br/> </td> 
</tr>
 <tr> 
   <td>Resa(er)<br/> </td> 
   <td>Antal besök på landningssidan som kommer från en resa.<br/> </td> 
</tr>
 <tr> 
   <td>Andra källor<br/> </td> 
   <td>Antal besök på landningssidan som kommer från en extern källa i stället för en resa.<br/> </td> 
</tr>
 <tr> 
   <td>Totalt antal besök<br/> </td> 
   <td> Totalt antal besök på din landningssida som kommer från resor och externa källor, inklusive flera besök av en mottagare.<br/> </td> 
</tr>
 <tr> 
   <td>Unika besökare<br/> </td> 
   <td>Antal personer som besökte landningssidan, varav flera besök av en mottagare inte beaktas.<br/> </td> 
</tr>
 <tr> 
   <td>Besök<br/> </td> 
   <td>Antal besök på landningssidan, inklusive flera besök av en mottagare.<br/> </td> 
</tr>
 </tbody> 
</table>

### Mätvärden för push-meddelanden {#push-notification-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Mått<br/> </th> 
   <th> Definition<br/> </th> 
</tr>
 </thead> 
 <tbody>
 <tr> 
   <td>Instruktioner<br/> </td> 
   <td> Totalt antal åtgärder för push-meddelandet som levererats, t.ex. knappklickning eller avbruten.<br/> </td> 
</tr>
  <tr> 
   <td>Studsar<br/> </td> 
   <td> Totalt antal fel som ackumulerats under leverans och automatisk returbearbetning.<br/> </td> 
</tr> 
  <tr> 
   <td> Levererat<br/> </td> 
   <td> Antal meddelanden som har skickats.<br/> </td> 
</tr> 
  <tr> 
   <td>Åtaganden<br/> </td> 
   <td> Totalt antal öppningar och åtgärder för det här push-meddelandet, dvs om profilen öppnade push-meddelandet eller om någon klickade på en knapp.<br/> </td> 
</tr> 
  <tr> 
   <td> Fel<br/> </td> 
   <td> Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.<br/> </td> 
</tr>
  <tr> 
   <td> Exkluderad<br/> </td> 
   <td> Antal profiler som har uteslutits av Adobe Journey Optimizer.<br/> </td> 
</tr>
  <tr> 
   <td> Öppnar<br/> </td> 
   <td> Totalt antal push-meddelanden som levererats till enheten och användaren klickat på för att öppna appen. Detta liknar kommandot Push Click, men Push Open aktiveras inte om meddelandet stängs.<br/> </td> 
</tr> 
  <tr> 
   <td> Skickat<br/> </td> 
   <td> Totalt antal försändelser för leveransen.<br/> </td> 
</tr> 
  <tr> 
   <td> Målinriktad<br/> </td> 
   <td> Totalt antal push-meddelanden som bearbetats under leveransanalysen.<br/> </td> 
</tr>  
 </tbody> 
</table>

<!--
### In-app metrics {#inapp-metrics}
<table> 
 <thead> 
  <tr> 
   <th> Metric<br/> </th> 
   <th> Definition<br/> </th> 
</tr>
 </thead> 
 <tbody>
 <tr> 
   <td>Clicks<br/> </td> 
   <td>Total number of recipients who interacted with the buttons included in the In-app message.<br/> </td> 
</tr>
  <tr> 
   <td>Impressions<br/> </td> 
   <td> Total number of In-app messages delivered to all users.<br/> </td>
</tr>
  <tr> 
   <td>Unique impressions<br/> </td> 
   <td>Number of unique users to whom the In-app message was delivered.<br/> </td>
</tr>
 </tbody> 
</table>
-->