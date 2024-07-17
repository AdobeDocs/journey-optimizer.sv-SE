---
title: Bibliotek för objektfunktioner
description: Bibliotek för objektfunktioner
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: 6ce70e32-aac3-4a2c-bfeb-c370521853ca
source-git-commit: f4068450dde5f85652096c09e7f817dbab40a3d8
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 3%

---

# Objektfunktioner {#objects}

## Är null{#isNull}

Funktionen `isNull` avgör om en objektreferens inte finns.

**Syntax**

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

**Syntax**

```sql
{%= isNotNull(object) %}
```

**Exempel**

Följande åtgärd kontrollerar om personens hemadress finns.

```sql
{%= isNotNull(person.homeAddress) %}
```
