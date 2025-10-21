---
product: journey optimizer
title: matchRegExp
description: Läs mer om funktionen matchRegExp
feature: Journeys
role: Developer
level: Experienced
keywords: matchRegExp, funktion, uttryck, resa
exl-id: 24cf362c-f390-4bb1-be82-a079bc27fa1f
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 7%

---

# matchRegExp {#matchRegExp}

Returnerar true om strängen i den första parametern matchar det reguljära uttrycket i den andra parametern. Mer information finns på [den här sidan](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## Kategori

Sträng

## Funktionssyntax

`matchRegExp(<parameters>)`

## Parametrar

| Parameter | Typ |
|--- |--- |
| string | string |
| regexp | string |

## Signatur och returtyp

`matchRegExp(<string>,<string>)`

Returnerar ett booleskt värde.

## Exempel

`matchRegExp("12345", "\\d+")`

Returnerar true.
