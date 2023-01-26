---
title: Kartfunktionens bibliotek
description: Kartfunktionens bibliotek
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: de6a8da2-55cf-4105-ba93-40c556732626
source-git-commit: f4068450dde5f85652096c09e7f817dbab40a3d8
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 5%

---

# Kartfunktioner{#maps}

Använd kartfunktioner i personalisering för att underlätta interaktionen med kartor.

## Hämta{#get}

The `get` används för att hämta värdet för en karta för en viss nyckel.

**Syntax**

```sql
{%= get(map, string) %}
```

**Exempel**

Följande åtgärd hämtar värdet för identitetskartan för nyckeln `example@example.com`.

```sql
{%= get(identityMap,"example@example.com") %}
```

## Tangenter{#keys}

The `keys` används för att hämta alla nycklar för en viss karta.

**Syntax**

```sql
{%= keys(map) %}
```

**Exempel**

Följande åtgärd hämtar alla nycklar för kartan `identityMap`.

```sql
{%= keys(identityMap) %}
```

## Värden{#values}

The `values` används för att hämta alla värden för en viss karta.

**Syntax**

```sql
{%= values(map) %}
```

**Exempel**

Följande åtgärd hämtar alla värden för kartan `identityMap`.

```sql
{%= values(identityMap) %}
```
