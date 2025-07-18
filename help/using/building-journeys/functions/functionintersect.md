---
product: journey optimizer
title: korsa
description: Lär dig mer om funktionsöverlappningen
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: intersect, function, expression, travel
exl-id: e236efa9-91a8-4f08-94c6-45f1e060bb2f
source-git-commit: 49c3fd09d23e6394b6eff8ba4da71ed7bab8c82c
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 8%

---

# korsa{#intersect}

Returnerar de gemensamma värdena i de två indatalistorna. Om en av de två listorna är null returneras en tom lista.

## Kategori

Lista

## Funktionssyntax

`intersect(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| lista 1 | list |
| lista 2 | list |

## Underskrifter och returnerade typer

`intersect(listString,listString)`: listString
`intersect(listDecimal,listDecimal)`: listDecimal
`intersect(listInteger,listInteger)`: listInteger
`intersect(listDateTime,listDateTime)`: listDateTime
`intersect(listDateTimeOnly,listDateTimeOnly)`: listDateTimeOnly
`intersect(listDateOnly,listDateOnly)`: listDateOnly
`intersect(listDuration,listDuration)`: listDuration
`intersect(listBoolean,listBoolean)`: listBoolean

Returnerar en lista.

## Exempel

```json
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

Returnerar [&quot;sport&quot;, &quot;news&quot;]

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "documentary"]
)
```

Returnerar vanliga objekt mellan profilattribut och angiven lista med kategorier.

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @event{myEvent.sport_interests}
)
```

Returnerar vanliga objekt mellan profilattribut och angivet händelsefält.
