---
product: journey optimizer
title: inNextYears
description: Läs om funktionen iNextYears
feature: Journeys
role: Engineer
level: Experienced
keywords: inNextYears, function, expression, travel
exl-id: e4597772-d53c-4e15-8237-b2460ce31170
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

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
