---
product: journey optimizer
title: in
description: Läs mer om funktionen i
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: in, funktion, uttryck, resa
exl-id: 629b7aa3-8904-453b-ba3c-c6a333b13c81
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 3%

---

# in {#in}

Kontrollerar om det första argumentvärdet finns i listan. Kontrollen utförs med en likhetskontroll för varje argumentvärde. Det returnerar true om argumentvärdet hittas, annars false.

Typen för `<expression>` måste matcha objekten i listan. Typer av objekt i listan måste, som en påminnelse, matcha varandra.

## Kategori

Lista

## Funktionssyntax

`in(<parameters>)`

## Parametrar

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

## Signatur och returtyp

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<dateOnly>,<listDateOnly>)`

`in(<duration>,<listDuration>)`

Returnera ett booleskt värde.

## Exempel

`in(4,[4,5,3,4])`

Returnerar true.

`in(8,[4,5,3,4])`

Returnerar false.

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
