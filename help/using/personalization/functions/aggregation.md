---
title: Sammanställningsfunktionens bibliotek
description: Sammanställningsfunktionens bibliotek
feature: Personalisering
topic: Personalisering
role: Data Engineer
level: Experienced
source-git-commit: 4be1d6f4034a0bb0a24fe5e4f634253dc1ca798e
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 5%

---

# Sammanställningsfunktioner {#aggregation}

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
