---
title: Kom igång med hjälp av hjälpfunktioner
description: Journey Optimizer Helper functions library
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: 9b0b0d8e-a819-4d2e-a241-f3c4d104eab9
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '1344'
ht-degree: 1%

---

# Kom igång med hjälp av hjälpfunktioner{#functionsL}

Använd [!DNL Journey Optimizer] mallspråk för att utföra dataåtgärder, t.ex. beräkningar, dataformatering eller konvertering, villkor och hantera dem i personaliseringssammanhang. Läs riktlinjerna för syntaxen för personalisering i [den här sidan](../personalization-syntax.md).

➡️ [Upptäck hur du använder hjälpfunktioner](#video) (video)

Mallspråk används i hjälpfunktioner som är tillgängliga i listrutan för anpassning i uttrycksredigeraren, enligt nedan:

![](../assets/access-helper-functions.png)

I [!DNL Journey Optimizer] Hjälpfunktionerna i uttrycksredigeraren är grupperade i tre kategorier: [Funktioner](#functions-helper), [Hjälpmedel](#helper-helper) och [Operatorer](#operators-helper).

Välj en kategori för att komma åt underkategorier och funktioner.

Åtkomst till underkategorier genom att klicka på `>` ikon. Välj en funktion genom att klicka på `+` ikon: funktionen läggs automatiskt till på skärmen för anpassning.

Klicka på `...` om du vill visa beskrivningen av funktionen och lägga till den i dina favoriter. [Läs mer](../personalize.md#fav)

## Funktioner{#functions-helper}

### Arrayfunktioner

<table>
    <tr>
        <td><a href="aggregation.md#average">Genomsnittlig</a></td><td>Den här funktionen returnerar det aritmetiska medelvärdet för alla markerade värden i arrayen</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#in">I</a></td><td>Den här funktionen används för att avgöra om ett objekt är medlem i en array eller lista</td>
    </tr>
    <tr>
        <td><a href="aggregation.md#min">Minimum</a></td><td>Den här funktionen returnerar det minsta av alla markerade värden i arrayen</td>
    </tr>
    <tr>
        <td><a href="aggregation.md#count">Antal</a></td><td>Den här funktionen returnerar antalet element i den angivna arrayen</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#includes">Inkluderar</a></td><td>Den här funktionen avgör om en array eller lista innehåller ett visst objekt</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#notin">Inte i</a></td><td>Den här funktionen avgör om ett objekt inte är medlem i en array eller lista</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#distinct">Distinkt</a></td><td>Den här funktionen hämtar värden från en array eller en lista med dubblettvärden borttagna</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#intersects">Överlappningar</a></td><td>Den här funktionen avgör om två arrayer eller listor har minst en gemensam medlem</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#subset">Delmängd av</a></td><td>Den här funktionen avgör om en viss array (array A) är en delmängd av en annan array (array B), d.v.s. om alla element i array A är element i array B</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#head">Första objektet</a></td><td>Den här funktionen returnerar det första objektet i en array eller lista</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#last-n">Senaste n i matris</a></td><td>Den här funktionen returnerar de sista "N"-objekten i en array, sorterade i stigande ordning baserat på det givna numeriska uttrycket</td>
    </tr>
    <tr>
        <td><a href="aggregation.md#sum">Summa</a></td><td>Den här funktionen returnerar summan av alla markerade värden i arrayen</td>
    </tr>
    <tr>
        <td><a href="arrays-list.md#first-n">Första n i matris</a></td><td>Den här funktionen returnerar de första "N"-objekten i en array, sorterade i stigande ordning baserat på det givna numeriska uttrycket</td>
    </tr>
    <tr>
        <td><a href="aggregation.md#max">Maximal</a></td><td>Den här funktionen returnerar det största av alla markerade värden i en array</td>
    </tr>
    <tr>
    <td><a href="arrays-list.md#superset">Supermängd till</a></td><td>Den här funktionen avgör om en viss array (array A) är en överordnad mängd till en annan array (array B), d.v.s. om den arrayen A innehåller alla element i array B</td>
    </tr>
</table>

### Funktioner för datum och tid{#date-functions}

<table>
    <tr>
        <td><a href="dates.md#age">Ålder</a></td><td>Den här funktionen hämtar åldern från ett visst datum</td>
    </tr>
    <tr>
        <td><a href="dates.md#current">Aktuell tid i millisekunder</a></td><td>Den här funktionen hämtar aktuell tid i epok millisekunder</td>
    </tr>
    <tr>
        <td><a href="dates.md#date-diff">Datumdifferens</a></td><td>Den här funktionen hämtar skillnaden mellan två datum i antal dagar</td>
    </tr>
    <tr>
        <td><a href="dates.md#day-week">Veckodag</a></td><td>Den här funktionen hämtar veckodag</td>
    </tr>
    <tr>
        <td><a href="dates.md#day-year">Dag på året</a></td><td>Den här funktionen hämtar dagen på året</td>
    </tr>
    <tr>
        <td><a href="dates.md#format-date">Formateringsdatum</a></td><td>Den här funktionen formaterar ett datum-/tidsvärde</td>
    </tr>
    <tr>
        <td><a href="dates.md#set-days">Ange dagar</a></td><td>Den här funktionen anger dag i månaden för angivet datum/tid</td>
    </tr>
    <tr>
        <td><a href="dates.md#set-hours">Ange dagar</a></td><td>Den här funktionen ställer in timmen för datum-/tidsvärdet</td>
    </tr>
    <tr>
        <td><a href="dates.md#to-utc">Till UTC</a></td><td>Den här funktionen konverterar en datetime till UTC</td>
    </tr>
    <tr>
        <td><a href="dates.md#week-of-year">Vecka på året</a></td><td>Den här funktionen returnerar årets vecka</td>
    </tr>
</table>
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

**Objektfunktioner**

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
        <td><a href="string.md#encode64">Koda 64</a></td><td>Den här funktionen används för att koda eller avkoda en sträng</td>
    </tr>
    <tr>
        <td><a href="string.md#endsWith">Slutar med</a></td><td>Den här funktionen används för att avgöra om en sträng avslutas med en angiven delsträng</td>
    </tr>
        </tr>
    <tr>
        <td><a href="string.md#equals">Är lika med</a></td><td>Den här funktionen används för att avgöra om en sträng inte börjar med en angiven delsträng, med skiftlägeskänslighet</td>
    </tr>
    <tr>
        <td><a href="string.md#equalsIgnoreCase">Lika med Ignorera skiftläge</a></td><td>Den här funktionen används för att avgöra om en sträng inte börjar med en angiven delsträng, utan skiftlägeskänslighet</td>
    </tr>
    <tr>
        <td><a href="string.md#extractEmailDomain">Extrahera e-postdomän</a></td><td>Den här funktionen används för att extrahera domänen för en e-postadress</td>
    </tr>
    <tr>
        <td><a href="string.md#isEmpty">IsEmpty</a></td><td>Den här funktionen används för att kontrollera om en sträng eller ett uttryck är tomt.</td>
    </tr>
    <tr>
        <td><a href="string.md#leftTrim">Vänster trimning</a></td><td>Den här funktionen tar bort blanksteg från början av en sträng</td>
    </tr>
    <tr>
        <td><a href="string.md#length">Length</a></td><td>Den här funktionen används för att hämta antalet tecken i en sträng eller ett uttryck</td>
    </tr>
    <tr>
        <td><a href="string.md#like">Gilla</a></td><td>Den här funktionen används för att avgöra om en sträng matchar ett angivet mönster</td>
    </tr>
    <tr>
        <td><a href="string.md#lower">Gemener</a></td><td>Den här funktionen konverterar en sträng till gemener</td>
    </tr>
    <tr>
        <td><a href="string.md#matches">Matchar</a></td><td>Den här funktionen används för att avgöra om en sträng matchar ett visst reguljärt uttryck</td>
    </tr>
    <tr>
        <td><a href="string.md#notEqualTo">Inte lika med</a></td><td>Den här funktionen används för att avgöra om en sträng inte är lika med den angivna strängen</td>
    </tr>
    <tr>
        <td><a href="string.md#regexGroup">Grupp för reguljära uttryck</a></td><td>Den här funktionen används för att extrahera specifik information baserat på det reguljära uttrycket</td>
    </tr>
    <tr>
        <td><a href="string.md#replace">Replace</a></td><td>Den här funktionen ersätter en given delsträng i en sträng med en annan delsträng</td>
    </tr>
    <tr>
        <td><a href="string.md#replaceAll">Ersätt alla</a></td><td>Den här funktionen ersätter alla delsträngar i en text som matchar"target" med den angivna strängen för"ersättning"</td>
    </tr>
    <tr>
        <td><a href="string.md#rightTrim">Högertrimning</a></td><td>Den här funktionen tar bort blanksteg från slutet av en sträng </td>
    </tr>
    <tr>
        <td><a href="string.md#split">Dela</a></td><td>Den här funktionen används för att dela en sträng med ett visst tecken</td>
    </tr>
    <tr>
        <td><a href="string.md#startsWith">Börjar med</a></td><td>Den här funktionen används för att avgöra om en sträng börjar med en angiven delsträng</td>
    </tr>
    <tr>
        <td><a href="string.md#titleCase">Inledande versal</a></td><td>Den här funktionen används för att ge inledande versal i varje ord i en sträng</td>
    </tr>
    <tr>
        <td><a href="string.md#trim">Rensa</a></td><td>Den här funktionen tar bort blanksteg från början och slutet av en sträng</td>
    </tr>
    <tr>
        <td><a href="string.md#upper">Versaler</a></td><td>Den här funktionen konverterar en sträng till versaler</td>
    </tr>
</table>


## Hjälpmedel{#helper-helper}

Hjälpprogram beskrivs i [den här sidan](helpers.md).


<table>
    <tr>
        <td><a href="helpers.md#each">Varje</a></td><td>Den här funktionen används för att iterera över en array</td>
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
        <td><a href="arithmetic-functions.md#add">Tillägg</a></td><td>Den här operatorn används för att hitta summan av två argumentuttryck</td>
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
        <td><a href="operators.md#not">If</a></td><td>Operatorn löser ett uttryck beroende på om ett angivet villkor är sant</td>
    </tr>
    <tr>
        <td><a href="operators.md#not">Inte</a></td><td>Den här operatorn skapar en logisk negation</td>
    </tr>
    <tr>
        <td><a href="operators.md#or">eller</a></td><td>Den här operatorn skapar en logisk koppling</td>
    </tr>
</table>


### Jämförelsefunktioner {#comparison-functions}

Jämförelsefunktioner används för att jämföra mellan olika uttryck och värden och returnera sant eller falskt efter det.

<table>
    <tr>
        <td><a href="operators.md#and">Lika med</a></td><td>Den här åtgärden kontrollerar om värdena är lika</td>
    </tr>
    <tr>
        <td><a href="operators.md#greaterthan">Greater than</a></td><td>Den här operatorn kontrollerar om det första värdet är större än det andra värdet</td>
    </tr>
    <tr>
        <td><a href="operators.md#greaterthanorequal">Större eller lika med</a></td><td>Den här operatorn kontrollerar om det första värdet är större än eller lika med det andra värdet</td>
    </tr>
    <tr>
        <td><a href="operators.md#notequal">Inte lika med</a></td><td>Den här operatorn kontrollerar om det angivna uttrycket inte är lika med värdet</td>
    </tr>
    <tr>
        <td><a href="operators.md#lessthanorequal">Mindre än eller lika med</a> </td><td>Den här operatorn kontrollerar om det första värdet är mindre än eller lika med det andra värdet</td>
    </tr>
</table>

## Instruktionsvideo{#video}

Lär dig omvandla personaliseringsvärden med hjälp av hjälpfunktioner för personalisering och förstå olika användningsexempel för hjälpfunktioner.

>[!VIDEO](https://video.tv.adobe.com/v/334244?quality=12)