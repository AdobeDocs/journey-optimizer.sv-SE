---
product: adobe campaign
title: replaceAll
description: Läs om funktionen replaceAll
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 5543e123-a5f4-4153-8709-97eeb9be83ba
source-git-commit: 87b8056d26fe91a71e92ca346a9811c609d41128
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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

Eftersom målparametern är en RegExp, beroende på vilken sträng du vill ersätta, kan du behöva undvika vissa tecken. Se exemplet i [den här sidan](../functions/functionreplace.md#example_2).
