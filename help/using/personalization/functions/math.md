---
title: Bibliotek för matematiska funktioner
description: Bibliotek för matematiska funktioner
feature: Personalization
topic: Personalization
role: Developer
level: Experienced
exl-id: b9149ad6-2be7-4bdf-82eb-7ab52780cb4e
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 4%

---

# Matematiska funktioner {#math}

Lär dig använda Math-funktioner i personaliseringsredigeraren.

## Absolut {#absolute}

Funktionen `absolute` används för att konvertera ett tal till dess absoluta värde.

**Syntax**

```sql
{%= absolute(int) %}: int
```

## formatNumber {#format-number}

Funktionen `formatNumber` används för att formatera valfritt tal till dess språkkänsliga representation.

Den accepterar ett tal och en sträng som representerar språkområdet och returnerar en formaterad sträng med talet i det önskade språkområdet.

**Syntax**

```sql
{%= formatNumber(number/double,string) %}: string
```

Du kan använda formatering och giltiga språkinställningar enligt en sammanfattning i [Oracle-dokumentationen](https://docs.oracle.com/javase/8/docs/api/java/util/Locale.html) och [Språkinställningar som stöds](https://www.oracle.com/java/technologies/javase/jdk11-suported-locales.html){_blank}

**Exempel**

Den här frågan returnerar en formaterad sträng på arabiska som motsvarar 123456.789 som indatanummer.

```sql
{%= formatNumber(123456.789, "ar_EG") %}
```

## Slumpmässig {#random}

Funktionen `random` används för att returnera ett slumpmässigt värde mellan 0 och 1.

**Syntax**

```sql
{%= random() %}: double
```

## Avrunda nedåt {#round-down}

Funktionen `roundDown` används för att avrunda ett tal.

**Syntax**

```sql
{%= roundDown(double) %}: double
```

## Avrunda uppåt {#round-up}

Funktionen `roundUp` används för att avrunda ett tal.

**Syntax**

```sql
{%= roundUp(double) %}: double
```

## Till hexadecimal sträng {#to-hex-string}

Funktionen `toHexString` konverterar alla tal till sin hexadecimala sträng.

**Syntax**

```sql
{%= toHexString(number) %}: string
```

**Exempel**

Frågan returnerar det hexadecimala värdet 158, dvs. 9e.

```sql
{%= toHexString(158) %}
```

## Till int {#to-int}

Funktionen `toInt` används för att konvertera någon av dessa typer (number, double, int, long, float, short, byte, boolean, string) till ett heltal.

**Syntax**

```sql
{%= toInt(<valueToConvert>) %}: integer
```

**Exempel**

Den här frågan returnerar heltalsvärdet 42,6, dvs. 42.

```sql
{%= toInt(42.6) %}: integer
```

## Till procent {#to-percentage}

Funktionen `toPercentage` används för att konvertera ett tal till procent.

**Syntax**

```sql
{%= toPercentage(double) %}: string
```

## Till precision {#to-precision}

Funktionen `toPrecision` används för att konvertera ett tal till nödvändig precision.

**Syntax**

```sql
{%= toPrecision(double,int) %}: string
```

## Till sträng {#to-string}

Funktionen **toString** konverterar alla tal till sin strängbeteckning.

**Syntax**

```sql
{%= toString(string) %}: string
```

**Exempel**

Frågan returnerar &quot;12&quot;.

```sql
{%= toString(12) %} 
```
