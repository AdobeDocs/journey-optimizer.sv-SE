---
solution: Journey Optimizer
product: journey optimizer
title: resefält
description: resefält
feature: Journeys, Reporting
topic: Content Management
role: Developer, Admin
level: Experienced
exl-id: 177b4a97-c757-40ca-a190-fbd88169e5e2
source-git-commit: 6961a07e2874f9beb76a9beaebb29997d114d8e7
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 3%

---

# Resefält {#sharing-journey-fields}

Den här fältgruppen används i schemat **travel** (i relation till **travelStepEvent**). Den innehåller fälten som listas nedan.


>[!NOTE]
>
>Läs mer om attribut för reseegenskaper [i det här avsnittet](../building-journeys/expression/journey-properties.md#journey-properties-fields).


## travelID {#journeyid-field}

ID för huvudresan.

Typ: sträng

## travelVersionID {#journeyversionid-field}

ID för reseversionen. Detta ID representerar identiteten på en resa.

Typ: sträng

## name {#name-field}

Namn på resan.

Typ: sträng

>[!NOTE]
>
>Resursnamnet används för att länka data för körning av resan till rapportdatamängder. Om du byter namn på en resa kontrollerar du att det nya namnet matchar namnet i rapportdatauppsättningen för att få korrekta rapporter. En felmatchning kan göra att rapportdata inte visas som förväntat. Läs mer om [felsökning av saknade rapporteringsdata](../building-journeys/report-journey.md#troubleshooting-missing-data).

## description {#description-field}

Beskrivning av resan.

Typ: sträng

## version {#version-field}

Version, representerad som `major`.`minor`

Typ: sträng
