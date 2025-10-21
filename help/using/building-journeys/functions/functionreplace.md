---
product: journey optimizer
title: ersätta
description: Läs mer om funktionsersättningen
feature: Journeys
role: Developer
level: Experienced
keywords: ersätt, funktion, uttryck, resa
exl-id: 3eb35fd6-2d11-4f24-b0d9-5334e7ed7872
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 2%

---

# ersätta {#replace}

Ersätter den första förekomsten som matchar målsträngen med ersättningssträngen i bassträngen.

Ersättningen fortsätter från början av strängen till slutet, t.ex. om&quot;a&quot; ersätts med&quot;b&quot; i strängen&quot;aaa&quot; resulterar det i&quot;ba&quot; i stället för&quot;ab&quot;.

## Kategori

Sträng

## Funktionssyntax

`replace(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|--------------|
| bas | string |
| target | sträng (RegExp) |
| ersättare | string |

## Signatur och returtyp

`replace(<base>,<target>,<replacement>)`

Returnera en sträng.

## Exempel 1

`replace("Hello World", "l", "x")`

Returnerar &quot;Hexlo World&quot;.

## Exempel 2 {#example_2}

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
