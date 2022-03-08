---
title: Aritmetiskt funktionsbibliotek
description: Aritmetiskt funktionsbibliotek
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: 21ef8f50-8389-4675-a8e5-0438a3eee592
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 2%

---

# Aritmetiska funktioner {#maths}

Aritmetiska funktioner används för att utföra grundläggande beräkningar på värden.

## Lägg till{#add}

The `+` Funktionen (addition) används för att hitta summan av två argumentuttryck.

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

The `*` (multiplikation) används för att hitta produkten av två argumentuttryck.

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

The `-` (subtraktion) används för att hitta skillnaden mellan två argumentuttryck.

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

The `/` Funktionen (division) används för att hitta kvoten mellan två argumentuttryck.

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

The `%` Funktionen (modulo/rest) används för att hitta resten efter att de två argumentuttrycken har delats.

**Format**

```sql
{%= double % double %}
```

**Exempel**

Följande åtgärd kontrollerar om personens ålder är delbar med fem.

```sql
{%= person.age % 5 = 0 %}
```
