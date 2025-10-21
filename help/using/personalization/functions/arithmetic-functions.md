---
title: Aritmetiskt funktionsbibliotek
description: Aritmetiskt funktionsbibliotek
feature: Personalization
topic: Personalization
role: Developer
level: Experienced
exl-id: 21ef8f50-8389-4675-a8e5-0438a3eee592
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 2%

---

# Aritmetiska funktioner {#maths}

Aritmetiska funktioner används för att utföra grundläggande beräkningar på värden.

## Lägg till{#add}

Funktionen `+` (addition) används för att hitta summan av två argumentuttryck.

**Syntax**

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

**Syntax**

```sql
{%= double * double %}
```

**Exempel**

Följande åtgärd hittar produkten i lagret och priset på en produkt för att hitta produktens bruttovärde.

```sql
{%= product.inventory * product.price %}
```

## Ta bort{#substract}

Funktionen `-` (subtraktion) används för att hitta skillnaden mellan två argumentuttryck.

**Syntax**

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

**Syntax**

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

**Syntax**

```sql
{%= double % double %}
```

**Exempel**

Följande åtgärd kontrollerar om personens ålder är delbar med fem.

```sql
{%= person.age % 5 = 0 %}
```
