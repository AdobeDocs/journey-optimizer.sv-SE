---
product: journey optimizer
title: inLastYears
description: Läs om funktionen iLastYears
feature: Journeys
role: Developer
level: Experienced
keywords: inLastYears, function, expression, travel
exl-id: cdf653d2-967e-4a1b-92e5-37dd22f379f9
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

---

# inLastYears {#inLastYears}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu - delta-år.

## Kategori

Datum

## Funktionssyntax

`inLastYears(<dateTime>,<delta>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

## Underskrifter och returtyp

`inLastYears(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

## Exempel

`inLastYears(toDateTime('2023-12-12T01:11:00Z'), 4)`

Returnerar true.
