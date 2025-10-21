---
product: journey optimizer
title: inLastHours
description: Läs om funktionen iLastHours
feature: Journeys
role: Developer
level: Experienced
keywords: inLastHours, funktion, uttryck, resa
exl-id: c648d711-c81b-403b-9adb-792c7e79e4e2
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 10%

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

`inLastHours(toDateTime('2023-12-12T01:11:00Z'), 4)`

Returnerar true.

`inLastHours(@event{MyEvent.timestamp}, 4)`

Returnerar true.
