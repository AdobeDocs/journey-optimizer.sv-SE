---
product: journey optimizer
title: toDuration
description: Läs mer om funktionen toDuration
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: toVaraktighet, funktion, uttryck, resa
exl-id: c78e30c5-99ee-4dc7-a03a-17f7ee65f83a
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 1%

---

# toDuration {#toDuration}

Konverterar ett argumentvärde till en längd. Mer information om datatyper finns på [den här sidan](../expression/data-types.md).

## Kategori

Konvertering

## Funktionssyntax

`toDuration(<parameter>)`

## Parametrar

| Parameter | Beskrivning |
|--- |--- |
| string | format som bygger på ISO-8601-varaktighetsformatet PnDTnHnMn.nS med dagar som anses vara exakt 24 timmar |
| heltal | antal millisekunder |

Om stränguttryck: godkända format baseras på varaktighetsformatet PnDTnHnMn.nS för ISO-8601 med dagar som anses vara exakt 24 timmar.

Strängen börjar med ett valfritt tecken som anges med ASCII-tecknet för negativ eller positiv symbol. Om värdet är negativt negeras hela perioden. ASCII-bokstaven&quot;P&quot; står bredvid med versaler eller gemener. Därefter finns det fyra avsnitt som består av ett tal och ett suffix. Avsnitten har suffix i ASCII av &quot;D&quot;, &quot;H&quot;, &quot;M&quot; och &quot;S&quot; för dagar, timmar, minuter och sekunder, vilka accepteras med versaler eller gemener. Suffixen måste finnas i ordning. ASCII-bokstaven &quot;T&quot; måste inträffa före den första förekomsten av en timme, minut eller sekund. Minst en av de fyra avsnitten måste finnas, och om T förekommer måste det finnas minst en sektion efter T. Nummerdelen av varje avsnitt måste bestå av en eller flera ASCII-siffror. Talet kan föregås av ASCII-negativa eller positiva symboler. Antalet dagar, timmar och minuter måste tolkas. Antalet sekunder måste tolkas tillsammans med den valfria fraktionen. Decimaltecknet kan vara antingen en punkt eller ett komma. Den bråkdelar kan innehålla mellan noll och nio siffror.

## Underskrifter och returtyp

`toDuration(<string>)`

`toDuration(<integer>)`

Returnerar en varaktighet.

## Exempel

`toDuration("PT10H")`

Returnerar längden 10 timmar.

`toDuration("PT4S")`

Returnerar längden på 4s.

`toDuration(4000)`

Returnerar längden på 4s.
