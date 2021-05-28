---
title: Funktionsbibliotek
description: Funktionsbibliotek
source-git-commit: 8c58dd667ea59a17833bbe3482b1a233ac2e28fe
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 3%

---

# Objektfunktioner {#objects}

![](../../assets/do-not-localize/badge.png)

## Är null{#isNull}

Funktionen `isNull` avgör om en objektreferens inte finns.

**Format**

```sql
{%= isNull(object) %}
```

**Exempel**

Följande åtgärd kontrollerar om personens hemadress inte finns.

```sql
{%= isNull(person.homeAddress) %}
```

## Är inte null{#isNotNull}

Funktionen `isNotNull` avgör om det finns en objektreferens.

**Format**

```sql
{%= isNotNull(object) %}
```

**Exempel**

Följande åtgärd kontrollerar om personens hemadress finns.

```sql
{%= isNotNull(person.homeAddress) %}
```
