---
product: journey optimizer
title: avg
description: Läs mer om avg för funktioner
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: avg, funktion, uttryck, resa
exl-id: cc70f90c-2d12-42a0-829f-5f28c3c29cad
source-git-commit: cb1fed2460ddbf3b226fe191b9695008970937c1
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 7%

---

# avg {#avg}

Returnerar det genomsnittliga värdet bland en uppsättning uttryck, givet antingen som en lista eller två uttryck. Null-värden ignoreras.


## Kategori

Aggregering

## Funktionssyntax

`avg(<parameter>)`

## Parametrar

Typer som stöds:

* listInteger
* listDecimal
* decimal
* heltal

## Underskrifter och returtyp

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

Returnerar ett decimaltal.

## Exempel

`avg(@event{BarBeacon.inventory},5)`

`avg([10,3,8])`

Returnerar 7.0.

`avg(10.2, 3)`

Returnerar 6,6.
