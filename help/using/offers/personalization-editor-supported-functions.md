---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: Funktioner som stöds i uttrycksredigeraren
description: Läs om vilka redigeringsfunktioner för personalisering som stöds i Beslutshantering (Offer Decisioning).
badge: label="Äldre" type="Informative"
feature: Decision Management
topic: Integrations
role: User
level: Intermediate
version: Journey Orchestration
exl-id: c4df41a2-d740-437c-acc3-957508c4a1c0
source-git-commit: b90e3af955496d4fcae54b109cb1e86a8a21be43
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 5%

---

# Funktioner som stöds i uttrycksredigeraren {#personalization-editor-supported-functions}

I beslutsprocessen bygger du uttryck med personaliseringsredigeraren. Du använder den här redigeraren särskilt när:

* **Definiera erbjudandeinnehåll** - när du [lägger till representationer](offer-library/add-representations.md) och anpassar erbjudandeinnehållet (bilder, text, länkar)
* **Skapar beslutsregler** - när du [definierar behörighet](offer-library/creating-decision-rules.md) för erbjudanden
* **Skapar rangordningsformler** - när du [skapar rangordningsformler](ranking/create-ranking-formulas.md) för att beställa erbjudanden

Offer Decisioning serverdel stöder endast en **delmängd** av de funktioner som är tillgängliga i personaliseringsredigeraren. På den här sidan visas alla funktioner som du kan använda på ett säkert sätt. Expandera varje avsnitt för att se vilka operatorer, hjälpprogram och funktioner som stöds.

## Lista över funktioner som stöds {#supported-functions-list}

+++ Operatorer

* Aritmetisk: `+` `-` `*` `/` `%`
* Logiskt: `and` `or` `!`
* Jämförelse: `=` `!=` `>` `>=` `<` `<=`

+++

+++ Hjälpmedel

* Varje
* Med
* If
* Om
* Låt
* Standardreservvärde
* fragment
* datasetLookup
* externalDataLookup (Alpha)
* Textbunden
* URL
* Körningsmetadata
* valueAtPath

+++

+++ Strängfunktioner

| Visningsnamn | Internt namn |
|--------------|---------------|
| Gemener | lowerCase |
| Versaler | upperCase |
| Kamerafodral | camelCase |
| Inledande versal | titleCase |
| Rensa | trim |
| Vänster trimning | leftTrim |
| Höger trimning | rightTrim |
| Är tom | isEmpty |
| Lika med Ignorera skiftläge | equalsIgnoreCase |
| Inte lika med Ignorera skiftläge | notEqualWithIgnoreCase |
| Ersätt | ersätta |
| Ersätt alla | replaceAll |
| Concat | concat |
| Dela | dela |
| Encode64 | encode64 |
| Längd | längd |
| MD5 | md5 |
| SHA256 | sha256 |
| Gilla | gilla |
| Börjar med | beginWith |
| Börjar inte med | doesNotStartWith |
| Slutar med | endsWith |
| Slutar inte med | doesNotEndWith |
| Innehåller | innehåller |
| Innehåller inte | doesNotContain |
| Lika med | är lika med |
| Inte lika med | notEqualTo |
| Matchar | matchar |
| Grupp för reguljära uttryck | regexGroup |
| Sträng till tal | stringToNumber |
| Sträng till datum | stringToDate |
| Till datum och tid | toDateTime |
| Endast till datum och tid | toDateTimeOnly |
| Extrahera e-postdomän | extractEmailDomain |
| Extrahera e-postanvändarnamn | extractEmailUsername |
| Är inte tom | isNotEmpty |
| index för | indexOf |
| Senaste index för | lastIndexOf |
| Delsträng | substr |
| Till boolesk | toBool |
| Sträng till heltal | string_to_integer |
| Mask | mask |
| Hämta formatvaluta | formatCurrency |
| Hämta Unicode-värde för tecken | charCodeAt |
| Hämta QR-kod för all text | qrCode |

+++

+++ Array-, list- och set-funktioner

| Visningsnamn | Internt namn |
|--------------|---------------|
| Distinkt | distinct |
| I | in |
| Inte i | notIn |
| Överlappningar | korsar |
| Delmängd av | subsetOf |
| Supermängd till | supersetOf |
| Inkluderar | inkluderar |
| Sortera och hämta första N i en array | topN |
| Sortera och hämta sista N i en array | bottomN |
| Första objektet | head |
| Antal | count |
| Summa | sum |
| Genomsnittlig | medel |
| Minimum | min |
| Maximal | max |

+++

+++ Kartfunktioner

| Visningsnamn | Internt namn |
|--------------|---------------|
| Hämta | get |
| Tangenter | tangenter |
| Värden | values |

+++

+++ Objektfunktioner

| Visningsnamn | Internt namn |
|--------------|---------------|
| Är null | isNull |
| Är inte null | isNotNull |

+++

+++ Matematiska funktioner

| Visningsnamn | Internt namn |
|--------------|---------------|
| Till procent | toPercentage |
| Avrunda uppåt | roundUp |
| Avrunda nedåt | roundDown |
| Till precision | toPrecision |
| Absolut | absolut |
| Slumpmässig | random |
| Till hexadecimal | toHexString |
| Hämta nummer till språkområde | formatNumber |
| Till sträng | toString |
| Till int | toInt |
| Till lång | toLong |

+++

+++ Funktioner för datum och tid

| Visningsnamn | Internt namn |
|--------------|---------------|
| Nu | now |
| Hämta CurrentZonedDateTime | getCurrentZonedDateTime |
| Till-datum | toDate |
| Till tid | toTime |
| Till datum och tid | toDateTime |
| Endast till datum och tid | toDateTimeOnly |
| Endast till-datum | toDateOnly |
| Endast till tid | toTimeOnly |
| Till tidszon | toTimeZone |
| Formateringsdatum | formatDate |
| Formatera datum och tid | formatDateTime |
| Formatera tid | formatTime |
| Tolkningsdatum | parseDate |
| Tolka datum/tid | parseDateTime |
| Tolkningstid | parseTime |
| Lägg till dagar | addDays |
| Lägg till månader | addMonths |
| Lägg till år | addYears |
| Lägg till timmar | addHours |
| Lägg till minuter | addMinutes |
| Lägg till sekunder | addSeconds |
| Subtrahera dagar | subtractDays |
| Subtrahera månader | subtractMonths |
| Subtrahera år | subtractYears |
| Subtrahera timmar | subtractHours |
| Ta bort minuter | subtractMinutes |
| Subtrahera sekunder | subtractSeconds |
| Differens i dagar | diffDays |
| Skillnad i månader | diffMonths |
| Skillnad i år | diffYears |
| Skillnad i timmar | diffHours |
| Differens i minuter | diffMinutes |
| Differens i sekunder | diffSeconds |
| Dagens början | startOfDay |
| Dagens slut | endOfDay |
| Är före | isBefore |
| Är efter | isAfter |

+++

+++ URL-funktioner

| Visningsnamn | Internt namn |
|--------------|---------------|
| Koda URL | encodeUrl |
| Avkodnings-URL | decodeUrl |
| Hämta URL-frågeparameter | getUrlQueryParam |
| Hämta URL-protokoll | getUrlProtocol |
| Hämta URL-värd | getUrlHost |

+++

>[!NOTE]
>
>Om du använder en funktion som inte finns i listan ovan kan uttrycket misslyckas vid körning eller ge oväntade resultat. Mer information om alla funktioner som är tillgängliga i [!DNL Journey Optimizer]-personalisering finns i [Hjälpfunktionslista](../personalization/functions/functions.md). I Offer Decisioning stöds bara den delmängd som finns dokumenterad på den här sidan.
