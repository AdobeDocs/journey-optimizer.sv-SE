---
title: Funktionsbibliotek för datum och tid
description: Funktionsbibliotek för datum och tid
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: edc040de-dfb3-4ebc-91b4-239e10c2260b
source-git-commit: f4068450dde5f85652096c09e7f817dbab40a3d8
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 4%

---

# Funktioner för datum och tid{#date-time}

Datum- och tidsfunktioner används för att utföra datum- och tidsåtgärder på värden inom Journey Optimizer.

## Ålder{#age}

The `age` används för att hämta åldern från ett visst datum.

**Syntax**

```sql
 {%= age(datetime) %}
```

<!--
**Example**

The following operation gets the value of the identity map for the key `example@example.com`.

```sql
 {%= age(datetime) %}
```
-->

## Aktuell tid i millisekunder{#current-time}

The `currentTimeInMillis` används för att hämta aktuell tid i epok millisekunder.

**Syntax**

```sql
{%= currentTimeInMillis() %}
```

<!--
**Example**

The following operation gets all the keys for the map `identityMap`.

```sql
{%= keys(identityMap) %}
```
-->

## Datumdifferens{#date-diff}

The `dateDiff` -funktionen används för att hämta skillnaden mellan två datum i antal dagar.

**Syntax**

```sql
{%= dateDiff(datetime,datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->


## Veckodag{#day-week}

The `dayOfWeek` används för att hämta veckodag.

**Syntax**

```sql
{%= dayOfWeek(datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

## Dag på året{#day-year}

The `dayOfYear` -funktionen används för att hämta dagen på året.

**Syntax**

```sql
{%= dayOfYear(datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

## Formateringsdatum{#format-date}

The `formatDate` -funktionen används för att formatera ett datum/tid-värde. Formatet ska vara ett giltigt Java DateTimeFormat-mönster.

**Syntax**

```sql
{%= formatDate(datetime, format) %}
```

Där den första strängen är datumattributet och det andra värdet är hur du vill att datumet ska konverteras och visas.

>[!NOTE]
>
> Om ett datummönster är ogiltigt återgår datumet till ISO-standardformat.
>
> Du kan använda Java-datumformateringsfunktioner enligt sammanfattningen i [Oraclets dokumentation](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html){_blank}

**Exempel**

Följande åtgärd returnerar datumet i följande format: MM/DD/YY.

```sql
{%= formatDate(profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate, "MM/DD/YY") %}
```

## Ange dagar{#set-days}

The `setDays` -funktionen används för att ange dag i månaden för angivet datum/tid.

**Syntax**

```sql
{%= setDays(datetime, day) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

## Ange timmar{#set-hours}

The `setHours` -funktionen används för att ställa in timmen för datum-tid.

**Syntax**

```sql
{%= setHours(datetime, hour) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->


## Till UTC{#to-utc}

The `toUTC` används för att konvertera en datetime till UTC.


**Syntax**

```sql
{%= toUTC(datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->


## Vecka på året UTC{#week-of-year}

The `weekOfYear` används för att hämta årets vecka.

**Syntax**

```sql
{%= weekOfYear(datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->