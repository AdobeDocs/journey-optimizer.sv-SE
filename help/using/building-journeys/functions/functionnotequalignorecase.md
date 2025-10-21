---
product: journey optimizer
title: notEqualIgnoreCase
description: Läs mer om funktionen notEqualIgnoreCase
feature: Journeys
role: Developer
level: Experienced
keywords: notEqualIgnoreCase, funktion, uttryck, resa
exl-id: 74f8cae0-7d2f-4f5e-bc13-837c9bc69ad9
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 2%

---

# notEqualIgnoreCase {#notEqualIgnoreCase}

Kontrollera om den första argumentsträngen med den andra argumentsträngen är annorlunda och ignorerar skiftlägeskänslighet.

## Kategori

Sträng

## Funktionssyntax

`notEqualIgnoreCase(<parameters>)`

## Parametrar

* string

## Signatur och returtyp

`notEqualIgnoreCase(<string>,<string>)`

Returnerar ett booleskt värde.

## Exempel

`notEqualIgnoreCase(@event{iOSPushPermissionAllowed.device.model}, "iPad")`
