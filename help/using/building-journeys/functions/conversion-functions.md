---
product: journey optimizer
title: Konverteringsfunktioner
description: Läs om konverteringsfunktioner
feature: Journeys
role: Developer
level: Experienced
keywords: konvertering, funktioner, uttryck, resa, typ, skiftning
version: Journey Orchestration
source-git-commit: 7d75abf6b428becc8b535a63421e85cca417daac
workflow-type: tm+mt
source-wordcount: '940'
ht-degree: 3%

---

# Konverteringsfunktioner {#conversion-functions}

Med konverteringsfunktionerna kan du omvandla data från en typ till en annan i dina reseuttryck. Dessa funktioner är nödvändiga för att säkerställa datakompatibilitet och korrekt typsnittshantering vid arbete med olika datakällor och operationer.

Använd konverteringsfunktioner när du behöver:

* Konvertera strängvärden till numeriska, booleska eller datumtyper
* Omvandla datum och tidpunkter mellan olika format och representationer
* Sänd numeriska värden mellan heltal- och decimaltyper
* Säkerställ typkompatibilitet för jämförelser och åtgärder
* Bearbeta data från externa källor som kan ha olika typformat

Varje konverteringsfunktion hanterar typspecifika regler och kantfall automatiskt, vilket gör dataomvandlingen mer tillförlitlig och förutsägbar i reseuttrycken.

## toBool {#toBool}

Konverterar ett argumentvärde till ett booleskt värde, beroende på dess typ.

* Från sträng: försök att konvertera strängvärdet som booleskt, från &quot;true&quot; om strängvärdet är &quot;true&quot;, annars false
* Från numeriskt: true om det numeriska värdet inte är lika med 0, annars false

+++Syntax

`toBool(<parameter>)`

+++

+++Parametrar

* decimal
* boolesk
* string
* heltal

+++

+++Underskrifter och returnerade typer

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

Returnera ett booleskt värde.

+++

+++Exempel

`toBool("true")`

`toBool(1)`

Returnerar true.

`toBool("this is not a boolean")`

Returnerar false.

+++

## toDateOnly {#toDateOnly}

Konverterar ett argument till ett dateOnly-typvärde. Mer information om datatyper finns i [avsnittet](../expression/data-types.md).

+++Syntax

`toDateOnly(<parameters>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| Strängbeteckning för ett datum som &quot;YYY-MM-DD&quot; (XDM-format). Stöder även ISO-8601-format: endast **heldatum**-delen beaktas (se [RFC 3339, avsnitt 5.6](https://www.rfc-editor.org/rfc/rfc3339#section-5.6)) | string |
| tid | dateTime |
| datum tid utan tidszon | dateTimeOnly |
| heltalsvärde för en epok i millisekunder | heltal |

+++

+++Underskrifter och returnerade typer

`toDateOnly(<dateTime>)`

`toDateOnly(<dateTimeOnly>)`

`toDateOnly(<string>)`

`toDateOnly(<integer>, <integer>, <integer>)`

Returnerar ett dateOnly-typvärde.

+++

+++Exempel

`toDateOnly("2023-08-18")`

`toDateOnly("2023-08-18T00:00:00.000Z")`

`toDateOnly("2023-08-18T00:00:00")`

alla returnerar ett dateOnly-objekt som representerar 2023-08-18.

`toDateOnly(#{ExperiencePlatform.ProfileFieldGroup.person.birthDate})`

Returnerar ett dateOnly.

+++

## toDateTime {#toDateTime}

Konverterar parametrar till ett datum/tid-värde, beroende på deras typer.

+++Syntax

`toDateTime(<parameters>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| datum och tid i ISO-8601-format | string |
| tidszon-id | string |
| datum tid utan tidszon | dateTimeOnly |
| heltalsvärde för en epok i millisekunder | heltal |

+++

+++Underskrifter och returnerade typer

`toDateTime(<string>)`

`toDateTime(<stringified time zone id>, <dateTimeOnly>)`

`toDateTime(<integer>)`

Returnera en **dateTime**.

+++

+++Exempel

`toDateTime ("2023-08-18T23:17:59.123Z")`

Returnerar 2023-08-18T23:17:59.123Z

`toDateTime(toDateTimeOnly("UTC", "2023-08-18T23:17:59.123"))`

Returnerar 2023-08-18T23:17:59.123Z

`toDateTime(1560762190189)`

Returnerar 2023-06-17T09:03:10.189Z

+++

>[!NOTE]
>
>Tidszons-ID måste vara en strängkonstant. Det kan inte vara en fältreferens eller ett uttryck. Mer information om datatyper finns på [den här sidan](../expression/data-types.md).

## toDateTimeOnly {#toDateTimeOnly}

Konverterar ett argumentvärde till ett värde för endast datum och tid.

+++Syntax

`toDateTimeOnly(<parameters>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| datumtid i ISO-8601- eller &quot;YYY-MM-DD&quot;-format (XDM-datumformat) | string |
| tid | dateTime |

+++

+++Underskrifter och returnerade typer

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`

Returnera en datetime utan att överväga tidszon.

+++

+++Exempel

`toDateTimeOnly ("2023-08-18")`

returnerar ett dateTime som representerar 2023-08-18T00:00:00.000

`toDateTimeOnly(now())`

+++

## toDecimal {#toDecimal}

Konverterar ett argumentvärde till ett decimalvärde, beroende på dess typ.

+++Syntax

`toDecimal(<parameter>)`

+++

+++Parametrar

| Parameter | Beskrivning |
|--- |--- |
| string | konverterar strängvärdet som ett decimaltal |
| dateTime | konverterar datumet som antal millisekunder (epok millisekunder) |
| boolesk | konverterar det booleska värdet till 1 om true, 0 om false |
| heltal | konverterar till ett decimaltal (exempel.: 1 blir 1.0) |

+++

+++Underskrifter och returnerade typer

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

Returnera ett decimaltal.

+++

+++Exempel

`toDecimal("4.0")`

Returnerar 4.0.

+++

## toDuration {#toDuration}

Konverterar ett argumentvärde till en längd. Mer information om datatyper finns på [den här sidan](../expression/data-types.md).

+++Syntax

`toDuration(<parameter>)`

+++

+++Parametrar

| Parameter | Beskrivning |
|--- |--- |
| string | format som bygger på ISO-8601-varaktighetsformatet PnDTnHnMn.nS med dagar som anses vara exakt 24 timmar |
| heltal | antal millisekunder |

Om stränguttryck: godkända format baseras på varaktighetsformatet PnDTnHnMn.nS för ISO-8601 med dagar som anses vara exakt 24 timmar.

Strängen börjar med ett valfritt tecken som anges med ASCII-tecknet för negativ eller positiv symbol. Om värdet är negativt negeras hela perioden. ASCII-bokstaven&quot;P&quot; står bredvid med versaler eller gemener. Därefter finns det fyra avsnitt som består av ett tal och ett suffix. Avsnitten har suffix i ASCII av &quot;D&quot;, &quot;H&quot;, &quot;M&quot; och &quot;S&quot; för dagar, timmar, minuter och sekunder, vilka accepteras med versaler eller gemener. Suffixen måste finnas i ordning. ASCII-bokstaven &quot;T&quot; måste inträffa före den första förekomsten av en timme, minut eller sekund. Minst en av de fyra avsnitten måste finnas, och om T förekommer måste det finnas minst en sektion efter T. Nummerdelen av varje avsnitt måste bestå av en eller flera ASCII-siffror. Talet kan föregås av ASCII-negativa eller positiva symboler. Antalet dagar, timmar och minuter måste tolkas. Antalet sekunder måste tolkas tillsammans med den valfria fraktionen. Decimaltecknet kan vara antingen en punkt eller ett komma. Den bråkdelar kan innehålla mellan noll och nio siffror.

+++

+++Underskrifter och returtyp

`toDuration(<string>)`

`toDuration(<integer>)`

Returnerar en varaktighet.

+++

+++Exempel

`toDuration("PT10H")`

Returnerar längden 10 timmar.

`toDuration("PT4S")`

Returnerar längden på 4s.

`toDuration(4000)`

Returnerar längden på 4s.

+++

## toInteger {#toInteger}

Konverterar ett argumentvärde till ett heltal.

+++Syntax

`toInteger(<parameter>)`

+++

+++Parametrar

| Parameter | Beskrivning |
|--- |--- |
| string | konverterar strängvärdet som ett heltal |
| dateTime | konverterar datumet som antal millisekunder (epok millisekunder) |
| decimal | konverterar till heltal genom att ta bort decimaldelen (exempel: 1,5 blir 1) |
| boolesk | konverterar det booleska värdet till 1 om true, 0 om false |

+++

+++Underskrifter och returtyp

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

Returnera ett heltal.

+++

+++Exempel

`toInteger("4")`

Returnerar 4.

+++

## toString {#toString}

Konverterar ett argumentvärde till ett strängvärde, beroende på dess typ. Mer information om datatyper finns på [den här sidan](../expression/data-types.md).

+++Syntax

`toString(<parameter>)`

+++

+++Parametrar

| Parameter | Beskrivning |
|--- |--- |
| dateTime | konverterar datumet i UTC-datumformat |
| dateTimeOnly | konverterar datumet i UTC-datumformat |
| varaktighet | konvertera till motsvarande antal millisekunder som en sträng |
| heltal | konverterar till strängbeteckning för värdet (1 blir &quot;1&quot;) |
| decimal | konverterar till strängbeteckning för värdet (1.5 blir &quot;1.5&quot;) |
| boolesk | konvertera det booleska värdet till true om true, false om false |

+++

+++Underskrifter och returtyp

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

Returnera en sträng.

+++

+++Exempel

`toString(4)`

Returnerar &quot;4&quot;.

`toString(#{ExperiencePlatform.test_date.person.birthDate}))`

Returnerar strängbeteckningen för angivet dateOnly-fält (XDM-datumfält), till exempel &quot;2023-08-18&quot;.

`toString(toDuration(1520))`

Returnerar &quot;PT1.52S&quot;.

+++

