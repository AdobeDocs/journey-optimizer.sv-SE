---
product: journey optimizer
title: updateTimeZone
description: Läs mer om funktionen updateTimeZone
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: updateTimeZone, funktion, uttryck, resa
exl-id: 1bf4662e-55d0-4631-af93-1430ec7ed7e2
source-git-commit: 4e7c4e7e6fcf488f572ccf3e9037e597dde06510
workflow-type: tm+mt
source-wordcount: '62'
ht-degree: 6%

---

# updateTimeZone {#updateTimeZone}

Returnerar en ny datumtid, med en ny tidszon på samma gång.

## Kategori

Datum

## Funktionssyntax

`updateTimeZone(<parameters>)`

## Parametrar

* tidszon-id: sträng
* dateTime

## Signatur och returtyp

`updateTimeZone(<dateTime>,<timeZone id>)`

Returnerar en datetime.

## Exempel

`updateTimeZone( toDateTime("2023-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

Returnerar 2023-08-28T17:15:30.123+02:00.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`
Returns "2019-08-28T17:15:30.123+02:00".-->

`updateTimeZone(@event{MyExpEvent.timestamp}, "Australia/Sydney")`

Om tidsstämpelfältets värde är `2021-11-16T16:55:12.939318+01:00` returnerar funktionen `2021-11-17T02:55:12.942115+11:00`.
