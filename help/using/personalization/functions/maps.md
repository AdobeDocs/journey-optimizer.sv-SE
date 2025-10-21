---
title: Kartfunktionens bibliotek
description: Kartfunktionens bibliotek
feature: Personalization
topic: Personalization
role: Developer
level: Experienced
exl-id: de6a8da2-55cf-4105-ba93-40c556732626
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 2%

---

# Kartfunktioner{#maps}

Använd kartfunktioner i personalisering för att underlätta interaktionen med kartor.

## Hämta{#get}

Funktionen `get` används för att hämta värdet för en karta för en given nyckel.

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

Funktionen `keys` används för att hämta alla nycklar för en given karta.

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

Funktionen `values` används för att hämta alla värden för en given karta.

**Syntax**

```sql
{%= values(map) %}
```

**Exempel**

Följande åtgärd hämtar alla värden för kartan `identityMap`.

```sql
{%= values(identityMap) %}
```
