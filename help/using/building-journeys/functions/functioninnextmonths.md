---
product: journey optimizer
title: inNextMonths
description: Läs mer om funktionen i NextMonths
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: inNextMonths, function, expression, travel
exl-id: e2e520ec-ae9e-4ed6-b50d-606fc6861d56
source-git-commit: 4e7c4e7e6fcf488f572ccf3e9037e597dde06510
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 12%

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
