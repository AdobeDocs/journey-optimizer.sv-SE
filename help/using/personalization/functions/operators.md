---
title: Bibliotek för operatorfunktioner
description: Bibliotek för operatorfunktioner
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: 75b0b380-d9a6-418e-b9f6-e64de385ba8d
source-git-commit: 284d95976ab1b58aaea2a4c41db20a3ea5a9b761
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 7%

---

# Operatorer {#operators}

## Booleska funktioner {#boolean-functions}

Booleska funktioner används för att utföra boolesk logik för olika element.

### Och{#and}

The `and` används för att skapa en logisk koppling.

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

The `or` används för att skapa en logisk förskjutning.

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

## Jämförelsefunktioner {#comparison-functions}

Jämförelsefunktioner används för att jämföra mellan olika uttryck och värden och returnera sant eller falskt efter det.

### Är lika med{#equals}

The `=` (lika med)-funktionen kontrollerar om ett värde eller uttryck är lika med ett annat värde eller uttryck.

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

The `!=` (inte lika med) kontrollerar funktionen om ett värde eller uttryck är **not** är lika med ett annat värde eller uttryck.

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

The `>` (större än) används för att kontrollera om det första värdet är större än det andra värdet.

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

The `>=` (större än eller lika med) används för att kontrollera om det första värdet är större än eller lika med det andra värdet.

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

The `<` (mindre än) används för att kontrollera om det första värdet är mindre än det andra värdet.

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

The `<=` (mindre än eller lika med) används för att kontrollera om det första värdet är mindre än eller lika med det andra värdet.

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
