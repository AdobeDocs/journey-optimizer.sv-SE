---
product: journey optimizer
title: toDecimal
description: Läs mer om funktionen toDecimal
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: decimal, funktion, uttryck, resa
exl-id: d761fa4d-5f99-4dee-b747-3eab464c4071
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 6%

---

# toDecimal {#toDecimal}

Konverterar ett argumentvärde till ett decimalvärde, beroende på dess typ.

## Kategori

Konvertering

## Funktionssyntax

`toDecimal(<parameter>)`

## Parametrar

| Parameter | Beskrivning |
|--- |--- |
| string | konverterar strängvärdet som ett decimaltal |
| dateTime | konverterar datumet som antal millisekunder (epok millisekunder) |
| boolesk | konverterar det booleska värdet till 1 om true, 0 om false |
| heltal | konverterar till ett decimaltal (exempel.: 1 blir 1.0) |

## Underskrifter och returnerade typer

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

Returnera ett decimaltal.

## Exempel

`toDecimal("4.0")`

Returnerar 4.0.
