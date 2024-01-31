---
product: journey optimizer
title: distinct
description: Lär dig mer om funktionens distinkt
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: distinkt, funktion, uttryck, resa
exl-id: f4e2dd34-b634-4a91-af53-60be155a65d0
source-git-commit: cb1fed2460ddbf3b226fe191b9695008970937c1
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 3%

---

# distinct {#distinct}

Returnerar de distinkta värdena eller objekten i en viss lista. Null-poster ignoreras.

## Kategori

Lista

## Funktionssyntax

`distinct(<parameters>)`

## Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly eller listObject | Lista som ska bearbetas. För listObject måste det vara en fältreferens. |
| keyAttributeName | string | Den här parametern är valfri och endast för listObject. Om parametern inte anges betraktas ett objekt som duplicerat om alla attribut har samma värden. Annars betraktas ett objekt som duplicerat om det angivna attributet har samma värde. |

## Underskrifter och returnerade typer

`distinct(<listInteger>)`

Returnerar en lista med heltal.

`distinct(<listDecimal>)`

Returnerar en lista med decimaler.

`distinct(<listString>)`

Returnerar en lista med strängar.

`distinct(<listDateTimeOnly>)`

Returnerar en lista med datum/tid utan hänsyn till tidszon.

`distinct(<listDateTime>)`

Returnerar en lista med datetimes.

`distinct(<listDateOnly>)`

Returnerar en lista med datum.

`distinct(<listBoolean>)`

Returnerar en lista med boolesk.

`distinct(<listDuration>)`

Returnerar en lista med varaktigheter.

`distinct(<listObject>)`

`distinct(<listObject>,<string>)`

Returnerar en lista med objekt.


## Exempel

`distinct([10,2,10,null])`

Returnerar `[10, 2]`.
