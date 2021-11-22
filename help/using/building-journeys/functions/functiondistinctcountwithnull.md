---
product: adobe campaign
title: distinctCountWithNull
description: Lär dig mer om funktionen distinktCountWithNull
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: d786f3d42515d65a6574f51b6cff4b85063a0126
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 30%

---

# clearCountWithNull {#distinctCountWithNull}

Räknar antalet olika värden inklusive null-värden.

## Kategori

Aggregera

## Funktionssyntax

`distinctCountWithNull(<listAny>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| Lista | listString |
| Lista | listBoolean |
| Lista | listInteger |
| Lista | listDecimal |
| Lista | listDuration |
| Lista | listDateTime |
| Lista | listDateTimeOnly |
| Lista | listDateOnly |

## Signatur och returtyp

`distinctCountWithNull(<listAny>)`

Returnerar ett heltal.

## Exempel

`distinctCountWithNull([10,2,10,null])`

Returnerar 3.
