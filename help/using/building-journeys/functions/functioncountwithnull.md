---
product: journey optimizer
title: countWithNull
description: Läs mer om funktionen countWithNull
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: countWithNull, funktion, uttryck, resa
exl-id: 8d53b6d8-f00f-4d1a-b6df-951f84a15430
source-git-commit: 2f47209ad2a5e5b5d26f01949f5e9ade63c2581f
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 7%

---

# countWithNull {#countWithNull}

Räknar alla element i listan inklusive null-värden.

Observera att parametern `<listObject>` inte stöds i den här funktionen.

## Kategori

Aggregering

## Funktionssyntax

`countWithNull(<listAny>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly |

## Signatur och returtyp

`countWithNull(<listAny>)`

Returnerar ett heltal.

## Exempel

`countWithNull([10,2,10,null])`

Returnerar 4.
