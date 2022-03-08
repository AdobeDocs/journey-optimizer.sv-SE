---
product: adobe campaign
title: containIgnoreCase
description: Läs mer om funktionen containIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 26074584-a215-4515-8a61-7460bd9d4447
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 14%

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
