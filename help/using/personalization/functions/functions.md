---
title: Kom igång med hjälp av hjälpfunktioner
description: Journey Optimizer Helper functions library
feature: Personalization
topic: Personalization
role: Developer
level: Experienced
exl-id: 9b0b0d8e-a819-4d2e-a241-f3c4d104eab9
source-git-commit: 8ca1c995bc38b110fa07573f922906c775fd5e6f
workflow-type: tm+mt
source-wordcount: '2434'
ht-degree: 0%

---

# Kom igång med hjälp av hjälpfunktioner{#functions}

Använd mallspråket [!DNL Journey Optimizer] för att utföra dataåtgärder, till exempel beräkningar, dataformatering eller konvertering, villkor och ändra dem i personaliseringssammanhang. Lär dig riktlinjerna för syntaxen för personalisering på [den här sidan](../personalization-syntax.md).

➡️ [Lär dig använda hjälpfunktioner i den här videon](#video)

Mallspråk används i hjälpfunktioner som finns i personaliseringslistrutan i personaliseringsredigeraren, enligt nedan:

![](../assets/access-helper-functions.png)

Hjälpfunktionerna i redigeraren för anpassning av [!DNL Journey Optimizer] är grupperade i tre kategorier: [Funktioner](#functions-helper), [Hjälpprogram](#helper-helper) och [Operatorer](#operators-helper).

Välj en kategori för att komma åt underkategorier och funktioner.

Du får åtkomst till underkategorier genom att klicka på ikonen `>`. Välj en funktion genom att klicka på ikonen `+`: funktionen läggs automatiskt till på anpassningsskärmen.

Klicka på ikonen `...` för att visa beskrivningen av funktionen och lägga till den i dina favoriter. [Läs mer](../personalize.md#fav)

>[!NOTE]
>
>De funktioner och funktioner som är tillgängliga i personaliseringsredigeraren skiljer sig från dem som finns i den avancerade uttrycksredigeraren [Journey](../../building-journeys/expression/expressionadvanced.md). Funktionen `now()` är till exempel bara tillgänglig i reseuttryck. [Läs mer](../../email/code-content.md#date-time-limitations)

## Funktioner{#functions-helper}

### Funktioner för aggregering och array

<table>
    <tr>
        <td><a href="aggregation.md#average">Genomsnittlig</a></td><td>Den här funktionen returnerar det aritmetiska medelvärdet för alla markerade värden i arrayen</td>
    </tr>
    <tr>
        <td><a href="aggregation.md#count">Antal</a></td><td>Den här funktionen returnerar antalet element i den angivna arrayen</td>
    </tr>
    <tr>
        <td><a href="aggregation.md#count-only-null">Endast antal null</a></td><td>Den här funktionen räknar antalet null-värden i listan.</td>
    </tr>
    <tr>
        <td><a href="aggregation.md#count-with-null">Antal med null</a></td><td>Den här funktionen räknar alla element i listan inklusive null-värden</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#distinct">Distinkt</a></td><td>Den här funktionen hämtar värden från en array eller en lista med dubblettvärden borttagna</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#distinct-count-with-null">Distinkt antal med null</a></td><td>Den här funktionen räknar antalet olika värden inklusive null-värden</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#head">Första objektet</a></td><td>Den här funktionen returnerar det första objektet i en array eller lista</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#first-n">Första n i matris</a></td><td>Den här funktionen returnerar de första "N"-objekten i en array, sorterade i stigande ordning baserat på det givna numeriska uttrycket</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#in">I</a></td><td>Den här funktionen används för att avgöra om ett objekt är medlem i en array eller lista</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#includes">Inkluderar</a></td><td>Den här funktionen avgör om en array eller lista innehåller ett visst objekt</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#intersects">Överlappningar</a></td><td>Den här funktionen avgör om två arrayer eller listor har minst en gemensam medlem</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#last-n">Senaste n i matris</a></td><td>Den här funktionen returnerar de sista "N"-objekten i en array, sorterade i stigande ordning baserat på det givna numeriska uttrycket</td>
    </tr>
    <tr>
        <td><a href="aggregation.md#max">Maximal</a></td><td>Den här funktionen returnerar det största av alla markerade värden i en array</td>
    </tr>
    <tr>
        <td><a href="aggregation.md#min">Minimum</a></td><td>Den här funktionen returnerar det minsta av alla markerade värden i arrayen</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#notin">Inte i</a></td><td>Den här funktionen avgör om ett objekt inte är medlem i en array eller lista</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#subset">Delmängd av</a></td><td>Den här funktionen avgör om en viss array (array A) är en delmängd av en annan array (array B), dvs. om alla element i array A är element i array B</td>
    </tr>
    <tr>
        <td><a href="aggregation.md#sum">Summa</a></td><td>Den här funktionen returnerar summan av alla markerade värden i arrayen</td>
    </tr>
    <tr>
    <td><a href="arrays-list.md#superset">Supermängd till</a></td><td>Den här funktionen avgör om en viss array (array A) är en överordnad mängd till en annan array (array B), dvs. om den arrayen A innehåller alla element i array B</td>
    </tr>
</table>

### Funktioner för datum och tid{#date-functions}

<table>
    <tr>
        <td><a href="dates.md#add-days">Lägg till dagar</a></td><td>Den här funktionen justerar ett givet datum med ett angivet antal dagar, och använder positiva värden för att öka och negativa värden för minskning.</td>
    </tr>
    <tr>
        <td><a href="dates.md#add-hours">Lägg till timmar</a></td><td>Den här funktionen justerar ett givet datum med ett angivet antal timmar, och använder positiva värden för att öka och negativa värden för minskning.</td>
    </tr>
    <tr>
        <td><a href="dates.md#add-minutes">Lägg till minuter</a></td><td>Den här funktionen justerar ett givet datum med ett angivet antal minuter, och använder positiva värden för att öka och negativa värden för att minska.</td>
    </tr>
    <tr>
        <td><a href="dates.md#add-months">Lägg till månader</a></td><td>Den här funktionen justerar ett givet datum med ett angivet antal månader, och använder positiva värden för att öka och negativa värden för minskning.</td>
    </tr>
    <tr>
        <td><a href="dates.md#add-seconds">Lägg till sekunder</a></td><td>Den här funktionen justerar ett givet datum med ett angivet antal sekunder och använder positiva värden för att öka och negativa värden för att minska.</td>
    </tr>
    <tr>
        <td><a href="dates.md#add-years">Lägg till år</a></td><td>Den här funktionen justerar ett givet datum med ett angivet antal år och använder positiva värden för ökning och negativa värden för minskning.</td>
    </tr>
    <tr>
        <td><a href="dates.md#age">Ålder</a></td><td>Den här funktionen hämtar åldern från ett visst datum.</td>
    </tr>
    <tr>
        <td><a href="dates.md#age-days">Ålder i dagar</a></td><td>Den här funktionen beräknar ett visst datums ålder i dagar, dvs. antalet dagar som förflutit mellan det angivna datumet och det aktuella datumet, negativa för framtida datum och positiva för tidigare datum.</td>
    </tr>
    <tr>
        <td><a href="dates.md#age-months">Ålder i månader</a></td><td>Med den här funktionen beräknas åldern för ett givet datum i månader, dvs. antalet månader som förflutit mellan det angivna datumet och det aktuella datumet, negativa för framtida datum och positiva för tidigare datum.</td>
    </tr>
    <tr>
        <td><a href="dates.md#compare-dates">Jämför datum</a></td><td>Den här funktionen jämför det första indatadatumet med det andra. Returnerar 0 om date1 är lika med date2, -1 om date1 kommer före date2 och 1 om date1 kommer efter date2.</td>
    </tr>
    <tr>
        <td><a href="dates.md#convert-zoned-date-time">Konvertera ZonedDateTime</a></td><td>Den här funktionen konverterar ett datum/tid till en given tidszon.</td>
    </tr>
    <tr>
        <td><a href="dates.md#current">Aktuell tid i millisekunder</a></td><td>Den här funktionen hämtar aktuell tid i epok millisekunder.</td>
    </tr>
    <tr>
        <td><a href="dates.md#date-diff">Datumdifferens</a></td><td>Den här funktionen hämtar skillnaden mellan två datum i antal dagar.</td>
    </tr>
    <tr>
        <td><a href="dates.md#day-month">Dag i månaden</a></td><td>Den här funktionen returnerar talet som representerar dagen i månaden.</td>
    </tr>
    <tr>
        <td><a href="dates.md#day-week">Veckodag</a></td><td>Den här funktionen hämtar veckodag.</td>
    </tr>
    <tr>
        <td><a href="dates.md#day-year">Dag på året</a></td><td>Den här funktionen hämtar dagen på året.</td>
    </tr>
    <tr>
        <td><a href="dates.md#diff-seconds">Skillnad i sekunder</a></td><td>Den här funktionen returnerar skillnaden mellan två datum i sekunder.</td>
    </tr>
    <tr>
        <td><a href="dates.md#extract-hours">Extrahera timmar</a></td><td>Den här funktionen extraherar timkomponenten från en viss tidsstämpel.</td>
    </tr>
    <tr>
        <td><a href="dates.md#extract-minutes">Extrahera minuter</a></td><td>Den här funktionen extraherar minutkomponenten från en viss tidsstämpel.</td>
    </tr>
    <tr>
        <td><a href="dates.md#extract-months">Extrahera månader</a></td><td>Den här funktionen extraherar månadskomponenten från en viss tidsstämpel.</td>
    </tr>
    <tr>
        <td><a href="dates.md#extract-seconds">Extrahera sekunder</a></td><td>Den här funktionen extraherar den andra komponenten från en viss tidsstämpel.</td>
    </tr>
    <tr>
        <td><a href="dates.md#format-date">Formateringsdatum</a></td><td>Den här funktionen formaterar ett datum/tid-värde.</td>
    </tr>
    <tr>
        <td><a href="dates.md#format-date-locale">Formatera datum med språkstöd</a></td><td>Den här funktionen formaterar ett datum- och tidsvärde till motsvarande språkkänsliga representation, dvs. i ett önskat språkområde.</td>
    </tr>
    <tr>
        <td><a href="dates.md#get-current-zoned-date-time">Hämta CurrentZonedDateTime</a></td><td>Den här funktionen returnerar aktuellt datum och tid med tidszonsinformation.</td>
    </tr>
    <tr>
        <td><a href="dates.md#hours-difference">Timskillnad</a></td><td>Den här funktionen returnerar skillnaden mellan två datum i timmar.</td>
    </tr>
    <tr>
        <td><a href="dates.md#diff-minutes">Minutdifferens</a></td><td>Den här funktionen returnerar skillnaden mellan två datum i minuter.</td>
    </tr>
    <tr>
        <td><a href="dates.md#months-difference">Månadsskillnad</a></td><td>Den här funktionen returnerar skillnaden mellan två datum i månader.</td>
    </tr>
    <tr>
        <td><a href="dates.md#set-days">Ange dagar</a></td><td>Den här funktionen anger dag i månaden för angivet datum/tid.</td>
    </tr>
    <tr>
        <td><a href="dates.md#set-hours">Ange timmar</a></td><td>Den här funktionen anger timmen för datum-tid.</td>
    </tr>
    <tr>
        <td><a href="dates.md#to-date-time">Till datum och tid</a></td><td>Den här funktionen konverterar en sträng till ett datum. Det returnerar epokdatumet som utdata för ogiltiga indata.</td>
    </tr>
    <tr>
        <td><a href="dates.md#to-utc">Till UTC</a></td><td>Den här funktionen konverterar en datetime till UTC.</td>
    </tr>
    <tr>
        <td><a href="dates.md#truncate-day">Trunkera till början av dagen</a></td><td>Den här funktionen ändrar ett visst datum-tid genom att ställa in det till början av dagen med tiden inställd på 00:00.</td>
    </tr>
    <tr>
        <td><a href="dates.md#truncate-quarter">truncateToStartOfQuarter</a></td><td>Den här funktionen trunkerar ett datum-tid till den första dagen i kvartalet (t.ex. Jan 1, Apr 1, Jul 1, Oct 1) kl. 00:00.
</td>
    </tr>
    <tr>
        <td><a href="dates.md#truncate-week">truncateToStartOfWeek</a></td><td>Den här funktionen ändrar ett visst datum/tid genom att ställa in det till veckans början (måndag 00:00).</td>
    </tr>
    <tr>
        <td><a href="dates.md#truncate-year">truncateToStartOfYear</a></td><td>Den här funktionen ändrar ett visst datum/tid genom att trunkera det till årets första dag (1 januari) kl. 00:00.</td>
    </tr>
    <tr>
        <td><a href="dates.md#week-of-year">Vecka på året</a></td><td>Den här funktionen returnerar årets vecka</td>
    </tr>
    <tr>
        <td><a href="dates.md#diff-years">Årets skillnad</a></td><td>Den här funktionen returnerar skillnaden mellan två datum i termer av år.</td>
    </tr>
</table>

### Kartfunktioner {#map-functions}

<table>
    <tr>
        <td><a href="maps.md#get">Hämta</a></td><td>Den här funktionen används för att hämta värdet för en karta för en given nyckel</td>
    </tr>
    <tr>
        <td><a href="maps.md#keys">Tangenter</a></td><td>Den här funktionen används för att hämta alla nycklar för en given karta</td>
    </tr>
    <tr>
        <td><a href="maps.md#values">Värden</a></td><td>Den här funktionen hämtar alla värden för en given karta</td>
    </tr>
</table>

### Matematiska funktioner {#math-functions}

<table>
    <tr>
        <td><a href="math.md#absolute">Absolut</a></td><td>Den här funktionen formaterar alla tal i sin språkkänsliga representation.</td>
    </tr>
    <tr>
        <td><a href="math.md#format-number">Formatnummer</a></td><td>Den här funktionen formaterar alla tal i sin språkkänsliga representation.</td>
    </tr>
    <tr>
        <td><a href="math.md#random">Slumpmässig</a></td><td>Den här funktionen returnerar ett slumpvärde mellan 0 och 1</td>
    </tr>
    <tr>
        <td><a href="math.md#round-down">Avrunda nedåt</a></td><td>Den här funktionen avrundar ett tal nedåt</td>
    </tr>
    <tr>
        <td><a href="math.md#round-up">Avrunda uppåt</a></td><td>Den här funktionen avrundar ett tal</td>
    </tr>
    <tr>
    <td><a href="math.md#to-hex-string">Till hexadecimal sträng</a></td><td>Konverterar alla tal till dess hexadecimala sträng.</td>
    </tr>
    <tr>
    <td><a href="math.md#to-int">ToInt</a></td><td>Konverterar alla dessa typer (tal, double, int, long, float, short, byte, boolean, string) till ett heltal.</td>
    </tr>
    <tr>
        <td><a href="math.md#to-percentage">Till procent</a></td><td>Den här funktionen konverterar ett tal till procent</td>
    </tr>
    <tr>
        <td><a href="math.md#to-precision">Till precision</a></td><td>Den här funktionen konverterar ett tal till nödvändig precision</td>
    </tr>
    <tr>
        <td><a href="math.md#to-string">Till sträng</a></td><td>Den här funktionen konverterar alla tal till strängbeteckningen. </td>
    </tr>
</table>

### Objektfunktioner {#object-functions}

<table>
    <tr>
        <td><a href="objects.md#isNotNull">Är inte null</a></td><td>Den här funktionen används för att avgöra om det finns en objektreferens</td>
    </tr>
    <tr>
        <td><a href="objects.md#isNull">Är null</a></td><td>Den här funktionen används för att avgöra om en objektreferens inte finns</td>
    </tr>
</table>

### Strängfunktioner {#string-functions}

<table>
    <tr>
        <td><a href="string.md#camelCase">Camera Case</a></td><td>Den här funktionen används för att ge den första bokstaven i varje ord i en sträng inledande versal</td>
    </tr>
    <tr>
        <td><a href="string.md#char-code-at">Teckenkod på</a></td><td>Den här funktionen returnerar ASCII-värdet för ett tecken, precis som funktionen charCodeAt i JavaScript</td>
    </tr>
    <tr>
        <td><a href="string.md#concat">Concat</a></td><td>Den här funktionen används för att kombinera två strängar till en</td>
    </tr>
    <tr>
        <td><a href="string.md#contains">Innehåller</a></td><td>Den här funktionen används för att avgöra om en sträng innehåller en angiven delsträng</td>
    </tr>
    <tr>
        <td><a href="string.md#doesNotContain">Innehåller inte</a></td><td>Den här funktionen används för att avgöra om en sträng inte innehåller en angiven delsträng</td>
    </tr>
    <tr>
        <td><a href="string.md#doesNotEndWith">Slutar inte med</a></td><td>Den här funktionen används för att avgöra om en sträng inte avslutas med en angiven delsträng</td>
    </tr>
    <tr>
        <td><a href="string.md#doesNotStartWith">Börjar inte med</a></td><td>Den här funktionen används för att avgöra om en sträng inte börjar med en angiven delsträng</td>
    </tr>
    <tr>
        <td><a href="string.md#encode64">Koda 64</a></td><td>Den här funktionen används för att koda en sträng</td>
    </tr>
    <tr>
        <td><a href="string.md#endsWith">Slutar med</a></td><td>Den här funktionen används för att avgöra om en sträng avslutas med en angiven delsträng</td>
    </tr>
        </tr>
    <tr>
        <td><a href="string.md#equals">Lika med</a></td><td>Den här funktionen används för att avgöra om en sträng inte börjar med en angiven delsträng, med skiftlägeskänslighet</td>
    </tr>
    <tr>
        <td><a href="string.md#equalsIgnoreCase">Lika med Ignorera skiftläge</a></td><td>Den här funktionen används för att avgöra om en sträng inte börjar med en angiven delsträng, utan skiftlägeskänslighet</td>
    </tr>
    <tr>
        <td><a href="string.md#extractEmailDomain">Extract Email Domain</a></td><td>Den här funktionen används för att extrahera domänen för en e-postadress</td>
    </tr>
    <tr>
        <td><a href="string.md#format-currency">Formatera valuta</a></td><td>Den här funktionen konverterar alla tal till motsvarande språkkänsliga valutarepresentation beroende på vilket språk som skickas som en sträng i det andra argumentet</td>
    </tr>
    <tr>
        <td><a href="string.md#get-url-host">Hämta URL-värd</a></td><td>Den här funktionen används för att hämta URL-värden.</td>
    </tr>
    <tr>
        <td><a href="string.md#get-url-path">Hämta URL-sökväg</a></td><td>Den här funktionen används för att hämta URL-sökvägen</td>
    </tr>
    <tr>
        <td><a href="string.md#get-url-protocol">Hämta URL-protokoll</a></td><td>Den här funktionen används för att hämta URL-protokoll</td>
    </tr>
    <tr>
        <td><a href="string.md#index-of">index för</a></td><td>Den här funktionen returnerar positionen (i det första argumentet) för den första förekomsten av den andra parametern. Returnerar -1 om ingen matchning finns</td>
    </tr>
    <tr>
        <td><a href="string.md#isEmpty">IsEmpty</a></td><td>Den här funktionen används för att kontrollera om en sträng eller ett uttryck är tomt.</td>
    </tr>
    <tr>
        <td><a href="string.md#is-not-empty">Är inte tom</a></td><td>Den här funktionen returnerar true om strängen i parametern inte är tom.</td>
    </tr>
    <tr>
        <td><a href="string.md#last-index-of">Senaste index för</a></td><td>Den här funktionen returnerar positionen (i det första argumentet) för den sista förekomsten av den andra parametern. Returnerar -1 om det inte finns någon matchning.</td>
    </tr>
    <tr>
        <td><a href="string.md#leftTrim">Vänster trimning</a></td><td>Den här funktionen tar bort blanksteg från början av en sträng</td>
    </tr>
    <tr>
        <td><a href="string.md#length">Längd</a></td><td>Den här funktionen används för att hämta antalet tecken i en sträng eller ett uttryck</td>
    </tr>
    <tr>
        <td><a href="string.md#like">Gilla</a></td><td>Den här funktionen används för att avgöra om en sträng matchar ett angivet mönster</td>
    </tr>
    <tr>
        <td><a href="string.md#lower">Gemener</a></td><td>Den här funktionen konverterar en sträng till gemener</td>
    </tr>
    <tr>
        <td><a href="string.md#mask">Mask</a></td><td>Den här funktionen används för att ersätta en del av en sträng med "X"-tecken.</td>
    </tr>
    <tr>
        <td><a href="string.md#matches">Matchar</a></td><td>Den här funktionen används för att avgöra om en sträng matchar ett visst reguljärt uttryck</td>
    </tr>
    <tr>
        <td><a href="string.md#md5">MD5</a></td><td>Den här funktionen returnerar md5-hash av indatasträngen.</td>
    </tr>
    <tr>
        <td><a href="string.md#notEqualTo">Inte lika med</a></td><td>Den här funktionen används för att avgöra om en sträng inte är lika med den angivna strängen</td>
    </tr>
    <tr>
        <td><a href="string.md#not-equal-with-ignore-case">Inte lika med Ignorera skiftläge</a></td><td>Den här funktionen jämför två strängar utan skiftläge.</td>
    </tr>
    <tr>
        <td><a href="string.md#regexGroup">Grupp för reguljära uttryck</a></td><td>Den här funktionen används för att extrahera specifik information baserat på det reguljära uttrycket</td>
    </tr>
    <tr>
        <td><a href="string.md#replace">Ersätt</a></td><td>Den här funktionen ersätter en given delsträng i en sträng med en annan delsträng</td>
    </tr>
    <tr>
        <td><a href="string.md#replaceAll">Ersätt alla</a></td><td>Den här funktionen ersätter alla delsträngar i en text som matchar"target" med den angivna strängen för"ersättning"</td>
    </tr>
    <tr>
        <td><a href="string.md#rightTrim">Högertrimning</a></td><td>Den här funktionen tar bort blanksteg från slutet av en sträng </td>
    </tr>
    <tr>
        <td><a href="string.md#sha256">SHA256</a></td><td>Den här funktionen beräknar och returnerar sha256-hash för en sträng.</td>
    </tr>
    <tr>
        <td><a href="string.md#split">Dela</a></td><td>Den här funktionen används för att dela en sträng med ett visst tecken</td>
    </tr>
    <tr>
        <td><a href="string.md#startsWith">Börjar med</a></td><td>Den här funktionen används för att avgöra om en sträng börjar med en angiven delsträng</td>
    </tr>
    <tr>
        <td><a href="string.md#string-to-date">Sträng till datum</a></td><td>Den här funktionen konverterar ett strängvärde till ett datum/tid-värde</td>
    </tr>
    <tr>
        <td><a href="string.md#string-to-integer">Sträng till heltal</a></td><td>Den här funktionen konverterar ett strängvärde till ett heltalsvärde.</td>
    </tr>
    <tr>
        <td><a href="string.md#string-to-number">Sträng till tal</a></td><td>Den här funktionen används för att konvertera en sträng till ett tal. Den returnerar samma sträng som utdata för ogiltiga indata.</td>
    </tr>
    <tr>
        <td><a href="string.md#sub-string">Delsträng</a></td><td>Den här funktionen returnerar delsträngen för stränguttrycket mellan startindexet och slutindexet.</td>
    </tr>
    <tr>
        <td><a href="string.md#titleCase">Inledande versal</a></td><td>Den här funktionen används för att ge inledande versal i varje ord i en sträng</td>
    </tr>
    <tr>
        <td><a href="string.md#to-bool">Till boolesk</a></td><td>Den här funktionen konverterar ett argumentvärde till ett booleskt värde, beroende på dess typ.</td>
    </tr>
    <tr>
        <td><a href="string.md#to-date-time">Till datum och tid</a></td><td>Den här funktionen används för att konvertera en sträng till ett datum. Det returnerar epokdatumet som utdata för ogiltiga indata.</td>
    </tr>
    <tr>
        <td><a href="string.md#to-date-time-only">Endast till datum och tid</a></td><td>Den här funktionen konverterar ett argumentvärde till ett värde som bara gäller för datum och tid. Det returnerar epokdatumet som utdata för ogiltiga indata.</td>
    </tr>
    <tr>
        <td><a href="string.md#trim">Rensa</a></td><td>Den här funktionen tar bort blanksteg från början och slutet av en sträng</td>
    </tr>
    <tr>
        <td><a href="string.md#upper">Versaler</a></td><td>Den här funktionen konverterar en sträng till versaler</td>
    </tr>
    <tr>
        <td><a href="string.md#url-decode">URL-avkodning</a></td><td>Den här funktionen används för att avkoda en URL-kodad sträng.</td>
    </tr>
    <tr>
        <td><a href="string.md#url-encode">URL-kodning</a></td><td>Den här funktionen används för att URL-koda en sträng.</td>
    </tr>
</table>


## Hjälpmedel{#helper-helper}

Hjälpprogram visas på [den här sidan](helpers.md).


<table>
    <tr>
        <td><a href="helpers.md#default">Standardreservvärde</a></td><td>Den här funktionen används för att återge en variabel med standardvärdet</td>
    </tr>
    <tr>
        <td><a href="helpers.md#each">Varje</a></td><td>Den här funktionen används för att iterera över en array</td>
    </tr>
    <tr>
        <td><a href="helpers.md#execution-metadata">Körningsmetadata</a></td><td>Den här hjälpen hämtar anpassade metadata för nyckelvärden vid meddelandeåtergivning så att de kan lagras i metadataobjektet för körning</td>
    </tr>
    <tr>
        <td><a href="helpers.md#if-function">If</a></td><td>Den här funktionen används för att definiera ett villkorsstyrt block - om uttrycket utvärderas som true återges blocket</td>
    </tr>
    <tr>
        <td><a href="helpers.md#let">Låt</a></td><td>Den här funktionen tillåter att ett uttryck lagras som en variabel som kan användas senare i en fråga</td>
    </tr>
   <tr>
        <td><a href="helpers.md#unless">Om</a></td><td>Den här funktionen används för att definiera ett villkorsstyrt block - om uttrycket returnerar false återges blocket</td>
    </tr>
    <tr>
        <td><a href="helpers.md#with">Med</a></td><td>Den här funktionen används för att ändra utvärderingstoken för malldel</td>
    </tr>
</table>

## Operatorer{#operators-helper}

### Aritmetiska funktioner {#arithmetic-helper}

Aritmetiska funktioner används för att utföra grundläggande beräkningar på värden.

<table>
    <tr>
        <td><a href="arithmetic-functions.md#add">Tillägg</a></td><td>Operatorn används för att hitta summan av två argumentuttryck</td>
    </tr>
    <tr>
        <td><a href="arithmetic-functions.md#divide">Dela</a></td><td>Den här operatorn används för att hitta kvoten av två argumentuttryck</td>
    </tr>
    <tr>
        <td><a href="arithmetic-functions.md#multiply">Multiplikation</a></td><td>Den här operatorn används för att hitta produkten av två argumentuttryck</td>
    </tr>
    <tr>
        <td><a href="arithmetic-functions.md#remainder">Återstående</a> </td><td>Den här operatorn används för att hitta resten efter att de två argumentuttrycken har delats</td>
    </tr>
    <tr>
        <td><a href="arithmetic-functions.md#substract">Subtraktion</a> </td><td>Den här operatorn hittar skillnaden mellan två uttryck</td>
    </tr>
</table>


### Booleska funktioner {#boolean-functions}

Booleska funktioner används för att utföra boolesk logik för olika element.

<table>
    <tr>
        <td><a href="operators.md#and">Och</a></td><td>Den här operatorn skapar en logisk koppling</td>
    </tr>
    <tr>
        <td><a href="operators.md#or">eller</a></td><td>Den här operatorn skapar en logisk koppling</td>
    </tr>
</table>


### Jämförelsefunktioner {#comparison-functions}

Jämförelsefunktioner används för att jämföra mellan olika uttryck och värden och returnera sant eller falskt efter det.

<table>
    <tr>
        <td><a href="operators.md#equals">Lika med</a></td><td>Den här åtgärden kontrollerar om värdena är lika</td>
    </tr>
    <tr>
        <td><a href="operators.md#greaterthan">Större än</a></td><td>Operatorn kontrollerar om det första värdet är större än det andra värdet</td>
    </tr>
    <tr>
        <td><a href="operators.md#greaterthanorequal">Större eller lika med</a></td><td>Operatorn kontrollerar om det första värdet är större än eller lika med det andra värdet</td>
    </tr>
    <tr>
        <td><a href="operators.md#lessthanorequal">Mindre än eller lika med </a> </td><td>Operatorn kontrollerar om det första värdet är mindre än eller lika med det andra värdet</td>
    </tr>
    <tr>
        <td><a href="operators.md#notequal">Inte lika med</a></td><td>Den här operatorn kontrollerar om det angivna uttrycket inte är lika med värdet</td>
    </tr>
</table>

## Instruktionsvideo{#video}

Lär dig omvandla personaliseringsvärden med hjälp av hjälpfunktioner för personalisering och förstå olika användningsexempel för hjälpfunktioner.

>[!VIDEO](https://video.tv.adobe.com/v/334244?quality=12)
