---
product: journey optimizer
title: inSegment
description: Läs mer om funktionen inSegment
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: inSegment, funktion, uttryck, resa
exl-id: 8417af75-6e97-4ad4-86b4-3ecd264a5560
source-git-commit: 85a8d0713f87a8b3505a2294402156ba6598c8bb
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 4%

---

# inSegment {#inSegment}

Kontrollerar om en person tillhör en viss målgrupp.

>[!NOTE]
>
>Ni kan hämta upp till 100 målgrupper.

Målgruppsnamnet måste vara en strängkonstant. Det kan inte vara en fältreferens eller ett uttryck.

Målgrupper definieras i [Adobe Experience Platform](https://platform.adobe.com/audience/overview) . Uttrycksredigeraren innehåller en automatiskt ifylld lista över målgrupper.

Målgrupper kan ha två statusar:

* realiserad: Enheten kvalificerar sig för segmentdefinitionen.
* avslutad: Entiteten avslutar segmentdefinitionen.

Endast personer med **Realiserad**-målgruppsdeltagarstatus betraktas som medlemmar av målgruppen. Mer information om hur du utvärderar en målgrupp finns i [dokumentationen för segmenteringstjänsten](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=sv-SE#interpret-segment-results).

`IF inSegment('segmentName') == true` betyder att du har ett segmentMembership med den angivna/befintliga statusen.

`ELSE inSegment('segmentName') == false` betyder att du har ett segmentMembership med statusen avslutad.

## Kategori

Adobe Experience Platform

## Funktionssyntax

`inSegment(<parameter>)`

## Parametrar

| Parameter | Beskrivning | Typ |
|--- |--- |--- |
| Segment | Målgruppens namn | `<string>` |

## Signatur och returtyp

`inSegment(<string>)`

Returnerar ett booleskt värde.

## Exempel

`inSegment("men over 50")`

Förklaring:

Funktionen returnerar **[!UICONTROL true]** om personen i reseinstansen är en del av Adobe Experience Platform-publiken med namnet&quot;män över 50&quot;, annars **[!UICONTROL false]**.
