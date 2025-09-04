---
product: journey optimizer
title: isNotEmpty
description: Läs mer om funktionen isNotEmpty
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: isNotEmpty, funktion, uttryck, resa
exl-id: 654d0e3d-10d9-4a40-b9be-7979c08e0e97
version: Journey Orchestration
source-git-commit: 62783c5731a8b78a8171fdadb1da8a680d249efd
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 7%

---

# isNotEmpty {#isNotEmpty}

Returnerar true om strängen i parametern inte är tom.

## Kategori

Sträng

## Funktionssyntax

`isNotEmpty(<parameters>)`

## Parametrar

* string

## Signatur och returtyp

`isNotEmpty(<string>)`

Returnerar ett booleskt värde.

## Exempel

`isNotEmpty("")`

Returnerar false.

`isNotEmpty("hello")`

Returnerar true.
