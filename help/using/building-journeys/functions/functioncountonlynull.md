---
product: journey optimizer
title: countOnlyNull
description: Läs mer om funktionen countOnlyNull
feature: Journeys
role: Engineer
level: Experienced
keywords: countOnlyNull, funktion, uttryck, resa
exl-id: d06fc594-33dd-48ce-8c62-2f2892a867da
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 7%

---

# countOnlyNull {#countOnlyNull}

Räknar antalet null-värden i listan.

Observera att parametern `<listObject>` inte stöds i den här funktionen.

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
