---
title: Sammanställningsfunktionens bibliotek
description: Sammanställningsfunktionens bibliotek
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: a029f716-ea1e-4d79-82b7-59770f05161b
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 3%

---

# Sammanställningsfunktioner {#aggregation}

Sammanställningsfunktioner används för att gruppera flera värden för att skapa ett enda sammanfattningsvärde.

## Antal{#count}

The `count` returnerar antalet element i den angivna arrayen.

**Format**

```sql
{%= count(array) %}
```

**Exempel**

Följande åtgärd returnerar antalet order i arrayen.

```sql
{%= count(orders) %}
```

## Summa{#sum}

The `sum` returnerar summan av alla markerade värden i arrayen.

**Format**

```sql
{%= sum(array) %}
```

**Exempel**

Följande operation returnerar summan av alla orderpriser.

```sql
{%=sum(orders.order.price)%}
```

## Genomsnittlig{#average}

The `average` returnerar det aritmetiska medelvärdet för alla markerade värden i arrayen.

**Format**

```sql
{%= average(array) %}
```

**Exempel**

Följande åtgärd returnerar genomsnittspriset för alla order.

```sql
{%=average(orders.order.price)%}
```

## Minimum{#min}

The `min` returnerar det minsta av alla markerade värden i arrayen.

**Format**

```sql
{%= min(array) %}
```

**Exempel**

Följande åtgärd returnerar det lägsta priset för alla order.

```sql
{%=min(orders.order.price)%}
```

## Maximal{#max}

The `max` returnerar den största av alla markerade värden i arrayen.

**Format**

```sql
{%= max(array) %}
```

**Exempel**

Följande åtgärd returnerar det högsta priset för alla order.

```sql
{%=max(orders.order.price)%}
```