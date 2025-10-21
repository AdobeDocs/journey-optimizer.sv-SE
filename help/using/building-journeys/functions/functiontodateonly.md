---
product: journey optimizer
title: toDateOnly
description: Läs mer om funktionen toDateOnly
feature: Journeys
role: Developer
level: Experienced
keywords: toDateOnly, function, expression, travel
exl-id: 1929644f-8b51-4f95-aea5-627fc1dd115d
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 5%

---

# toDateOnly{#toDateOnly}

Konverterar ett argument till ett dateOnly-typvärde. Mer information om datatyper finns i [avsnittet](../expression/data-types.md).

## Kategori

Konvertering

## Funktionssyntax

`toDateOnly(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| Strängbeteckning för ett datum som &quot;YYY-MM-DD&quot; (XDM-format). Stöder även ISO-8601-format: endast **heldatum**-delen beaktas (se [RFC 3339, avsnitt 5.6](https://www.rfc-editor.org/rfc/rfc3339#section-5.6)) | string |
| tid | dateTime |
| datum tid utan tidszon | dateTimeOnly |
| heltalsvärde för en epok i millisekunder | heltal |

## Underskrifter och returnerade typer

`toDateOnly(<dateTime>)`

`toDateOnly(<dateTimeOnly>)`

`toDateOnly(<string>)`

`toDateOnly(<integer>, <integer>, <integer>)`

Returnerar ett dateOnly-typvärde.

## Exempel

`toDateOnly("2023-08-18")`

`toDateOnly("2023-08-18T00:00:00.000Z")`

`toDateOnly("2023-08-18T00:00:00")`

alla returnerar ett dateOnly-objekt som representerar 2023-08-18.

`toDateOnly(#{ExperiencePlatform.ProfileFieldGroup.person.birthDate})`

Returnerar ett dateOnly.
