---
product: journey optimizer
title: countOnlyNull
description: Läs mer om funktionen countOnlyNull
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: countOnlyNull, funktion, uttryck, resa
exl-id: d06fc594-33dd-48ce-8c62-2f2892a867da
source-git-commit: 2f47209ad2a5e5b5d26f01949f5e9ade63c2581f
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 8%

---

# countOnlyNull {#countOnlyNull}

Räknar antalet null-värden i listan.

Observera att parametern `<listObject>` stöds inte i den här funktionen.

## Kategori

Aggregering

## Funktionssyntax

`countOnlyNull(<listAny>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly |

## Signatur och returtyp

`countOnlyNull(<listAny>)`

Returnerar ett heltal.

## Exempel

`countOnlyNull([10,2,10,null])`

Returnerar 1.
