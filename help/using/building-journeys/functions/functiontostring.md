---
product: journey optimizer
title: toString
description: Läs mer om funktionen toString
feature: Journeys
role: Developer
level: Experienced
keywords: toString, funktion, uttryck, resa
exl-id: 06727146-2a44-4b74-aac4-be60e9e0e37c
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 3%

---

# toString {#toString}

Konverterar ett argumentvärde till ett strängvärde, beroende på dess typ. Mer information om datatyper finns på [den här sidan](../expression/data-types.md).

## Kategori

Konvertering

## Funktionssyntax

`toString(<parameter>)`

## Parametrar

| Parameter | Beskrivning |
|--- |--- |
| dateTime | konverterar datumet i UTC-datumformat |
| dateTimeOnly | konverterar datumet i UTC-datumformat |
| varaktighet | konvertera till motsvarande antal millisekunder som en sträng |
| heltal | konverterar till strängbeteckning för värdet (1 blir &quot;1&quot;) |
| decimal | konverterar till strängbeteckning för värdet (1.5 blir &quot;1.5&quot;) |
| boolesk | konvertera det booleska värdet till true om true, false om false |

## Underskrifter och returtyp

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

Returnera en sträng.

## Exempel

`toString(4)`

Returnerar &quot;4&quot;.

`toString(#{ExperiencePlatform.test_date.person.birthDate}))`

Returnerar strängbeteckningen för angivet dateOnly-fält (XDM-datumfält), till exempel &quot;2023-08-18&quot;.

`toString(toDuration(1520))`

Returnerar &quot;PT1.52S&quot;.
