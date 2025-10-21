---
product: journey optimizer
title: endWithIgnoreCase
description: Läs mer om funktionen endWithIgnoreCase
feature: Journeys
role: Developer
level: Experienced
keywords: endWithIgnoreCase, funktion, uttryck, resa
exl-id: 278ef1a4-571c-4b5f-b4de-0cfc644ac7d7
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
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
