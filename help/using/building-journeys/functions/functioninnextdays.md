---
product: journey optimizer
title: inNextDays
description: Läs mer om funktionen i NextDays
feature: Journeys
role: Developer
level: Experienced
keywords: inNextDays, funktion, uttryck, resa
exl-id: 0cb3e0db-dc5b-4d4e-a057-af030d9bdb21
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

---

# inNextDays {#inNextDays}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu + delta-dagar.

## Kategori

Datum

## Funktionssyntax

`inNextDays(<dateTime>,<delta>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

## Underskrifter och returtyp

`inNextDays(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

## Exempel

`inNextDays(toDateTime('2023-12-12T01:11:00Z'), 4)`

Returnerar true.
