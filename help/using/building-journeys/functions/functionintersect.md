---
product: adobe campaign
title: korsa
description: Lär dig mer om funktionsöverlappningen
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e236efa9-91a8-4f08-94c6-45f1e060bb2f
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 11%

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
| lista 1 | lista |
| lista 2 | lista |

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
    ["sports", "news", "documentary"]
)
```

Returnerar vanliga objekt mellan profilattribut och angiven lista med kategorier.

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @{myEvent.sport_interests}
)
```

Returnerar vanliga objekt mellan profilattribut och angivet händelsefält.