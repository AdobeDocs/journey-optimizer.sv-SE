---
product: journey optimizer
title: inNextMonths
description: Läs mer om funktionen i NextMonths
feature: Journeys
role: Engineer
level: Experienced
keywords: inNextMonths, function, expression, travel
exl-id: e2e520ec-ae9e-4ed6-b50d-606fc6861d56
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

---

# inNextMonths {#inNextMonths}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu + delta-månader.

## Kategori

Datum

## Funktionssyntax

`inNextMonths(<dateTime>,<delta>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

## Underskrifter och returtyp

`inNextMonths(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

## Exempel

`inNextMonths(toDateTime('2023-01-12T01:11:00Z'), 4)`

Returnerar true.
