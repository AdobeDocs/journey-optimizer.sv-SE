---
product: journey optimizer
title: Strängfunktioner
description: Läs om strängfunktioner
feature: Journeys
role: Developer
level: Experienced
keywords: sträng, funktioner, uttryck, resa, text, manipulation
version: Journey Orchestration
source-git-commit: bb47ca4957129a4d05aa3d7286409eef0cb62143
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 6%

---

# Strängfunktioner {#string-functions}

Med strängfunktionerna kan du ändra och arbeta med textvärden i dina reseuttryck. De här funktionerna är viktiga för textbearbetning, validering, omvandling och analys i kundresorna.

Använd strängfunktioner när du behöver:

* Sammanfoga och kombinera flera textvärden ([sammanfoga](#concat))
* Sök efter specifika textmönster eller delsträngar ([contains](#contain), [containIgnoreCase](#containIgnoreCase), [indexOf](#indexOf), [lastIndexOf](#lastIndexOf), [matchRegExp](#matchRegExp))
* Jämför strängar med skiftlägeskänslig eller skiftlägeskänslig matchning ([equalIgnoreCase](#equalIgnoreCase), [notEqualIgnoreCase](#notEqualIgnoreCase))
* Kontrollsträngen börjar och slutar ([startWith](#startWith), [startWithIgnoreCase](#startWithIgnoreCase), [endWith](#endWith), [endWithIgnoreCase](#endWithIgnoreCase))
* Extrahera delar av text med delsträngsåtgärder ([substr](#substr))
* Omforma text till versaler eller gemener ([övre](#upper), [nedre](#lower), [trimma](#trim))
* Kontrollera om strängarna är tomma eller innehåller specifika värden ([isEmpty](#isEmpty), [isNotEmpty](#isNotEmpty))
* Ersätt textmönster med nya värden ([replace](#replace), [replaceAll](#replaceAll))
* Dela strängar i arrayer för vidare bearbetning ([split](#split))
* Hämta stränglängd ([length](#length)) eller generera unika identifierare ([uid](#uuid))

Strängfunktionerna ger omfattande funktioner för textbehandling, vilket möjliggör avancerad databehandling och villkorsstyrd logik som bygger på textinnehåll i dina resematerial.

## concat {#concat}

Sammanfogar två strängparametrar eller en lista med strängar.

+++Syntax

`concat(<parameters>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| Lista | listString |
| string | string |

+++

+++Signatur och returtyp

`concat(<string>,<string>)`

`concat(<listString>)`

Returnerar en sträng.

+++

+++Exempel

`concat("Hello","World")`

Returnerar&quot;HelloWorld&quot;.

`concat(["Hello"," ","World"])`

Returnerar &quot;Hello World&quot;.

+++

## contain {#contain}

Kontrollerar om den andra argumentsträngen finns i den första argumentsträngen.

+++Syntax

`contain(<parameters>)`

+++

+++Parametrar

* string

+++

+++Signatur och returtyp

`contain(<string>,<string>)`

Returnerar ett booleskt värde.

+++

+++Exempel

`contain("rowing is great", "great")`

Returnerar true.

+++

## containIgnoreCase {#containIgnoreCase}

Kontrollerar om den andra argumentsträngen finns i den första argumentsträngen, utan att ta hänsyn till skiftläget.

+++Syntax

`containIgnoreCase(<parameters>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| string | string |
| sträng genomsöktes | string |

+++

+++Signatur och returtyp

`containIgnoreCase(<string>,<string>)`

Returnerar ett booleskt värde.

+++

+++Exempel

`containIgnoreCase("rowing is great", "GREAT")`

Returnerar true.

+++

## endWith {#endWith}

Returnerar true om den andra parametern är ett suffix till den första.

+++Syntax

`endWith(<parameters>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| string | string |
| suffix | string |

+++

+++Signatur och returtyp

`endWith(<string>,<string>)`

Returnerar ett booleskt värde.

+++

+++Exempel

`endWith("Hello World", "World")`

Returnerar true.

`endWith("Hello World", "Hello")`

Returnerar false.

+++

## endWithIgnoreCase {#endWithIgnoreCase}

Kontrollerar om den första argumentsträngen slutar med en viss sträng (den andra argumentsträngen), utan att ta hänsyn till skiftläget.

+++Syntax

`endWithIgnoreCase(<parameters>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| string | string |
| suffix | string |

+++

+++Signatur och returtyp

`endWithIgnoreCase(<string>,<string>)`

Returnerar ett booleskt värde.

+++

+++Exempel

`endWithIgnoreCase("rowing is great", "AT")`

Returnerar true.

+++

## equalIgnoreCase {#equalIgnoreCase}

Jämför den första argumentsträngen med den andra argumentsträngen och ignorerar skiftlägeskänsliga värden.

+++Syntax

`equalIgnoreCase(<parameters>)`

+++

+++Parametrar

* string

+++

+++Signatur och returtyp

`equalIgnoreCase(<string>,<string>)`

Returnerar ett booleskt värde.

+++

+++Exempel

`equalIgnoreCase("rowing is great", "rowing is GREAT")`

Returnerar true.

+++

## indexOf {#indexOf}

Returnerar positionen (i det första argumentet) för den första förekomsten av den andra parametern. Returnerar -1 om det inte finns någon matchning.

+++Syntax

`indexOf(<parameters>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| string | Sträng |
| angivet värde | Sträng |

+++

+++Signatur och returtyp

`indexOf(<string>,<string>)`

Returnerar ett heltal.

+++

+++Exempel

`indexOf("Hello", "l")`

Returnerar 2.

Förklaring:

I &quot;Hello&quot; är den första förekomsten av &quot;l&quot; på position 2.

+++

## isEmpty {#isEmpty}

Returnerar true om strängen i parametern saknar tecken.

+++Syntax

`isEmpty(<parameters>)`

+++

+++Parametrar

* string

+++

+++Signatur och returtyp

`isEmpty(<string>)`

Returnerar ett booleskt värde.

+++

+++Exempel

`isEmpty("")`

Returnerar true.

`isEmpty("Hello World")`

Returnerar false.

+++

## isNotEmpty {#isNotEmpty}

Returnerar true om strängen i parametern inte är tom.

+++Syntax

`isNotEmpty(<parameters>)`

+++

+++Parametrar

* string

+++

+++Signatur och returtyp

`isNotEmpty(<string>)`

Returnerar ett booleskt värde.

+++

+++Exempel

`isNotEmpty("")`

Returnerar false.

`isNotEmpty("hello")`

Returnerar true.

+++

## lastIndexOf {#lastIndexOf}

Returnerar positionen (i det första argumentet) för den sista förekomsten av den andra parametern. Returnerar -1 om det inte finns någon matchning.

+++Syntax

`lastIndexOf(<parameters>)`

+++

+++Parameter

| Parameter | Typ |
|-----------|------------------|
| string | Sträng |
| angivet värde | Sträng |

+++

+++Signatur och returtyp

`lastIndexOf(<string>,<string>)`

Returnerar ett heltal.

+++

+++Exempel

`lastIndexOf("Hello", "l")`

Returnerar 3.

Förklaring:

I &quot;Hello&quot; är den sista förekomsten av &quot;l&quot; i position 3.

+++

## längd {#length}

Returnerar antalet tecken i stränguttrycket i parametern.

+++Syntax

`length(<parameters>)`

+++

+++Parameter

* string

+++

+++Signatur och returtyp

`length(<string>)`

Returnerar ett heltal.

+++

+++Exempel

`length("Hello World")`

Returnerar 11.

+++

## nedre {#lower}

Returnerar en version med gemener av parametern.

+++Syntax

`lower(<parameter>)`

+++

+++Parameter

* string

+++

+++Signatur och returtyp

`lower(<string>)`

Returnerar en sträng.

+++

+++Exempel

`lower("A")`

Returnerar &quot;a&quot;.

+++

## matchRegExp {#matchRegExp}

Returnerar true om strängen i den första parametern matchar det reguljära uttrycket i den andra parametern. Mer information finns på [den här sidan](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

+++Syntax

`matchRegExp(<parameters>)`

+++

+++Parametrar

| Parameter | Typ |
|--- |--- |
| string | string |
| regexp | string |

+++

+++Signatur och returtyp

`matchRegExp(<string>,<string>)`

Returnerar ett booleskt värde.

+++

+++Exempel

`matchRegExp("12345", "\\d+")`

Returnerar true.

+++

## notEqualIgnoreCase {#notEqualIgnoreCase}

Kontrollera om den första argumentsträngen med den andra argumentsträngen är annorlunda och ignorerar skiftlägeskänslighet.

+++Syntax

`notEqualIgnoreCase(<parameters>)`

+++

+++Parametrar

* string

+++

+++Signatur och returtyp

`notEqualIgnoreCase(<string>,<string>)`

Returnerar ett booleskt värde.

+++

+++Exempel

`notEqualIgnoreCase(@event{iOSPushPermissionAllowed.device.model}, "iPad")`

+++

## ersätta {#replace}

Ersätter den första förekomsten som matchar målsträngen med ersättningssträngen i bassträngen.

Ersättningen fortsätter från början av strängen till slutet, t.ex. om&quot;a&quot; ersätts med&quot;b&quot; i strängen&quot;aaa&quot; resulterar det i&quot;ba&quot; i stället för&quot;ab&quot;.

+++Syntax

`replace(<parameters>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|--------------|
| bas | string |
| target | sträng (RegExp) |
| ersättare | string |

+++

+++Signatur och returtyp

`replace(<base>,<target>,<replacement>)`

Returnera en sträng.

+++

+++Exempel

`replace("Hello World", "l", "x")`

Returnerar &quot;Hexlo World&quot;.

**Exempel med RegExp:**

Eftersom målparametern är en RegExp, beroende på vilken sträng du vill ersätta, kan du behöva undvika vissa tecken. Här är ett exempel:

* sträng som ska utvärderas: `|OFFER_A|OFFER_B`
* tillhandahålls av ett profilattribut `#{ExperiencePlatform.myFieldGroup.profile.myOffers}`
* Sträng som ska ersättas: `|OFFER_A`
* Sträng ersatt av: `''`
* Du måste lägga till `\\` före tecknet `|`.

Uttrycket är:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|OFFER_A', '')`

Den returnerade strängen är: `|OFFER_B`

Du kan också skapa strängen som ska ersättas från ett visst attribut:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|' + #{ExperiencePlatform.myFieldGroup.profile.myOfferCode}, '')`

+++

## replaceAll {#replaceAll}

Ersätter alla förekomster som matchar målsträngen med ersättningssträngen i bassträngen.

Ersättningen fortsätter från början av strängen till slutet, t.ex. om&quot;a&quot; ersätts med&quot;b&quot; i strängen&quot;aaa&quot; resulterar det i&quot;ba&quot; i stället för&quot;ab&quot;.

+++Syntax

`replaceAll(<parameters>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|--------------|
| bas | string |
| target | sträng (RegExp) |
| ersättare | string |

+++

+++Signatur och returtyp

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

Returnerar en sträng.

+++

+++Exempel

`replaceAll("Hello World", "l", "x")`

Returnerar &quot;Hexo Worxd&quot;.

Eftersom målparametern är en RegExp, beroende på vilken sträng du vill ersätta, kan du behöva undvika vissa tecken. Se exemplet i funktionen [replace](#replace).

+++

## dela {#split}

Delar den första argumentsträngen med en avgränsningssträng (den andra argumentsträngen, som kan vara ett reguljärt uttryck) för att skapa en lista med strängar (tokens).

+++Syntax

`split(<parameters>)`

+++

+++Parametrar

| Parameter | Typ |
|-----------|------------------|
| indatasträng | string |
| avgränsarsträng | string |

+++

+++Underskrifter och returtyp

`split(<input string>, <separator string>)`

Returnerar en listString.

+++

+++Exempel

`split("A_B_C", "_")`

Returnerar `["A","B","C"]`

Exempel med ett händelsefält &#39;event.appVersion&#39; med värdet: &quot;20.45.2.3434&quot;

`split(@event{event.appVersion}, "\\.")`

Returnerar `["20", "45", "2", "3434"]`

+++

## startWith {#startWith}

Returnerar true om den andra parametern är ett prefix till den första.

+++Syntax

`startWith(<parameters>)`

+++

+++Parametrar

| Parameter | Typ |
|-------------|--------|
| string | string |
| prefix | string |

+++

+++Signatur och returtyp

`startWith(<string>,<string>)`

Returnera ett booleskt värde.

+++

+++Exempel

`startWith("Hello World", "Hello")`

Returnerar true.

`startWith("Hello World", "World")`

Returnerar false.

+++

## startWithIgnoreCase {#startWithIgnoreCase}

Returnerar true om den andra parametern är ett prefix till den första utan att ta hänsyn till skiftläge.

+++Syntax

`startWithIgnoreCase(<parameters>)`

+++

+++Parametrar

| Parameter | Typ |
|-------------|--------|
| string | string |
| prefix | string |

+++

+++Signatur och returtyp

`startWithIgnoreCase(<string>,<string>)`

Returnera ett booleskt värde.

+++

+++Exempel

`startWithIgnoreCase("rowing is great", "RO")`

Returnerar true.

+++

## substr {#substr}

Returnerar delsträngen för stränguttrycket mellan startindexvärdet och slutindexvärdet. Om slutindexvärdet inte är definierat ligger det mellan startindexet och slutet.

+++Syntax

`substr(<parameters>)`

+++

+++Parametrar

| Parameter | type |
|-------------|----------|
| string | string |
| beginIndex | heltal |
| endIndex | heltal |

+++

+++Signatur och returtyp

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

Returnera en sträng.

+++

+++Exempel

`substr("Hello World",6)`

Returnerar &quot;World&quot;.

`substr("Hello World", 0, 5)`

Returnerar &quot;Hello&quot;.

+++

## trim {#trim}

Tar bort start- och slutblanksteg.

+++Syntax

`trim(<parameters>)`

+++

+++Parameter

| Parameter | Typ |
|-----------|------------------|
| string | string |

+++

+++Signatur och returtyp

`trim(<string>)`

Returnera en sträng.

+++

+++Exempel

`trim(" Hello ")`

Returnerar &quot;Hello&quot;.

+++

## övre {#upper}

Returnerar en versalversion av parametern.

+++Syntax

`upper(<parameters>)`

+++

+++Signatur och returtyp

`upper(<string>)`

Returnera en sträng.

+++

+++Exempel

`upper("b")`

Returnerar &quot;B&quot;.

+++

## uuid {#uuid}

Skapar ett slumpmässigt UUID (Unikt IDentifier).

+++Syntax

`uuid()`

+++

+++Parametrar 

Den här funktionen kräver inga parametrar.

+++

+++Signatur och returtyp

`uuid()`

Returnerar en sträng.

+++

+++Exempel

`uuid()`

Returnerar &quot;79e70b7f-8a85-400b-97a1-9f9826121553&quot;.

+++

