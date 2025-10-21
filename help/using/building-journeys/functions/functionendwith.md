---
product: journey optimizer
title: endWith
description: Läs mer om funktionen endWith
feature: Journeys
role: Developer
level: Experienced
keywords: endWith, function, expression, travel
exl-id: ae54c127-9de2-42fd-942c-664d2cfe66d2
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 8%

---

# endWith {#endWith}

Returnerar true om den andra parametern är ett suffix till den första.

## Kategori

Sträng

## Funktionssyntax

`endWith(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| string | string |
| suffix | string |

## Signatur och returtyp

`endWith(<string>,<string>)`

Returnerar ett booleskt värde.

## Exempel

`endWith("Hello World", "World")`

Returnerar true.

`endWith("Hello World", "Hello")`

Returnerar false.
