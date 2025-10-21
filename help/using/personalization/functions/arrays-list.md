---
title: Arrayfunktioner, bibliotek
description: Arrayfunktioner, bibliotek
feature: Personalization
topic: Personalization
role: Developer
level: Experienced
exl-id: dfe611fb-9c50-473c-9eb7-b983e1e6f01e
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 2%

---

# Arrayer och listfunktioner {#arrays}

Använd de här funktionerna för att underlätta interaktionen med arrayer, listor och strängar.

## Endast antal null {#count-only-null}

Funktionen `countOnlyNull` används för att räkna antalet null-värden i en lista.

**Syntax**

```sql
{%= countOnlyNull(array) %}
```

**Exempel**

```sql
{%= countOnlyNull([4,0,1,6,0,0]) %}
```

Returnerar 3.

## Antal med null {#count-with-null}

Funktionen `countWithNull` används för att räkna alla element i en lista inklusive null-värden.

**Syntax**

```sql
{%= countWithNull(array) %}
```

**Exempel**

```sql
{%= countOnlyNull([4,0,1,6,0,0]) %}
```

Returnerar 6.

## Distinkt{#distinct}

Funktionen `distinct` används för att hämta värden från en array eller lista där dubblettvärden har tagits bort.

**Syntax**

```sql
{%= distinct(array) %}
```

**Exempel**

Följande åtgärd anger personer som har gjort beställningar i mer än en butik.

```sql
{%= distinct(person.orders.storeId).count() > 1 %}
```

## Distinkt antal med null {#distinct-count-with-null}

Funktionen `distinctCountWithNull` används för att räkna antalet olika värden i en lista inklusive null-värden.

**Syntax**

```sql
{%= distinctCountWithNull(array) %}
```

**Exempel**

```sql
{%= distinctCountWithNull([10,2,10,null]) %}
```

Returnerar 3.

## Första objektet{#head}

Funktionen `head` används för att returnera det första objektet i en array eller lista.

**Syntax**

```sql
{%= head(array) %}
```

**Exempel**

Följande åtgärd returnerar den första av de fem främsta beställningarna med det högsta priset. Mer information om funktionen `topN` finns i avsnittet [first `n` i array](#first-n).

```sql
{%= head(topN(orders,price, 5)) %}
```

## Första `n` i matris {#first-n}

Funktionen `topN` används för att returnera de första `N` objekten i en array, sorterade i stigande ordning baserat på det angivna numeriska uttrycket.

**Syntax**

```sql
{%= topN(array, value, amount) %}
```

| Argument | Beskrivning |
| --------- | ----------- |
| `{ARRAY}` | Den array eller lista som ska sorteras. |
| `{VALUE}` | Den egenskap som arrayen eller listan ska sorteras i. |
| `{AMOUNT}` | Antalet artiklar som ska returneras. |

**Exempel**

Följande åtgärd returnerar de första fem beställningarna med det lägsta priset.

```sql
{%= topN(orders,price, 5) %}
```

## I{#in}

Funktionen `in` används för att avgöra om ett objekt är medlem i en array eller lista.

**Syntax**

```sql
{%= in(value, array) %}
```

**Exempel**

Följande åtgärd definierar personer med födelsedagar i mars, juni eller september.

```sql
{%= in (person.birthMonth, [3, 6, 9]) %}
```

## Inkluderar{#includes}

Funktionen `includes` används för att avgöra om en array eller lista innehåller ett visst objekt.

**Syntax**

```sql
{%= includes(array,item) %}
```

**Exempel**

Följande åtgärd definierar personer vars favoritfärg innehåller rött.

```sql
{%= includes(person.favoriteColors,"red") %}
```

## Överlappningar{#intersects}

Funktionen `intersects` används för att avgöra om två arrayer eller listor har minst en gemensam medlem.

**Syntax**

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

**Syntax**

```sql
intersection({ARRAY},{ARRAY})
```

**Example**

The following operation defines if person 1 and person 2 both have favorite colors of red, blue, and green.

```sql
intersection(person1.favoriteColors,person2.favoriteColors) = ["red", "blue", "green"]
```
-->

## Senaste `n` i matris{#last-n}

Funktionen `bottomN` används för att returnera de sista `N` objekten i en array, sorterade i stigande ordning baserat på det angivna numeriska uttrycket.

**Syntax**

```sql
{%= bottomN(array, value, amount) %}
```

| Argument | Beskrivning |
| --------- | ----------- | 
| `{ARRAY}` | Den array eller lista som ska sorteras. |
| `{VALUE}` | Den egenskap som arrayen eller listan ska sorteras i. |
| `{AMOUNT}` | Antalet artiklar som ska returneras. |

**Exempel**

Följande åtgärd returnerar de fem sista beställningarna med det högsta priset.

```sql
{%= bottomN(orders,price, 5) %}
```

## Inte i{#notin}

Funktionen `notIn` används för att avgöra om ett objekt inte är medlem i en array eller lista.

>[!NOTE]
>
>`notIn`-funktionen *ser också* till att inget av värdena är lika med null. Resultatet är därför inte en exakt negation av funktionen `in`.

**Syntax**

```sql
{%= notIn(value, array) %}
```

**Exempel**

Följande åtgärd definierar personer med födelsedagar som inte är i mars, juni eller september.

```sql
{%= notIn(person.birthMonth ,[3, 6, 9]) %}
```


## Delmängd av{#subset}

Funktionen `subsetOf` används för att avgöra om en viss array (array A) är en delmängd av en annan array (array B). Det vill säga att alla element i array A är element i array B.

**Syntax**

```sql
{%= subsetOf(array1, array2) %}
```

**Exempel**

Följande åtgärd definierar personer som har besökt alla sina favoritstäder.

```sql
{%= subsetOf(person.favoriteCities,person.visitedCities) %}
```

## Supermängd till{#superset}

Funktionen `supersetOf` används för att avgöra om en viss array (array A) är en överordnad mängd till en annan array (array B). Arrayen A innehåller alltså alla element i array B.

**Syntax**

```sql
{%= supersetOf(array1, array2) %}
```

**Exempel**

Följande åtgärd definierar personer som har ätit sushi och pizza minst en gång.

```sql
{%= supersetOf(person.eatenFoods,["sushi", "pizza"]) %}
```
