---
product: adobe campaign
title: notEqualIgnoreCase
description: Läs mer om funktionen notEqualIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 23f4e8224ea5b00e8132b6a3f3e32f73b0cc993f
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 10%

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

`notEqualIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad")`
