---
product: adobe campaign
title: notEqualIgnoreCase
description: Läs mer om funktionen notEqualIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 74f8cae0-7d2f-4f5e-bc13-837c9bc69ad9
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
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
