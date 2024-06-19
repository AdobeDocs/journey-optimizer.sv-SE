---
solution: Journey Optimizer
product: journey optimizer
title: Lista över komponenter
description: Lär dig använda data från den globala rapporten
feature: Reporting
topic: Content Management
role: User
level: Intermediate
source-git-commit: 854f593710a28bde605aa995d747d4e084a6c4b4
workflow-type: tm+mt
source-wordcount: '1110'
ht-degree: 0%

---

# Lista över komponenter {#list-of-components-global}

Tabellerna nedan ger dig en lista över de mätvärden som används i rapporter och deras definitioner beroende på leveranstyp.

## Resemått {#journey-metrics}

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

## Dimensioner och mått för e-post och SMS {#email-and-sms-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Mått<br/> </th> 
   <th> Definition<br/> </th> 
</tr>
 </thead> 
 <tbody>
  <tr> 
   <td> studsar<br/> </td> 
   <td> Totalt antal fel som sammanställts under sändningsprocessen och automatisk returbearbetning i relation till det totala antalet skickade meddelanden.<br/> </td> 
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
   <td> Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.<br/></td> 
</tr> 
  <tr> 
   <td> Leveransnivå<br/> </td> 
   <td> Procentandel meddelanden som har skickats.<br/> </td> 
</tr>
  <tr> 
   <td> Fel<br/> </td> 
   <td> Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.<br/> </td> 
</tr> 
  <tr> 
   <td> Felfrekvens<br/> </td> 
   <td> Procentandel fel som uppstod under sändningsprocessen och som förhindrade att den skickades jämfört med skickade e-postmeddelanden.<br/> </td> 
</tr>
</tr> 
  <tr> 
   <td> Felorsak<br/> </td> 
   <td> Namnet på den specifika ursprungliga orsaken till felet. <a href="exclusion-list.md">Läs mer om felorsaker</a>.<br/> </td> 
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
   <td> Försök igen<br/> </td> 
   <td> Antal e-postmeddelanden i kön för återförsök.<br/> </td> 
</tr> 
  <tr> 
   <td> Skickat<br/> </td> 
   <td> Totalt antal försändelser för leveransen.<br/> </td> 
</tr>
  <tr> 
   <td> Mjuk studsa<br/> </td> 
   <td> Totalt antal tillfälliga fel, till exempel en fullständig inkorg.<br/> </td> 
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
   <td> Antal mottagare som klickat på ett innehåll i ett e-postmeddelande.<br> Observera att de senaste tio dagarna beaktas när unika klick beräknas. Om en profil registrerar flera klick inom 10-dagarsperioden räknas de som unika klick. Om en profil har 2 klick med mer än 10 dagars mellanrum betraktas de dock inte som unika klick.<br/> </td> 
</tr> 
  <tr> 
   <td>Unik klickfrekvens<br/> </td> 
   <td> Procentandel användare som interagerade med leveransen.<br/> </td> 
</tr>
  <tr> 
   <td> Unika öppningar<br/> </td> 
   <td>Antal mottagare som öppnade leveransen. <br> Observera att de senaste tio dagarna beaktas när unika öppningar beräknas. Om en profil registrerar flera öppningar inom 10-dagarsperioden räknas de som unika öppningar. Om en profil har 2 öppningar med mer än 10 dagars mellanrum räknas de inte som unika öppningar.<br/> </td> 
</tr> 
  <tr> 
   <td> Avbeställ<br/> </td> 
   <td> Antal klick på länken för att avbryta prenumerationen.<br/> </td> 
</tr> 
 </tbody> 
</table>

<!--
## Experimentation metrics {#experimentation-metrics}
<table> 
 <thead> 
  <tr> 
   <th> Metric<br/> </th> 
   <th> Definition<br/> </th> 
</tr>
 </thead> 
 <tbody>
  <tr> 
   <td>App installs<br/> </td> 
   <td><br/> </td> 
</tr>
  <tr> 
   <td>App launches<br/> </td> 
   <td><br/> </td> 
</tr>
 <tr> 
   <td>Average lift<br/> </td> 
   <td> Percentage improvement in conversion rate of a given treatment over the baseline.<a href="../campaigns/experiment-calculations.md#understand-lift">Learn more</a>.<br/> </td> 
  </tr>
  <tr> 
   <td>Confidence<br/> </td> 
   <td>Evidence that a given treatment is the same as the baseline treatment. <a href="../campaigns/experiment-calculations.md#understand-confidence">Learn more</a>.<br/> </td> 
</tr>
  <tr> 
   <td>Confidence interval<br/> </td> 
   <td>Percentage difference in performance between the baseline and the best performing treatment. <a href="../campaigns/experiment-calculations.md#understand-intervals">Learn more</a>.<br/> </td> 
</tr> 
  <tr> 
   <td>Count per profile<br/> </td> 
   <td>Total value of the Experiment objective metric divided by the number of profiles.<br/> </td> 
</tr>
  <tr> 
   <td>Email Opens<br/> </td> 
   <td>Number of times the email was opened.<br/> </td> 
</tr>
  <tr> 
   <td>Email Unsubscribes<br/> </td> 
   <td>Number of clicks on the unsubscription link.<br/> </td> 
</tr>
  <tr> 
   <td>First app launches<br/> </td> 
   <td><br/> </td> 
</tr>
  <tr> 
   <td>Outbound Clicks<br/> </td> 
   <td><br/> </td> 
</tr>
  <tr> 
   <td>Profiles<br/> </td> 
   <td>Number of profiles targeted for this treatment.<br/> </td> 
</tr>
  <tr> 
   <td>Unique email opens<br/> </td> 
   <td>Number of recipients who opened the email.<br/> </td>
<tr>
  <tr> 
   <td>Unique email unsubscribes<br/> </td> 
   <td>Number of recipients who clicked on the unsubscription link.<br/> </td>
</tr>
  <tr> 
   <td>Unique installs<br/> </td> 
   <td><br/> </td> 
</tr>
  <tr> 
   <td>Unique launches<br/> </td> 
   <td><br/> </td> 
</tr> 
  <tr> 
   <td>Unique outbound clicks<br/> </td> 
   <td><br/> </td> 
</tr>
  <tr> 
   <td>Unique upgrades<br/> </td> 
   <td><br/> </td> 
</tr>
   <td>Upgrades<br/> </td> 
   <td><br/> </td> 
</tr> 
</tbody> 
</table>
-->

## Mätvärden i appen {#inapp-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Mått<br/> </th> 
   <th> Definition<br/> </th> 
</tr>
 </thead> 
 <tbody>
 <tr> 
   <td>Klickningar<br/> </td> 
   <td>Totalt antal mottagare som interagerat med knapparna i meddelandet i appen.<br/> </td> 
</tr>
  <tr> 
   <td>Klickfrekvens<br/> </td> 
   <td>Procentandel användare som interagerade med knapparna i meddelandet i appen jämfört med användare som såg meddelandet.<br/> </td> 
</tr> 
  <tr> 
   <td>Avstängningsfrekvens<br/> </td> 
   <td> Procentandel meddelanden i appen som mottagarna avvisade.<br/> </td> 
</tr> 
  <tr> 
   <td>Impressions<br/> </td> 
   <td> Totalt antal meddelanden i appen som levereras till alla användare.<br/> </td>
</tr>
  <tr> 
   <td>Unika intryck<br/> </td> 
   <td>Antal unika användare som meddelandet i appen levererades till.<br/> </td>
</tr>
 </tbody> 
</table>

## Mätvärden för push-meddelanden

<table> 
 <thead> 
  <tr> 
   <th> Mått<br/> </th> 
   <th> Definition<br/> </th> 
</tr>
 </thead> 
 <tbody>
 <tr> 
   <td>Åtgärder<br/> </td> 
   <td> Totalt antal åtgärder för push-meddelandet som levererats, t.ex. knappklickning eller avbruten.<br/> </td> 
</tr>
  <tr> 
   <td>studsar<br/> </td> 
   <td> Totalt antal fel som sammanställts under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.<br/> </td> 
</tr> 
  <tr> 
   <td> Studsfrekvens<br/> </td> 
   <td> Procentandel push-meddelanden som studsade jämfört med skickade push-meddelanden.<br/> </td>
</tr>
  <tr> 
   <td> Levererat<br/> </td> 
   <td> Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.<br/> </td> 
</tr> 
  <tr> 
   <td> Leveransnivå<br/> </td> 
   <td> Procentandel push-meddelanden som har skickats.<br/> </td> 
</tr>
  <tr> 
   <td>Åtaganden<br/> </td> 
   <td> Totalt antal öppningar och åtgärder för det här push-meddelandet, dvs om profilen öppnade push-meddelandet eller om någon klickade på en knapp.<br/> </td> 
</tr> 
  <tr> 
   <td> Hastighet<br/> </td> 
   <td> Procentandel öppningar och åtgärder för det här push-meddelandet, dvs. om profilen öppnade push-meddelandet eller om någon klickade på en knapp.<br/> </td> 
</tr>
  <tr> 
   <td> Fel<br/> </td> 
   <td> Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.<br/> </td> 
</tr>
  <tr> 
   <td> Felfrekvens<br/> </td> 
   <td> Procentandel fel som uppstod under en leverans och som förhindrar att den skickas jämfört med push-meddelanden som skickas.<br/> </td> 
</tr>
  <tr> 
   <td> Felorsak<br/> </td> 
   <td> Namnet på den specifika ursprungliga orsaken till felet. <a href="exclusion-list.md">Läs mer om felorsaker</a>.<br/> </td> 
</tr>
  <tr> 
   <td> Exkluderad<br/> </td> 
   <td> Antal profiler som har uteslutits av Adobe Journey Optimizer.<br/> </td> 
</tr>
  <tr> 
   <td> Öppnar<br/> </td> 
   <td> Totalt antal push-meddelanden som levererats till enheten och användaren klickat på för att öppna appen. Det här liknar kommandot Push Click (Push-klicka), förutom att Push Open (Push Open) inte aktiveras om meddelandet stängs.<br/> </td> 
</tr> 
  <tr> 
   <td> Öppen kurs<br/> </td> 
   <td> Procentandel öppnade push-meddelanden.<br/> </td> 
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

## Mätvärden för landningssida {#landing-page-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Mått<br/> </th> 
   <th> Definition<br/> </th> 
</tr>
 </thead> 
 <tbody>
 <tr> 
  <td>studsar<br/> </td> 
   <td>Antal personer som inte interagerade med landningssidan och inte slutförde prenumerationsåtgärden.<br/> </td> 
</tr>
 <tr> 
   <td>Studsfrekvens<br/> </td> 
   <td>Antal personer som inte interagerade med landningssidan och inte slutförde prenumerationsåtgärden i förhållande till det totala antalet besök.<br/> </td> 
</tr>
 <tr>
  <tr> 
   <td>Klickningar<br/> </td> 
   <td>Antal gånger som ett innehåll klickades på på landningssidan.<br/> </td> 
</tr>
 <tr> 
   <td>Klickfrekvens<br/> </td> 
   <td>Procentandel klick på landningssidan.<br/> </td>
</tr>
<tr>
<td>Konvertering<br/> </td> 
   <td>Antal personer som interagerat med landningssidan, t.ex. prenumererat på ett formulär.<br/> </td> 
</tr>
<tr>
   <td>Konverteringsgrad<br/> </td> 
   <td>Antal personer som interagerat med landningssidan, t.ex. prenumererat på ett formulär, i förhållande till det totala antalet besök.<br/> </td> 
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
