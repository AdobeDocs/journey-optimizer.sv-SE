---
solution: Journey Optimizer
product: journey optimizer
title: Operatorer
description: Läs om operatorer i avancerade uttryck
feature: Journeys
role: Engineer
level: Experienced
keywords: uttryck, syntax, operatorer, redigerare, resa
exl-id: 706e2e02-9bd9-46e7-a73d-dda3c9ae4ba8
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 5%

---

# Operatorer {#operators}

Det finns två typer av operatorer: unära operatorer och binära operatorer. Det finns unära operatorer till vänster och unära operatorer till höger.

```json
// left-hand unary operators
// <operator> <operand> 
// operand is an expression
not (@event{LobbyBeacon.endUserIDs._experience.emailid.id}=="example@adobe.com")

// right-hand unary operators
// <operator> <operand> 
// operand is an expression
@event{LobbyBeacon.endUserIDs._experience.emailid.id} is not null

// binary operators
// <operand1> <operator> <operand2>
// operand is an expression
(@event{LobbyBeacon.endUserIDs._experience.emailid.id}=="example1@adobe.com") or (@event{LobbyBeacon.endUserIDs._experience.emailid.id}=="example2@adobe.com") 
```

## Viktiga anteckningar{#important-notes}

* När du använder en multiplikation (`*`) måste båda åtgärdsfälten ha samma typ, antingen heltal eller decimal. Exempel:
   * följande exempel är korrekt: `3.0 * 4.0`
   * `3 * 4.0` leder till ett fel

* När du använder operatorn `+` måste uttrycket kapslas in inom parenteser. Exempel:
   * `toDateTimeOnly(toDateTime((currentTimeInMillis()) + 1))` är korrekt
   * `toDateTimeOnly(toDateTime(currentTimeInMillis() + 1))` leder till ett fel

## Logisk  {#logical}

### och

```json
<expression1> and <expression2>
```

Både &lt;expression1> och &lt;expression2> måste vara booleska. Resultatet är booleskt.

Exempel:

```json
3.14 > 2 and 3.15 < 1
```

### eller

```json
<expression1> or <expression2>
```

Både &lt;expression1> och &lt;expression2> måste vara booleska. Resultatet är booleskt.

Exempel:

```json
3.14 > 2 or 3.15 < 1
```

### not

```json
not <expression>
```

&lt;expression> måste vara booleskt. Resultatet är booleskt.

Exempel:

```json
not 3.15 < 1
```

## Jämförelse {#comparison}

### är null

```json
<expression> is null
```

Resultatet är booleskt.

Observera att null betyder att uttrycket inte har något utvärderat värde.

Exempel:

```json
@event{BarBeacon.location} is null
```

### är inte null

```json
<expression> is not null
```

Resultatet är booleskt.

Observera att null betyder att uttrycket inte har något utvärderat värde.

Exempel:

```json
@event{BarBeacon.location} is not null
```

### har null

```json
<expression> has null
```

&lt;expression> måste vara en lista. Resultatet är booleskt.

Användbart för att identifiera att en lista innehåller minst ett null-värde.

Exempel:

```json
["foo", "bar", null] has null
```

Returnerar sant

```json
["foo", "bar", ""] has null
```

Returnerar false eftersom &quot;&quot; inte betraktas som null.

### ==

```json
<expression1> == <expression2>
```

>[!NOTE]
>
>Det finns ingen datatypskontroll för &lt;expression1> och &lt;expression2>.

Exempel:

```json
3.14 == 42
```

```json
"foo" == "bar"
```

### !=

```json
<expression1> != <expression2>
```

>[!NOTE]
>
>Det finns ingen datatypskontroll för &lt;expression1> och &lt;expression2>.

Resultatet är booleskt.

Exempel:

```json
3.14 != 42
```

```json
"foo" != "bar"
```

### >

```json
<expression1> > <expression2>
```

Datetime kan jämföras med Datetime.

Datetimeonly kan jämföras med Datetimeonly.

Både heltal och decimal kan jämföras med både heltal och decimal.

Alla andra kombinationer är förbjudna.

Resultatet är booleskt.

Exempel:

```json
3.14 > 42
```

### >=

```json
<expression1> >= <expression2>
```

Datetime kan jämföras med Datetime.

Datetimeonly kan jämföras med Datetimeonly.

Både heltal och decimal kan jämföras med både heltal och decimal.

Alla andra kombinationer är förbjudna.

Resultatet är booleskt.

Exempel:

```json
42 >= 3.14
```

### &lt;

```json
<expression1> < <expression2>
```

Datetime kan jämföras med Datetime.

Datetimeonly kan jämföras med Datetimeonly.

Både heltal och decimal kan jämföras med både heltal och decimal.

Alla andra kombinationer är förbjudna.

Resultatet är booleskt.

Exempel:

```json
42 < 3.14
```

### &lt;=

```json
<expression1> <= <expression2>
```

Datetime kan jämföras med Datetime.

Datetimeonly kan jämföras med Datetimeonly.

Både heltal och decimal kan jämföras med både heltal och decimal.

Alla andra kombinationer är förbjudna.

Resultatet är booleskt.

Exempel:

```json
42 <= 3.14
```

## Aritmetisk {#arithmetic}

### +

```json
<expression1> + <expression2>
```

Båda uttrycken måste vara numeriska (heltal eller decimal).

Resultatet är också numeriskt.

Exempel:

```json
1 + 2
```

Returnerar 3

### –

```json
<expression1> - <expression2>
```

Båda uttrycken måste vara numeriska (heltal eller decimal).

Resultatet är också numeriskt.

Exempel:

```json
2 - 1 
```

Returnerar 1

### /

```json
<expression1> / <expression2>
```

Båda uttrycken måste vara numeriska (heltal eller decimal).

Resultatet är också numeriskt.

&lt;expression2> får inte vara lika med 0 (returnerar 0).

Exempel:

```json
4 / 2
```

Returnerar 2

### *

```json
<expression1> * <expression2>
```

Båda uttrycken måste vara numeriska (heltal eller decimal).

Resultatet är också numeriskt.

Exempel:

```json
3 * 4
```

Returnerar 12

### %

```json
<expression1> % <expression2>
```

Båda uttrycken måste vara numeriska (heltal eller decimal).

Resultatet är också numeriskt.

Exempel:

```json
3 % 2
```

Returnerar 1.

## Matematik {#math}

### är numerisk

```json
<expression> is numeric
```

Uttryckstypen är heltal eller decimal.

Exempel:

```json
@ is numeric
```

### är heltal

```json
<expression> is integer
```

Uttryckstypen är ett heltal.

Exempel:

```json
@ is integer
```

### är decimal

```json
<expression> is decimal
```

Uttryckstypen är decimal.

Exempel:

```json
@ is decimal
```

## Sträng {#string}

### +

```json
<string> + <expression>
```

```json
<expression> + <string>
```

Det sammanfogar två uttryck.

Ett uttryck måste vara en kedjad sträng.

Exempel:

```json
"the current time is " + (now())
```

Returnerar &quot;den aktuella tiden är 2023-09-23T09:30:06.693Z&quot;

```json
(now()) + " is the current time"
```

Returnerar &quot;2023-09-23T09:30:06.693Z är den aktuella tiden&quot;

```json
"a" + "b" + "c" + 1234
```

Returnerar &quot;abc1234&quot;.

## Datum {#date}

### +

```json
<expression> + <duration>
```

Lägg till en varaktighet för ett dateTime, ett dateTimeOnly eller en varaktighet.

Exempel:

```json
(toDateTime("2023-12-03T15:15:30Z")) + (toDuration("PT15M"))  
```

Returnerar en _dateTime_ 2023-12-03T15:30:30Z

```json
(toDateTimeOnly("2023-12-03T15:15:30")) + (toDuration("PT15M"))
```

Returnerar _dateTimeOnly_ 2023-12-03T15:30:30

```json
(now()) + (toDuration("PT1H"))
```

Returnerar _dateTime_ (med UTC-tidszon) en timme senare från aktuell tid

```json
(toDuration("PT1H")) + (toDuration("PT1H"))
```

Returnerar en _varaktighet_ PT2H
