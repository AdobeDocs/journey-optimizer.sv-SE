---
product: adobe campaign
title: startWith
description: Läs mer om funktionen startWith
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 23f4e8224ea5b00e8132b6a3f3e32f73b0cc993f
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 16%

---

# startWith {#startWith}

Returnerar true om den andra parametern är ett prefix till den första.

## Kategori

Sträng

## Funktionssyntax

`startWith(<parameters>)`

## Parametrar

| Parameter | Typ |
|-------------|--------|
| string | string |
| prefix | string |

## Signatur och returtyp

`startWith(<string>,<string>)`

Returnera ett booleskt värde.

## Exempel

`startWith("Hello World", "Hello")`

Returnerar true.

`startWith("Hello World", "World")`

Returnerar false.
