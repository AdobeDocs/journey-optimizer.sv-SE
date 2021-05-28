---
title: Funktionsbibliotek
description: Funktionsbibliotek
source-git-commit: cd1b07bbb4b247d1d8c0cc87be9e4bdad22377ed
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 2%

---

# Aritmetiska funktioner {#maths}

![](../../assets/do-not-localize/badge.png)

Aritmetiska funktioner används för att utföra grundläggande beräkningar på värden.

## Lägg till{#add}

Funktionen `+` (addition) används för att hitta summan av två argumentuttryck.

**Format**

```sql
{%= double + double %}
```

**Exempel**

Följande operation summerar priset på två olika produkter.

```sql
{%= product1.price + product2.price %}
```

## Multiplicera{#multiply}

Funktionen `*` (multiplikation) används för att hitta produkten av två argumentuttryck.

**Format**

```sql
{%= double * double %}
```

**Exempel**

Följande åtgärd hittar produkten i lagret och priset på en produkt för att hitta produktens bruttovärde.

```sql
{%= product.inventory * product.price %}
```

## Subtrahera{#substract}

Funktionen `-` (subtraktion) används för att hitta skillnaden mellan två argumentuttryck.

**Format**

```sql
{%= double - double %}
```

**Exempel**

Följande åtgärd identifierar prisskillnaden mellan två olika produkter.

```sql
{%= product1.price - product2.price %}
```

## Dela{#divide}

Funktionen `/` (division) används för att hitta kvoten mellan två argumentuttryck.

**Format**

```sql
{%= double / double %}
```

**Exempel**

I följande åtgärd hittas kvoten mellan de totala sålda produkterna och de totala intjänade pengarna för att se den genomsnittliga kostnaden per artikel.

```sql
{%= totalProduct.price / totalProduct.sold %}
```

## Återstående{#remainder}

Funktionen `%` (modulo/rest) används för att hitta resten efter att de två argumentuttrycken har delats.

**Format**

```sql
{%= double % double %}
```

**Exempel**

Följande åtgärd kontrollerar om personens ålder är delbar med fem.

```sql
{%= person.age % 5 = 0 %}
```
