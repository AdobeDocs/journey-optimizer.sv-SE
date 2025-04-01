---
solution: Journey Optimizer
product: journey optimizer
title: Lista över komponenter
description: Lär dig använda data från din rapport
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: aa060d8e-23e2-4bab-b709-636077eb5d20
source-git-commit: 3de7826ae4a7efc2837288779fb444fa15688d3f
workflow-type: tm+mt
source-wordcount: '1362'
ht-degree: 0%

---

# Lista över komponenter {#list-of-components-global}

Tabellerna nedan ger dig en lista över de mätvärden som används i rapporter och deras definitioner beroende på leveranstyp.

## Resemått {#journey-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Mått <br/> </th> 
   <th> Definition <br/> </th> 
</tr>
 </thead> 
 <tbody> 
<tr> 
<td>Reseengagemang</td> 
<td>Totalt antal unika personer som tagit emot meddelanden som skickats genom resan, vilket representerar distinkta profiler som nått en angiven åtgärdspunkt under resan.</td> 
</tr> 
<tr> 
<td>Resenärer</td> 
<td>Totalt antal personer som har nått resans inträde.</td> 
</tr>
<tr> 
<td>Reseutträde</td> 
<td>Totalt antal personer som avbrutit resan.</td> 
</tr>
<tr> 
<td>Resefel</td> 
<td>Totalt antal enskilda resor som inte har slutförts.</td> 
</tr>
<tr> 
<td>Unika resebyråer</td> 
<td>Totalt antal personer som har nått ingångshändelsen för resan, där flera interaktioner med samma profil inte har beaktats.</td> 
</tr>
<tr> 
<td>Unika reseutträden</td> 
<td>Totalt antal personer som avbrutit resan, där flera interaktioner med samma profil inte beaktas.</td> 
</tr>
<tr> 
<td>Unika misslyckade resor</td> 
<td>Totalt antal enskilda resor som inte har slutförts utan flera interaktioner med samma profil beaktas inte.</td> 
</tr>
 </tbody> 
</table>

## E-postmått {#email-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Mått <br/> </th> 
   <th> Definition <br/> </th> 
  </tr>
 </thead> 
 <tbody>
  <tr> 
   <td> studsar<br/> </td> 
   <td> Totalt antal fel som har kumulerats under sändningsprocessen och automatisk returbearbetning i relation till totalt antal skickade meddelanden.<br/> </td> 
  </tr> 
  <tr> 
   <td> Klicka genom öppningsfrekvens (CTOR)<br/> </td> 
   <td> Antal gånger som e-postmeddelandet öppnades.<br/> </td> 
  </tr>
  <tr> 
   <td> Klicka genom frekvens (CTR)<br/> </td> 
   <td> Procentandel användare som interagerade med e-postmeddelandet.<br/> </td> 
  </tr>
  <tr> 
   <td> Klicka <br/> </td> 
   <td> Antal gånger som ett innehåll klickades i ett e-postmeddelande.<br/> </td> 
  </tr> 
  <tr> 
   <td> Levererat <br/> </td> 
   <td> Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.<br/></td> 
  </tr> 
  <tr> 
   <td> Leveransnivå <br/> </td> 
   <td> Procentandel meddelanden som skickades.<br/> </td> 
  </tr>
  <tr> 
   <td> Felorsak<br/> </td> 
   <td> Namnet på den specifika ursprungliga orsaken till felet. <a href="exclusion-list.md">Läs mer om felorsaker</a>.<br/> </td> 
  </tr>
  <tr> 
   <td> Erbjud klickfrekvens <br/> </td> 
   <td> Procentandel användare som interagerade med erbjudandet.<br/> </td> 
  </tr>
  <tr> 
   <td> Erbjud visningsfrekvens <br/> </td> 
   <td> Procentandel öppnade erbjudanden jämfört med antalet skickade erbjudanden.<br/> </td> 
  </tr>
  <tr> 
   <td> Erbjudandenamn <br/> </td> 
   <td> Namn på erbjudandet som lagts till i leveransen. Mer information om placering finns på <a href="../offers/offer-library/creating-personalized-offers.md">sidan</a>.<br/> </td> 
  </tr>
  <tr> 
   <td> Erbjudandet har skickats<br/> </td> 
   <td> Totalt antal utskick för erbjudandet.<br/> </td> 
  </tr> 
  <tr> 
   <td> Öppnar <br/> </td> 
   <td> Antal gånger som meddelandet öppnades.<br/> </td> 
  </tr> 
  <tr> 
   <td> Utgående fel <br/> </td> 
   <td> Totalt antal fel som uppstod under sändningsprocessen och som förhindrar att den skickas till profiler.<br/> </td> 
  </tr> 
  <tr> 
   <td> Utgående undantag <br/> </td> 
   <td> Antal profiler som har uteslutits av Adobe Journey Optimizer.<br/> </td> 
  </tr>
  <tr> 
   <td> Placeringsnamn <br/> </td> 
   <td> Namn på den placering som användes för att visa ditt erbjudande. Mer information om placering finns på den här <a href="../offers/offer-library/creating-placements.md">sidan</a>. </td> 
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
   <td> Antal profiler som klickat på ett innehåll i ett e-postmeddelande.<br> Observera att de senaste tio dagarna beaktas när unika klick beräknas. Om en profil registrerar flera klick inom 10-dagarsperioden räknas de som unika klick. Om en profil har 2 klick med mer än 10 dagars mellanrum betraktas de inte som unika klick.<br/> </td> 
  </tr>
  <tr> 
   <td> Unik avbeställning av e-post<br/> </td> 
   <td> Antal profiler som avbrutit prenumerationen på dina e-postmeddelanden.<br/> </td> 
  </tr>
  <tr> 
   <td> Unika öppna<br/> </td> 
   <td> Antal profiler som öppnade leveransen. <br> Observera att de senaste tio dagarna beaktas när unika öppningar beräknas. Om en profil registrerar flera öppningar inom 10-dagarsperioden räknas de som unika öppningar. Om en profil har 2 öppningar med mer än 10 dagars mellanrum räknas de inte som unika öppningar.<br/> </td> 
  </tr> 
  <tr> 
   <td> Avbeställer<br/> </td> 
   <td> Antal klick på länken för att avbryta prenumerationen.<br/> </td> 
  </tr> 
 </tbody> 
</table>

## SMS-mått

<table> 
  <thead> 
    <tr> 
      <th> SMS-mått </th> 
      <th> Definition </th> 
    </tr>
  </thead> 
  <tbody> 
    <tr> 
      <td>Levererat</td> 
      <td>Antal SMS-meddelanden som har skickats, i relation till totalt antal SMS-meddelanden.</td> 
    </tr>
    <tr> 
      <td>Klickningar</td> 
      <td>Antal gånger som en länk i ett SMS-meddelande klickades.</td> 
    </tr>
    <tr> 
      <td>Avrundningar för utgående SMS-meddelanden</td> 
      <td>Totalt antal fel som uppstått under sändningsprocessen och automatisk returbehandling i relation till totalt antal skickade SMS-meddelanden.</td> 
    </tr>
    <tr> 
      <td>Utgående SMS-fel</td> 
      <td>Totalt antal fel som inträffat, vilket förhindrar att SMS-meddelandet skickas till mottagarna.</td> 
    </tr>
    <tr> 
      <td>Utgående SMS-undantag</td> 
      <td>Antal profiler som har uteslutits från att ta emot SMS-meddelanden från Adobe Journey Optimizer.</td> 
    </tr>
    <tr> 
      <td>Unika klick</td> 
      <td>Antal unika mottagare som klickat på en länk i ett SMS-meddelande.</td> 
    </tr>
    <tr> 
      <td>Visar</td> 
      <td>Antal gånger ett SMS-meddelande visades eller öppnades.</td> 
    </tr>
    <tr> 
      <td>Unika bildskärmar</td> 
      <td>Antal unika mottagare som öppnade SMS-meddelandet, exklusive flera interaktioner från samma användare.</td> 
    </tr>
    <tr> 
      <td>Folk</td> 
      <td>Antal unika användarprofiler som har tagit emot eller interagerat med ett SMS-meddelande.</td> 
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
   <td>Number of profiles who opened the email.<br/> </td>
<tr>
  <tr> 
   <td>Unique email unsubscribes<br/> </td> 
   <td>Number of profiles who clicked on the unsubscription link.<br/> </td>
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
   <th> Mått <br/> </th> 
   <th> Definition <br/> </th> 
  </tr>
 </thead> 
 <tbody>
  <tr> 
   <td>Klicka <br/> </td> 
   <td>Totalt antal profiler som interagerat med knapparna i meddelandet i appen.<br/> </td> 
  </tr>
  <tr> 
   <td>Klickfrekvens <br/> </td> 
   <td>Procentandel användare som interagerade med knapparna i meddelandet i appen jämfört med användare som såg meddelandet.<br/> </td> 
  </tr>
  <tr> 
   <td>Frånkopplingsfrekvens <br/> </td> 
   <td>Procentandel av meddelanden i appen som profiler stängs.<br/> </td> 
  </tr>
  <tr> 
   <td>Impressions<br/> </td> 
   <td>Totalt antal meddelanden i appen som levereras till alla användare.<br/> </td>
  </tr>
  <tr> 
   <td>Unika avtryck <br/> </td> 
   <td>Antal unika användare som meddelandet i appen levererades till.<br/> </td>
  </tr>
  <tr> 
   <td>Visar<br/> </td>
   <td>Antal gånger som meddelandet i appen öppnades.<br/> </td>
  </tr>
  <tr> 
   <td>Unika skärmar <br/> </td>
   <td>Antal gånger som meddelandet i appen öppnades, exklusive flera interaktioner från samma profil.<br/> </td>
  </tr>
  <tr> 
   <td>Unika klick<br/> </td>
   <td>Antal profiler som klickat på innehåll i meddelanden i appen.<br/> </td>
  </tr>
  <tr> 
   <td>Klicka <br/> </td>
   <td>Antal gånger som innehåll klickades på i dina meddelanden i appen.<br/> </td>
  </tr>
  <tr> 
   <td>Klicka genom frekvens (CTR)<br/> </td>
   <td>Procentandel användare som interagerade med meddelanden i appen.<br/> </td>
  </tr>
  <tr> 
   <td>Klicka genom öppningsfrekvens (CTOR)<br/> </td>
   <td>Antal gånger som meddelandet i appen öppnades.<br/> </td>
  </tr>
  <tr> 
   <td>Skickar<br/> </td>
   <td>Totalt antal skickade meddelanden i appen.<br/> </td>
  </tr>
  <tr> 
   <td>Inkommande utlöst <br/> </td>
   <td>Antal gånger ett meddelande i appen utlöstes av en användarinteraktion eller en fördefinierad händelse.<br/> </td>
  </tr>
  <tr> 
   <td>Inkommande avhopp <br/> </td>
   <td>Antal gånger som användare har stängt meddelandet i appen utan att interagera med det.<br/> </td>
  </tr>
 </tbody> 
</table>

## Mätvärden för push-meddelanden

<table> 
 <thead> 
  <tr> 
   <th> Mått <br/> </th> 
   <th> Definition <br/> </th> 
</tr>
 </thead> 
 <tbody>
 <tr> 
   <td>Åtgärder<br/> </td> 
   <td> Totalt antal åtgärder för det skickade push-meddelandet, t.ex. knappklickning eller avbruten.<br/> </td> 
</tr>
  <tr> 
   <td>studsar<br/> </td> 
   <td> Totalt antal fel som sammanställts under leverans och automatisk returbearbetning i relation till totalt antal skickade meddelanden.<br/> </td> 
</tr> 
  <tr> 
   <td> Studsfrekvens <br/> </td> 
   <td> Procentandel push-meddelanden som studsade jämfört med skickade push-meddelanden.<br/> </td>
</tr>
  <tr> 
   <td> Levererad<br/> </td> 
   <td> Antal meddelanden som har skickats, i relation till totalt antal skickade meddelanden.<br/> </td> 
</tr> 
  <tr> 
   <td> Leveransnivå <br/> </td> 
   <td> Procentandel skickade push-meddelanden.<br/> </td> 
</tr>
  <tr> 
   <td>Åtaganden <br/> </td> 
   <td> Totalt antal öppningar och åtgärder för det här push-meddelandet, dvs. om profilen öppnade push-meddelandet eller om någon klickade på en knapp.<br/> </td> 
</tr> 
  <tr> 
   <td> Åtagandefrekvens <br/> </td> 
   <td> Procentandel öppningar och åtgärder för det här push-meddelandet, dvs. om profilen öppnade push-meddelandet eller om någon klickade på en knapp.<br/> </td> 
</tr>
  <tr> 
   <td> Fel <br/> </td> 
   <td> Totalt antal fel som uppstod under en leverans och som förhindrar att den skickas till profiler.<br/> </td> 
</tr>
  <tr> 
   <td> Felfrekvens <br/> </td> 
   <td> Procentandel fel som uppstod under en leverans och som förhindrar att den skickas jämfört med skickade push-meddelanden.<br/> </td> 
</tr>
  <tr> 
   <td> Felorsak<br/> </td> 
   <td> Namnet på den specifika ursprungliga orsaken till felet. <a href="exclusion-list.md">Läs mer om felorsaker</a>.<br/> </td> 
</tr>
  <tr> 
   <td> Utesluten<br/> </td> 
   <td> Antal profiler som har uteslutits av Adobe Journey Optimizer.<br/> </td> 
</tr>
  <tr> 
   <td> Öppnar <br/> </td> 
   <td> Totalt antal push-meddelanden som levererats till enheten och användaren klickat på för att öppna appen. Detta liknar push-klickning, men push-öppning kommer inte att aktiveras om meddelandet stängs.<br/> </td> 
</tr> 
  <tr> 
   <td> Öppen frekvens <br/> </td> 
   <td> Procentandel öppna push-meddelanden.<br/> </td> 
</tr>
  <tr> 
   <td> Skjut anpassade åtgärder <br/> </td> 
   <td>Antal anpassade åtgärder som har vidtagits av profiler som svar på push-meddelanden.<br/> </td> 
</tr>
  <tr> 
   <td> Skickat <br/> </td> 
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
   <th> Mått <br/> </th> 
   <th> Definition <br/> </th> 
</tr>
 </thead> 
 <tbody>
 <tr> 
  <td>studsar<br/> </td> 
   <td>Antal personer som inte interagerade med landningssidan och inte slutförde prenumerationsåtgärden.<br/> </td> 
</tr>
 <tr> 
   <td>Studsfrekvens <br/> </td> 
   <td>Antal personer som inte interagerade med landningssidan och inte slutförde prenumerationsåtgärden i förhållande till det totala antalet besök.<br/> </td> 
</tr>
 <tr>
  <tr> 
   <td>Klicka <br/> </td> 
   <td>Antal gånger som ett innehåll klickades på på landningssidan.<br/> </td> 
</tr>
 <tr> 
   <td>Klickfrekvens <br/> </td> 
   <td>Procentandel klick på landningssidan.<br/> </td>
</tr>
<tr>
<td>Konvertering <br/> </td> 
   <td>Antal personer som interagerat med landningssidan, t.ex. prenumererat på ett formulär.<br/> </td> 
</tr>
<tr>
   <td>Konverteringsgrad <br/> </td> 
   <td>Antal personer som interagerat med landningssidan, t.ex. prenumererat på ett formulär, i förhållande till det totala antalet besök.<br/> </td> 
</tr>
 <tr> 
   <td>Resa(er) <br/> </td> 
   <td>Antal besök på din landningssida som kommer från en resa.<br/> </td> 
</tr>
 <tr> 
   <td>Andra källor <br/> </td> 
   <td>Antal besök på din landningssida som kommer från en extern källa i stället för en resa.<br/> </td> 
</tr>
 <tr> 
   <td>Totalt antal besök <br/> </td> 
   <td> Totalt antal besök på din landningssida som kommer från resor och externa källor, inklusive flera besök av en profil.<br/> </td> 
</tr>
 <tr> 
   <td>Unika besökare<br/> </td> 
   <td>Antal personer som besökte din landningssida, flera besök i en profil räknas inte.<br/> </td> 
</tr>
 <tr> 
   <td>Besök<br/> </td> 
   <td>Antal besök på din landningssida, inklusive flera besök på en profil.<br/> </td> 
</tr>
 </tbody> 
</table>
