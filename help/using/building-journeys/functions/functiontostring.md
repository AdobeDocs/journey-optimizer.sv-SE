---
product: adobe campaign
title: toString
description: Läs mer om funktionen toString
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 23f4e8224ea5b00e8132b6a3f3e32f73b0cc993f
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 6%

---

# toString {#toString}

Konverterar ett argumentvärde till ett strängvärde, beroende på dess typ. Mer information om datatyper finns i [den här sidan](../expression/data-types.md).

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
| tidszon | konvertera till strängrepresentation av tidszon-id (JODA-id) |
| heltal | konverterar till strängbeteckning för värdet (1 blir &quot;1&quot;) |
| decimal | konverterar till strängbeteckning för värdet (1.5 blir &quot;1.5&quot;) |
| boolesk | konvertera det booleska värdet till true om true, false om false |

## Underskrifter och returtyp

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<timeZone>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

Returnera en sträng.

## Exempel

`toString(4)`

Returnerar &quot;4&quot;.
