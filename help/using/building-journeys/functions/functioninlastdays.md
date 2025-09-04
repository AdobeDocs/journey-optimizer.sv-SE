---
product: journey optimizer
title: inLastDays
description: Läs mer om funktionen inLastDays
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: inLastDays, funktion, uttryck, resa
exl-id: 1b150568-17c2-454d-847e-17bac3d0b35d
version: Journey Orchestration
source-git-commit: 62783c5731a8b78a8171fdadb1da8a680d249efd
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 10%

---

# inLastDays {#inLastDays}

Returnerar true om en viss dateTime är mellan nu och nu - delta-dagar.

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

`inLastDays(toDateTime('2023-12-12T01:11:00Z'), 4)`

Returnerar true.
