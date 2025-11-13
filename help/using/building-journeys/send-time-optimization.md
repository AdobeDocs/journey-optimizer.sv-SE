---
solution: Journey Optimizer
product: journey optimizer
title: Tidsoptimering för sändning
description: Lär dig hur du parameterar optimering av sändningstid i dina meddelanden
feature: Journeys, Activities, Email, Push, Send Time Optimization
topic: Content Management
role: User
level: Intermediate
keywords: sändningstid, skicka, meddelande, optimering, resa, AI, intelligent
exl-id: ec604e91-4c7f-459c-b6ff-d825919e7181
version: Journey Orchestration
source-git-commit: 7822e9662d03e6c6b2d5bc5ecb9ca85dc32f0942
workflow-type: tm+mt
source-wordcount: '1546'
ht-degree: 0%

---

# Sändningsoptimering{#send-time-optimization}

>[!CONTEXTUALHELP]
>id="jo_bestsendtime_disabled"
>title="Om Tidsoptimering för Skickat"
>abstract="Adobe Journey Optimizer funktion för optimering av sändningstid, som bygger på Adobe AI-tjänster, kan förutsäga den bästa tidpunkten för att skicka e-post eller push-meddelanden för att maximera engagemanget baserat på tidigare öppnings- och klickfrekvenser."

>[!CONTEXTUALHELP]
>id="jo_bestsendtime_email"
>title="Aktivera optimering av sändningstid"
>abstract="Välj om du vill optimera e-postöppningen eller skicka e-postklick genom att välja lämplig alternativknapp. Du kan också välja att klamra de sändningstider som används av systemet genom att ange ett värde för Skicka i nästa alternativ."

>[!CONTEXTUALHELP]
>id="jo_bestsendtime_push"
>title="Aktivera optimering av sändningstid"
>abstract="Standardinställningen för push-meddelanden är öppningsalternativet, eftersom klickningar inte kan användas för push-meddelanden. Du kan också välja att klamra de sändningstider som används av systemet genom att ange ett värde för Skicka i nästa alternativ."

Adobe Journey Optimizer funktion för optimering av sändningstid, som bygger på Adobe AI-tjänster för resan, väljer den optimala sändningstiden för e-post och push-meddelanden för att maximera kundengagemanget, baserat på kundernas tidigare öppnings- och klickbeteende.

Sändningsoptimering är endast tillgängligt för Journey Optimizer inbyggda åtgärdstyper för e-post och push och är för närvarande inte tillgängligt för meddelanden som skickas via anpassade åtgärder eller för andra åtgärdstyper. Tidsoptimering för sändning är endast tillgängligt för e-post- och push-åtgärder inom resor och är för närvarande inte tillgängligt för meddelanden som skickas via kampanjer.

>[!AVAILABILITY]
>
>* Funktionen för optimering av sändningstid är aktiverad för Adobe Journey Optimizer-kunder på begäran. Kontakta Adobe kundtjänst eller en Adobe-representant för att aktivera funktionen för din organisation.
>
>* Tidsoptimering för sändning gäller endast för kanalerna **E-post** och **Push-meddelanden**.
>

## Använd optimering vid sändning{#use-send-time-optimization}

Använd optimering av sändningstid för ett e-postmeddelande eller push-åtgärd genom att aktivera alternativet för optimering av sändningstid från åtgärdsparametrarna.

![Växla optimering av sändningstid i e-postkanalskonfiguration](assets/jo-message5.png)

Optimering av sändningstid ska inte användas för brådskande, tidskänsliga operativa meddelanden, till exempel en orderbekräftelse, ett meddelande om lösenordsåterställning eller ett meddelande om ändring av flygport. Optimering för sändningstid är bäst när det gäller mindre brådskande marknadsföringsmeddelanden, t.ex. en veckoannons, kampanjinformation för en ny produkt eller information om en månadsförsäljning.

För e-postmeddelanden väljer du om du vill optimera e-postöppningar eller e-postklick genom att välja lämplig alternativknapp. Push-meddelanden är alltid optimerade för öppning.

>[!TIP]
>
>För bästa resultat bör de flesta e-postmeddelanden optimeras för Klickningar. Välj att optimera för Öppnar om ditt e-postmeddelande är av informativ natur och inte är avsett att direkt köra en åtgärd.

För både e-post- och push-meddelanden väljer du det maximala antal timmar som systemet ska vänta innan meddelandet skickas genom att ange ett värde för alternativet&quot;Skicka inom nästa&quot;. Du kan välja mellan 1 och 168 timmar.

>[!TIP]
>
>För bästa resultat bör du välja en maximal väntetid mellan 6 och 24 timmar. Om du väljer ett lägre värde för maximal väntetid minskas antalet tillgängliga sändningstider och därför kan det potentiella värdet för optimering av sändningstid minska. Om du väljer ett högre värde för maximal väntetid kan ett meddelande bli inaktuellt eller irrelevant när det skickas.

När kundresan aktiveras och kunden når åtgärden E-post eller push under resan, väljer optimering av sändningstid den bästa förväntade sändningstiden som är tillgänglig för varje användare inom de angivna gränserna.


## Så här fungerar optimering vid körning {#how-send-time}

Modellen för optimering av sändningstid innebär att din organisations kundbeteendedata från Adobe Journey Optimizer importeras och att användaren undersöker öppna- och klickhändelser för att avgöra när det är mest troligt att dina kunder interagerar med dina meddelanden.

Med optimering för sändningstid kan man förutse för varje timme i veckan, för varje användare, baserat på tre typer av beteendedata:

1. Beteendet för dina användare generellt
1. Beteendet för lookalike-användare i samma tidszon
1. Beteendet för den enskilda användaren

Dessa prognoser vägs och kombineras med hjälp av en bayesisk metod, vilket ger en&quot;värmekarta&quot; för varje mätvärde (e-postöppning, e-postklick och push-öppning) för varje kund, som anger de timmar i veckan som kontaktar användaren mest och minst sannolikt resulterar i önskat engagemangsresultat (öppna/klicka), vilket visas i följande exempelheatmap:

![Åtagandeheatmap som visar optimala sändningstider för e-post per dag och timme](assets/heatmap-1.png)

Om en användare med ovanstående sannolikhet för meddelande anges som mål på onsdagen kl. 9 och optimering av sändningstid aktiverat och en maximal väntetid på 7 timmar, kommer den valda sändningstiden för meddelandet att vara 12.00:

![Åtagandeheatmap med detaljerade timmars-för-timma-optimeringsdata](assets/heatmap-2.png)

## Utbildning och poänginformation om modellerna för optimering av sändningstid  {#model-send-time}

När funktionen för optimering av sändningstid har aktiverats för din organisation har Journey AI-modellen utbildats för e-post och push-sändning, öppna och klicka på händelser under alla organisationens resor och åtgärder under de senaste 16 veckorna - oavsett om dessa åtgärder använder optimering av sändningstid eller inte. Detta gör att optimering av sändningstid kan dra nytta av alla data som genereras av dina kunder.

Modeller är initialt utbildade och poängsätts varje vecka. Efter 16 veckor får modellerna ny utbildning och ny kodning varje månad. Modellpoängen innehåller alla kundprofiler - både befintliga och nya sedan den senaste poängsättningen.

Meddelanden som skickas av optimering av sändningstid får antingen ett meddelande om att utforska sändningstiden som valts för att testa olika sändningstider och observera hur kunderna svarar, eller en optimerad sändningstid för meddelanden som valts för att maximera antalet klickningar/öppningar. 5 % av sändningshändelserna får en utforskande sändningstid och 95 % av sändningshändelserna är&quot;optimerade&quot;.

Utforska sändningstider väljs slumpvis bland de sändningstider som är tillgängliga med den konfigurerade maximala väntetiden. Om ett meddelande till exempel markeras på onsdag 09:00 med optimering för Skicka-tid aktiverat och en maximal väntetid på 3 timmar, kommer meddelandetiden för prospektering att delas jämnt mellan 09:00, 10:00 och 12:00.


## Vanliga frågor {#faq-send-time}

Nedan hittar du Vanliga frågor om optimering av sändningstid.

Behöver du mer information? Använd alternativen för feedback längst ned på den här sidan för att ställa din fråga eller kontakta [Adobe Journey Optimizer Community](https://experienceleaguecommunities.adobe.com/t5/adobe-journey-optimizer/ct-p/journey-optimizer?profile.language=en){target="_blank"}.

+++Hur lång tid behöver jag vänta innan jag använder optimering för Skicka-tid?

Din organisation bör använda e-poståtgärden i Journey Optimizer i minst 30 dagar innan du använder optimering av sändningstid i e-postmeddelanden för att tillåta insamling av vissa e-postutskick, öppna och klickningar.

Din organisation bör använda åtgärden Push i Journey Optimizer i minst 30 dagar innan den använder Send-Time Optimization i Push för att samla in push-skicka och öppna händelser.

Om din organisation redan har använt åtgärderna E-post och/eller Push i minst 30 dagar behöver din organisation inte vänta längre för att använda optimering för Skicka-tid efter att den har aktiverats av Adobe. Resultaten kommer att fortsätta att förbättras i takt med att organisationen samlar in data i upp till 16 veckor.

+++

+++Hur kan jag se den sändningstid som en viss användare får ett meddelande på?

För att minimera modellens påverkan på profilens detaljrikedom lagras modellpoäng i 3 profilattribut som lagras i `_experience.intelligentServices.journeyAI.sendTimeOptimization` och är inte utformade för att vara läsbara för människor.

+++


+++Vilken är den genomsnittliga fördelen med optimering för Skicka-tid?

Sändningsoptimering kan öka e-postklickfrekvensen och öka öppningsfrekvensen i intervallet mellan cirka 2 % och 10 % för alla meddelanden som optimeras av en organisation.

Om en organisation som skickar e-post utan att optimera sändningstiden har en genomsnittlig klickfrekvens på 5,0 %, kan samma uppsättning e-postmeddelanden med optimerad sändningstid resultera i en klickfrekvens på i genomsnitt 5,5 % (5,0 % * (1+10 %) = 5,5 %).

På grund av variationer inom små provstorlekar är det inte säkert att fördelarna med optimering av sändningstid kan observeras vid enskilda meddelanden.

Det är troligare att organisationer får större fördelar av att använda optimering vid sändning när:

* Befintliga resor använder fasta och inte optimerade sändningstider
* Variabilitet i kundbeteende (klickningar och öppningar) motsvarar kundens position och kundens önskemål
* Organisationer använder Send-Time Optimization på en större del av e-post och push-meddelanden
* Organisationer väljer maximal väntetid inom det rekommenderade intervallet på 6-12 timmar

+++

+++Jag klickar alltid på e-post eller push-meddelanden vid 12:00, varför skickade inte algoritmen ett meddelande till mig kl. 12:00?


Detta kan inträffa av flera orsaker:

* Ditt meddelande valdes som en sändningstid för meddelandet &quot;Exploration&quot; i stället för som en sändningstid för meddelandet &quot;Optimized&quot;.
* Beteendet hos lookalike-användare påverkade modellen så att den kunde rekommendera en annan sändningstid.

+++

+++Hur känner optimering av sändningstid en användares tidszon?

För optimering av sändningstid används profilfältet `timeZone` för att fastställa en användares tidszon. Om den användaren inte är tillgänglig försöker Send-Time Optimization härleda en användares tidszon från annan geografisk information i användarens profil, till exempel land och delstat.

+++


+++Kommer optimering av sändningstid att skicka push-meddelanden till användare under natten i den lokala tidszonen?

Tidsoptimering för sändning kan skicka push-meddelanden till användare under natten i den lokala tidszonen under följande omständigheter:

* När en användare uppvisar ett beteende som tyder på att de sannolikt kommer att interagera med ett meddelande som skickas nattetid
* När modellen väljer en utforskande sändningstid

För att undvika att skicka push-meddelanden till kunder under nattetid, schemalägger du push-meddelanden i batch till morgonen eller tidig eftermiddag och väljer en kortare varaktighet för Send-Time Optimization. (Exempelvis en sändningstid på 9 AM och en maximal väntetid på 8 timmar.)

+++



