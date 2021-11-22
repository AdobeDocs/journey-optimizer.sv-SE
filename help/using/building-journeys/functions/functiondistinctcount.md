---
product: adobe campaign
title: distinctCount
description: Lär dig mer om funktionen distinktCount
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: d786f3d42515d65a6574f51b6cff4b85063a0126
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 30%

---

# clearCount{#distinctCount}

Räknar antalet olika värden som ignorerar null-värden.

## Kategori

Aggregera

## Funktionssyntax

`distinctCount(<listAny>)`

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

`distinctCount(<listAny>)`

Returnerar ett heltal.

## Exempel

`distinctCount([10,2,10,null])`

Returnerar 2.
