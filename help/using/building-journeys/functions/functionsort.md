---
product: journey optimizer
title: sort
description: Lär dig mer om funktionssortering
feature: Journeys
role: Engineer
level: Experienced
keywords: sortering, funktion, uttryck, resa
exl-id: 607e1424-4165-48ae-b896-cce2d18f7dcc
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 3%

---

# sort {#sort}

Sorterar en lista med värden eller objekt i den naturliga ordningen.

## Kategori

Lista

## Funktionssyntax

`sort(<parameters>)`

## Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToSort | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly eller listObject | Lista att sortera ut. För listObject måste det vara en fältreferens. |
| keyAttributeName | string | Den här parametern är bara för listObject. Attributnamnet i objekten i den angivna listan används som nyckel för sorteringen. |
| sortingOrder | boolesk | Stigande (true) eller fallande (false) |

## Signatur och returtyp

`sort(<listInteger>,<boolean>)`

Returnerar en lista med heltal.

`sort(<listDecimal>,<boolean>)`

Returnerar en lista med decimaler.

`sort(<listString>,<boolean>)`

Returnerar en lista med strängar.

`sort(<listDateTimeOnly>,<boolean>)`

Returnerar en lista med datum/tid utan hänsyn till tidszon.

`sort(<listDateTime>,<boolean>)`

Returnerar en lista med datetimes.

`sort(<listDateOnly>,<boolean>)`

Returnerar en lista med datum.

`sort(<listBoolean>,<boolean>)`

Returnerar en lista med boolesk.

`sort(<listObject>,<string>,<boolean>)`

Returnerar en lista med objekt.

## Exempel

`sort(["A", "C", "B"], true)`

Returnerar `["A","B","C"]`.

`sort([1, 3, 2], false)`

Returnerar `[3, 2, 1]`.

`sort(@event{my_event.productListItems}, "SKU", true)`

Returnerar listObject sorterat efter SKU-attribut (stigande ordning)

