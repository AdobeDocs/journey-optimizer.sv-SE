---
product: journey optimizer
title: inLastDays
description: Läs mer om funktionen inLastDays
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: inLastDays, funktion, uttryck, resa
exl-id: 1b150568-17c2-454d-847e-17bac3d0b35d
source-git-commit: 4e7c4e7e6fcf488f572ccf3e9037e597dde06510
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

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

`inLastDays(toDateTime('2023-12-12T01:11:00Z'), 4)`

Returnerar true.
