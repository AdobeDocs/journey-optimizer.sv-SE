---
product: adobe campaign
title: substr
description: Läs mer om funktionssubstr
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 58a3107a-b4f3-43da-b454-5ce597515847
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 9%

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
