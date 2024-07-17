---
product: journey optimizer
title: listSize
description: Läs mer om funktionen listSize
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: listSize, function, expression, travel
exl-id: dd378e4d-f65a-495c-ac10-b4209d6b6b88
source-git-commit: 2f47209ad2a5e5b5d26f01949f5e9ade63c2581f
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 6%

---

# listSize {#listSize}

Räknar antalet element i listan.

## Kategori

Lista

## Funktionssyntax

`listSize(<parameters>)`

## Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly eller listObject | Lista som ska bearbetas. För listObject måste det vara en fältreferens. Ett listObject får inte innehålla null-objekt. |

## Underskrifter och returtyp

`listSize(<listInteger>)`

`listSize(<listDecimal>)`

`listSize(<listString>)`

`listSize(<listBoolean>)`

`listSize(<listDateTimeOnly>)`

`listSize(<listDateTime>)`

`listSize(<listDateOnly>)`

`listSize(<listDuration>)`

Returnera ett heltal.

`listSize(<listObject>)`

## Exempel

`listSize([10,2,3])`

Returnerar 3.

`listSize(@event{my_event.productListItems})`

Returnerar antalet objekt i den angivna arrayen med objekt (typen listObject).
