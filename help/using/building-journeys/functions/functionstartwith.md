---
product: journey optimizer
title: startWith
description: Läs mer om funktionen startWith
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 1abdf947-2873-4e45-a26c-cb895980e76a
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
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
