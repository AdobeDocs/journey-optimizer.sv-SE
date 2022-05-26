---
title: Bibliotek för strängfunktioner
description: Bibliotek för strängfunktioner
feature: Personalization
topic: Personalization
role: Data Engineer
level: Experienced
exl-id: 8674ef9e-261b-49d9-800e-367f9f7ef979
source-git-commit: b9ebacf410f268e19bbaf1d43ee98f5376d0913f
workflow-type: tm+mt
source-wordcount: '1237'
ht-degree: 3%

---

# Strängfunktioner {#string}

Lär dig hur du använder strängfunktioner i uttrycksredigeraren.

## Camera Case {#camelCase}

The `camelCase` funktionen ändrar den första bokstaven i varje ord i en sträng till versal.

**Format**

```sql
{%= camelCase(string)%}
```

**Exempel**

Med följande funktion infogas den första bokstaven i ordet i profilens gatuadress.

```sql
{%= camelCase(profile.homeAddress.street) %}
```

## Concat {#concate}

The `concat` funktionen kombinerar två strängar till en.

**Format**

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

**Format**

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

**Format**

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

**Format**

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

**Format**

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

**Format**

```sql
{%= encode64(string) %}
```

## Slutar med{#endsWith}

The `endsWith` används för att avgöra om en sträng avslutas med en angiven delsträng.

**Format**

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

**Format**

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

**Format**

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

**Format**

```sql
{%= extractEmailDomain(string) %}
```

**Exempel**

Följande fråga extraherar e-postdomänen för den personliga e-postadressen.

```sql
{%= extractEmailDomain(profile.personalEmail.address) %}
```

## Is empty {#isEmpty}

The `isEmpty` -funktionen används för att bestämma om en sträng är tom.

**Format**

```sql
{%= isEmpty(string) %}
```

**Exempel**

Följande funktion returnerar &#39;true&#39; om profilens mobiltelefonnummer är tomt. Annars returneras &quot;false&quot;.

```sql
{%= isEmpty(profile.mobilePhone.number) %}
```

## Vänster trimning {#leftTrim}

The `leftTrim` används för att ta bort blanksteg från början av en sträng.

**Format**

```sql
{%= leftTrim(string) %}
```

## Length {#length}

The `length` används för att hämta antalet tecken i en sträng eller ett uttryck.

**Format**

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

**Format**

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

**Format**

```sql
{%= matches(STRING_1, STRING_2) %}
```

**Exempel**

Följande fråga avgör, utan skiftlägeskänslighet, om personens namn börjar med &quot;John&quot;.

```sql
{%= matches(person.name.,"(?i)^John") %}
```

## Mask (#mask)

The `Mask` används för att ersätta en del av en sträng med &quot;X&quot;-tecken.

**Format**

```sql
{%= mask(string,integer,integer) %}
```

**Exempel**

Följande fråga ersätter strängen &quot;123456789&quot; med &quot;X&quot;-tecken, med undantag för de första och de sista två tecknen.

```sql
{%= mask("123456789",1,2) %}
```

Frågan returnerar `1XXXXXX89`.

## Inte lika med{#notEqualTo}

The `notEqualTo` -funktionen används för att avgöra om en sträng inte är lika med den angivna strängen.

**Format**

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

## Grupp för reguljära uttryck{#regexGroup}

The `Group` -funktionen används för att extrahera specifik information baserat på det reguljära uttrycket.

**Format**

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
{%= regexGroup(emailAddress,"@(\w+)", 1) %}
```

## Replace {#replace}

The `replace` -funktionen används för att ersätta en viss delsträng i en sträng med en annan delsträng.

**Format**

```sql
{%= replace(string,string,string) %}
```

**Exempel**

Följande funktion:

```sql

```


## Ersätt alla{#replaceAll}

The `replaceAll` används för att ersätta alla delsträngar i en text som matchar&quot;target&quot; med den angivna strängen&quot;teckenersättning&quot;. Ersättningen fortsätter från början av strängen till slutet, t.ex. om&quot;a&quot; ersätts med&quot;b&quot; i strängen&quot;aaa&quot; resulterar det i&quot;ba&quot; i stället för&quot;ab&quot;.

**Format**

```sql
{%= replaceAll(string,string,string) %}
```


## Högertrimning {#rightTrim}

The `rightTrim` funktionen används för att ta bort blanksteg från slutet av en sträng.


**Format**

```sql
{%= rightTrim(string) %}
```

## Dela {#split}

The `split` används för att dela en sträng med ett visst tecken.

**Format**

```sql
{%= split(string,string) %}
```

<!--
**Example**

The following function .

```sql

```

-->

## Börjar med{#startsWith}

The `startsWith` -funktionen används för att avgöra om en sträng börjar med en angiven delsträng.

**Format**

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

## Rensa{#trim}

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
