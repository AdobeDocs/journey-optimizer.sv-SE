---
product: journey optimizer
title: Datumfunktioner
description: Läs om datumfunktioner
feature: Journeys
role: Developer
level: Experienced
keywords: datum, funktioner, uttryck, resa, tid
version: Journey Orchestration
source-git-commit: 48b3ef3d2e041ea49d1b0c91cc72ea04237a5e33
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 6%

---

# Datumfunktioner {#date-functions}

Med datumfunktionerna kan du ändra och arbeta med datum- och tidsvärden i dina reseuttryck. Dessa funktioner är viktiga för tidsbaserade förhållanden, schemaläggning och tidsberäkningar i kundresor.

>[!NOTE]
>
>Funktionerna på den här sidan är tillgängliga i reseuttryck. Vissa funktioner som `now()` är inte tillgängliga i anpassningsredigeraren för e-postinnehåll. [Läs mer](../../personalization/functions/dates.md)

Använd datumfunktioner när du behöver:

* Hämta aktuell tid eller aktuellt datum med specifik hantering av tidszoner ([nu](#now), [nowWithDelta](#nowWithDelta), [currentTimeInMillis](#currentTimeInMillis))
* Kontrollera om ett datum ligger inom ett visst tidsintervall ([inLastDays](#inLastDays), [inLastHours](#inLastHours), [inLastMonths](#inLastMonths), [inLastYears](#inLastYears), [inNextDays](#inNextDays), [inNextHours](#inNextHours), [in Nästa månad ](#inNextMonths), [inNästaÅr](#inNextYears))
* Ändra datum- och tidskomponenter ([setHours](#setHours), [setDays](#setDays), [updateTimeZone](#updateTimeZone))
* Tidsbaserade beräkningar och jämförelser
* Konvertera mellan olika tidsformat och representationer

Datumfunktioner ger exakt kontroll över tidslogiken, vilket gör att du kan skapa tidskänsliga resvägar och villkor som svarar på specifika tidsramar och tidsplaner.

## currentTimeInMillis {#currentTimeInMillis}

Returnerar aktuell tid i epok i millisekunder.

+++Syntax

`currentTimeInMillis()`

+++

+++Parametrar

Den här funktionen använder inga parametrar.

+++

+++Underskrifter och returtyp

`currentTimeInMillis()`

Returnerar ett heltal.

+++

+++Exempel

`currentTimeInMillis()`

Returnerar &quot;1544712617131&quot;.

+++

## inLastDays {#inLastDays}

Returnerar true om en viss dateTime är mellan nu och nu - delta-dagar.

+++Syntax

`inLastDays(<dateTime>,<delta>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

+++

+++Underskrifter och returtyp

`inLastDays(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

+++

+++Exempel

`inLastDays(toDateTime('2023-12-12T01:11:00Z'), 4)`

Returnerar true.

+++

## inLastHours {#inLastHours}

Returnerar true om den angivna datumtiden är mellan nu och nu - deltatimmar.

+++Syntax

`inLastHours(<dateTime>,<delta>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

+++

+++Underskrifter och returtyp

`inLastHours(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

+++

+++Exempel

`inLastHours(toDateTime('2023-12-12T01:11:00Z'), 4)`

Returnerar true.

`inLastHours(@event{MyEvent.timestamp}, 4)`

Returnerar true.

+++

## inLastMonths {#inLastMonths}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu - delta-månader.

+++Syntax

`inLastMonths(<dateTime>,<delta>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

+++

+++Underskrifter och returtyp

`inLastMonths(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

+++

+++Exempel

`inLastMonths(toDateTime('2023-12-12T01:11:00Z'), 4)`

Returnerar true.

+++

## inLastYears {#inLastYears}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu - delta-år.

+++Syntax

`inLastYears(<dateTime>,<delta>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

+++

+++Underskrifter och returtyp

`inLastYears(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

+++

+++Exempel

`inLastYears(toDateTime('2023-12-12T01:11:00Z'), 4)`

Returnerar true.

+++

## inNextDays {#inNextDays}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu + delta-dagar.

+++Syntax

`inNextDays(<dateTime>,<delta>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

+++

+++Underskrifter och returtyp

`inNextDays(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

+++

+++Exempel

`inNextDays(toDateTime('2023-12-12T01:11:00Z'), 4)`

Returnerar true.

+++

## inNextHours {#inNextHours}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu + delta-timmar.

+++Syntax

`inNextHours(<dateTime>,<delta>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

+++

+++Underskrifter och returtyp

`inNextHours(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

+++

+++Exempel

`inNextHours(toDateTime('2023-12-12T01:11:00Z'), 4)`

Returnerar true.

+++

## inNextMonths {#inNextMonths}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu + delta-månader.

+++Syntax

`inNextMonths(<dateTime>,<delta>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

+++

+++Underskrifter och returtyp

`inNextMonths(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

+++

+++Exempel

`inNextMonths(toDateTime('2023-01-12T01:11:00Z'), 4)`

Returnerar true.

+++

## inNextYears {#inNextYears}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu + delta-år.

+++Syntax

`inNextYears(<dateTime>,<delta>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

+++

+++Underskrifter och returtyp

`inNextYears(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

+++

+++Exempel

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4)`

Returnerar true.

+++

## now {#now}

Returnerar aktuellt datum i tidsformat för datum. Mer information om datatyper finns på [den här sidan](../expression/data-types.md).

>[!NOTE]
>
>Den här funktionen är bara tillgänglig i reseuttryck. Använd `getCurrentZonedDateTime()` i stället för e-postanpassning och annat innehåll. [Läs mer](../../personalization/functions/dates.md#get-current-zoned-date-time)

+++Syntax

`now(<parameter>)`

+++

+++Parametrar

| Parameter | Beskrivning |
|--- |--- |
| string | Identifierare för tidszon (valfritt) |

+++

+++Underskrifter och returtyp

`now()`

`now("<timeZone id>")`

Returnerar ett dateTime.

+++

+++Exempel

`now()`

Returnerar 2023-06-03T06:30Z.

`toString(now())`

Returnerar &quot;2023-06-03T06:30Z&quot;

`now("Europe/Paris")`

Returnerar 2023-06-03T08 :30+02:00.

+++

## nowWithDelta {#nowWithDelta}

Returnerar aktuell datetime inklusive en offset. Om ett tidszon-ID anges används tidszonsförskjutningen. Mer information om datatyper finns på [den här sidan](../expression/data-types.md).

+++Syntax

`nowWithDelta(<parameters>)`

+++

+++Parametrar

| Parameter | Beskrivning |
|--- |--- |
| delta | positivt eller negativt heltalsvärde |
| datumdel | år, månader, dagar, timmar, minuter eller sekunder som en sträng |
| tidszon-id | strängbeteckning för tidszonsvärdet. Mer information finns i [Datatyper](../expression/data-types.md). Tidszons-ID måste vara en strängkonstant. Det kan inte vara en fältreferens eller ett uttryck. |

+++

+++Underskrifter och returtyp

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Returnerar ett dateTime.

+++

+++Exempel

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Returnerar ett dateTime för exakt 2 timmar sedan.

+++

## setHours {#setHours}

Anger endast timmar för datum och tid. Om du till exempel vill vänta en viss timme i morgon kan du tvinga timmen.

+++Syntax

`setHours(<parameter>)`

+++

+++Parametrar

| Parameter | Typ |
|--- |--- |
| tid | dateTime |
| datum tid utan att överväga tidszon | dateTimeOnly |
| timmar | heltal |

+++

+++Underskrifter och returtyp

`setHours(<dateTime>,<hours>)`

Returnerar en datetime.

`setHours(<dateTimeOnly>,<hours>)`

Returnerar en datetime utan att ta hänsyn till tidszon.

+++

+++Exempel

`setHours(toDateTime('2023-12-12T01:11:00Z'), 4)`

Returnerar 2023-12-12T04:11:00Z.

`setHours(nowWithDelta(1, "days"), 20)`

Returnerar imorgon kl. 8:XY PM, XY är minuter vid tidpunkten för den aktuella tidsutvärderingen. Om utvärderingen görs kl. 2:45 är den returnerade tiden 8:45 PM.

+++

## setDays {#setDays}

Anger endast dag för datum och tid. Om du t.ex. vill vänta till en viss dag i månaden kan du tvinga fram dagen.

+++Syntax

`setDays(<parameter>)`

+++

+++Parametrar

| Parameter | Typ |
|--- |--- |
| tid | dateTime |
| datum tid utan att överväga tidszon | dateTimeOnly |
| dagar | heltal |

+++

+++Underskrifter och returtyp

`setDays(<dateTime>,<days>)`

Returnerar en datetime.

`setDays(<dateTimeOnly>,<days>)`

Returnerar en datetime utan att ta hänsyn till tidszon.

+++

+++Exempel

`setDays(toDateTime('2023-12-12T01:11:00Z'), 25)`

Returnerar 2023-12-25T01:11:00Z.

`setDays(toDateTimeOnly(@event{MyEvent.registrationDate}), 1)`

+++

## updateTimeZone {#updateTimeZone}

Returnerar en ny datumtid, med en ny tidszon på samma gång.

+++Syntax

`updateTimeZone(<parameters>)`

+++

+++Parametrar

* tidszon-id: sträng
* dateTime

+++

+++Signatur och returtyp

`updateTimeZone(<dateTime>,<timeZone id>)`

Returnerar en datetime.

+++

+++Exempel

`updateTimeZone( toDateTime("2023-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

Returnerar 2023-08-28T17:15:30.123+02:00.

`updateTimeZone(@event{MyExpEvent.timestamp}, "Australia/Sydney")`

Om tidsstämpelfältets värde är `2021-11-16T16:55:12.939318+01:00` returnerar funktionen `2021-11-17T02:55:12.942115+11:00`.

+++

