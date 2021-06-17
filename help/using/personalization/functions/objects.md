---
title: Bibliotek för objektfunktioner
description: Bibliotek för objektfunktioner
feature: Personalisering
topic: Personalisering
role: Data Engineer
level: Experienced
source-git-commit: 4be1d6f4034a0bb0a24fe5e4f634253dc1ca798e
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 6%

---

# Objektfunktioner {#objects}

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
