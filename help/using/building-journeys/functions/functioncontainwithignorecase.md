---
product: journey optimizer
title: containIgnoreCase
description: Läs mer om funktionen containIgnoreCase
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: containIgnoreCase, function, expression, travel
exl-id: 26074584-a215-4515-8a61-7460bd9d4447
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 7%

---

# containIgnoreCase {#containIgnoreCase}

Kontrollerar om den andra argumentsträngen finns i den första argumentsträngen, utan att ta hänsyn till skiftläget.

## Kategori

Sträng

## Funktionssyntax

`containIgnoreCase(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| string | string |
| sträng genomsöktes | string |

## Signatur och returtyp

`containIgnoreCase(<string>,<string>)`

Returnerar ett booleskt värde.

## Exempel

`containIgnoreCase("rowing is great", "GREAT")`

Returnerar true.
