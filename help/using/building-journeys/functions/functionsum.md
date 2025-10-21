---
product: journey optimizer
title: sum
description: Läs mer om funktionssumman
feature: Journeys
role: Developer
level: Experienced
keywords: summa, funktion, uttryck, resa
exl-id: a9085f4d-6434-4bc5-8e5d-3f2b6033defc
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 7%

---

# sum {#sum}

Returnerar summan av värdena för en uppsättning uttryck. Null-värden ignoreras.

## Kategori

Aggregering

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

`sum(@event{BarBeacon.inventory},5)`

`sum([10,3,8])`

Returnerar 21.

`sum([10.5,null,8.1])`

Returnerar 18.6.
