---
product: adobe campaign
title: toString
description: Läs mer om funktionen toString
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 06727146-2a44-4b74-aac4-be60e9e0e37c
source-git-commit: cca94d15da5473aa9890c67af7971f2e745d261e
workflow-type: tm+mt
source-wordcount: '116'
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

Returnerar strängbeteckningen för angivet dateOnly-fält (XDM-datumfält), till exempel &quot;2016-08-18&quot;.
