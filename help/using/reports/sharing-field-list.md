---
solution: Journey Optimizer
product: journey optimizer
title: Lista över steghändelsefält
description: Lista över steghändelsefält
feature: Journeys, Reporting
topic: Content Management
role: Data Engineer, Data Architect, Admin
level: Experienced
exl-id: e96efa67-ee47-40b9-b680-f5119d8c3481
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 12%

---

# Lista över steghändelsefält {#sharing-field-list}

Fälten för steghändelser är ordnade efter kategori.

* Felsöka informationsfält
* Resefält
* Profilfält
* Tjänstehändelsefält

## debugInfo {#debuginfo-field}

| Fältnamn | Typ | Beskrivning |
|---|---|------------|
| requestId | Sträng | Begärande-ID som används av Journey Optimizer för att spåra flödet för en begäran. |

## resa {#journey-field}

Den här fältgruppen används i transportschemat (i relation till travelStepEvent). Den innehåller följande fält:

| Fältnamn | Typ | Beskrivning |
|---|---|------------|
| ID | Sträng | Identifierare för angiven resa |
| VersionID | Sträng | ID för reseversionen. Detta ID representerar identiteten på en resa |
| name | Sträng | Namn på resan |
| description | Sträng | Beskrivning av resan |
| version | Sträng | version, representerad som `major`.`minor` |

## profil {#profile-field}

Den här fältgruppen är specifik för travelStepEvent: den här händelsen är relaterad till resan och har inte identityMap, som beskriver profilens identitet, om sådan finns.

För travelStepEvent måste vi även lägga till fält som är relaterade till identiteten:

| Fältnamn | Typ | Beskrivning |
|---|---|------------|
| ID | Sträng | Profilidentifierare identifierar den profil som skickas/används under en resa. Exempel: foo@adobe.com. |
| namespace | Sträng | Det här fältet beskriver namnutrymmet som refereras av den profil som används i resan. Exempel: E-post, ECID |

## serviceEvents {#servicevents-field}

Den här mixinen innehåller alla fält som motsvarar ett profilexportjobb.

| Fältnamn | Typ | Beskrivning |
|---|---|------------|
| ID | Sträng | Identifieraren för det utlösta målgruppsexportjobbet |
| status | Sträng | Status för målgruppens exportjobb: köad, startad, avslutad |
| exportCountTotal | Heltal | Högsta möjliga värde för målgruppens exportjobb |
| exportCountRealized | Heltal | Det faktiska antalet målgrupper som exporterats via jobbet |
| exportCountFailed | Heltal | Antalet målgrupper som misslyckades vid export via jobbet |
| exportSegmentID | Sträng | Identifieraren för målgruppen som exporteras |
| eventType | Sträng | Händelsetypen anger om det är en felhändelse för info-händelsen: Info, Error |
| eventCode | Sträng | Felkoden som anger orsaken till motsvarande eventType |

## stepEvents {#stepevents-field}

Den här kategorin innehåller de ursprungliga fälten för steghändelser. Se detta [section](../reports/sharing-legacy-fields.md).
