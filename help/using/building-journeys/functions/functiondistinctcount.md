---
product: adobe campaign
title: distinctCount
description: Lär dig mer om funktionen distinktCount
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8796ba91-5c64-43c2-a444-27ac8b719c86
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
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