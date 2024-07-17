---
product: journey optimizer
title: inAudience
description: Läs om funktionen inAudience
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: inAudience, funktion, uttryck, resa
exl-id: 8417af75-6e97-4ad4-86b4-3ecd264a5560
source-git-commit: d3f0adab52ed8e44a6097c5079396d1e9c06e0a7
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 3%

---

# inAudience {#inAudience}

Kontrollerar om en person tillhör en viss målgrupp.

>[!NOTE]
>
>Ni kan hämta upp till 100 målgrupper.

Målgruppsnamnet måste vara en strängkonstant. Det kan inte vara en fältreferens eller ett uttryck.

Målgrupper definieras i [Adobe Experience Platform](https://platform.adobe.com/audience/overview) . Uttrycksredigeraren innehåller en automatiskt ifylld lista över målgrupper.

Målgrupper kan ha tre statusvärden:

* befintlig: entiteten fortsätter att vara i målgruppen.
* realiserad: företaget går in i målgruppen.
* avslutad: entiteten avslutar publiken.

Endast personer med **Realiserad** och **befintlig** status för målgruppsdeltagande betraktas som medlemmar i målgruppen. Mer information om hur du utvärderar en målgrupp finns i [dokumentationen för segmenteringstjänsten](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html#interpret-segment-results).

`inAudience('audienceName') == true` betyder att du har ett segmentMembership med den angivna/befintliga statusen.

`inAudience('audienceName') == false` betyder att du har ett segmentMembership med statusen avslutad.

## Kategori

Adobe Experience Platform

## Funktionssyntax

`inAudience(<parameter>)`

## Parametrar

| Parameter | Beskrivning | Typ |
|--- |--- |--- |
| Målgrupp | Målgruppens namn | `<string>` |

## Signatur och returtyp

`inAudience(<string>)`

Returnerar ett booleskt värde.

## Exempel

`inAudience("men over 50")`

Förklaring:

Funktionen returnerar **[!UICONTROL true]** om personen i reseinstansen är en del av Adobe Experience Platform-publiken med namnet&quot;män över 50&quot;, annars **[!UICONTROL false]**.
