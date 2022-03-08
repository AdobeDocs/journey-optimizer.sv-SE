---
product: adobe campaign
title: startWithIgnoreCase
description: Läs mer om funktionen startWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b6bd9f77-272f-4c2b-b085-20ab5f043793
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 15%

---

# startWithIgnoreCase {#startWithIgnoreCase}

Returnerar true om den andra parametern är ett prefix till den första utan att ta hänsyn till skiftläge.

## Kategori

Sträng

## Funktionssyntax

`startWithIgnoreCase(<parameters>)`

## Parametrar

| Parameter | Typ |
|-------------|--------|
| string | string |
| prefix | string |

## Signatur och returtyp

`startWithIgnoreCase(<string>,<string>)`

Returnera ett booleskt värde.

## Exempel

`startWithIgnoreCase("rowing is great", "RO")`

Returnerar true.
