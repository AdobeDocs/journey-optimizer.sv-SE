---
solution: Journey Optimizer
product: journey optimizer
title: Funktioner
description: Läs om funktioner
feature: Journeys
role: Developer
level: Experienced
keywords: funktion, uttryck, redigerare, resa
exl-id: 5b978eef-7d3e-41fe-bb08-0cf37c3b125d
version: Journey Orchestration
source-git-commit: 7d75abf6b428becc8b535a63421e85cca417daac
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
| Aggregering | [avg](../functions/aggregation-functions.md#avg) |
| Aggregering | [count](../functions/aggregation-functions.md#count) |
| Aggregering | [countOnlyNull](../functions/aggregation-functions.md#countOnlyNull) |
| Aggregering | [countWithNull](../functions/aggregation-functions.md#countWithNull) |
| Aggregering | [distinctCount](../functions/aggregation-functions.md#distinctCount) |
| Aggregering | [distinctCountWithNull](../functions/aggregation-functions.md#distinctCountWithNull) |
| Aggregering | [max](../functions/aggregation-functions.md#max) |
| Aggregering | [min](../functions/aggregation-functions.md#min) |
| Aggregering | [sum](../functions/aggregation-functions.md#sum) |
| Konvertering | [toBool](../functions/conversion-functions.md#toBool) |
| Konvertering | [toDateOnly](../functions/conversion-functions.md#toDateOnly) |
| Konvertering | [toDateTime](../functions/conversion-functions.md#toDateTime) |
| Konvertering | [toDateTimeOnly](../functions/conversion-functions.md#toDateTimeOnly) |
| Konvertering | [toDecimal](../functions/conversion-functions.md#toDecimal) |
| Konvertering | [toDuration](../functions/conversion-functions.md#toDuration) |
| Konvertering | [toInteger](../functions/conversion-functions.md#toInteger) |
| Konvertering | [toString](../functions/conversion-functions.md#toString) |
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
