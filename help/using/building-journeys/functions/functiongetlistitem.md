---
product: adobe campaign
title: getListItem
description: Läs mer om funktionen gstListItem
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: d786f3d42515d65a6574f51b6cff4b85063a0126
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 16%

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
| lista | listString |
| lista | listBoolean |
| lista | listInteger |
| lista | listDecimal |
| lista | listDuration |
| lista | listDateTime |
| lista | listDateTimeOnly |
| lista | listDateOnly |
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
