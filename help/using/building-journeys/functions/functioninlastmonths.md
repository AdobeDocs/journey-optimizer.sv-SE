---
product: journey optimizer
title: inLastMonths
description: Läs mer om funktionen i LastMonths
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: inLastMonths, function, expression, travel
exl-id: 4933ef43-66b8-462d-867c-03edd4c34947
source-git-commit: 4e7c4e7e6fcf488f572ccf3e9037e597dde06510
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

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

`inLastMonths(toDateTime('2023-12-12T01:11:00Z'), 4)`

Returnerar true.
