---
product: Journey Optimizer
title: Syntax
description: Läs mer om den avancerade uttrycksredigeraren
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: c9434b28-2750-4a53-985e-c4a3f940472c
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 2%

---

# Avancerad syntax för uttrycksredigeraren {#syntax}

## Parenteser och uttrycksprioritet{#parentheses-and-expression-priority}

Parenteser kan användas för att göra ett komplext uttryck mer läsbart. _(&lt;expression>)_ motsvarar _&lt;expression>_. Parenteser kan också användas för att definiera utvärderingsordningen och associativiteten.

Uttrycken utvärderas från vänster till höger. Associativiteten för aritmetiska operatorer måste tillämpas: multiplikationer och indelningar prioriteras framför tillägg och subtraktioner. För att införa en viss ordning måste parenteser läggas till för att avgränsa operationerna. Exempel:

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| Uttryck | Utvärdering |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39; har högre prioritet än &#39;+&#39;: 2 * 10 utvärderas → 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>Parenteserna ändrar prioriteten: (4 + 2) utvärderas → 6</li><li> 6 * 10 → 60</li></ul> |

## Skiftlägeskänslighet{#case-sensitivity}

Här är de olika reglerna för skiftlägeskänslighet:

* Alla operatorer (och, eller, osv.) ska skrivas med gemener. Till exempel _`<expression1>`och`<expression2>`_ är ett giltigt uttryck medan uttrycket _`<expression1>`OCH`<expression2>`_ inte.
* Alla funktionsnamn är skiftlägeskänsliga. Till exempel _inSegment()_ är giltigt medan funktionen _INSEGMENT()_ inte.
* Fältreferenser och konstanta värden är skiftlägeskänsliga: de inte är inbyggda element i språket (till skillnad från operatorer och funktioner), de författas av slutanvändaren.

## Returnerad uttryckstyp{#returned-expression-type}

Beroende på användningssammanhanget kan uttrycksredigeraren returnera olika värden.

| Avancerad användning av uttrycksredigeraren | Returnerad uttryckstyp förväntades |
|--- |--- |
| Villkor (datakällans villkor, datumvillkor) | boolesk |
| Anpassad timer | dateTimeOnly |
| Mappning av åtgärdsparametrar | Alla |
