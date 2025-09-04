---
product: journey optimizer
title: inNextHours
description: Läs mer om funktionen i NextHours
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: inNextHours, function, expression, travel
exl-id: 079a91b6-49c5-4e68-a240-358ed0cded92
version: Journey Orchestration
source-git-commit: 62783c5731a8b78a8171fdadb1da8a680d249efd
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
