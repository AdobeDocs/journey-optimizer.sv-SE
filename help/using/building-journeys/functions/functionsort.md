---
product: adobe campaign
title: sort
description: Lär dig mer om funktionssortering
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 607e1424-4165-48ae-b896-cce2d18f7dcc
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 13%

---

# sortera {#sort}

Sorterar en lista med värden i den naturliga ordningen. Det första argumentet är listan med värden, det andra är ett booleskt värde som anger om sorteringen är stigande (true) eller fallande (false).

## Kategori

Lista

## Funktionssyntax

`sort(<parameters>)`

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
| Boolean | Boolean |

## Signatur och returtyp

`sort(<listInteger>,<boolean>)`

Returnerar en lista med heltal.

`sort(<listDecimal>,<boolean>)`

Returnerar en lista med decimaler.

`sort(<listString>,<boolean>)`

Returnerar en lista med strängar.

`sort(<listDateTimeOnly>,<boolean>)`

Returnerar en lista med datum/tid utan hänsyn till tidszon.

`sort(<listDateTime>,<boolean>)`

Returnerar en lista med datetimes.

`sort(<listDateOnly>,<boolean>)`

Returnerar en lista med datum.

`sort(<listBoolean>,<boolean>)`

Returnerar en lista med boolesk.

## Exempel

`sort(["A", "C", "B"], true)`

Returnerar `["A","B","C"]`.

`sort([1, 3, 2], false)`

Returnerar `[3, 2, 1]`.
