---
product: journey optimizer
title: setDays
description: Läs mer om funktionen setDays
feature: Journeys
role: Developer
level: Experienced
keywords: setDays, function, expression, travel
exl-id: c2757e41-8206-44f7-9dbb-1fa79c0ba6e6
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 6%

---

# setDays {#setDays}

Anger endast dag för datum och tid. Om du t.ex. vill vänta till en viss dag i månaden kan du tvinga fram dagen.

## Kategori

Datum

## Funktionssyntax

`setDays(<parameter>)`

## Parametrar

| Parameter | Typ |
|--- |--- |
| tid | dateTime |
| datum tid utan att överväga tidszon | dateTimeOnly |
| dagar | heltal |

## Underskrifter och returtyp

`setDays(<dateTime>,<days>)`

Returnerar en datetime.

`setDays(<dateTimeOnly>,<days>)`

Returnerar en datetime utan att ta hänsyn till tidszon.

## Exempel

`setDays(toDateTime('2023-12-12T01:11:00Z'), 25)`

Returnerar 2023-12-25T01:11:00Z.

`setDays(toDateTimeOnly(@event{MyEvent.registrationDate}), 1)`
