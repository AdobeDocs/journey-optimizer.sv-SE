---
product: adobe campaign
title: inLastYears
description: Läs om funktionen iLastYears
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: cdf653d2-967e-4a1b-92e5-37dd22f379f9
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 15%

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

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4)`

Returnerar true.
