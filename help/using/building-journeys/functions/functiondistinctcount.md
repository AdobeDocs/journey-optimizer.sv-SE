---
product: journey optimizer
title: distinctCount
description: Lär dig mer om funktionen distinktCount
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: distinktAntal, funktion, uttryck, resa
exl-id: 8796ba91-5c64-43c2-a444-27ac8b719c86
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 28%

---

# distinctCount{#distinctCount}

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
