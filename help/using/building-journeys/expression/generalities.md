---
solution: Journey Optimizer
product: journey optimizer
title: Syntax för avancerad uttrycksredigerare
description: Läs mer om syntaxen som används i den avancerade uttrycksredigeraren
feature: Journeys
role: Developer
level: Experienced
keywords: syntax, redigerare, resa
exl-id: c9434b28-2750-4a53-985e-c4a3f940472c
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---

# Syntax för avancerad uttrycksredigerare {#syntax}

Syntaxgrunderna när du använder [redigeraren för avancerade uttryck](expressionadvanced.md) visas nedan. <!-- Samples of use of the advanced expression editor are available on [this page](advanced-editor-use-cases.md).-->

## Parenteser och uttrycksprioritet {#parentheses-and-expression-priority}

Parenteser kan användas för att göra ett komplext uttryck mer läsbart. _(&lt;expression>)_ är motsvarigheten till _&lt;expression>_. Parenteser kan också användas för att definiera utvärderingsordningen och associativiteten.

Uttrycken utvärderas från vänster till höger. Associativiteten för aritmetiska operatorer måste tillämpas: multiplikationer och indelningar prioriteras framför tillägg och subtraktioner. För att införa en viss ordning måste parenteser läggas till för att avgränsa operationerna. Exempel:

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| Uttryck | Utvärdering |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39; har högre prioritet än &#39;+&#39;: 2 \* 10 utvärderas → 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>Parenteserna ändrar prioriteten: (4 + 2) utvärderas → 6</li><li> 6 * 10 → 60</li></ul> |

## Skiftlägeskänslighet {#case-sensitivity}

Här är de olika reglerna för skiftlägeskänslighet:

* Alla operatorer (och, eller, osv.) ska skrivas med gemener. _`<expression1>`och`<expression2>`_ är till exempel ett giltigt uttryck, men uttrycket _`<expression1>`AND`<expression2>`_ är inte det.
* Alla funktionsnamn är versalkänsliga. _inAudience()_ är till exempel giltig, men funktionen _INAUDIENCE()_ är inte giltig.
* Fältreferenser och konstanta värden är skiftlägeskänsliga: de är inte inbyggda element i språket (till skillnad från operatorer och funktioner), utan skapas av slutanvändaren.

## Returnerad uttryckstyp {#returned-expression-type}

Beroende på användningssammanhanget kan uttrycksredigeraren returnera olika värden.

| Avancerad användning av uttrycksredigerare | Returnerad uttryckstyp förväntades |
|--- |--- |
| Villkor (datakällans villkor, datumvillkor) | boolesk |
| Anpassad timer | dateTimeOnly |
| Mappning av åtgärdsparametrar | Alla |
