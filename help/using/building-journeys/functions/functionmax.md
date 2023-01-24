---
product: journey optimizer
title: max
description: Läs mer om funktionen max
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: max, funktion, uttryck, resa
exl-id: 5c792d33-32b9-4b1b-ab99-3ebfac391678
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 6%

---

# max{#max}

Returnerar det maximala värdet bland en uppsättning uttryck, givet antingen som en lista eller två uttryck. Null-värden ignoreras.

## Kategori

Aggregera

## Funktionssyntax

`max(<parameter>)`

## Parametrar

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

## Underskrifter och returnerade typer

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

## Exempel

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

Returnerar 10.

`max([10,null,8])`

Returnerar 10.
