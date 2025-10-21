---
product: journey optimizer
title: startWithIgnoreCase
description: Läs mer om funktionen startWithIgnoreCase
feature: Journeys
role: Developer
level: Experienced
keywords: startWithIgnoreCase, funktion, uttryck, resa
exl-id: b6bd9f77-272f-4c2b-b085-20ab5f043793
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
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
