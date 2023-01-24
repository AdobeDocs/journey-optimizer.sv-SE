---
product: journey optimizer
title: inLastHours
description: Läs om funktionen iLastHours
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: inLastHours, funktion, uttryck, resa
exl-id: c648d711-c81b-403b-9adb-792c7e79e4e2
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 14%

---

# inLastHours {#inLastHours}

Returnerar true om den angivna datumtiden är mellan nu och nu - deltatimmar.

## Kategori

Datum

## Funktionssyntax

`inLastHours(<dateTime>,<delta>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

## Underskrifter och returtyp

`inLastHours(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

## Exempel

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4)`

Returnerar true.

`inLastHours(@{MyEvent.timestamp}, 4)`

Returnerar true.
