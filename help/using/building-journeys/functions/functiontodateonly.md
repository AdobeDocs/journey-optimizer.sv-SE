---
product: adobe campaign
title: toDateOnly
description: Läs mer om funktionen toDateOnly
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 23f4e8224ea5b00e8132b6a3f3e32f73b0cc993f
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 13%

---

# toDateOnly{#toDateOnly}

Konverterar ett argumentvärde till ett värde för endast datum.

## Kategori

Konvertering

## Funktionssyntax

`toDateOnly(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| datum i ISO-8601- eller &quot;YYY-MM-DD&quot;-format (XDM-datumformat) | string |
| datum | datum |

## Underskrifter och returnerade typer

`toDateOnly(<date>)`

`toDateOnly(<string>)`

Returnera en datetime utan att överväga tidszon.

## Exempel

`toDateOnly("2016-08-18")`

returnerar ett dateOnly-objekt som representerar 2016-08-18.
