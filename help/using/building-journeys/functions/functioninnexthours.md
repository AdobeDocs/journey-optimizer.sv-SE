---
product: journey optimizer
title: inNextHours
description: Läs mer om funktionen i NextHours
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 079a91b6-49c5-4e68-a240-358ed0cded92
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 15%

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

`inNextHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

Returnerar true.
