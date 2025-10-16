---
product: journey optimizer
title: concat
description: Lär dig mer om funktionssammanfogningen
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: concat, function, expression, travel
exl-id: 690c8aa9-f754-4720-b4ed-a338e5d3b79d
version: Journey Orchestration
source-git-commit: 7ac246c0aa6776d3ec67223c4b07536b8ed0c881
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

---

# concat {#concat}

Sammanfogar två strängparametrar eller en lista med strängar.

## Kategori

Sträng

## Funktionssyntax

`concat(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| Lista | listString |
| string | string |

## Signatur och returtyp

`concat(<string>,<string>)`

`concat(<listString>)`

Returnerar en sträng.

## Exempel

`concat("Hello","World")`

Returnerar&quot;HelloWorld&quot;.

`concat(["Hello"," ","World"])`

Returnerar &quot;Hello World&quot;.
