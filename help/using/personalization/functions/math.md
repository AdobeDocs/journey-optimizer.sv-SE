---
title: Bibliotek för matematiska funktioner
description: Bibliotek för matematiska funktioner
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
source-git-commit: 284d95976ab1b58aaea2a4c41db20a3ea5a9b761
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 1%

---

# Matematiska funktioner {#math}

Lär dig hur du använder matematiska funktioner i uttrycksredigeraren.

## Absolut {#absolute}

The `absolute` -funktionen används för att konvertera ett tal som det är absolut värde för.

**Format**

```sql
{%= absolute(int) %}: int
```

## Random {#random}

The `random` -funktionen används för att returnera ett slumpmässigt värde mellan 0 och 1.

**Format**

```sql
{%= random() %}: double
```

## Avrunda nedåt {#round-down}

The `roundDown` -funktionen används för att avrunda ett tal nedåt.

**Format**

```sql
{%= roundDown(double) %}: double
```

## Avrunda uppåt {#round-up}

The `Count only null` -funktionen används för att avrunda ett tal.

**Format**

```sql
{%= roundUp(double) %}: double
```

## Till procent {#to-percentage}

The `toPercentage` används för att konvertera ett tal till ett procenttal.

**Format**

```sql
{%= toPercentage(double) %}: string
```

## Till precision {#to-precision}

The `toPrecision` -funktionen används för att konvertera ett tal till önskad precision.

**Format**

```sql
{%= toPrecision(double,int) %}: string
```
