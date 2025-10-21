---
product: journey optimizer
title: startWith
description: Läs mer om funktionen startWith
feature: Journeys
role: Developer
level: Experienced
keywords: startWith, funktion, uttryck, resa
exl-id: 1abdf947-2873-4e45-a26c-cb895980e76a
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 8%

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
