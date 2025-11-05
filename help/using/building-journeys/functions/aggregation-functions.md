---
product: journey optimizer
title: Sammanställningsfunktioner
description: Lär dig mer om sammanställningsfunktioner
feature: Journeys
role: Developer
level: Experienced
keywords: aggregering, funktioner, uttryck, resa, avg, count, max, min, sum
version: Journey Orchestration
source-git-commit: af1babe501a5b2c6a67730396a8f5e2c5d85e60a
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 5%

---

# Sammanställningsfunktioner {#aggregation-functions}

Sammanställningsfunktioner används för att utföra beräkningar på en uppsättning värden och returnera ett enda värde. De här funktionerna är särskilt användbara när du arbetar med listor och arrayer i dina reseuttryck.

## avg {#avg}

Returnerar det genomsnittliga värdet bland en uppsättning uttryck, givet antingen som en lista eller två uttryck. Null-värden ignoreras.

+++Syntax

`avg(<parameter>)`

+++

+++Parametrar

Typer som stöds:

* listInteger
* listDecimal
* decimal
* heltal

+++

+++Underskrifter och returtyp

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

Returnerar ett decimaltal.

+++

+++Exempel

`avg(@event{BarBeacon.inventory},5)`

`avg([10,3,8])`

Returnerar 7.0.

`avg(10.2, 3)`

Returnerar 6,6.

+++

## count {#count}

Räknar elementen i listan utan att ta hänsyn till null-värden.

+++Syntax

`count(<listAny>)`

`count(<listObject>)`

+++

+++Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly eller listObject | Lista som ska bearbetas. För listObject måste det vara en fältreferens. Ett listObject får inte innehålla null-objekt. |

+++

+++Underskrifter och returtyp

`count(<listAny>)`

Returnerar ett heltal.

+++

+++Exempel

`count([10,2,10,null])`

Returnerar 3.

`count(@event{my_event.productListItems})`

Returnerar antalet objekt i den angivna arrayen med objekt (typen listObject). Obs! Ett listObject får inte innehålla ett null-objekt

+++

## countOnlyNull {#countOnlyNull}

Räknar antalet null-värden i listan.

**Obs!** Parametern `<listObject>` stöds inte i den här funktionen.

+++Syntax

`countOnlyNull(<listAny>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly |

+++

+++Underskrifter och returtyp

`countOnlyNull(<listAny>)`

Returnerar ett heltal.

+++

+++Exempel

`countOnlyNull([10,2,10,null])`

Returnerar 1.

+++

## countWithNull {#countWithNull}

Räknar alla element i listan inklusive null-värden.

**Obs!** Parametern `<listObject>` stöds inte i den här funktionen.

+++Syntax

`countWithNull(<listAny>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly |

+++

+++Underskrifter och returtyp

`countWithNull(<listAny>)`

Returnerar ett heltal.

+++

+++Exempel

`countWithNull([10,2,10,null])`

Returnerar 4.

+++

## distinctCount {#distinctCount}

Räknar antalet olika värden som ignorerar null-värden.

+++Syntax

`distinctCount(<listAny>)`

+++

+++Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly eller listObject | Lista som ska bearbetas. För listObject måste det vara en fältreferens. |
| keyAttributeName | string | Den här parametern är valfri och endast för listObject. Om parametern inte anges betraktas ett objekt som duplicerat om alla attribut har samma värden. Annars betraktas ett objekt som duplicerat om det angivna attributet har samma värde. |

+++

+++Underskrifter och returtyp

`distinctCount(<listAny>)`

Returnerar ett heltal.

`distinctCount(<listObject>)`

`distinctCount(<listObject>,<string>)`

Returnerar en lista med objekt.

+++

+++Exempel

`distinctCount([10,2,10,null])`

Returnerar 2.

`distinctCount(@event{my_event.productListItems})`

Returnerar antalet strikt distinkta objekt i den angivna objektarrayen (typen listObject).

`distinctCount(@event{my_event.productListItems}, "SKU")`

Returnerar antalet objekt som har ett tydligt SKU-attributvärde {}.

+++

## distinctCountWithNull {#distinctCountWithNull}

Räknar antalet olika värden inklusive null-värden.

**Obs!** Parametern `<listObject>` stöds inte i den här funktionen.

+++Syntax

`distinctCountWithNull(<listAny>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly |

+++

+++Underskrifter och returtyp

`distinctCountWithNull(<listAny>)`

Returnerar ett heltal.

+++

+++Exempel

`distinctCountWithNull([10,2,10,null])`

Returnerar 3.

+++

## max {#max}

Returnerar det maximala värdet bland en uppsättning uttryck, givet antingen som en lista eller två uttryck. Null-värden ignoreras.

+++Syntax

`max(<parameter>)`

+++

+++Parametrar

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* listDateOnly
* varaktighet
* heltal
* decimal
* dateTime
* dateTimeOnly

+++

+++Underskrifter och returnerade typer

`max(<listDuration>)`

Returnerar en varaktighet.

`max(<listInteger>)`

Returnerar en varaktighet.

`max(<listDateTimeOnly>)`

Returnerar en datetime utan att ta hänsyn till tidszon.

`max(<listDateTime>)`

Returnerar en datetime.

`max(<listDateOnly>)`

Returnerar ett datum.

`max(<listDecimal>)`

Returnerar ett decimaltal.

`max(<decimal>,<decimal>)`

Returnerar ett decimaltal.

`max(<duration>,<duration>)`

Returnerar en varaktighet.

`max(<dateTime>,<dateTime>)`

Returnerar en datetime.

`max(<dateTimeOnly>,<dateTimeOnly>)`

Returnerar en datetime utan att ta hänsyn till tidszon.

`max(<integer>,<integer>)`

Returnerar ett heltal.

+++

+++Exempel

`max(@event{BarBeacon.inventory},5)`

`max([10,3,8])`

Returnerar 10.

`max([10,null,8])`

Returnerar 10.

+++

## min {#min}

Returnerar det minsta värdet bland en uppsättning uttryck, givet antingen som en lista eller två uttryck. Null-värden ignoreras.

+++Syntax

`min(<parameters>)`

+++

+++Parametrar

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* listDateOnly
* varaktighet
* heltal
* decimal
* dateTime
* dateTimeOnly

+++

+++Underskrifter och returnerade typer

`min(<listDuration>)`

Returnerar en varaktighet.

`min(<listInteger>)`

Returnerar en varaktighet.

`min(<listDateTimeOnly>)`

Returnerar en datetime utan att ta hänsyn till tidszon.

`min(<listDateTime>)`

Returnerar en datetime.

`min(<listDateOnly>)`

Returnerar ett datum.

`min(<listDecimal>)`

Returnerar ett decimaltal.

`min(<decimal>,<decimal>)`

Returnerar ett decimaltal.

`min(<duration>,<duration>)`

Returnerar en varaktighet.

`min(<dateTime>,<dateTime>)`

Returnerar en datetime.

`min(<dateTimeOnly>,<dateTimeOnly>)`

Returnerar en datetime utan att ta hänsyn till tidszon.

`min(<integer>,<integer>)`

Returnerar ett heltal.

+++

+++Exempel

`min(@event{BarBeacon.inventory},5)`

`min([10,3,8])`

Returnerar 3.

`min([10,null,8])`

Returnerar 8.

+++

## sum {#sum}

Returnerar summan av värdena för en uppsättning uttryck. Null-värden ignoreras.

+++Syntax

`sum(<parameters>)`

+++

+++Parametrar

* listInteger
* listDecimal
* varaktighet
* heltal
* decimal

+++

+++Underskrifter och returnerade typer

`sum(<listDecimal>)`

Returnerar ett decimaltal.

`sum(<listInteger>)`

Returnerar ett heltal.

`sum(<integer>,<integer>)`

Returnerar ett heltal.

`sum(<decimal>,<decimal>)`

Returnerar ett decimaltal.

+++

+++Exempel

`sum(@event{BarBeacon.inventory},5)`

`sum([10,3,8])`

Returnerar 21.

`sum([10.5,null,8.1])`

Returnerar 18.6.

+++
