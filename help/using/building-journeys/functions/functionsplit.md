---
product: journey optimizer
title: dela
description: Lär dig mer om funktionsdelningen
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 37bcdf98-203c-4f82-8d8a-be2b2c45c4e7
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 11%

---

# dela {#split}

Delar den första argumentsträngen med en avgränsningssträng (den andra argumentsträngen, som kan vara ett reguljärt uttryck) för att skapa en lista med strängar (tokens).

## Kategori

Sträng

## Funktionssyntax

`split(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| indatasträng | string |
| avgränsarsträng | string |

## Underskrifter och returtyp

`split(<input string>, <separator string>)`

Returnerar en listString.

## Exempel

`split(["A_B_C"], "_")`

Returnerar `["A","B","C"]`

Exempel med ett händelsefält &#39;event.appVersion&#39; med värdet: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Returnerar `["20", "45", "2", "3434"]`
