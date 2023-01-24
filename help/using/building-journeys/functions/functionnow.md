---
product: journey optimizer
title: now
description: Läs om funktionen nu
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: nu, funktion, uttryck, resa
exl-id: 16dcc772-e48d-4f10-be75-62dd39473556
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 13%

---

# now {#now}

Returnerar aktuellt datum i tidsformat för datum. Mer information om datatyper finns i [den här sidan](../expression/data-types.md).

## Kategori

Datum

## Funktionssyntax

`now(<parameter>)`

## Parametrar

| Parameter | Beskrivning |
|--- |--- |
| string |  |

## Underskrifter och returtyp

`now()`

`now("<timeZone id>")`

Returnerar ett dateTime.

## Exempel

`now()`

Returnerar 2019-06-03T06:30Z.

`toString(now())`

Returnerar &quot;2019-06-03T06:30Z&quot;

`now("Europe/Paris")`

Returnerar 2019-06-03T08:30+02:00.
