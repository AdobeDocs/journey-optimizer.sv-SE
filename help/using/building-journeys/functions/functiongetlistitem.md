---
product: journey optimizer
title: getListItem
description: Läs mer om funktionen gstListItem
feature: Journeys
role: Engineer
level: Experienced
keywords: getListItem, funktion, uttryck, resa
exl-id: e995f479-bbaa-45f3-9531-e05680c5a723
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 12%

---

# getListItem {#gestListItem}

Returnerar objektet i listan vid det angivna indexvärdet.

## Kategori

Lista

## Funktionssyntax

`getListItem(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| list | listString |
| list | listBoolean |
| list | listInteger |
| list | listDecimal |
| list | listDuration |
| list | listDateTime |
| list | listDateTimeOnly |
| list | listDateOnly |
| index | heltal |

## Underskrifter och returtyp

`getListItem(<listInteger>,<index>)`

Returnerar ett heltal.

`getListItem(<listDecimal>,<index>)`

Returnerar ett decimaltal.

`getListItem(<listString>,<index>)`

Returnerar en sträng.

`getListItem(<listDateTimeOnly>,<index>)`

Returnerar en datetime utan att ta hänsyn till tidszon.

`getListItem(<listDateTime>,<index>)`

Returnerar en datetime.

`getListItem(<listDateOnly>,<index>)`

Returnerar en lista med datum.

`getListItem(<listBoolean>,<index>)`

Returnerar ett booleskt värde.

`getListItem(<listDuration>,<index>)`

Returnerar en varaktighet.

## Exempel

`getListItem([10, 2, 3], 1)`

Returnerar &quot;2&quot;

`getListItem(["A", "B", "C"], 2)`
Returnerar &quot;C&quot;

Exempel med ett händelsefält &#39;event.appVersion&#39; med värdet: &quot;20.45.2.3434&quot;

`split(@event{event.appVersion}, "\\.")`

Returnerar `["20", "45", "2", "3434"]`

`getListItem(split(@event{event.appVersion}, "\\."), 0)`

Returnerar &quot;20&quot;
