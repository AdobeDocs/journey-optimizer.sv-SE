---
title: Bibliotek för operatorfunktioner
description: Bibliotek för operatorfunktioner
feature: Personalisering
topic: Personalisering
role: Data Engineer
level: Experienced
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 8%

---

# Operatorer {#operators}

![](../../assets/do-not-localize/badge.png)

## Booleska funktioner

Booleska funktioner används för att utföra boolesk logik för olika element.

### Och{#and}

Funktionen `and` används för att skapa en logisk koppling.

**Format**

```sql
{%= query1 and query2 %}
```

**Exempel**

Följande operation kommer att återlämna alla med hemland som Frankrike och födelseåret 1985.

```sql
{%= profile.homeAddress.country = "France" and profile.person.birthYear = 1985 %}
```

### eller{#or}

Funktionen `or` används för att skapa en logisk koppling.

**Format**

```sql
{%= query1 or query2 %}
```

**Exempel**

Följande operation kommer att återlämna alla med hemland som Frankrike eller födelseåret 1985.

```sql
{%= profile.homeAddress.country = "France" or profile.person.birthYear = 1985 %}
```

<!--
## Not{#not}

The `not` (or `!`) function is used to create a logical negation.

**Format**

```sql
not ({QUERY})
!({QUERY})
```

**Example**

The following operation will return all people who do not have their home country as Canada.

```sql
not (homeAddress.countryISO = "CA")
```
-->





## Jämförelsefunktioner

Jämförelsefunktioner används för att jämföra mellan olika uttryck och värden och returnera sant eller falskt efter det.

### Är lika med{#equals}

Funktionen `=` (lika med) kontrollerar om ett värde eller uttryck är lika med ett annat värde eller uttryck.

**Format**

```sql
{%= expression = value %}
```

**Exempel**

Följande åtgärd kontrollerar om hemadresslandet är Frankrike.

```sql
{%= profile.homeAddress.country = "France" %}
```

### Inte lika med{#notequal}

Funktionen `!=` (inte lika med) kontrollerar om ett värde eller uttryck är **inte** lika med ett annat värde eller uttryck.

**Format**

```sql
{%= expression != value %}
```

**Exempel**

Följande åtgärd kontrollerar om hemadresslandet inte är Frankrike.

```sql
{%= profile.homeAddress.country != "France" %}
```

### Greater than{#greaterthan}

Funktionen `>` (större än) används för att kontrollera om det första värdet är större än det andra värdet.

**Format**

```sql
{%= expression1 > expression2 %}
```

**Exempel**

Följande operation definierar personer som är födda strikt efter 1970.

```sql
{%= profile.person.birthYear > 1970 %}
```

### Greater than or equal to{#greaterthanorequal}

Funktionen `>=` (större än eller lika med) används för att kontrollera om det första värdet är större än eller lika med det andra värdet.

**Format**

```sql
{%= expression1 >= expression2 %}
```

**Exempel**

Följande operation definierar personer födda i eller efter 1970.

```sql
{%= profile.person.birthYear >= 1970 %}
```

### Less than{#lessthan}

Jämförelsefunktionen `<` (mindre än) används för att kontrollera om det första värdet är mindre än det andra värdet.

**Format**

```sql
{%= expression1 < expression2 %}
```

**Exempel**

Följande åtgärd definierar personer som är födda före 2000.

```sql
{%= profile.person.birthYear < 2000 %}
```

### Less than or equal to{#lessthanorequal}

Jämförelsefunktionen `<=` (mindre än eller lika med) används för att kontrollera om det första värdet är mindre än eller lika med det andra värdet.

**Format**

```sql
{%= expression1 <= expression2 %}
```

**Exempel**

Följande operation definierar personer födda år 2000 eller tidigare.

```sql
{%= profile.person.birthYear <= 2000 %}
```

**Åtgärder med siffror**

