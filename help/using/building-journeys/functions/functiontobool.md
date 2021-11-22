---
product: adobe campaign
title: toBool
description: Läs om funktionen toBool
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 23f4e8224ea5b00e8132b6a3f3e32f73b0cc993f
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 8%

---

# toBool {#toBool}

Konverterar ett argumentvärde till ett booleskt värde, beroende på dess typ.

* Från sträng: försök att konvertera strängvärdet som booleskt, från &quot;true&quot; om strängvärdet är &quot;true&quot;, annars false
* Från numeriska: true om det numeriska värdet inte är lika med 0, annars false

## Kategori

Konvertering

## Funktionssyntax

`toBool(<parameter>)`

## Parametrar

* decimal
* boolesk
* string
* heltal

## Underskrifter och returnerade typer

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

Returnera ett booleskt värde.

## Exempel

`toBool("true")`

`toBool(1)`

Returnerar true.

`toBool("this is not a boolean")`

Returnerar false.
