---
product: journey optimizer
title: distinctCountWithNull
description: Lär dig mer om funktionen distinktCountWithNull
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: distinktCountWithNull, funktion, uttryck, resa
exl-id: 2c3f629f-2220-44a4-9b0c-8aa602301098
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 21%

---

# distinctCountWithNull {#distinctCountWithNull}

Räknar antalet olika värden inklusive null-värden.

>[!NOTE]
>
>Om mållistan är ett listObject kan den här funktionen bara användas i anpassade åtgärdsuttryck.

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
