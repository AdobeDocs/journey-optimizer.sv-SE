---
product: journey optimizer
title: replaceAll
description: Läs mer om funktionen replaceAll
feature: Journeys
role: Developer
level: Experienced
keywords: replaceAll, funktion, uttryck, resa
exl-id: 5543e123-a5f4-4153-8709-97eeb9be83ba
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 3%

---

# replaceAll {#replaceAll}

Ersätter alla förekomster som matchar målsträngen med ersättningssträngen i bassträngen.

Ersättningen fortsätter från början av strängen till slutet, t.ex. om&quot;a&quot; ersätts med&quot;b&quot; i strängen&quot;aaa&quot; resulterar det i&quot;ba&quot; i stället för&quot;ab&quot;.

## Kategori

Sträng

## Funktionssyntax

`replaceAll(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|--------------|
| bas | string |
| target | sträng (RegExp) |
| ersättare | string |

## Signatur och returtyp

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

Returnerar en sträng.

## Exempel{#example}

`replaceAll("Hello World", "l", "x")`

Returnerar &quot;Hexo Worxd&quot;.

Eftersom målparametern är en RegExp, beroende på vilken sträng du vill ersätta, kan du behöva undvika vissa tecken. Se exemplet på [den här sidan](../functions/functionreplace.md#example_2).
