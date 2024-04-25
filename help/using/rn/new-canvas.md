---
solution: Journey Optimizer
product: journey optimizer
title: Nytt resegränssnitt
feature: Release Notes
topic: Content Management
description: Nytt resegränssnitt
hide: true
hidefromtoc: true
exl-id: 03828fca-dde7-4b3b-b890-2c007d1245cc
source-git-commit: 59f41003183e155632124fde294bea575fb0f493
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 0%

---

# Välkommen till den förbättrade resedesignern {#new-canvas}

Vi har utvecklat en **förenklad resemodell** som syftar till att förbättra interna processer. Även om den här nya modellen är en backend-förbättring har vårt team tagit tillfället i akt att lägga till funktioner som är synliga och till nytta för Journey Optimizer-användare:

* A **omdesignad arbetsyta** för en moderniserad användarupplevelse
* A **live-rapportering** Gränssnitt som är direkt tillgängliga på arbetsytan

>[!NOTE]
>
>Tänk på att utrullningen för den här funktionen kommer att vara progressiv. Du kanske inte ser ändringarna direkt.

## Uppdateringar av resemodellen

Den nya resemodellen kommer att leva tillsammans med den befintliga, vilket innebär att det kommer att finnas resor som använder **två olika modeller**:

* Den gamla, med namnet &quot;v1&quot;
* Och den nya som kallas &quot;v2&quot;

Alla resor i v1 stannar i v1. Du kan fortfarande redigera, testa och publicera dem. Alla nya versioner som skapas från en v1 behålls också i v1. Det finns **inga funktionsändringar** runt v1-resor.

Som du ser i skärmbilden nedan är noderna rundformade, vilket är det gamla användargränssnittet för resor med v1-modellen.

![](assets/new-canvas.png)

Men när du **skapa en ny resa** eller **duplicera en befintlig**, blir det en v2-resa.  Vi planerar att fortsätta stödja v1-resor tills en majoritet av kunderna går över till v2-resor.

Det finns en begränsning i den nya resemodellen som **det inte går att kopiera och klistra in aktiviteter från en v1-resa till en v2 och vice versa**. Om du vill göra detta rekommenderar vi att du duplicerar din v1-resa så att den blir v2-version och sedan kopierar dina aktiviteter.

På skärmbilden nedan ser du det omdesignade gränssnittet för arbetsytan (endast tillgängligt med v2-modellen):

![](assets/new-canvas2.png)

**Alla nya funktioner som läggs till resedesignern (inklusive direktrapportering) är endast tillgängliga för v2-resor från och med nu.**

## Förbättrad design av arbetsyta

Med den nya resemodellen introducerar vi en ny och förbättrad **arbetsytans gränssnitt**, som smidigt passar in i Adobe Experience Cloud lösningar och ekosystem, vilket ger en intuitiv och effektiv användarupplevelse. Alla resor i v2-stacken kommer att finnas i den nya designen.

![](assets/new-canvas3.gif)

Aktiviteter visas nu med fyrkantiga rutor med följande funktioner:

* Den första raden som representerar aktivitetstypen, som ofta skrivs över av mer sammanhangsberoende information (t.ex.: på Läser målgrupper innehåller den namnet på den valda målgruppen), eller av en anpassad etikett om du definierar en sådan.
* Den andra raden representerar alltid aktivitetstypen.

![](assets/new-canvas4.png)

Det nya användargränssnittet förbättrar läsbarheten på arbetsytan genom att tillhandahålla **tydligare aktivitetsetiketter och -typer**.

Det gör det även möjligt för produktteamet att lägga till mer information på arbetsytan med färre klick. Ett exempel på&quot;mer information&quot; kan vara att lägga in live-rapportering på arbetsytan där du kan se profiler som läggs in och avslutas på grund av fel.

![](assets/new-canvas5.png)


## Live-rapportering på arbetsytan under resan

Tillsammans med den förbättrade utformningen av arbetsytan ger vi nu möjlighet att se **senaste 24 timmars rapportstatistik** (s.k.&quot;live reporting&quot;) direkt på arbetsytan.

![](assets/new-canvas6bis.png)

Med varje live-resa på den nya modellen kommer du att kunna se **för varje aktivitet**, antalet profiler som gick in i aktiviteten och antalet som slutade på grund av ett fel:

![](assets/new-canvas8.png)

<!--`
With every live journey on the new model, you will be able to see two types of "last 24 hours" reporting information:

* On a **new insert**, you will see:
    * The number of profiles that have been exported for audience-triggered journeys. You will see the number of profiles available in the last export job alongside the time when that export has been made.
    * The number of profiles who exited the journey
    * The percentage of errors
    ![](assets/new-canvas7.png)
* **On each activity**, you will see the number of profiles who entered that activity and the number who exited because of an error:
    ![](assets/new-canvas8.png)
-->

Användargränssnittet uppdateras automatiskt varje minut.

<!--
Please note that you may see differences between the number of exported profiles and the number of profiles flowing through the journey. The exported profiles count only provides information about the last export job being made while the number of profiles entering an activity only contains profiles who did it in the last 24 hours. This can especially be visible on recurring daily journeys as there could be a data overlap between two days.
-->
