---
product: journey optimizer
title: getListItem
description: Läs mer om funktionen gstListItem
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: getListItem, funktion, uttryck, resa
exl-id: e995f479-bbaa-45f3-9531-e05680c5a723
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 15%

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

`split(@{event.appVersion}, "\\.")`

Returnerar `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

Returnerar &quot;20&quot;
