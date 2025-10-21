---
product: journey optimizer
title: now
description: Läs om funktionen nu
feature: Journeys
role: Developer
level: Experienced
keywords: nu, funktion, uttryck, resa
exl-id: 16dcc772-e48d-4f10-be75-62dd39473556
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '62'
ht-degree: 8%

---

# now {#now}

Returnerar aktuellt datum i tidsformat för datum. Mer information om datatyper finns på [den här sidan](../expression/data-types.md).

## Kategori

Datum

## Funktionssyntax

`now(<parameter>)`

## Parametrar

| Parameter | Beskrivning |
|--- |--- |
| string | Identifierare för tidszon (valfritt) |

## Underskrifter och returtyp

`now()`

`now("<timeZone id>")`

Returnerar ett dateTime.

## Exempel

`now()`

Returnerar 2023-06-03T06:30Z.

`toString(now())`

Returnerar &quot;2023-06-03T06:30Z&quot;

`now("Europe/Paris")`

Returnerar 2023-06-03T08 :30+02:00.
