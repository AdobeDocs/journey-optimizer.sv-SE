---
title: Bibliotek för arrayfunktioner
description: Bibliotek för arrayfunktioner
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: dfe611fb-9c50-473c-9eb7-b983e1e6f01e
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 2%

---

# Arrayer och listfunktioner {#arrays}

Använd de här funktionerna för att underlätta interaktionen med arrayer, listor och strängar.

## Distinkt{#distinct}

The `distinct` används för att hämta värden från en array eller lista där dubblettvärden har tagits bort.

**Format**

```sql
{%= distinct(array) %}
```

**Exempel**

Följande åtgärd anger personer som har gjort beställningar i mer än en butik.

```sql
{%= distinct(person.orders.storeId).count() > 1 %}
```

## Första objektet{#head}

The `head` -funktionen används för att returnera det första objektet i arrayen eller listan.

**Format**

```sql
{%= head({array}) %}
```

**Exempel**

Följande åtgärd returnerar den första av de fem främsta beställningarna med det högsta priset. Mer information om `topN` finns i [först `n` i array](#first-n) -avsnitt.

```sql
{%= head(topN(orders,price, 5)) %}
```

## Första `n` i array {#first-n}

The `topN` -funktionen används för att returnera den första `N` objekt i en array, när de sorteras i stigande ordning baserat på det givna numeriska uttrycket.

**Format**

```sql
{%= topN(array, value, amount) %}
```

| Argument | Beskrivning |
| --------- | ----------- |
| `{ARRAY}` | Arrayen eller listan som ska sorteras. |
| `{VALUE}` | Den egenskap som arrayen eller listan ska sorteras i. |
| `{AMOUNT}` | Antalet artiklar som ska returneras. |

**Exempel**

Följande åtgärd returnerar de fem främsta beställningarna med det högsta priset.

```sql
{%= topN(orders,price, 5) %}
```

## I{#in}

The `in` används för att avgöra om ett objekt är medlem i en array eller lista.

**Format**

```sql
{%= in(value, array) %}
```

**Exempel**

Följande åtgärd definierar personer med födelsedagar i mars, juni eller september.

```sql
{%= in (person.birthMonth, [3, 6, 9]) %}
```

## Inkluderar{#includes}

The `includes` används för att avgöra om en array eller lista innehåller ett visst objekt.

**Format**

```sql
{%= includes(array,item) %}
```

**Exempel**

Följande åtgärd definierar personer vars favoritfärg är röd.

```sql
{%= includes(person.favoriteColors,"red") %}
```

## Överlappningar{#intersects}

The `intersects` används för att avgöra om två arrayer eller listor har minst en gemensam medlem.

**Format**

```sql
{%= intersects(array1, array2) %}
```

**Exempel**

Följande åtgärd definierar personer vars favoritfärger innehåller minst en röd, blå eller grön färg.

```sql
{%= intersects(person.favoriteColors,["red", "blue", "green"]) %}
```


<!-- ## Intersection{#intersection}

The `intersection` function is used to determine the common members of two arrays or lists.

**Format**

```sql
intersection({ARRAY},{ARRAY})
```

**Example**

The following operation defines if person 1 and person 2 both have favorite colors of red, blue, and green.

```sql
intersection(person1.favoriteColors,person2.favoriteColors) = ["red", "blue", "green"]
```
-->

## Sista `n` i array{#last-n}

The `bottomN` -funktionen används för att returnera den sista `N` objekt i en array, när de sorteras i stigande ordning baserat på det givna numeriska uttrycket.

**Format**

```sql
{%= bottomN(array, value, amount) %}
```

| Argument | Beskrivning |
| --------- | ----------- | 
| `{ARRAY}` | Arrayen eller listan som ska sorteras. |
| `{VALUE}` | Den egenskap som arrayen eller listan ska sorteras i. |
| `{AMOUNT}` | Antalet artiklar som ska returneras. |

**Exempel**

Följande åtgärd returnerar de fem främsta beställningarna med det lägsta priset.

```sql
{%= bottomN(orders,price, 5) %}
```


## Inte i{#notin}

The `notIn` används för att avgöra om ett objekt inte är medlem i en array eller lista.

>[!NOTE]
>
>The `notIn` function *även* säkerställer att inget av värdena är lika med null. Resultatet är därför inte en exakt negation av `in` funktion.

**Format**

```sql
{%= notIn(value, array) %}
```

**Exempel**

Följande åtgärd definierar personer med födelsedagar som inte är i mars, juni eller september.

```sql
{%= notIn(person.birthMonth ,[3, 6, 9]) %}
```


## Delmängd av{#subset}

The `subsetOf` används för att avgöra om en viss array (array A) är en delmängd av en annan array (array B). Det vill säga att alla element i array A är element i array B.

**Format**

```sql
{%= subsetOf(array1, array2) %}
```

**Exempel**

Följande åtgärd definierar personer som har besökt alla sina favoritstäder.

```sql
{%= subsetOf(person.favoriteCities,person.visitedCities) %}
```

## Supermängd till{#superset}

The `supersetOf` används för att avgöra om en viss array (array A) är en överordnad mängd till en annan array (array B). Arrayen A innehåller alltså alla element i array B.

**Format**

```sql
{%= supersetOf(array1, array2) %}
```

**Exempel**

Följande åtgärd definierar personer som har ätit sushi och pizza minst en gång.

```sql
{%= supersetOf(person.eatenFoods,["sushi", "pizza"] %}
```