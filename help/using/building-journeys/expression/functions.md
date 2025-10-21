---
solution: Journey Optimizer
product: journey optimizer
title: Funktioner
description: Läs om funktioner
feature: Journeys
role: Engineer
level: Experienced
keywords: funktion, uttryck, redigerare, resa
exl-id: 5b978eef-7d3e-41fe-bb08-0cf37c3b125d
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 31%

---

# Funktioner {#functions}

En funktion kan ha olika signaturer (en annan uppsättning ordnade parametrar). En funktionssignatur kan ha 0-N-uttryck som ordnade parametrar.

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ..., `<expression as param N>`)

Varje funktion har en specifik returtyp.

Här är en lista över funktioner som stöds.

## Huvudfunktioner

| Kategori | Funktion |
|-------------|-----------------------|
| Adobe Experience Platform | [inAudience](../functions/functioninaudience.md) |
| Aggregering | [avg](../functions/functionavg.md) |
| Aggregering | [count](../functions/functioncount.md) |
| Aggregering | [countOnlyNull](../functions/functioncountonlynull.md) |
| Aggregering | [countWithNull](../functions/functioncountwithnull.md) |
| Aggregering | [distinctCount](../functions/functiondistinctcount.md) |
| Aggregering | [distinctCountWithNull](../functions/functiondistinctcountwithnull.md) |
| Aggregering | [max](../functions/functionmax.md) |
| Aggregering | [min](../functions/functionmin.md) |
| Aggregering | [sum](../functions/functionsum.md) |
| Konvertering | [toBool](../functions/functiontobool.md) |
| Konvertering | [toDateOnly](../functions/functiontodateonly.md) |
| Konvertering | [toDateTime](../functions/functiontodatetime.md) |
| Konvertering | [toDateTimeOnly](../functions/functiontodatetimeonly.md) |
| Konvertering | [toDecimal](../functions/functiontodecimal.md) |
| Konvertering | [toDuration](../functions/functiontoduration.md) |
| Konvertering | [toInteger](../functions/functiontointeger.md) |
| Konvertering | [toString](../functions/functiontostring.md) |
| Datum | [currentTimeInMillis](../functions/functioncurrenttimeinmillis.md) |
| Datum | [inLastDays](../functions/functioninlastdays.md) |
| Datum | [inLastHours](../functions/functioninlasthours.md) |
| Datum | [inLastMonths](../functions/functioninlastmonths.md) |
| Datum | [inLastYears](../functions/functioninlastyears.md) |
| Datum | [inNextDays](../functions/functioninnextdays.md) |
| Datum | [inNextHours](../functions/functioninnexthours.md) |
| Datum | [inNextMonths](../functions/functioninnextmonths.md) |
| Datum | [inNextYears](../functions/functioninnextyears.md) |
| Datum | [now](../functions/functionnow.md) |
| Datum | [nowWithDelta](../functions/functionnowwithdelta.md) |
| Datum | [setHours](../functions/functionsethours.md) |
| Datum | [setDays](../functions/functionsetdays.md) |
| Datum | [updateTimeZone](../functions/functionupdatetimezone.md) |
| Lista | [distinct](../functions/functiondistinct.md) |
| Lista | [distinctWithNull](../functions/functiondistinctwithnull.md) |
| Lista | [filter](../functions/functionfilter.md) |
| Lista | [getListItem](../functions/functiongetlistitem.md) |
| Lista | [in](../functions/functionin.md) |
| Lista | [överlappa](../functions/functionintersect.md) |
| Lista | [gräns](../functions/functionlimit.md) |
| Lista | [listSize](../functions/functionlistsize.md) |
| Lista | [serializeList](../functions/functionserializelist.md) |
| Lista | [sort](../functions/functionsort.md) |
| Matematik | [random](../functions/functionrandom.md) |
| Matematik | [round](../functions/functionround.md) |
| Sträng | [concat](../functions/functionconcat.md) |
| Sträng | [contain](../functions/functioncontain.md) |
| Sträng | [containIgnoreCase](../functions/functioncontainwithignorecase.md) |
| Sträng | [endWith](../functions/functionendwith.md) |
| Sträng | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| Sträng | [equalIgnoreCase](../functions/functionequalignorecase.md) |
| Sträng | [indexOf](../functions/functionindexof.md) |
| Sträng | [isEmpty](../functions/functionisempty.md) |
| Sträng | [isNotEmpty](../functions/functionisnotempty.md) |
| Sträng | [lastIndexOf](../functions/functionlastindexof.md) |
| Sträng | [length](../functions/functionlength.md) |
| Sträng | [lower](../functions/functionlower.md) |
| Sträng | [matchRegExp](../functions/functionmatchregexp.md) |
| Sträng | [notEqualIgnoreCase](../functions/functionnotequalignorecase.md) |
| Sträng | [replace](../functions/functionreplace.md) |
| Sträng | [replaceAll](../functions/functionreplaceall.md) |
| Sträng | [split](../functions/functionsplit.md) |
| Sträng | [startWith](../functions/functionstartwith.md) |
| Sträng | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| Sträng | [substr](../functions/functionsubstr.md) |
| Sträng | [trim](../functions/functiontrim.md) |
| Sträng | [upper](../functions/functionupper.md) |
| Sträng | [uuid](../functions/functionuuid.md) |
