---
title: Kartfunktionens bibliotek
description: Kartfunktionens bibliotek
feature: Personalisering
topic: Personalisering
role: Data Engineer
level: Experienced
source-git-commit: e3b7e80b72e6be71d5b38cd5507d20ad2e8ca8d4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 4%

---

# Kartfunktioner{#maps}

Använd kartfunktioner i personalisering för att underlätta interaktionen med kartor.

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
