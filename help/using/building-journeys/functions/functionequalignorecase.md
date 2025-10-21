---
product: journey optimizer
title: equalIgnoreCase
description: Läs mer om funktionen equalIgnoreCase
feature: Journeys
role: Developer
level: Experienced
keywords: equalIgnoreCase, funktion, uttryck, resa
exl-id: b74ef5c9-0202-4a69-8870-77004a4397e0
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 7%

---

# equalIgnoreCase {#equalIgnoreCase}

Jämför den första argumentsträngen med den andra argumentsträngen och ignorerar skiftlägeskänsliga värden.

## Kategori

Sträng

## Funktionssyntax

`equalIgnoreCase(<parameters>)`

## Parametrar

* string

## Signatur och returtyp

`equalIgnoreCase(<string>,<string>)`

Returnerar ett booleskt värde.

## Exempel

`equalIgnoreCase("rowing is great", "rowing is GREAT")`

Returnerar true.
