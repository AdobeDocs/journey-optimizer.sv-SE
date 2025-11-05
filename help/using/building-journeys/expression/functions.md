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
source-git-commit: d58319d687d113ce680c415524fdea0400cb38f0
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
| Lista | [distinct](../functions/list-functions.md#distinct) |
| Lista | [distinctWithNull](../functions/list-functions.md#distinctWithNull) |
| Lista | [filter](../functions/list-functions.md#filter) |
| Lista | [getListItem](../functions/list-functions.md#getListItem) |
| Lista | [in](../functions/list-functions.md#in) |
| Lista | [överlappa](../functions/list-functions.md#intersect) |
| Lista | [gräns](../functions/list-functions.md#limit) |
| Lista | [listSize](../functions/list-functions.md#listSize) |
| Lista | [serializeList](../functions/list-functions.md#serializeList) |
| Lista | [sort](../functions/list-functions.md#sort) |
| Matematik | [random](../functions/functionrandom.md) |
| Matematik | [round](../functions/functionround.md) |
| Sträng | [concat](../functions/string-functions.md#concat) |
| Sträng | [contain](../functions/string-functions.md#contain) |
| Sträng | [containIgnoreCase](../functions/string-functions.md#containIgnoreCase) |
| Sträng | [endWith](../functions/string-functions.md#endWith) |
| Sträng | [endWithIgnoreCase](../functions/string-functions.md#endWithIgnoreCase) |
| Sträng | [equalIgnoreCase](../functions/string-functions.md#equalIgnoreCase) |
| Sträng | [indexOf](../functions/string-functions.md#indexOf) |
| Sträng | [isEmpty](../functions/string-functions.md#isEmpty) |
| Sträng | [isNotEmpty](../functions/string-functions.md#isNotEmpty) |
| Sträng | [lastIndexOf](../functions/string-functions.md#lastIndexOf) |
| Sträng | [length](../functions/string-functions.md#length) |
| Sträng | [lower](../functions/string-functions.md#lower) |
| Sträng | [matchRegExp](../functions/string-functions.md#matchRegExp) |
| Sträng | [notEqualIgnoreCase](../functions/string-functions.md#notEqualIgnoreCase) |
| Sträng | [replace](../functions/string-functions.md#replace) |
| Sträng | [replaceAll](../functions/string-functions.md#replaceAll) |
| Sträng | [split](../functions/string-functions.md#split) |
| Sträng | [startWith](../functions/string-functions.md#startWith) |
| Sträng | [startWithIgnoreCase](../functions/string-functions.md#startWithIgnoreCase) |
| Sträng | [substr](../functions/string-functions.md#substr) |
| Sträng | [trim](../functions/string-functions.md#trim) |
| Sträng | [upper](../functions/string-functions.md#upper) |
| Sträng | [uuid](../functions/string-functions.md#uuid) |
