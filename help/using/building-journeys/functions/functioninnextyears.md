---
product: journey optimizer
title: inNextYears
description: Läs om funktionen iNextYears
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e4597772-d53c-4e15-8237-b2460ce31170
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 15%

---

# inNextYears {#inNextYears}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu + delta-år.

## Kategori

Datum

## Funktionssyntax

`inNextYears(<dateTime>,<delta>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

## Underskrifter och returtyp

`inNextYears(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

## Exempel

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4)`

Returnerar true.
