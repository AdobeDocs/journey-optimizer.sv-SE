---
title: Bibliotek för objektfunktioner
description: Bibliotek för objektfunktioner
feature: Personalisering
topic: Personalisering
role: Data Engineer
level: Experienced
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 6%

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
