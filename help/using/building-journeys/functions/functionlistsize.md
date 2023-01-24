---
product: journey optimizer
title: listSize
description: Läs mer om funktionen listSize
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: listSize, function, expression, travel
exl-id: dd378e4d-f65a-495c-ac10-b4209d6b6b88
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 29%

---

# listSize {#listSize}

Räknar antalet element i listan.

## Kategori

Lista

## Funktionssyntax

`listSize(<parameters>)`

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

## Underskrifter och returtyp

`listSize(<listInteger>)`

`listSize(<listDecimal>)`

`listSize(<listString>)`

`listSize(<listBoolean>)`

`listSize(<listDateTimeOnly>)`

`listSize(<listDateTime>)`

`listSize(<listDateOnly>)`

`listSize(<listDuration>)`

`listSize(<listPoint>)`

Returnera ett heltal.

## Exempel

`listSize([10,2,3])`

Returnerar 3.
