---
product: adobe campaign
title: avg
description: Läs mer om avg för funktioner
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: cc70f90c-2d12-42a0-829f-5f28c3c29cad
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 12%

---

# avg {#avg}

Returnerar det genomsnittliga värdet bland en uppsättning uttryck, givet antingen som en lista eller två uttryck. Null-värden ignoreras.


## Kategori

Aggregera

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

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

Returnerar 7.0.

`avg(10.2, 3)`

Returnerar 6,6.
