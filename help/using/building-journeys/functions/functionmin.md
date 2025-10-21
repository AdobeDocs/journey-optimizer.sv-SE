---
product: journey optimizer
title: min
description: Läs mer om min-funktionen
feature: Journeys
role: Engineer
level: Experienced
keywords: min, funktion, uttryck, resa
exl-id: 1c425d1d-08b4-446b-83ce-db376b2bf39f
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 4%

---

# min {#min}

Returnerar det minsta värdet bland en uppsättning uttryck, givet antingen som en lista eller två uttryck. Null-värden ignoreras.

## Kategori

Aggregering

## Funktionssyntax

`min(<parameters>)`

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

## Exempel

`min(@event{BarBeacon.inventory},5)`

`min([10,3,8])`

Returnerar 3.

`min([10,null,8])`

Returnerar 8.
