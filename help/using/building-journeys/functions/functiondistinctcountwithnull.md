---
product: journey optimizer
title: distinctCountWithNull
description: Lär dig mer om funktionen distinktCountWithNull
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: distinktCountWithNull, funktion, uttryck, resa
exl-id: 2c3f629f-2220-44a4-9b0c-8aa602301098
source-git-commit: 2f47209ad2a5e5b5d26f01949f5e9ade63c2581f
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 7%

---

# distinctCountWithNull {#distinctCountWithNull}

Räknar antalet olika värden inklusive null-värden.

Observera att parametern `<listObject>` inte stöds i den här funktionen.

## Kategori

Aggregering

## Funktionssyntax

`distinctCountWithNull(<listAny>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly |

## Signatur och returtyp

`distinctCountWithNull(<listAny>)`

Returnerar ett heltal.

## Exempel

`distinctCountWithNull([10,2,10,null])`

Returnerar 3.
