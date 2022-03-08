---
title: Kartfunktionens bibliotek
description: Kartfunktionens bibliotek
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: de6a8da2-55cf-4105-ba93-40c556732626
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 2%

---

# Kartfunktioner{#maps}

Använd kartfunktioner i personalisering för att underlätta interaktionen med kartor.

## Hämta{#get}

The `get` används för att hämta värdet för en karta för en viss nyckel.

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

The `keys` används för att hämta alla nycklar för en viss karta.

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

The `values` används för att hämta alla värden för en viss karta.

**Format**

```sql
{%= values(map) %}
```

**Exempel**

Följande åtgärd hämtar alla värden för kartan `identityMap`.

```sql
{%= values(identityMap) %}
```
