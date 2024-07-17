---
product: journey optimizer
title: matchRegExp
description: Läs mer om funktionen matchRegExp
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: matchRegExp, funktion, uttryck, resa
exl-id: 24cf362c-f390-4bb1-be82-a079bc27fa1f
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
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

`matchRegExp("username@adobe.com", "*adobe")`

Returnerar true.
