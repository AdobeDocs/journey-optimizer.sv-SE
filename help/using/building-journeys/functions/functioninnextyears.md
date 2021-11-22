---
product: adobe campaign
title: inNextYears
description: Läs om funktionen iNextYears
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 23f4e8224ea5b00e8132b6a3f3e32f73b0cc993f
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 15%

---

# inNextYears {#inNextYears}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu + delta-år.

## Kategori

Datum

## Funktionssyntax

`inNextYears(<dateTime>,<delta>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

## Underskrifter och returtyp

`inNextYears(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

## Exempel

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4)`

Returnerar true.
