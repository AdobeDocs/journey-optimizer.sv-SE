---
product: adobe campaign
title: inNextDays
description: Läs mer om funktionen i NextDays
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 23f4e8224ea5b00e8132b6a3f3e32f73b0cc993f
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 15%

---

# inNextDays {#inNextDays}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu + delta-dagar.

## Kategori

Datum

## Funktionssyntax

`inNextDays(<dateTime>,<delta>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

## Underskrifter och returtyp

`inNextDays(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

## Exempel

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

Returnerar true.
