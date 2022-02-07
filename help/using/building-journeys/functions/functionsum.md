---
product: adobe campaign
title: sum
description: Läs mer om funktionssumman
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: a9085f4d-6434-4bc5-8e5d-3f2b6033defc
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 11%

---

# summa {#sum}

Returnerar summan av värdena för en uppsättning uttryck. Null-värden ignoreras.

## Kategori

Aggregera

## Funktionssyntax

`sum(<parameters>)`

## Parametrar

* listInteger
* listDecimal
* varaktighet
* heltal
* decimal

## Underskrifter och returnerade typer

`sum(<listDecimal>)`

Returnerar ett decimaltal.

`sum(<listInteger>)`

Returnerar ett heltal.

`sum(<integer>,<integer>)`

Returnerar ett heltal.

`sum(<decimal>,<decimal>)`

Returnerar ett decimaltal.

## Exempel

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

Returnerar 21.

`sum([10.5,null,8.1])`

Returnerar 18.6.
