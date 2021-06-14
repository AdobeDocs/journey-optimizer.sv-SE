---
title: Sammanställningsfunktionens bibliotek
description: Sammanställningsfunktionens bibliotek
feature: Personalisering
topic: Personalisering
role: Data Engineer
level: Experienced
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 5%

---

# Sammanställningsfunktioner {#aggregation}

![](../../assets/do-not-localize/badge.png)

Sammanställningsfunktioner används för att gruppera flera värden för att skapa ett enda sammanfattningsvärde.

## Antal{#count}

Funktionen `count` returnerar antalet element i den angivna arrayen.

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

Funktionen `sum` returnerar summan av alla markerade värden i arrayen.

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

Funktionen `average` returnerar det aritmetiska medelvärdet för alla markerade värden i arrayen.

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

Funktionen `min` returnerar det minsta av alla markerade värden i arrayen.

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

Funktionen `max` returnerar det största av alla markerade värden i arrayen.

**Format**

```sql
{%= max(array) %}
```

**Exempel**

Följande åtgärd returnerar det högsta priset för alla order.

```sql
{%=max(orders.order.price)%}
```
