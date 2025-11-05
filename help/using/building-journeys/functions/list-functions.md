---
product: journey optimizer
title: Listfunktioner
description: Läs om listfunktioner
feature: Journeys
role: Developer
level: Experienced
keywords: lista, funktioner, uttryck, resa, matris, samling
version: Journey Orchestration
source-git-commit: 0331f8fe2439d41c08ad88a6d0bd95dd150bab90
workflow-type: tm+mt
source-wordcount: '1144'
ht-degree: 5%

---

# Listfunktioner {#list-functions}

Med listfunktioner kan du hantera och arbeta med samlingar av värden i dina reseuttryck. Dessa funktioner är viktiga för att filtrera, sortera, omforma och analysera arrayer och listor på kundresorna.

Använd listfunktioner när du behöver:

* Filtrera och extrahera specifika objekt från samlingar baserat på kriterier
* Sortera och ordna listelement i stigande eller fallande ordning
* Ta bort dubbletter och hämta unika värden från listor
* Kontrollera om det finns värden i samlingar
* Begränsa antalet objekt som returneras från en lista
* Omvandla listor till olika format eller datatyper
* Utför uppsättningsåtgärder som att söka efter gemensamma element mellan listor

Listfunktioner har kraftfulla verktyg för att arbeta med komplexa datastrukturer, vilket möjliggör avancerad databearbetning och villkorsstyrd logik baserat på samlingens innehåll.

## distinct {#distinct}

Returnerar de distinkta värdena eller objekten i en viss lista. Null-poster ignoreras.

+++Syntax

`distinct(<parameters>)`

+++

+++Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly eller listObject | Lista som ska bearbetas. För listObject måste det vara en fältreferens. |
| keyAttributeName | string | Den här parametern är valfri och endast för listObject. Om parametern inte anges betraktas ett objekt som duplicerat om alla attribut har samma värden. Annars betraktas ett objekt som duplicerat om det angivna attributet har samma värde. |

+++

+++Underskrifter och returnerade typer

`distinct(<listInteger>)`

Returnerar en lista med heltal.

`distinct(<listDecimal>)`

Returnerar en lista med decimaler.

`distinct(<listString>)`

Returnerar en lista med strängar.

`distinct(<listDateTimeOnly>)`

Returnerar en lista med datum/tid utan hänsyn till tidszon.

`distinct(<listDateTime>)`

Returnerar en lista med datetimes.

`distinct(<listDateOnly>)`

Returnerar en lista med datum.

`distinct(<listBoolean>)`

Returnerar en lista med boolesk.

`distinct(<listDuration>)`

Returnerar en lista med varaktigheter.

`distinct(<listObject>)`

`distinct(<listObject>,<string>)`

Returnerar en lista med objekt.

+++

+++Exempel

`distinct([10,2,10,null])`

Returnerar `[10, 2]`.

+++

## distinctWithNull {#distinctWithNull}

Returnerar de distinkta värdena eller objekten i en viss lista. Om listan har minst en null-post kommer en null-post att finnas i den returnerade listan.

+++Syntax

`distinctWithNull(<parameters>)`

+++

+++Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly | Lista som ska bearbetas. |

+++

+++Underskrifter och returnerade typer

`distinctWithNull(<listInteger>)`

Returnerar en lista med heltal.

`distinctWithNull(<listDecimal>)`

Returnerar en lista med decimaler.

`distinctWithNull(<listString>)`

Returnerar en lista med strängar.

`distinctWithNull(<listDateTimeOnly>)`

Returnerar en lista med datum/tid utan hänsyn till tidszon.

`distinctWithNull(<listDateTime>)`

Returnerar en lista med datetimes.

`distinctWithNull(<listDateOnly>)`

Returnerar en lista med datum.

`distinctWithNull(<listBoolean>)`

Returnerar en lista med boolesk.

`distinctWithNull(<listDuration>)`

Returnerar en lista med varaktigheter.

+++

+++Exempel

`distinctWithNull([10,2,10,null])`

Returnerar [10, 2, null]

+++

**Obs!** Parametern `<listObject>` stöds inte i den här funktionen.

## filter {#filter}

Returnerar ett listObject med objekt som har nyckelattributet som matchar ett av de angivna nyckelvärdena.

+++Syntax

`filter(<parameters>)`

+++

+++Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToFilter | listObject | lista med objekt som ska filtreras. Det måste vara en fältreferens. |
| keyAttributeName | string | attributnamn i objekten i den angivna listan, används som nyckel för filtrering |
| keyValueList | list | array med nyckelvärden för filtrering |

+++

+++Underskrifter och returnerade typer

`filter(listObject, string, listString)`

`filter(listObject, string, listInteger)`

`filter(listObject, string, listDecimal)`

`filter(listObject, string, listDateTime)`

`filter(listObject, string, listDateTimeOnly)`

`filter(listObject, string, listDateOnly)`

`filter(listObject, string, listDuration)`

`filter(listObject, string, listBoolean)`

Returnerar ett listObject.

+++

+++Exempel

Här är ett exempel på en nyttolast som skickas i en inkommande händelse, &quot;myevent&quot;:

```json
"productListItems": [{
   "id": "product1",
   "name": "the product 1",
   "price": 20
},{
   "id": "product2",
   "name": "the product 2",
   "price": 30
},{
   "id": "product3",
   "name": "the product 3",
   "price": 50
}]
```

Du kan använda följande uttryck:

```json
filter(
 @event{myevent.productListItems},
 "id", 
 ["product2", "product3", "product4"]
)
```

Returnerar ett listObject som innehåller de två objekten med &quot;product2&quot; och &quot;product3&quot; som id.

+++

## getListItem {#getListItem}

Returnerar objektet i listan vid det angivna indexvärdet.

+++Syntax

`getListItem(<parameters>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| list | listString |
| list | listBoolean |
| list | listInteger |
| list | listDecimal |
| list | listDuration |
| list | listDateTime |
| list | listDateTimeOnly |
| list | listDateOnly |
| index | heltal |

+++

+++Underskrifter och returtyp

`getListItem(<listInteger>,<index>)`

Returnerar ett heltal.

`getListItem(<listDecimal>,<index>)`

Returnerar ett decimaltal.

`getListItem(<listString>,<index>)`

Returnerar en sträng.

`getListItem(<listDateTimeOnly>,<index>)`

Returnerar en datetime utan att ta hänsyn till tidszon.

`getListItem(<listDateTime>,<index>)`

Returnerar en datetime.

`getListItem(<listDateOnly>,<index>)`

Returnerar en lista med datum.

`getListItem(<listBoolean>,<index>)`

Returnerar ett booleskt värde.

`getListItem(<listDuration>,<index>)`

Returnerar en varaktighet.

+++

+++Exempel

`getListItem([10, 2, 3], 1)`

Returnerar &quot;2&quot;

`getListItem(["A", "B", "C"], 2)`

Returnerar &quot;C&quot;

Exempel med ett händelsefält &#39;event.appVersion&#39; med värdet: &quot;20.45.2.3434&quot;

`split(@event{event.appVersion}, "\\.")`

Returnerar `["20", "45", "2", "3434"]`

`getListItem(split(@event{event.appVersion}, "\\."), 0)`

Returnerar &quot;20&quot;

+++

## in {#in}

Kontrollerar om det första argumentvärdet finns i listan. Kontrollen utförs med en likhetskontroll för varje argumentvärde. Det returnerar true om argumentvärdet hittas, annars false.

Typen för `<expression>` måste matcha objekten i listan. Typer av objekt i listan måste, som en påminnelse, matcha varandra.

+++Syntax

`in(<parameters>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| Sträng | Sträng |
| Boolean | Boolean |
| Heltal | Heltal |
| Decimal | Decimal |
| Varaktighet | Varaktighet |
| DateTime | DateTime |
| DateTimeOnly | DateTimeOnly |
| Lista | listString |
| Lista | listBoolean |
| Lista | listInteger |
| Lista | listDecimal |
| Lista | listDuration |
| Lista | listDateTime |
| Lista | listDateTimeOnly |
| Lista | listDateOnly |

+++

+++Signatur och returtyp

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<dateOnly>,<listDateOnly>)`

`in(<duration>,<listDuration>)`

Returnera ett booleskt värde.

+++

+++Exempel

`in(4,[4,5,3,4])`

Returnerar true.

`in(8,[4,5,3,4])`

Returnerar false.

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`

+++

## korsa {#intersect}

Returnerar de gemensamma värdena i de två indatalistorna. Om en av de två listorna är null returneras en tom lista.

+++Syntax

`intersect(<parameters>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| lista 1 | list |
| lista 2 | list |

+++

+++Underskrifter och returnerade typer

`intersect(listString,listString)`: listString

`intersect(listDecimal,listDecimal)`: listDecimal

`intersect(listInteger,listInteger)`: listInteger

`intersect(listDateTime,listDateTime)`: listDateTime

`intersect(listDateTimeOnly,listDateTimeOnly)`: listDateTimeOnly

`intersect(listDateOnly,listDateOnly)`: listDateOnly

`intersect(listDuration,listDuration)`: listDuration

`intersect(listBoolean,listBoolean)`: listBoolean

Returnerar en lista.

+++

+++Exempel

```json
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

Returnerar [&quot;sport&quot;, &quot;news&quot;]

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "documentary"]
)
```

Returnerar vanliga objekt mellan profilattribut och angiven lista med kategorier.

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @event{myEvent.sport_interests}
)
```

Returnerar vanliga objekt mellan profilattribut och angivet händelsefält.

+++

## gräns {#limit}

Returnerar det första eller sista N-elementet i en lista.

+++Syntax

`limit(<parameters>)`

+++

+++Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly eller listObject | Lista att tänka på. För listObject måste det vara en fältreferens. |
| numberOfItems | heltal | Antal objekt som ska returneras från den angivna listan. |
| firstOrLastItems | boolesk | Den här parametern är valfri (true som standard). true returnerar de första objekten. false returnerar de sista objekten. |

+++

+++Signatur och returtyp

`limit(<listString>,<integer>)`

`limit(<listString>,<integer>,<boolean>)`

Returnerar en lista med strängar.

`limit(<listInteger>,<integer>)`

`limit(<listInteger>,<integer>,<boolean>)`

Returnerar en lista med heltal.

`limit(<listDecimal>,<integer>)`

`limit(<listDecimal>,<integer>,<boolean>)`

Returnerar en lista med decimaler.

`limit(<listBoolean>,<integer>)`

`limit(<listBoolean>,<integer>,<boolean>)`

Returnerar en lista med boolesk.

`limit(<listDateOnly>,<integer>)`

`limit(<listDateOnly>,<integer>,<boolean>)`

Returnerar en lista med datum.

`limit(<listDateTimeOnly>,<integer>)`

`limit(<listDateTimeOnly>,<integer>,<boolean>)`

Returnerar en lista med datum/tid utan hänsyn till tidszon.

`limit(<listDateTime>,integer>)`

`limit(<listDateTime>,<integer>,<boolean>)`

Returnerar en lista med datetimes.

`limit(<listDuration>,<integer>)`

`limit(<listDuration>,<integer>,<boolean>)`

Returnerar en lista med varaktigheter.

`limit(<listObject>,<integer>)`

`limit(<listObject>,<integer>,<boolean>)`

Returnerar en lista med objekt.

+++

+++Exempel

`limit(["A", "B", "C", "D", "E"], 3)`

Returnerar `["A","B","C"]`.

`limit(["A", "B", "C", "D", "E"], 3, false)`

Returnerar `["C","D","E"]`.

+++

## listSize {#listSize}

Räknar antalet element i listan.

+++Syntax

`listSize(<parameters>)`

+++

+++Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly eller listObject | Lista som ska bearbetas. För listObject måste det vara en fältreferens. Ett listObject får inte innehålla null-objekt. |

+++

+++Underskrifter och returtyp

`listSize(<listInteger>)`

`listSize(<listDecimal>)`

`listSize(<listString>)`

`listSize(<listBoolean>)`

`listSize(<listDateTimeOnly>)`

`listSize(<listDateTime>)`

`listSize(<listDateOnly>)`

`listSize(<listDuration>)`

Returnera ett heltal.

`listSize(<listObject>)`

+++

+++Exempel

`listSize([10,2,3])`

Returnerar 3.

`listSize(@event{my_event.productListItems})`

Returnerar antalet objekt i den angivna arrayen med objekt (typen listObject).

+++

## serializeList {#serializeList}

Konverterar en given lista (alla typer utom listObject) till en sträng.

+++Syntax

`serializeList(<parameters>)`

+++

+++Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly | Lista som ska konverteras till en sträng. |
| avgränsare | string | Avgränsare mellan varje listelement i utdatasträngen. |
| addQuotes | boolesk | Den här parametern anger om varje element i utdatasträngen ska innehålla citattecken (true) eller inte (false). |

+++

+++Signatur och returtyp

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDateOnly>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

Returnera en sträng.

+++

+++Exempel

`serializeList(["Hello","World"], " ", false)`

Returnerar &quot;Hello World&quot;.

`serializeList(["Hello", "World"], ",", true)`

Returnerar &quot;&quot;Hello&quot;,&quot;World&quot;&quot;.

+++

## sort {#sort}

Sorterar en lista med värden eller objekt i den naturliga ordningen.

+++Syntax

`sort(<parameters>)`

+++

+++Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToSort | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly eller listObject | Lista att sortera ut. För listObject måste det vara en fältreferens. |
| keyAttributeName | string | Den här parametern är bara för listObject. Attributnamnet i objekten i den angivna listan används som nyckel för sorteringen. |
| sortingOrder | boolesk | Stigande (true) eller fallande (false) |

+++

+++Signatur och returtyp

`sort(<listInteger>,<boolean>)`

Returnerar en lista med heltal.

`sort(<listDecimal>,<boolean>)`

Returnerar en lista med decimaler.

`sort(<listString>,<boolean>)`

Returnerar en lista med strängar.

`sort(<listDateTimeOnly>,<boolean>)`

Returnerar en lista med datum/tid utan hänsyn till tidszon.

`sort(<listDateTime>,<boolean>)`

Returnerar en lista med datetimes.

`sort(<listDateOnly>,<boolean>)`

Returnerar en lista med datum.

`sort(<listBoolean>,<boolean>)`

Returnerar en lista med boolesk.

`sort(<listObject>,<string>,<boolean>)`

Returnerar en lista med objekt.

+++

+++Exempel

`sort(["A", "C", "B"], true)`

Returnerar `["A","B","C"]`.

`sort([1, 3, 2], false)`

Returnerar `[3, 2, 1]`.

`sort(@event{my_event.productListItems}, "SKU", true)`

Returnerar listObject sorterat efter SKU-attribut (stigande ordning)

+++

