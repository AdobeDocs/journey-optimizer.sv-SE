---
product: journey optimizer
title: distinctCount
description: Lär dig mer om funktionen distinktCount
feature: Journeys
role: Developer
level: Experienced
keywords: distinktAntal, funktion, uttryck, resa
exl-id: 8796ba91-5c64-43c2-a444-27ac8b719c86
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 3%

---

# distinctCount{#distinctCount}

Räknar antalet olika värden som ignorerar null-värden.

## Kategori

Aggregering

## Funktionssyntax

`distinctCount(<listAny>)`

## Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly eller listObject | Lista som ska bearbetas. För listObject måste det vara en fältreferens. |
| keyAttributeName | string | Den här parametern är valfri och endast för listObject. Om parametern inte anges betraktas ett objekt som duplicerat om alla attribut har samma värden. Annars betraktas ett objekt som duplicerat om det angivna attributet har samma värde. |

## Signatur och returtyp

`distinctCount(<listAny>)`

Returnerar ett heltal.

`distinctCount(<listObject>)`

`distinctCount(<listObject>,<string>)`

Returnerar en lista med objekt.


## Exempel

`distinctCount([10,2,10,null])`

Returnerar 2.

`distinctCount(@event{my_event.productListItems})`

Returnerar antalet strikt distinkta objekt i den angivna objektarrayen (typen listObject).

`distinctCount(@event{my_event.productListItems}, "SKU")`

Returnerar antalet objekt som har ett tydligt SKU-attributvärde {}.
