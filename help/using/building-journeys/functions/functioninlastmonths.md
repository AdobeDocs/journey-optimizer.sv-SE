---
product: adobe campaign
title: inLastMonths
description: Läs mer om funktionen i LastMonths
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 4933ef43-66b8-462d-867c-03edd4c34947
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 15%

---

# inLastMonths {#inLastMonths}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu - delta-månader.

## Kategori

Datum

## Funktionssyntax

`inLastMonths(<dateTime>,<delta>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

## Underskrifter och returtyp

`inLastMonths(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

## Exempel

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4)`

Returnerar true.
