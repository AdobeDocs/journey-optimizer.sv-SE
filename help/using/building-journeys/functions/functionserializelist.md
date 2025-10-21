---
product: journey optimizer
title: serializeList
description: Läs mer om funktionen serializeList
feature: Journeys
role: Developer
level: Experienced
keywords: serializeList, funktion, uttryck, resa
exl-id: 7ead9fa1-59b3-4960-818c-fe6321422952
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 5%

---

# serializeList {#serializeList}

Konverterar en given lista (alla typer utom listObject) till en sträng.

## Kategori

Lista

## Funktionssyntax

`serializeList(<parameters>)`

## Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly | Lista som ska konverteras till en sträng. |
| avgränsare | string | Avgränsare mellan varje listelement i utdatasträngen. |
| addQuotes | boolesk | Den här parametern anger om varje element i utdatasträngen ska innehålla citattecken (true) eller inte (false). |

## Signatur och returtyp

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDateOnly>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

Returnera en sträng.

## Exempel

`serializeList(["Hello","World"], " ", false)`

Returnerar &quot;Hello World&quot;.

`serializeList(["Hello", "World"], ",", true)`

Returnerar &quot;&quot;Hello&quot;,&quot;World&quot;&quot;.
