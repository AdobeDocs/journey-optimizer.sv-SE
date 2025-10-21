---
product: journey optimizer
title: distinctWithNull
description: Lär dig mer om funktionen distinktMedNull
feature: Journeys
role: Developer
level: Experienced
keywords: distinktMedNull, funktion, uttryck, resa
exl-id: 73fa9837-d2e1-4f0a-a423-cf7728882eba
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 4%

---

# distinctWithNull {#distinctWithNull}

Returnerar de distinkta värdena eller objekten i en viss lista. Om listan har minst en null-post kommer en null-post att finnas i den returnerade listan.

Observera att parametern `<listObject>` inte stöds i den här funktionen.

## Kategori

Lista

## Funktionssyntax

`distinctWithNull(<parameters>)`

## Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly | Lista som ska bearbetas. |

## Underskrifter och returnerade typer

`distinctWithNull(<listInteger>)`

Returnerar en lista med heltal.

`distinctWithNull(<listDecimal>)`

Returnerar en lista med decimaler.

`distinctWithNull(<listString>)`

Returnerar en lista med strängar.

`distinctWithNull(<listDateTimeOnly>)`

Returnerar en lista med datum/tid utan hänsyn till tidszon.

`distinctWithNull(<listDateTime>)`

Returnerar en lista med datetimes.

`distinctWithNull(<listDateOnly>)`

Returnerar en lista med datum.

`distinctWithNull(<listBoolean>)`

Returnerar en lista med boolesk.

`distinctWithNull(<listDuration>)`

Returnerar en lista med varaktigheter.

## Exempel

`distinctWithNull([10,2,10,null])`

Returnerar [10, 2, null]
