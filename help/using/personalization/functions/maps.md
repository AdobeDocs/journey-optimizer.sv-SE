---
title: Funktionsbibliotek
description: Funktionsbibliotek
source-git-commit: 8c58dd667ea59a17833bbe3482b1a233ac2e28fe
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 3%

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
