---
product: journey optimizer
title: setHours
description: Läs mer om funktionen setHours
feature: Journeys
role: Engineer
level: Experienced
keywords: setHours, function, expression, travel
exl-id: ed78c2a9-d83a-4fac-a2e9-7383da131a1f
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 4%

---

# setHours {#setHours}

Anger endast timmar för datum och tid. Om du till exempel vill vänta en viss timme i morgon kan du tvinga timmen.

## Kategori

Datum

## Funktionssyntax

`setHours(<parameter>)`

## Parametrar

| Parameter | Typ |
|--- |--- |
| tid | dateTime |
| datum tid utan att överväga tidszon | dateTimeOnly |
| timmar | heltal |

## Underskrifter och returtyp

`setHours(<dateTime>,<hours>)`

Returnerar en datetime.

`setHours(<dateTimeOnly>,<hours>)`

Returnerar en datetime utan att ta hänsyn till tidszon.

## Exempel

`setHours(toDateTime('2023-12-12T01:11:00Z'), 4)`

Returnerar 2023-12-12T04:11:00Z.

`setHours(nowWithDelta(1, "days"), 20)`

Returnerar imorgon kl. 8:XY PM, XY är minuter vid tidpunkten för den aktuella tidsutvärderingen. Om utvärderingen görs kl. 2:45 är den returnerade tiden 8:45 PM.
