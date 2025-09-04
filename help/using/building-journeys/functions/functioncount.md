---
product: journey optimizer
title: count
description: Läs mer om antalet funktioner
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: antal, funktion, uttryck, resa
exl-id: 6980c1ec-3afd-4fc9-ae10-76bcf7364a04
version: Journey Orchestration
source-git-commit: 62783c5731a8b78a8171fdadb1da8a680d249efd
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 5%

---

# count {#count}

Räknar elementen i listan utan att ta hänsyn till null-värden.

## Kategori

Aggregering

## Funktionssyntax

`count(<listAny>)`

`count(<listObject>)`

## Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly eller listObject | Lista som ska bearbetas. För listObject måste det vara en fältreferens. Ett listObject får inte innehålla null-objekt. |

## Underskrifter och returtyp

`count(<listAny>)`

Returnerar ett heltal.

## Exempel

`count([10,2,10,null])`

Returnerar 3.

`count(@event{my_event.productListItems})`

Returnerar antalet objekt i den angivna arrayen med objekt (typen listObject). Obs! Ett listObject får inte innehålla ett null-objekt
