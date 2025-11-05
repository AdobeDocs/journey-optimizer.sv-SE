---
product: journey optimizer
title: Matematiska funktioner
description: Läs om matematiska funktioner
feature: Journeys
role: Developer
level: Experienced
keywords: matematik, funktioner, uttryck, resa, beräkning, tal
version: Journey Orchestration
source-git-commit: bb47ca4957129a4d05aa3d7286409eef0cb62143
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 2%

---

# Matematiska funktioner {#math-functions}

Matematiska funktioner tillhandahåller viktiga matematiska operationer för numeriska beräkningar i dina reseuttryck. Med de här funktionerna kan du utföra exakta numeriska beräkningar och omformningar av data.

Använd matematiska funktioner när du behöver:

* Generera slumpmässiga värden för testning, sampling eller slumpgenerering ([random](#random))
* Rundade decimaltal till närmaste heltal för tydligare datapresentation ([round](#round))
* Utför matematiska beräkningar på numeriska fält
* Omvandla numeriska värden för logiska funktioner och beslutsfattande

Matematiska funktioner hanterar både decimaltyper och heltalstyper, och hanterar automatiskt typkonverteringar för att säkerställa korrekta resultat i dina reseuttryck.

## random {#random}

Genererar ett slumpmässigt tal mellan 0 och 1.

+++Syntax

`random()`

+++

+++Signatur och returtyp

`random()`

Returnerar ett decimaltal.

+++

## round {#round}

Returnerar det närmaste heltalsvärdet till argumentet med banden avrundade till positiv oändlighet.

+++Syntax

`round(<parameters>)`

+++

+++Parametrar

* decimal
* heltal

+++

+++Underskrifter och returtyp

`round(<decimal>)`

`round(<integer>)`

Returnera ett heltal.

+++

+++Exempel

`round(3.14)`

Returnerar 3.

`round(3.54)`

Returnerar 4.

`round(-3.14)`

Returnerar -3.

`round(3)`

Returnerar 3.

+++

