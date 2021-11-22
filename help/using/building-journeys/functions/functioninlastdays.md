---
product: adobe campaign
title: inLastDays
description: Läs mer om funktionen inLastDays
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 23f4e8224ea5b00e8132b6a3f3e32f73b0cc993f
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 15%

---

# inLastDays {#inLastDays}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu - delta-dagar.

## Kategori

Datum

## Funktionssyntax

`inLastDays(<dateTime>,<delta>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

## Underskrifter och returtyp

`inLastDays(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

## Exempel

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4)`

Returnerar true.
