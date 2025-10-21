---
product: journey optimizer
title: inNextHours
description: Läs mer om funktionen i NextHours
feature: Journeys
role: Engineer
level: Experienced
keywords: inNextHours, function, expression, travel
exl-id: 079a91b6-49c5-4e68-a240-358ed0cded92
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

---

# inNextHours {#inNextHours}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu + delta-timmar.

## Kategori

Datum

## Funktionssyntax

`inNextHours(<dateTime>,<delta>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

## Underskrifter och returtyp

`inNextHours(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

## Exempel

`inNextHours(toDateTime('2023-12-12T01:11:00Z'), 4)`

Returnerar true.
