---
product: journey optimizer
title: toInteger
description: Läs mer om funktionen toInteger
feature: Journeys
role: Developer
level: Experienced
keywords: toInteger, funktion, uttryck, resa
exl-id: 901a91d1-13dd-4283-b87f-223196eb072f
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 6%

---

# toInteger {#toInteger}

Konverterar ett argumentvärde till ett heltal.

## Kategori

Konvertering

## Funktionssyntax

`toInteger(<parameter>)`

## Parametrar

| Parameter | Beskrivning |
|--- |--- |
| string | konverterar strängvärdet som ett heltal |
| dateTime | konverterar datumet som antal millisekunder (epok millisekunder) |
| decimal | konverterar till heltal genom att ta bort decimaldelen (exempel: 1,5 blir 1) |
| boolesk | konverterar det booleska värdet till 1 om true, 0 om false |

## Underskrifter och returtyp

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

Returnera ett heltal.

## Exempel

`toInteger("4")`

Returnerar 4.
