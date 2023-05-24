---
product: journey optimizer
title: filter
description: Läs mer om funktionsfiltret
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: filter, funktion, uttryck, resa
exl-id: 05e3d2ba-1a27-4f27-88cc-3d83eb3b14af
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 6%

---

# filter{#filter}

Returnerar ett listObject med objekt som har nyckelattributet som matchar ett av de angivna nyckelvärdena.

>[!NOTE]
>
>Om mållistan är ett listObject kan den här funktionen bara användas i anpassade åtgärdsuttryck.

## Kategori

Lista

## Funktionssyntax

`filter(<parameters>)`

## Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToFilter | listObject | lista med objekt som ska filtreras. Det måste vara en fältreferens. |
| keyAttributeName | string | attributnamn i objekten i den angivna listan, används som nyckel för filtrering |
| keyValueList | list | array med nyckelvärden för filtrering |

## Underskrifter och returnerade typer

`filter(listObject, string, listString)`

`filter(listObject, string, listInteger)`

`filter(listObject, string, listDecimal)`

`filter(listObject, string, listDateTime)`

`filter(listObject, string, listDateTimeOnly)`

`filter(listObject, string, listDateOnly)`

`filter(listObject, string, listDuration)`

`filter(listObject, string, listBoolean)`

Returnerar ett listObject.

## Exempel

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
 @{myevent.productListItems},
 "id", 
 ["product2", "product3", "product4"]
)
```

Returnerar ett listObject som innehåller de två objekten med &quot;product2&quot; och &quot;product3&quot; som id.
