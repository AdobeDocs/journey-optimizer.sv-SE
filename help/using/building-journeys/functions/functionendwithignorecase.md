---
product: journey optimizer
title: endWithIgnoreCase
description: Läs mer om funktionen endWithIgnoreCase
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: endWithIgnoreCase, funktion, uttryck, resa
exl-id: 278ef1a4-571c-4b5f-b4de-0cfc644ac7d7
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 3%

---

# endWithIgnoreCase {#endWithIgnoreCase}

Kontrollerar om den första argumentsträngen slutar med en viss sträng (den andra argumentsträngen), utan att ta hänsyn till skiftläget.

## Kategori

Sträng

## Funktionssyntax

`endWithIgnoreCase(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| string | string |
| suffix | string |

## Signatur och returtyp

`endWithIgnoreCase(<string>,<string>)`

Returnerar ett booleskt värde.

## Exempel

`endWithIgnoreCase("rowing is great", "AT")`

Returnerar true.
