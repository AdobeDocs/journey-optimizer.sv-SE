---
product: journey optimizer
title: countOnlyNull
description: Läs mer om funktionen countOnlyNull
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: countOnlyNull, funktion, uttryck, resa
exl-id: d06fc594-33dd-48ce-8c62-2f2892a867da
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 28%

---

# countOnlyNull {#countOnlyNull}

Räknar antalet null-värden i listan.

## Kategori

Aggregera

## Funktionssyntax

`countOnlyNull(<listAny>)`

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

`countOnlyNull(<listAny>)`

Returnerar ett heltal.

## Exempel

`countOnlyNull([10,2,10,null])`

Returnerar 1.
