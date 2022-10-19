---
product: journey optimizer
title: inSegment
description: Läs mer om funktionen inSegment
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8417af75-6e97-4ad4-86b4-3ecd264a5560
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 5%

---

# inSegment {#inSegment}

Kontrollerar om en individ tillhör ett visst segment.

>[!NOTE]
>
>Du kan hämta upp till 100 segment.

Segmentnamnet måste vara en strängkonstant. Det kan inte vara en fältreferens eller ett uttryck.

Segmenten definieras i [Adobe Experience Platform](https://platform.adobe.com/segment/overview). Uttrycksredigeraren innehåller en lista över segment som fylls i automatiskt.

Segment kan ha tre statusar:

* befintlig: entiteten fortsätter att vara i segmentet.
* realiserad: företaget anger segmentet.
* avslutad: enheten avslutar segmentet.

Endast personer med **Realiserad** och **Befintlig** Deltagandestatus för segment betraktas som medlemmar i segmentet. Mer information om hur du utvärderar ett segment finns i [Dokumentation för segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

`IF inSegment('segmentName') == true` betyder att du har ett segmentMembership med den angivna/befintliga statusen.

`ELSE inSegment('segmentName') == false` betyder att du har ett segmentMembership med statusen avslutad.

## Kategori

Adobe Experience Platform

## Funktionssyntax

`inSegment(<parameter>)`

## Parametrar

| Parameter | Beskrivning | Typ |
|--- |--- |--- |
| Segment | Segmentnamnet | `<string>` |

## Signatur och returtyp

`inSegment(<string>)`

Returnerar ett booleskt värde.

## Exempel

`inSegment("men over 50")`

Förklaring:

Funktionen returneras **[!UICONTROL true]** om personen i reseinstansen är en del av Adobe Experience Platform-segmentet med namnet&quot;män över 50&quot;, **[!UICONTROL false]** i annat fall.
