---
title: Bibliotek för strängfunktioner
description: Bibliotek för strängfunktioner
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: 8674ef9e-261b-49d9-800e-367f9f7ef979
source-git-commit: db7c57ce9f5c46d8beb6ff0037a8854fd136cb4a
workflow-type: tm+mt
source-wordcount: '1868'
ht-degree: 5%

---

# Strängfunktioner {#string}

Lär dig hur du använder strängfunktioner i uttrycksredigeraren.

## Camera Case {#camelCase}

The `camelCase` funktionen ändrar den första bokstaven i varje ord i en sträng till versal.

**Syntax**

```sql
{%= camelCase(string)%}
```

**Exempel**

Med följande funktion infogas den första bokstaven i ordet i profilens gatuadress.

```sql
{%= camelCase(profile.homeAddress.street) %}
```

## Teckenkod på {#char-code-at}

The `charCodeAt` funktionen returnerar ASCII-värdet för ett tecken, som funktionen charCodeAt i JavaScript. Den tar en sträng och ett heltal (som definierar positionen för tecknet) som indataargument och returnerar motsvarande ASCII-värde.

**Syntax**

```sql
{%= charCodeAt(string,int) %}: int
```

**Exempel**

Följande funktion returnerar ASCII-värdet för o, d.v.s. 111.

```sql
{%= charCodeAt("some", 1)%}
```

## Concat {#concate}

The `concat` funktionen kombinerar två strängar till en.

**Syntax**

```sql
{%= concat(string,string) %}
```

**Exempel**

Följande funktion kombinerar profilens ort och land i en enda sträng.

```sql
{%= concat(profile.homeAddress.city,profile.homeAddress.country) %}
```

## Innehåller {#contains}

The `contains` -funktionen används för att avgöra om en sträng innehåller en angiven delsträng.

**Syntax**

```sql
{%= contains(STRING_1, STRING_2, CASE_SENSITIVE) %}
```

| Argument | Beskrivning |
| --------- | ----------- |
| `STRING_1` | Strängen som kontrollen ska utföras på. |
| `STRING_2` | Den sträng som ska sökas efter i den första strängen. |
| `CASE_SENSITIVE` | En valfri parameter som avgör om kontrollen är skiftlägeskänslig. Möjliga värden: true (standard) / false. |

**Exempel**

* Följande funktion kontrollerar om profilens förnamn innehåller bokstaven A (i versaler eller gemener). Om så är fallet returneras true, annars returneras false.

   ```sql
   {%= contains(profile.person.name.firstName, "A", false) %}
   ```

* Följande fråga avgör, med skiftlägeskänslighet, om personens e-postadress innehåller strängen &quot;2010@gm&quot;.

   ```sql
   {%= contains(profile.person.emailAddress,"2010@gm") %}
   ```

## Innehåller inte{#doesNotContain}

The `doesNotContain` -funktionen används för att avgöra om en sträng inte innehåller en angiven delsträng.

**Syntax**

```sql
{%= doesNotContain(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| Argument | Beskrivning |
| --------- | ----------- |
| `STRING_1` | Strängen som kontrollen ska utföras på. |
| `STRING_2` | Den sträng som ska sökas efter i den första strängen. |
| `CASE_SENSITIVE` | En valfri parameter som avgör om kontrollen är skiftlägeskänslig. Möjliga värden: true (standard) / false. |

**Exempel**

Följande fråga avgör, med skiftlägeskänslighet, om personens e-postadress inte innehåller strängen &quot;2010@gm&quot;.

```sql
{%= doesNotContain(profile.person.emailAddress,"2010@gm")%}
```


## Slutar inte med{#doesNotEndWith}

The `doesNotEndWith` -funktionen används för att avgöra om en sträng inte avslutas med en angiven delsträng.

**Syntax**

```sql
{%= doesNotEndWith(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| Argument | Beskrivning |
| --------- | ----------- |
| `{STRING_1}` | Strängen som kontrollen ska utföras på. |
| `{STRING_2}` | Den sträng som ska sökas efter i den första strängen. |
| `{CASE_SENSITIVE}` | En valfri parameter som avgör om kontrollen är skiftlägeskänslig. Möjliga värden: true (standard) / false. |

**Exempel**

Följande fråga avgör, med skiftlägeskänslighet, om personens e-postadress inte avslutas med &quot;.com&quot;.

```sql
doesNotEndWith(person.emailAddress,".com")
```

## Börjar inte med{#doesNotStartWith}

The `doesNotStartWith` -funktionen används för att avgöra om en sträng inte börjar med en angiven delsträng.

**Syntax**

```sql
{%= doesNotStartWith(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| Argument | Beskrivning |
| --------- | ----------- |
| `{STRING_1}` | Strängen som kontrollen ska utföras på. |
| `{STRING_2}` | Den sträng som ska sökas efter i den första strängen. |
| `{CASE_SENSITIVE}` | En valfri parameter som avgör om kontrollen är skiftlägeskänslig. Möjliga värden: true (standard) / false. |

**Exempel**

Följande fråga avgör, med skiftlägeskänslighet, om personens namn inte börjar med &quot;Joe&quot;.

```sql
{%= doesNotStartWith(person.name,"Joe")%}
```

## Koda 64{#encode64}

The `encode64` -funktionen används för att koda en sträng för att bevara personlig information (PI) om den ska inkluderas t.ex. i en URL.

**Syntax**

```sql
{%= encode64(string) %}
```

## Slutar med{#endsWith}

The `endsWith` används för att avgöra om en sträng avslutas med en angiven delsträng.

**Syntax**

```sql
{%= endsWith(STRING_1, STRING_2, CASE_SENSITIVE) %}
```

| Argument | Beskrivning |
| --------- | ----------- |
| `{STRING_1}` | Strängen som kontrollen ska utföras på. |
| `{STRING_2}` | Den sträng som ska sökas efter i den första strängen. |
| `{CASE_SENSITIVE}` | En valfri parameter som avgör om kontrollen är skiftlägeskänslig. Möjliga värden: true (standard) / false. |

**Exempel**

Följande fråga avgör, med skiftlägeskänslighet, om personens e-postadress slutar med &quot;.com&quot;.

```sql
{%= endsWith(person.emailAddress,".com") %}
```


## Är lika med{#equals}

The `equals` -funktionen används för att avgöra om en sträng är lika med den angivna strängen, med skiftlägeskänslighet.

**Syntax**

```sql
{%= equals(STRING_1, STRING_2) %}
```

| Argument | Beskrivning |
| --------- | ----------- |
| `{STRING_1}` | Strängen som kontrollen ska utföras på. |
| `{STRING_2}` | Strängen som ska jämföras med den första strängen. |

**Exempel**

Följande fråga avgör, med skiftlägeskänslighet, om personens namn är &quot;John&quot;.

```sql
{%=equals(profile.person.name,"John") %}
```

## Lika med Ignorera skiftläge{#equalsIgnoreCase}

The `equalsIgnoreCase` används för att avgöra om en sträng är lika med den angivna strängen, utan skiftlägeskänslighet.

**Syntax**

```sql
{%= equalsIgnoreCase(STRING_1, STRING_2) %}
```

| Argument | Beskrivning |
| --------- | ----------- |
| `{STRING_1}` | Strängen som kontrollen ska utföras på. |
| `{STRING_2}` | Strängen som ska jämföras med den första strängen. |

**Exempel**

Följande fråga avgör, utan skiftlägeskänslighet, om personens namn är &quot;John&quot;.

```sql
{%= equalsIgnoreCase(profile.person.name,"John") %}
```

## Extrahera e-postdomän {#extractEmailDomain}

The `extractEmailDomain` används för att extrahera domänen för en e-postadress.

**Syntax**

```sql
{%= extractEmailDomain(string) %}
```

**Exempel**

Följande fråga extraherar e-postdomänen för den personliga e-postadressen.

```sql
{%= extractEmailDomain(profile.personalEmail.address) %}
```

## Formatera valuta {#format-currency}

The `formatCurrency` används för att konvertera ett tal till motsvarande språkkänsliga valutarepresentation beroende på vilket språk som skickas som en sträng i det andra argumentet.

**Syntax**

```sql
{%= formatCurrency(number/double,string) %}: string
```

**Exempel**

Frågan returnerar 56,00 GBP

```sql
{%= formatCurrency(56L,"en_GB") %}
```

## Hämta URL-värd {#get-url-host}

The `getUrlHost` används för att hämta värdnamnet för en URL.

**Syntax**

```sql
{%= getUrlHost(string) %}: string
```

**Exempel**

```sql
{%= getUrlHost("http://www.myurl.com/contact") %}
```

Returnerar &quot;www.myurl.com&quot;

## Hämta URL-sökväg {#get-url-path}

The `getUrlPath` används för att hämta sökvägen efter domännamnet för en URL.

**Syntax**

```sql
{%= getUrlPath(string) %}: string
```

**Exempel**

```sql
{%= getUrlPath("http://www.myurl.com/contact.html") %}
```

Returnerar &quot;/contact.html&quot;

## Hämta URL-protokoll {#get-url-protocol}

The `getUrlProtocol` -funktionen används för att hämta protokollet för en URL.

**Syntax**

```sql
{%= getUrlProtocol(string) %}: string
```

**Exempel**

```sql
{%= getUrlProtocol("http://www.myurl.com/contact.html") %}
```

Returnerar &quot;http&quot;

## index för {#index-of}

The `indexOf` -funktionen används för att returnera positionen (i det första argumentet) för den första förekomsten av den andra parametern. Returnerar -1 om det inte finns någon matchning.

**Syntax**

```sql
{%= indexOf(STRING_1, STRING_2) %}: integer
```

| Argument | Beskrivning |
| --------- | ----------- |
| `{STRING_1}` | Strängen som kontrollen ska utföras på. |
| `{STRING_2}` | Strängen som ska sökas i den första parametern |

**Exempel**

```sql
{%= indexOf("hello world","world" ) %}
```

Returnerar 6.

## Is empty {#isEmpty}

The `isEmpty` -funktionen används för att avgöra om en sträng är tom.

**Syntax**

```sql
{%= isEmpty(string) %}
```

**Exempel**

Följande funktion returnerar &#39;true&#39; om profilens mobiltelefonnummer är tomt. Annars returneras &quot;false&quot;.

```sql
{%= isEmpty(profile.mobilePhone.number) %}
```

## Är inte tom {#is-not-empty}

The `isNotEmpty` -funktionen används för att avgöra om en sträng inte är tom.

**Syntax**

```sql
{= isNotEmpty(string) %}: boolean
```

**Exempel**

Följande funktion returnerar &#39;true&#39; om profilens mobiltelefonnummer inte är tomt. Annars returneras &quot;false&quot;.

```sql
{%= isNotEmpty(profile.mobilePhone.number) %}
```

## Senaste index för {#last-index-of}

The `lastIndexOf` -funktionen används för att returnera positionen (i det första argumentet) för den sista förekomsten av den andra parametern. Returnerar -1 om det inte finns någon matchning.

**Syntax**

```sql
{= lastIndexOf(STRING_1, STRING_2) %}: integer
```

| Argument | Beskrivning |
| --------- | ----------- |
| `{STRING_1}` | Strängen som kontrollen ska utföras på. |
| `{STRING_2}` | Strängen som ska sökas i den första parametern |

**Exempel**

```sql
{%= lastIndexOf("hello world","o" ) %}
```

Returnerar 7.

## Vänster trimning {#leftTrim}

The `leftTrim` används för att ta bort blanksteg från början av en sträng.

**Syntax**

```sql
{%= leftTrim(string) %}
```

## Length {#length}

The `length` används för att hämta antalet tecken i en sträng eller ett uttryck.

**Syntax**

```sql
{%= length(string) %}
```

**Exempel**

Följande funktion returnerar längden på profilens stadsnamn.

```sql
{%= length(profile.homeAddress.city) %}
```

## Gilla{#like}

The `like` används för att avgöra om en sträng matchar ett angivet mönster.

**Syntax**

```sql
{%= like(STRING_1, STRING_2) %}
```

| Argument | Beskrivning |
| --------- | ----------- |
| `{STRING_1}` | Strängen som kontrollen ska utföras på. |
| `{STRING_2}` | Det uttryck som ska matchas mot den första strängen. Det finns två specialtecken som stöds för att skapa ett uttryck: `%` och `_`. <ul><li>`%` används för att representera noll eller flera tecken.</li><li>`_` används för att representera exakt ett tecken.</li></ul> |

**Exempel**

Följande fråga hämtar alla städer där profiler som innehåller mönstret &quot;es&quot; finns.

```sql
{%= like(profile.homeAddress.city, "%es%")%}
```

## Gemener{#lower}

The `lowerCase` funktionen konverterar en sträng till gemener.

**Syntax**

```sql
{%= lowerCase(string) %}
```

**Exempel**

Den här funktionen konverterar profilens förnamn till gemener.

```sql
{%= lowerCase(profile.person.name.firstName) %}
```

## Matchar{#matches}

The `matches` används för att avgöra om en sträng matchar ett visst reguljärt uttryck. Se [det här dokumentet](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html) för mer information om att matcha mönster i reguljära uttryck.

**Syntax**

```sql
{%= matches(STRING_1, STRING_2) %}
```

**Exempel**

Följande fråga avgör, utan skiftlägeskänslighet, om personens namn börjar med &quot;John&quot;.

```sql
{%= matches(person.name.,"(?i)^John") %}
```

## Mask {#mask}

The `Mask` används för att ersätta en del av en sträng med &quot;X&quot;-tecken.

**Syntax**

```sql
{%= mask(string,integer,integer) %}
```

**Exempel**

Följande fråga ersätter strängen &quot;123456789&quot; med &quot;X&quot;-tecken, med undantag för de första och de sista två tecknen.

```sql
{%= mask("123456789",1,2) %}
```

Frågan returnerar `1XXXXXX89`.

## MD5 {#md5}

The `md5` -funktionen används för att beräkna och returnera md5-hash för en sträng.

**Syntax**

```sql
{%= md5(string) %}: string
```

**Exempel**

```sql
{%= md5("hello world") %}
```

Returnerar &quot;5eb63bbbe01eed093cb22bb8f5acdc3&quot;

## Inte lika med{#notEqualTo}

The `notEqualTo` -funktionen används för att avgöra om en sträng inte är lika med den angivna strängen.

**Syntax**

```sql
{%= notEqualTo(STRING_1, STRING_2) %}
```

| Argument | Beskrivning |
| --------- | ----------- |
| `{STRING_1}` | Strängen som kontrollen ska utföras på. |
| `{STRING_2}` | Strängen som ska jämföras med den första strängen. |

**Exempel**

Följande fråga avgör, med skiftlägeskänslighet, om personens namn inte är&quot;John&quot;.

```sql
{%= notEqualTo(profile.person.name,"John") %}
```

## Inte lika med Ignorera skiftläge {#not-equal-with-ignore-case}

The `notEqualWithIgnoreCase` används för att jämföra två strängar utan skiftläge.

**Syntax**

```sql
{= notEqualWithIgnoreCase(STRING_1,STRING_2) %}: boolean
```

| Argument | Beskrivning |
| --------- | ----------- |
| `{STRING_1}` | Strängen som kontrollen ska utföras på. |
| `{STRING_2}` | Strängen som ska jämföras med den första strängen. |

**Exempel**

Följande fråga avgör om personens namn inte är &quot;john&quot;, utan skiftlägeskänslighet.

```sql
{%= notEqualTo(profile.person.name,"john") %}
```

## Grupp för reguljära uttryck{#regexGroup}

The `Group` -funktionen används för att extrahera specifik information baserat på det reguljära uttrycket.

**Syntax**

```sql
{%= regexGroup(STRING, EXPRESSION, GROUP) %}
```

| Argument | Beskrivning |
| --------- | ----------- |
| `{STRING}` | Strängen som kontrollen ska utföras på. |
| `{EXPRESSION}` | Det reguljära uttryck som ska matchas mot den första strängen. |
| `{GROUP}` | Uttrycksgrupp att matcha mot. |

**Exempel**

Följande fråga används för att extrahera domännamnet från en e-postadress.

```sql
{%= regexGroup(emailAddress,"@(\\w+)", 1) %}
```

## Replace {#replace}

The `replace` -funktionen används för att ersätta en viss delsträng i en sträng med en annan delsträng.

**Syntax**

```sql
{%= replace(STRING_1,STRING_2,STRING_3) %}:string
```

| Argument | Beskrivning |
| --------- | ----------- |
| `{STRING_1}` | Strängen där delsträngen måste ersättas. |
| `{STRING_2}` | Den delsträng som ska ersättas. |
| `{STRING_3}` | Ersättningsdelsträngen. |

**Exempel**

```sql
{%= replace("Hello John, here is your monthly newsletter!","John","Mark") %}
```

Returnerar&quot;Hello Mark, här kommer ditt månatliga nyhetsbrev!&quot;

## Ersätt alla{#replaceAll}

The `replaceAll` används för att ersätta alla delsträngar i en text som matchar &quot;regex&quot;-uttrycket med den angivna literala &quot;ersättningssträngen&quot;. Regex har specialhantering av &quot;\&quot; och &quot;+&quot; och alla regex-uttryck följer PQL:s flyktstrategi. Ersättningen fortsätter från början av strängen till slutet, t.ex. om&quot;a&quot; ersätts med&quot;b&quot; i strängen&quot;aaa&quot; resulterar det i&quot;ba&quot; i stället för&quot;ab&quot;.

**Syntax**

```sql
{%= replaceAll(string,string,string) %}
```
>[!NOTE]
>
> Om det regex-uttryck som används som andra argument är ett särskilt regex-tecken måste vi använda ett dubbelt omvänt snedstreck (`//`) för att hantera sådana fall.
>
> Lista med specialregextecken [., +, *, ?, ^, $, (, ), [, ], {, }, |, \.]
> 
> Detta sammanfattas i [Oraclets dokumentation](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html){_blank}

## Högertrimning {#rightTrim}

The `rightTrim` funktionen används för att ta bort blanksteg från slutet av en sträng.

**Syntax**

```sql
{%= rightTrim(string) %}
```

## Dela {#split}

The `split` används för att dela en sträng med ett visst tecken.

**Syntax**

```sql
{%= split(string,string) %}
```

## Börjar med{#startsWith}

The `startsWith` -funktionen används för att avgöra om en sträng börjar med en angiven delsträng.

**Syntax**

```sql
{%= startsWith(STRING_1, STRING_2, CASE_SENSITIVE) %}
```

| Argument | Beskrivning |
| --------- | ----------- |
| `{STRING_1}` | Strängen som kontrollen ska utföras på. |
| `{STRING_2}` | Den sträng som ska sökas efter i den första strängen. |
| `{CASE_SENSITIVE}` | En valfri parameter som avgör om kontrollen är skiftlägeskänslig. Som standard är detta true. |

**Exempel**

Följande fråga avgör, med skiftlägeskänslighet, om personens namn börjar med &quot;Joe&quot;.

```sql
{%= startsWith(person.name,"Joe") %}
```

## Sträng till datum {#string-to-date}

The `stringToDate` funktionen konverterar ett strängvärde till ett datum/tid-värde. Det finns två argument: strängrepresentation av ett datum- och tidsbeteckning samt strängbeteckning för formateringen.

**Syntax**

```sql
{= stringToDate("date-time value","formatter" %}
```

**Exempel**

```sql
{= stringToDate("2023-01-10 23:13:26", "yyyy-MM-dd HH:mm:ss") %}
```

## Sträng till heltal {#string-to-integer}

The `string_to_integer` används för att konvertera ett strängvärde till ett heltalsvärde.

**Syntax**

```sql
{= string_to_integer(string) %}: int
```

## Sträng till tal {#string-to-number}

The `stringToNumber` används för att konvertera en sträng till tal. Den returnerar samma sträng som utdata för ogiltiga indata.

**Syntax**

```sql
{%= stringToNumber(string) %}: double
```

## Delsträng {#sub-string}

The `Count string` -funktionen används för att returnera delsträngen för stränguttrycket mellan startindexet och slutindexet.
**Syntax**

```sql
{= substr(string, integer, integer) %}: string
```

## Inledande versal{#titleCase}

The **titleCase** -funktionen används för att ge inledande versal i varje ord i en sträng.

**Syntax**

```sql
{%= titleCase(string) %}
```

**Exempel**

Om personen bor i Washington High Street, returnerar den här funktionen Washington High Street.

```sql
{%= titleCase(profile.person.location.Street) %}
```

## Till boolesk {#to-bool}

The `toBool` -funktionen används för att konvertera ett argumentvärde till ett booleskt värde, beroende på dess typ.

**Syntax**

```sql
{= toBool(string) %}: boolean
```

## Till datum och tid {#to-date-time}

The `toDateTime` -funktionen används för att konvertera strängen till ett datum. Det returnerar epokdatumet som utdata för ogiltiga indata.

**Syntax**

```sql
{%= toDateTime(string, string) %}: date-time
```

## Endast till datum och tid {#to-date-time-only}

The `toDateTimeOnly` -funktionen används för att konvertera ett argumentvärde till ett värde som bara gäller för datum och tid. Det returnerar epokdatumet som utdata för ogiltiga indata. Den här funktionen accepterar fälttyperna string, date, long och int.

**Syntax**

```sql
{%= toDateTimeOnly(string/date/long/int) %}: date-time
```

## Rensa {#trim}

The **trimma** funktionen tar bort alla blanksteg från början och slutet av en sträng.

**Syntax**

```sql
{%= trim(string) %}
```

## Versaler{#upper}

The **upperCase** funktionen konverterar en sträng till versaler.

**Syntax**

```sql
{%= upperCase(string) %}
```

**Exempel**

Den här funktionen konverterar profilens efternamn till versaler.

```sql
{%= upperCase(profile.person.name.lastName) %}
```

## URL-avkodning {#url-decode}

The `urlDecode` används för att avkoda en URL-kodad sträng.

**Syntax**

```sql
{%= urlDecode(string) %}: string
```

## URL-kodning {#url-encode}

The `Count only null` -funktionen används för att URL-koda en sträng.

**Syntax**

```sql
{%= urlEncode(string) %}: string
```
