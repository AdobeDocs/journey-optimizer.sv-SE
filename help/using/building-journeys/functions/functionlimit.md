---
product: journey optimizer
title: gräns
description: Läs mer om funktionsgränsen
feature: Journeys
role: Engineer
level: Experienced
keywords: gräns, funktion, uttryck, resa
exl-id: 7fa1e393-2912-4392-b759-e54d08d5635a
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 3%

---

# gräns {#limit}

Returnerar det första eller sista N-elementet i en lista.

## Kategori

Lista

## Funktionssyntax

`limit(<parameters>)`

## Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly eller listObject | Lista att tänka på. För listObject måste det vara en fältreferens. |
| numberOfItems | heltal | Antal objekt som ska returneras från den angivna listan. |
| firstOrLastItems | boolesk | Den här parametern är valfri (true som standard). true returnerar de första objekten. false returnerar de sista objekten. |

## Signatur och returtyp

`limit(<listString>,<integer>)`
`limit(<listString>,<integer>,<boolean>)`

Returnerar en lista med strängar.

`limit(<listInteger>,<integer>)`
`limit(<listInteger>,<integer>,<boolean>)`

Returnerar en lista med heltal.

`limit(<listDecimal>,<integer>)`
`limit(<listDecimal>,<integer>,<boolean>)`

Returnerar en lista med decimaler.

`limit(<listBoolean>,<integer>)`
`limit(<listBoolean>,<integer>,<boolean>)`

Returnerar en lista med boolesk.

`limit(<listDateOnly>,<integer>)`
`limit(<listDateOnly>,<integer>,<boolean>)`

Returnerar en lista med datum.

`limit(<listDateTimeOnly>,<integer>)`
`limit(<listDateTimeOnly>,<integer>,<boolean>)`

Returnerar en lista med datum/tid utan hänsyn till tidszon.

`limit(<listDateTime>,integer>)`
`limit(<listDateTime>,<integer>,<boolean>)`

Returnerar en lista med datetimes.

`limit(<listDuration>,<integer>)`
`limit(<listDuration>,<integer>,<boolean>)`

Returnerar en lista med varaktigheter.

`limit(<listObject>,<integer>)`
`limit(<listObject>,<integer>,<boolean>)`

Returnerar en lista med objekt.

## Exempel

`limit(["A", "B", "C", "D", "E"], 3)`

Returnerar `["A","B","C"]`.

`limit(["A", "B", "C", "D", "E"], 3, false)`

Returnerar `["C","D","E"]`.
