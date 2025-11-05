---
solution: Journey Optimizer
product: journey optimizer
title: Funktioner
description: Lär dig mer om funktioner i reseuttryck
feature: Journeys
role: Developer
level: Experienced
keywords: funktion, uttryck, editor, resa, data, manipulation
exl-id: 5b978eef-7d3e-41fe-bb08-0cf37c3b125d
version: Journey Orchestration
source-git-commit: 99053c6c1327818645adc4ab9a5d3dd30eb96b87
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 7%

---

# Funktioner {#functions}

Funktioner är byggstenarna i dynamiska reseuttryck i Adobe Journey Optimizer. Med dem kan ni omvandla, beräkna, validera och hantera data i realtid för att skapa personaliserade kundupplevelser. Med över 60 funktioner ordnade i intuitiva kategorier kan ni skapa avancerade villkor, utföra komplexa beräkningar och fatta databaserade beslut under varje steg av kundresan.

## Funktioner

Funktioner i reseuttryck följer ett konsekvent syntaxmönster:

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ..., `<expression as param N>`)

**Viktiga egenskaper:**

* **Flera signaturer**: En funktion kan ha olika signaturer (olika uppsättningar med ordnade parametrar) för olika användningsområden
* **Typspecifika returnerar**: Varje funktion har en specifik returtyp (sträng, heltal, boolesk, datum, lista osv.)
* **Parametrar från noll till N**: Funktioner kan acceptera 0-N-uttryck som ordnade parametrar, vilket ger flexibilitet i hur du använder dem

## Varför använda funktioner?

Med funktionerna kan du

* **Skapa dynamiska villkor** - Sökvägar för grenresa baserat på datautvärdering i realtid
* **Anpassa i stor skala** - Anpassa innehåll och upplevelser med kunddata och beteendeinsikter
* **Automatisera beslut** - Skapa intelligent logik utan manuell åtgärd
* **Omforma data** - Konvertera, formatera och ändra datatyper för att säkerställa kompatibilitet
* **Utför beräkningar** - Utför matematiska operationer och statistisk analys
* **Verifiera indata** - Kontrollera datakvalitet och fullständighet innan du vidtar någon åtgärd

## Funktioner per kategori

Bläddra bland funktioner ordnade efter deras primära syfte för att snabbt hitta rätt verktyg för dina behov.

### Adobe Experience Platform {#aep-functions}

**Målgruppssegmentering och målinriktning**

Utvärdera målgruppsmedlemskapet för att skapa personaliserade kundresor baserat på kundsegment som definieras i Adobe Experience Platform.

| Funktion | Beskrivning |
|----------|-------------|
| [inAudience](../functions/functioninaudience.md) | Kontrollera om en person tillhör en viss målgrupp |

[Visa information om Adobe Experience Platform-funktioner →](../functions/functioninaudience.md)

### Sammanställningsfunktioner {#aggregation-functions}

**Statistiska beräkningar och datasammanfattning**

Utför beräkningar på uppsättningar av värden för att få insikter som medelvärden, antal, summor och min/max-värden. Grundläggande för datadrivet beslutsfattande.

| Funktion | Beskrivning |
|----------|-------------|
| [avg](../functions/aggregation-functions.md#avg) | Beräkna genomsnittsvärde |
| [count](../functions/aggregation-functions.md#count) | Räkna element som inte är null |
| [countOnlyNull](../functions/aggregation-functions.md#countOnlyNull) | Endast null-värden |
| [countWithNull](../functions/aggregation-functions.md#countWithNull) | Räkna alla element inklusive null |
| [distinctCount](../functions/aggregation-functions.md#distinctCount) | Räkna unika värden som inte är null |
| [distinctCountWithNull](../functions/aggregation-functions.md#distinctCountWithNull) | Räkna unika värden inklusive null |
| [max](../functions/aggregation-functions.md#max) | Sök efter maxvärde |
| [min](../functions/aggregation-functions.md#min) | Sök efter minimivärde |
| [sum](../functions/aggregation-functions.md#sum) | Beräkna totalsumma |

[Visa alla aggregeringsfunktioner →](../functions/aggregation-functions.md)

### Konverteringsfunktioner {#conversion-functions}

**Datatypsomformning**

Konvertera data mellan olika typer (sträng, heltal, decimal, boolesk, datum, varaktighet) för att säkerställa kompatibilitet mellan operationer och datakällor.

| Funktion | Beskrivning |
|----------|-------------|
| [toBool](../functions/conversion-functions.md#toBool) | Konvertera till boolesk |
| [toDateOnly](../functions/conversion-functions.md#toDateOnly) | Konvertera endast till datum (ingen tid) |
| [toDateTime](../functions/conversion-functions.md#toDateTime) | Konvertera till datum med tid |
| [toDateTimeOnly](../functions/conversion-functions.md#toDateTimeOnly) | Konvertera till datum/tid utan tidszon |
| [toDecimal](../functions/conversion-functions.md#toDecimal) | Konvertera till decimaltal |
| [toDuration](../functions/conversion-functions.md#toDuration) | Konvertera till varaktighet |
| [toInteger](../functions/conversion-functions.md#toInteger) | Konvertera till heltal |
| [toString](../functions/conversion-functions.md#toString) | Konvertera till sträng |

[Visa alla konverteringsfunktioner →](../functions/conversion-functions.md)

### Datumfunktioner {#date-functions}

**Datum- och tidsändring**

Arbeta med datum, tidpunkter och tidszoner för att skapa tidsbaserade villkor, schemalägga åtgärder och utföra tidsberäkningar.

| Funktion | Beskrivning |
|----------|-------------|
| [currentTimeInMillis](../functions/date-functions.md#currentTimeInMillis) | Hämta aktuell tid i millisekunder |
| [inLastDays](../functions/date-functions.md#inLastDays) | Kontrollera om datumet ligger inom de senaste N dagarna |
| [inLastHours](../functions/date-functions.md#inLastHours) | Kontrollera om datumet ligger inom de senaste N timmarna |
| [inLastMonths](../functions/date-functions.md#inLastMonths) | Kontrollera om datumet ligger inom de senaste N månaderna |
| [inLastYears](../functions/date-functions.md#inLastYears) | Kontrollera om datumet ligger inom de senaste N åren |
| [inNextDays](../functions/date-functions.md#inNextDays) | Kontrollera om datumet ligger inom nästa N dagar |
| [inNextHours](../functions/date-functions.md#inNextHours) | Kontrollera om datumet ligger inom nästa N timmar |
| [inNextMonths](../functions/date-functions.md#inNextMonths) | Kontrollera om datumet ligger inom nästa N-månad |
| [inNextYears](../functions/date-functions.md#inNextYears) | Kontrollera om datumet infaller inom de följande N åren |
| [now](../functions/date-functions.md#now) | Hämta aktuellt datum/tid |
| [nowWithDelta](../functions/date-functions.md#nowWithDelta) | Hämta aktuell tid med förskjutning |
| [setHours](../functions/date-functions.md#setHours) | Ange specifika timmar i datum/tid |
| [setDays](../functions/date-functions.md#setDays) | Ange specifika dagar i datum/tid |
| [updateTimeZone](../functions/date-functions.md#updateTimeZone) | Uppdatera tidszon för datum/tid |

[Visa alla datumfunktioner →](../functions/date-functions.md)

### Listfunktioner {#list-functions}

**Samlingsändring och -analys**

Filtrera, sortera, omforma och analysera arrayer och listor för att arbeta med komplexa datastrukturer och utföra angivna åtgärder.

| Funktion | Beskrivning |
|----------|-------------|
| [distinct](../functions/list-functions.md#distinct) | Hämta unika värden (exkluderar null) |
| [distinctWithNull](../functions/list-functions.md#distinctWithNull) | Hämta unika värden (inklusive null) |
| [filter](../functions/list-functions.md#filter) | Filterlista baserad på villkor |
| [getListItem](../functions/list-functions.md#getListItem) | Hämta objekt vid specifikt index |
| [in](../functions/list-functions.md#in) | Kontrollera om värdet finns i listan |
| [överlappa](../functions/list-functions.md#intersect) | Söka efter gemensamma element mellan listor |
| [gräns](../functions/list-functions.md#limit) | Begränsa antalet returnerade objekt |
| [listSize](../functions/list-functions.md#listSize) | Hämta liststorlek |
| [serializeList](../functions/list-functions.md#serializeList) | Konvertera lista till sträng |
| [sort](../functions/list-functions.md#sort) | Sortera listelement |

[Visa alla listfunktioner →](../functions/list-functions.md)

### Matematiska funktioner {#math-functions}

**Matematiska åtgärder**

Utför numeriska beräkningar och omvandlingar för databearbetning och affärslogik.

| Funktion | Beskrivning |
|----------|-------------|
| [random](../functions/math-functions.md#random) | Generera slumptal (0-1) |
| [round](../functions/math-functions.md#round) | Avrunda till närmaste heltal |

[Visa alla matematiska funktioner →](../functions/math-functions.md)

### Strängfunktioner {#string-functions}

**Textredigering och validering**

Bearbeta, omvandla, söka och validera textdata för att skapa dynamiskt innehåll och villkorslogik.

| Funktion | Beskrivning |
|----------|-------------|
| [concat](../functions/string-functions.md#concat) | Sammanfoga strängar |
| [contain](../functions/string-functions.md#contain) | Kontrollera om strängen innehåller en delsträng |
| [containIgnoreCase](../functions/string-functions.md#containIgnoreCase) | Kontrollen innehåller (skiftlägesokänslig) |
| [endWith](../functions/string-functions.md#endWith) | Kontrollera om strängen slutar med suffix |
| [endWithIgnoreCase](../functions/string-functions.md#endWithIgnoreCase) | Kontrolländpunkter med (skiftlägesokänslig) |
| [equalIgnoreCase](../functions/string-functions.md#equalIgnoreCase) | Jämför strängar (skiftlägeskänsliga) |
| [indexOf](../functions/string-functions.md#indexOf) | Sök den första förekomstpositionen |
| [isEmpty](../functions/string-functions.md#isEmpty) | Kontrollera om strängen är tom |
| [isNotEmpty](../functions/string-functions.md#isNotEmpty) | Kontrollera om strängen inte är tom |
| [lastIndexOf](../functions/string-functions.md#lastIndexOf) | Sök efter den sista förekomstpositionen |
| [length](../functions/string-functions.md#length) | Hämta stränglängd |
| [lower](../functions/string-functions.md#lower) | Konvertera till gemener |
| [matchRegExp](../functions/string-functions.md#matchRegExp) | Matcha reguljärt uttryck |
| [notEqualIgnoreCase](../functions/string-functions.md#notEqualIgnoreCase) | Kontrollen är inte lika med (skiftlägesokänslig) |
| [replace](../functions/string-functions.md#replace) | Ersätt första förekomsten |
| [replaceAll](../functions/string-functions.md#replaceAll) | Ersätt alla förekomster |
| [split](../functions/string-functions.md#split) | Dela upp sträng i array |
| [startWith](../functions/string-functions.md#startWith) | Kontrollera om strängen börjar med prefix |
| [startWithIgnoreCase](../functions/string-functions.md#startWithIgnoreCase) | Kontrollen börjar med (skiftlägesokänslig) |
| [substr](../functions/string-functions.md#substr) | Extrahera delsträng |
| [trim](../functions/string-functions.md#trim) | Ta bort inledande/avslutande blanksteg |
| [upper](../functions/string-functions.md#upper) | Konvertera till versaler |
| [uuid](../functions/string-functions.md#uuid) | Generera UUID |

[Visa alla strängfunktioner →](../functions/string-functions.md)

## Nästa steg

Nu när du förstår vilka funktioner som finns tillgängliga kan du utforska:

* **[Avancerad uttrycksredigerare](expressionadvanced.md)** - Lär dig hur du skapar komplexa uttryck med den avancerade redigeraren
* **[Uttryckssyntax](generalities.md)** - bemästra syntaxreglerna för att skriva reseuttryck
* **[Operatorer](operators.md)** - Identifiera operatorer som du kan använda med funktioner för att skapa logik
* **[Fältreferenser](field-references.md)** - Lär dig hur du refererar till datafält i uttryck
