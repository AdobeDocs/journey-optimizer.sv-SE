---
product: journey optimizer
title: replaceAll
description: Läs mer om funktionen replaceAll
feature: Journeys
role: Engineer
level: Experienced
keywords: replaceAll, funktion, uttryck, resa
exl-id: 5543e123-a5f4-4153-8709-97eeb9be83ba
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
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
