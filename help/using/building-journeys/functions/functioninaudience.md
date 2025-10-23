---
product: journey optimizer
title: inAudience
description: Läs om funktionen inAudience
feature: Journeys
role: Developer
level: Experienced
keywords: inAudience, funktion, uttryck, resa
exl-id: 8417af75-6e97-4ad4-86b4-3ecd264a5560
version: Journey Orchestration
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 3%

---

# inAudience {#inAudience}

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

`inAudience('audienceName') == true` betyder att du har ett segmentMembership med den angivna statusen.

`inAudience('audienceName') == false` betyder att du har ett segmentMembership med statusen avslutad.


>[!IMPORTANT]
>
>Om du ändrar namnet på en befintlig målgrupp uppdateras inte automatiskt några referenser till den målgruppen i dina reseuttryck. Om villkorsnoden använder `inAudience('oldAudienceName')` måste du redigera uttrycket manuellt för att använda det nya namnet. Om du inte gör det kommer transportvillkoret att brytas.

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

