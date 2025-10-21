---
product: journey optimizer
title: startWithIgnoreCase
description: Läs mer om funktionen startWithIgnoreCase
feature: Journeys
role: Engineer
level: Experienced
keywords: startWithIgnoreCase, funktion, uttryck, resa
exl-id: b6bd9f77-272f-4c2b-b085-20ab5f043793
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 8%

---

# startWithIgnoreCase {#startWithIgnoreCase}

Returnerar true om den andra parametern är ett prefix till den första utan att ta hänsyn till skiftläge.

## Kategori

Sträng

## Funktionssyntax

`startWithIgnoreCase(<parameters>)`

## Parametrar

| Parameter | Typ |
|-------------|--------|
| string | string |
| prefix | string |

## Signatur och returtyp

`startWithIgnoreCase(<string>,<string>)`

Returnera ett booleskt värde.

## Exempel

`startWithIgnoreCase("rowing is great", "RO")`

Returnerar true.
