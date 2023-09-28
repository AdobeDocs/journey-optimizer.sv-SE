---
product: journey optimizer
title: inSegment
description: Läs mer om funktionen inSegment
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: inSegment, funktion, uttryck, resa
exl-id: 8417af75-6e97-4ad4-86b4-3ecd264a5560
source-git-commit: be372f8f80d304067748d539fb8e210df6280721
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# inSegment {#inSegment}

Kontrollerar om en person tillhör en viss målgrupp.

>[!NOTE]
>
>Ni kan hämta upp till 100 målgrupper.

Målgruppsnamnet måste vara en strängkonstant. Det kan inte vara en fältreferens eller ett uttryck.

Målgrupper definieras i [Adobe Experience Platform](https://platform.adobe.com/audience/overview). Uttrycksredigeraren innehåller en automatiskt ifylld lista över målgrupper.

Målgrupper kan ha tre statusvärden:

* befintlig: entiteten fortsätter att vara i målgruppen.
* realiserad: företaget går in i målgruppen.
* avslutad: entiteten avslutar publiken.

Endast personer med **Realiserad** och **Befintlig** Status för målgruppsdeltagande kommer att betraktas som medlemmar av målgruppen. Mer information om hur du utvärderar en målgrupp finns i [Dokumentation för segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html#interpret-segment-results).

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

Funktionen returneras **[!UICONTROL true]** om personen i reseinstansen är en del av Adobe Experience Platform målgrupp med namnet&quot;män över 50&quot;, **[!UICONTROL false]** annars.
