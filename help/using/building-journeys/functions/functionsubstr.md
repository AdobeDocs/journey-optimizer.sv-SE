---
product: journey optimizer
title: substr
description: Läs mer om funktionssubstr
feature: Journeys
role: Developer
level: Experienced
keywords: substr, funktion, uttryck, resa
exl-id: 58a3107a-b4f3-43da-b454-5ce597515847
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 4%

---

# substr {#substr}

Returnerar delsträngen för stränguttrycket mellan startindexvärdet och slutindexvärdet. Om slutindexvärdet inte är definierat ligger det mellan startindexet och slutet.

## Kategori

Sträng

## Funktionssyntax

`substr(<parameters>)`

## Parametrar

| Parameter | type |
|-------------|----------|
| string | string |
| beginIndex | heltal |
| endIndex | heltal |

## Signatur och returtyp

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

Returnera en sträng.

## Exempel

`substr("Hello World",6)`

Returnerar &quot;World&quot;.

`substr("Hello World", 0, 5)`

Returnerar &quot;Hello&quot;.
