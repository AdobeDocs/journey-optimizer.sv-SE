---
product: adobe campaign
title: endWith
description: Läs mer om funktionen endWith
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 23f4e8224ea5b00e8132b6a3f3e32f73b0cc993f
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 16%

---

# endWith {#endWith}

Returnerar true om den andra parametern är ett suffix till den första.

## Kategori

Sträng

## Funktionssyntax

`endWith(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| string | string |
| suffix | string |

## Signatur och returtyp

`endWith(<string>,<string>)`

Returnerar ett booleskt värde.

## Exempel

`endWith("Hello World", "World")`

Returnerar true.

`endWith("Hello World", "Hello")`

Returnerar false.
