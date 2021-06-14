---
title: Kartfunktionens bibliotek
description: Kartfunktionens bibliotek
feature: Personalisering
topic: Personalisering
role: Data Engineer
level: Experienced
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 4%

---

# Kartfunktioner{#maps}

![](../../assets/do-not-localize/badge.png)

[!DNL Profile Query Language] (PQL) har funktioner som underlättar interaktion med kartor.

## Hämta{#get}

Funktionen `get` används för att hämta värdet för en karta för en given nyckel.

**Format**

```sql
{%= get(map, string) %}
```

**Exempel**

Följande åtgärd hämtar värdet för identitetskartan för nyckeln `example@example.com`.

```sql
{%= get(identityMap,"example@example.com") %}
```

## Tangenter{#keys}

Funktionen `keys` används för att hämta alla nycklar för en given karta.

**Format**

```sql
{%= keys(map) %}
```

**Exempel**

Följande åtgärd hämtar alla nycklar för kartan `identityMap`.

```sql
{%= keys(identityMap) %}
```

## Värden{#values}

Funktionen `values` används för att hämta alla värden för en given karta.

**Format**

```sql
{%= values(map) %}
```

**Exempel**

Följande åtgärd hämtar alla värden för kartan `identityMap`.

```sql
{%= values(identityMap) %}
```
