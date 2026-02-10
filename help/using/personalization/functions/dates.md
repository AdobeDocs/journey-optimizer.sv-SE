---
title: Funktionsbibliotek för Date Time
description: Funktionsbibliotek för Date Time
feature: Personalization
topic: Personalization
role: Developer
level: Experienced
exl-id: edc040de-dfb3-4ebc-91b4-239e10c2260b
source-git-commit: 241af4304f0bed8f3addf28ed8e7bc746550d823
workflow-type: tm+mt
source-wordcount: '1269'
ht-degree: 3%

---

# Funktioner för datum och tid{#date-time}

Datum- och tidsfunktioner används för att utföra datum- och tidsåtgärder på värden inom Journey Optimizer.

>[!NOTE]
>
>Funktionen `now()` är inte tillgänglig i personaliseringsredigeraren. Använd `getCurrentZonedDateTime()` eller `currentTimeInMillis()` i stället för aktuella datum/tid-värden. [Läs mer](../../email/code-content.md#date-time-limitations)

## Lägg till dagar {#add-days}

Funktionen `addDays` justerar ett givet datum med ett angivet antal dagar och använder positiva värden för att öka och negativa värden för minskning.

**Syntax**

```sql
{%= addDays(date, number) %}
```

+++Exempel

* Indata: `{%= addDays(stringToDate("2024-11-01T17:19:51Z"),10) %}`
* Utdata: `2024-11-11T17:19:51Z`

+++

## Lägg till timmar {#add-hours}

Funktionen `addHours` justerar ett givet datum med ett angivet antal timmar, och använder positiva värden för att öka och negativa värden för minskning.

**Syntax**

```sql
{%= addHours(date, number) %}
```

+++Exempel

* Indata: `{%= addHours(stringToDate("2024-11-01T17:19:51Z"),1) %}`
* Utdata: `2024-11-01T18:19:51Z`

+++

## Lägg till minuter {#add-minutes}

Funktionen `addMinutes` justerar ett givet datum med ett angivet antal minuter och använder positiva värden för att öka och negativa värden för minskning.

**Syntax**

```sql
{%= addMinutes(date, number) %}
```

+++Exempel

* Indata: `{%= addMinutes(stringToDate("2024-11-01T17:59:51Z"),10) %}`
* Utdata: `2024-11-01T18:09:51Z`

+++

## Lägg till månader {#add-months}

Funktionen `addMonths` justerar ett givet datum med ett angivet antal månader och använder positiva värden för att öka och negativa värden för minskning.

**Syntax**

```sql
{%= addMonths(date, number) %}
```

+++Exempel

* Indata: `{%= addMonths(stringToDate("2024-11-01T17:19:51Z"),2) %}`
* Utdata: `2025-01-01T17:19:51Z`

+++

## Lägg till sekunder {#add-seconds}

Funktionen `addSeconds` justerar ett givet datum med ett angivet antal sekunder och använder positiva värden för att öka och negativa värden för minskning.

**Syntax**

```sql
{%= addSeconds(date, number) %}
```

+++Exempel

* Indata: `{%= addSeconds(stringToDate("2024-11-01T17:19:51Z"),10) %}`
* Utdata: `2024-11-01T17:20:01Z`

+++

## Lägg till år {#add-years}

Funktionen `addYears` justerar ett givet datum med ett angivet antal år och använder positiva värden för att öka och negativa värden för minskning.

**Syntax**

```sql
{%= addYears(date, number) %}
```

+++Exempel

* Indata: `{%= addYears(stringToDate("2024-11-01T17:19:51Z"),2) %}`
* Utdata: `2026-11-01T17:19:51Z`

+++

## Ålder{#age}

Funktionen `age` används för att hämta åldern från ett visst datum.

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

## Ålder i dagar {#age-days}

Funktionen `ageInDays` beräknar ett visst datums ålder i dagar, dvs. antalet dagar som förflutit mellan det angivna datumet och det aktuella datumet, negativa för framtida datum och positiva för tidigare datum.

**Syntax**

```sql
{%= ageInDays(date) %}
```

+++Exempel

currentDate = 2025-01-07T12:17:10.720122+05:30 (Asien/Kolkata)

* Indata: `{%= ageInDays(stringToDate("2025-01-01T17:19:51Z"))%}`
* Utdata: `5`

+++

## Ålder i månader {#age-months}

Funktionen `ageInMonths` beräknar åldern för ett givet datum i månader, dvs. antalet månader som förflutit mellan det angivna datumet och det aktuella datumet, negativa för framtida datum och positiva för tidigare datum.

**Syntax**

```sql
{%= ageInMonths(date) %}
```

+++Exempel

currentDate = 2025-01-07T12:22:46.993748+05:30(Asia/Kolkata)

* Indata: `{%=ageInMonths(stringToDate("2024-01-01T00:00:00Z"))%}`
* Utdata: `12`

+++

## Jämför datum {#compare-dates}

Funktionen `compareDates` jämför det första indatadatumet med det andra. Returnerar 0 om date1 är lika med date2, -1 om date1 kommer före date2 och 1 om date1 kommer efter date2.

**Syntax**

```sql
{%= compareDates(date1, date2) %}
```

+++Exempel

* Indata: `{%=compareDates(stringToDate("2024-12-02T00:00:00Z"), stringToDate("2024-12-03T00:00:00Z"))%}`
* Utdata: `-1`

+++

## Konvertera ZonedDateTime {#convert-zoned-date-time}

Funktionen `convertZonedDateTime` konverterar ett datum/tid till en given tidszon.

**Syntax**

```sql
{%= convertZonedDateTime(dateTime, timezone) %}
```

+++Exempel

* Indata: `{%=convertZonedDateTime(stringToDate("2019-02-19T08:09:00Z"), "Asia/Tehran")%}`
* Utdata: `2019-02-19T11:39+03:30[Asia/Tehran]`

+++

## Aktuell tid i millisekunder{#current-time}

Funktionen `currentTimeInMillis` används för att hämta aktuell tid i epok i millisekunder.

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

Funktionen `dateDiff` används för att hämta skillnaden mellan två datum i antal dagar.

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

## Dag i månaden {#day-month}

`dayOfMonth` returnerar talet som representerar dagen i månaden.

**Syntax**

```sql
{%= dayOfMonth(datetime) %}
```

+++Exempel

* Indata: `{%= dayOfMonth(stringToDate("2024-11-05T17:19:51Z")) %}`
* Utdata: `5`

+++


## Veckodag {#day-week}

Funktionen `dayOfWeek` används för att hämta veckodag.

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

Funktionen `dayOfYear` används för att hämta dagen på året.

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

## Skillnad i sekunder {#diff-seconds}

Funktionen `diffInSeconds` returnerar skillnaden mellan två datum i sekunder.

**Syntax**

```sql
{%= diffInSeconds(endDate, startDate) %}
```

+++Exempel

* Indata: `{%=diffInSeconds(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-11-01T17:19:01Z"))%}`
* Utdata: `50`

+++

## Extrahera timmar {#extract-hours}

Funktionen `extractHours` extraherar timkomponenten från en given tidsstämpel.

**Syntax**

```sql
{%= extractHours(date) %}
```

+++Exempel

* Indata: `{%= extractHours(stringToDate("2024-11-01T17:19:51Z"))%}`
* Utdata: `17`

+++

## Extrahera minuter {#extract-minutes}

Funktionen `extractMinutes` extraherar minutkomponenten från en given tidsstämpel.

**Syntax**

```sql
{%= extractMinutes(date) %}
```

+++Exempel

* Indata: `{%= extractMinutes(stringToDate("2024-11-01T17:19:51Z"))%}`
* Utdata: `19`

+++

## Extrahera månader {#extract-months}

Funktionen `extractMonth` extraherar månadskomponenten från en viss tidsstämpel.

**Syntax**

```sql
{%= extractMonths(date) %}
```

+++Exempel

* Indata: `{%=extractMonth(stringToDate("2024-11-01T17:19:51Z"))%}`
* Utdata: `11`

+++

## Extrahera sekunder {#extract-seconds}

Funktionen `extractSeconds` extraherar den andra komponenten från en viss tidsstämpel.

**Syntax**

```sql
{%= extractSeconds(date) %}
```

+++Exempel

* Indata: `{%=extractSeconds(stringToDate("2024-11-01T17:19:51Z"))%}`
* Utdata: `51`

+++

## Formateringsdatum{#format-date}

Funktionen `formatDate` används för att formatera ett datum/tid-värde. Formatet ska vara ett giltigt Java DateTimeFormat-mönster.

**Syntax**

```sql
{%= formatDate(datetime, format) %}
```

Där den första parametern är attributet date-time och det andra värdet är hur du vill att datumet ska konverteras och visas.

>[!NOTE]
>
> Funktionen `formatDate` kräver en **datum-tid-fälttyp** som indata, inte en sträng. Om fältet lagras som en strängtyp i XDM-schemat måste du först konvertera det till datum/tid med en konverteringsfunktion som `stringToDate()` eller `toDateTime()`. Se exemplen nedan.
>
> Om ett datummönster är ogiltigt återgår datumet till ISO-standardformat.
>
> Du kan använda Java-datumformateringsfunktioner som sammanfattas i [Oracle-dokumentationen](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html){_blank}

**Exempel**

+++Formatera ett datum/tid-fält

Följande åtgärd formaterar ett datum/tid-fält till formatet MM/DD/YY.

```sql
{%= formatDate(profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate, "MM/dd/YY") %}
```

+++

+++Konvertera en sträng till datum först

Om fältet lagras som en sträng måste du först konvertera det till ett datum/tid med `stringToDate()` innan du formaterar det.

```sql
{%= formatDate(stringToDate(profile.person.birthDayAndMonth), "MM/DD/YY") %}
```

+++

+++Fullständigt datumformat med dagnamn

Följande åtgärd returnerar ett fullständigt datumformat med namn på dag, månad, dag och år.

```sql
{%= formatDate(profile.person.birthDateTime, "EEEE MMMM dd yyyy") %}
```

Utdata: `Wednesday January 01 2020`

+++

+++Dynamiskt datum baserat på systemtid

Du kan formatera den aktuella systemtiden för att generera dynamiska datum. Följande åtgärd returnerar aktuellt datum i formatet MM/dd/ÅÅÅÅ.

```sql
{%= formatDate(getCurrentZonedDateTime(), "MM/dd/YYYY") %}
```

Utdata (30 januari 2026): `01/30/2026`

+++

+++Veckodag, format

Du kan extrahera veckodagen i kort form.

```sql
{%= formatDate(getCurrentZonedDateTime(), "EEE") %}
```

Utdata: `Sun` (för söndag), `Mon` (för måndag), `Tue` (för tisdag) osv.

Kombinera med funktionen `lowerCase` för gemener:

```sql
{%= lowerCase(formatDate(getCurrentZonedDateTime(), "EEE")) %}
```

Utdata: `sun`, `mon`, `tue` osv.

+++

### Mönstertecken {#pattern-characters}

Vissa mönsterbokstäver kan se likadana ut men representerar olika koncept.

| Mönster | Betydelse | Exempel (för `2023-12-31T10:15:30Z`) |
|---------|---------|--------------------------------------|
| `y` | Kalenderår (standardår) | `2023` |
| `Y` | Veckobaserat år (ISO 8601). Kan skilja sig åt vid årsgränser. | `2024` (sedan 31 december 2023 infaller under den första veckan 2024) |
| `M` | Månad på året (1-12 eller text som `Jan`, `January`) | `12` eller `Dec` |
| `m` | Timme (0-59) | `15` |
| `d` | Månadsdag (1-31) | `31` |
| `D` | Årsdag (1-366) | `365` |

### Formatera datum med språkstöd{#format-date-locale}

Funktionen `formatDate` kan användas för att formatera ett datum- och tidvärde till motsvarande språkkänsliga representation, dvs. i ett önskat språkområde. Formatet ska vara ett giltigt Java DateTimeFormat-mönster.

**Syntax**

```sql
{%= formatDate(datetime, format, locale) %}
```

Där den första strängen är datumattributet är det andra värdet hur du vill att datumet ska konverteras och visas och det tredje värdet representerar språkinställningen i strängformat.

>[!NOTE]
>
> Om ett datummönster är ogiltigt återgår datumet till ISO-standardformat.
>
> Du kan använda Java-datumformateringsfunktioner enligt sammanfattningen i [Oracle-dokumentationen](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html).
>
> Du kan använda formatering och giltiga språkinställningar enligt sammanfattningen i [Oracle-dokumentationen](https://docs.oracle.com/javase/8/docs/api/java/util/Locale.html) och [Språkinställningar som stöds](https://www.oracle.com/java/technologies/javase/jdk11-suported-locales.html).

**Exempel**

Följande åtgärd returnerar datumet i följande format: MM/dd/YY och språkområde FRANCE.

```sql
{%= formatDate(profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate, "MM/dd/YY", "fr_FR") %}
```

## Hämta CurrentZonedDateTime {#get-current-zoned-date-time}

Funktionen `getCurrentZonedDateTime` returnerar aktuellt datum och aktuell tid med tidszonsinformation.

**Syntax**

```sql
{%= getCurrentZonedDateTime() %}
```

+++Exempel

* Indata: `{%= getCurrentZonedDateTime() %}`
* Utdata: `2024-12-06T17:22:02.281067+05:30[Asia/Kolkata]`

+++

## Timskillnad {#hours-difference}

Funktionen `diffInHours` returnerar skillnaden mellan två datum i timmar.

**Syntax**

```sql
{%= diffInHours(endDate, startDate) %}
```

+++Exempel

* Indata: `{%= diffInHours(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-11-01T07:19:51Z"))%}`
* Utdata: `10`

+++

## Minutdifferens{#diff-minutes}

Funktionen `diffInMinutes` används för att returnera skillnaden mellan två datum i minuter.

**Syntax**

```sql
{%= diffInMinutes(endDate, startDate) %}
```

+++Exempel

* Indata: `{%= diffInMinutes(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-11-01T16:19:51Z"))%}`
* Utdata: `60`

+++

## Månadsskillnad {#months-difference}

Funktionen `diffInMonths` returnerar skillnaden mellan två datum i månader.

**Syntax**

```sql
{%= diffInMonths(endDate, startDate) %}
```

+++Exempel

* Indata: `{%=diffInMonths(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-08-01T17:19:51Z"))%}`
* Utdata: `3`

+++

## Ange dagar{#set-days}

Funktionen `setDays` används för att ange dag i månaden för angivet datum/tid.

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

Funktionen `setHours` används för att ange timmen för datum-tid.

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

## Till datum och tid {#to-date-time}

Funktionen `ToDateTime` konverterar sträng till datum. Det returnerar epokdatumet som utdata för ogiltiga indata.

**Syntax**

```sql
{%= toDateTime(string, string) %}
```

+++Exempel

* Indata: `{%=toDateTime("2024-11-01T17:19:51Z")%}`
* Utdata: `2024-11-01T17:19:51Z`

+++

## Till UTC{#to-utc}

Funktionen `toUTC` används för att konvertera en datetime till UTC.

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

## Trunkera till början av dagen {#truncate-day}

Funktionen `truncateToStartOfDay` används för att ändra ett givet datum/tid genom att ställa in den på början av dagen med tiden inställd på 0:00.

**Syntax**

```sql
{%= truncateToStartOfDay(date) %}
```

+++Exempel

* Indata: `{%= truncateToStartOfDay(stringToDate("2024-11-01T17:19:51Z")) %}`
* Utdata: `2024-11-01T00:00Z`

+++

## truncateToStartOfQuarter {#truncate-quarter}

Funktionen `truncateToStartOfQuarter` används för att korta av ett datum/tid till den första dagen i kvarteret (t.ex. Jan 1, Apr 1, Jul 1, Oct 1) kl. 00:00.

**Syntax**

```sql
{%= truncateToStartOfQuarter(dateTime) %}
```

+++Exempel

* Indata: `{%=truncateToStartOfQuarter(stringToDate("2024-11-01T17:19:51Z"))%}`
* Utdata: `2024-10-01T00:00Z`

+++

## truncateToStartOfWeek {#truncate-week}

Funktionen `truncateToStartOfWeek` ändrar ett visst datum/tid genom att ställa in det till veckans början (måndag 0:00).

**Syntax**

```sql
{%= truncateToStartOfWeek(dateTime) %}
```

+++Exempel

* Indata: `{%= truncateToStartOfWeek(stringToDate("2024-11-19T17:19:51Z"))%} // tuesday`
* Utdata: `2024-11-18T00:00Z // monday`

+++

## truncateToStartOfYear {#truncate-year}

Funktionen `truncateToStartOfYear` används för att ändra ett visst datum-tid genom att trunkera den till årets första dag (1 januari) kl. 00:00.

**Syntax**

```sql
{%= truncateToStartOfYear(dateTime) %}
```

+++Exempel

* Indata: `{%=truncateToStartOfYear(stringToDate("2024-11-01T17:19:51Z"))%}`
* Utdata: `2024-01-01T00:00Z`

+++

## Vecka på året {#week-of-year}

Funktionen `weekOfYear` används för att hämta årets vecka.

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

## Årets skillnad {#diff-years}

Funktionen `diffInYears` används för att returnera skillnaden mellan två datum i termer av år.

**Syntax**

```sql
{%= diffInYears(endDate, startDate) %}: int
```

+++Exempel

* Indata: `{%=diffInYears(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2019-10-01T17:19:51Z"))%}`
* Utdata: `5`

+++
