---
product: journey optimizer
title: endWithIgnoreCase
description: Läs mer om funktionen endWithIgnoreCase
feature: Journeys
role: Engineer
level: Experienced
keywords: endWithIgnoreCase, funktion, uttryck, resa
exl-id: 278ef1a4-571c-4b5f-b4de-0cfc644ac7d7
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
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
