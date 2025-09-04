---
product: journey optimizer
title: toBool
description: Läs mer om funktionen toBool
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: verktyg, funktion, uttryck, resa
exl-id: 0bb68d05-bb90-48b7-aff3-82ab15d55ebe
version: Journey Orchestration
source-git-commit: 62783c5731a8b78a8171fdadb1da8a680d249efd
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 5%

---

# toBool {#toBool}

Konverterar ett argumentvärde till ett booleskt värde, beroende på dess typ.

* Från sträng: försök att konvertera strängvärdet som booleskt, från &quot;true&quot; om strängvärdet är &quot;true&quot;, annars false
* Från numeriskt: true om det numeriska värdet inte är lika med 0, annars false

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
