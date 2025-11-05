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
source-git-commit: 42abfcc9711d87b2dc00df47e964dad07443f0ed
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
| Datum | [currentTimeInMillis](../functions/date-functions.md#currentTimeInMillis) |
| Datum | [inLastDays](../functions/date-functions.md#inLastDays) |
| Datum | [inLastHours](../functions/date-functions.md#inLastHours) |
| Datum | [inLastMonths](../functions/date-functions.md#inLastMonths) |
| Datum | [inLastYears](../functions/date-functions.md#inLastYears) |
| Datum | [inNextDays](../functions/date-functions.md#inNextDays) |
| Datum | [inNextHours](../functions/date-functions.md#inNextHours) |
| Datum | [inNextMonths](../functions/date-functions.md#inNextMonths) |
| Datum | [inNextYears](../functions/date-functions.md#inNextYears) |
| Datum | [now](../functions/date-functions.md#now) |
| Datum | [nowWithDelta](../functions/date-functions.md#nowWithDelta) |
| Datum | [setHours](../functions/date-functions.md#setHours) |
| Datum | [setDays](../functions/date-functions.md#setDays) |
| Datum | [updateTimeZone](../functions/date-functions.md#updateTimeZone) |
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
