---
product: adobe campaign
title: toDateTimeOnly
description: Läs mer om funktionen toDateTime
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: db54c119-5080-403a-b254-43645be6b4a8
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 12%

---

# toDateTimeOnly{#toDateTimeOnly}

Konverterar ett argumentvärde till ett värde för endast datum och tid.

## Kategori

Konvertering

## Funktionssyntax

`toDateTimeOnly(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| datumtid i ISO-8601- eller &quot;YYY-MM-DD&quot;-format (XDM-datumformat) | string |
| tid | dateTime |

## Underskrifter och returnerade typer

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

Returnera en datetime utan att överväga tidszon.

## Exempel

`toDateTimeOnly ("2016-08-18")`

returnerar ett dateTime som representerar 2016-08-18T00:00:00,000

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->