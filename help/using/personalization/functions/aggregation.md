---
title: Sammanställningsfunktionens bibliotek
description: Sammanställningsfunktionens bibliotek
feature: Personalization
topic: Personalization
role: Developer
level: Experienced
exl-id: a029f716-ea1e-4d79-82b7-59770f05161b
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 3%

---

# Sammanställningsfunktioner {#aggregation}

Sammanställningsfunktioner används för att gruppera flera värden för att skapa ett enda sammanfattningsvärde.

## Genomsnittlig{#average}

Funktionen `average` returnerar det aritmetiska medelvärdet för alla markerade värden i arrayen.

**Syntax**

```sql
{%= average(array) %}
```

**Exempel**

Följande åtgärd returnerar genomsnittspriset för alla order.

```sql
{%=average(orders.order.price)%}
```

## Antal{#count}

Funktionen `count` returnerar antalet element i den angivna arrayen.

**Syntax**

```sql
{%= count(array) %}
```

**Exempel**

Följande åtgärd returnerar antalet order i arrayen.

```sql
{%= count(orders) %}
```

## Maximal{#max}

Funktionen `max` returnerar det största av alla markerade värden i arrayen.

**Syntax**

```sql
{%= max(array) %}
```

**Exempel**

Följande åtgärd returnerar det högsta priset för alla order.

```sql
{%=max(orders.order.price)%}
```

## Minimum{#min}

Funktionen `min` returnerar det minsta av alla markerade värden i arrayen.

**Syntax**

```sql
{%= min(array) %}
```

**Exempel**

Följande åtgärd returnerar det lägsta priset för alla order.

```sql
{%=min(orders.order.price) %}
```

## Summa{#sum}

Funktionen `sum` returnerar summan av alla markerade värden i arrayen.

**Syntax**

```sql
{%= sum(array) %}
```

**Exempel**

Följande operation returnerar summan av alla orderpriser.

```sql
{%=sum(orders.order.price)%}
```
