---
product: adobe campaign
title: concat
description: Lär dig mer om funktionssammanfogningen
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 23f4e8224ea5b00e8132b6a3f3e32f73b0cc993f
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 20%

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
