---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: Konfigurera händelsehämtning
description: Lär dig hur du konfigurerar ditt erbjudandeschema för att hämta händelser
badge: label="Äldre" type="Informative"
feature: Ranking, Datasets, Decision Management
role: Developer
level: Experienced
exl-id: f70ba749-f517-4e09-a381-243b21713b48
version: Journey Orchestration
source-git-commit: d6a9a8a392f0492aa6e4f059198ce77b6b2cd962
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 0%

---

# Konfigurera datainsamling {#schema-requirements}

För att kunna få feedback om andra händelsetyper än beslutshändelser måste du ange rätt värde för varje händelsetyp i en **upplevelsehändelse** som skickas till Adobe Experience Platform.

>[!CAUTION]
>
>Kontrollera att schemat som används i datauppsättningen har fältgruppen **[!UICONTROL Experience Event - Proposition Interactions]** associerad för varje händelsetyp. [Läs mer](create-dataset.md)

Nedan visas schemakraven som du måste implementera i din JavaScript-kod.

>[!NOTE]
>
>Beslutshändelser behöver inte skickas in eftersom beslutshanteringen genererar dessa händelser automatiskt och placerar dem i den **[!UICONTROL ODE DecisionEvents]** datauppsättning <!--to check--> som genereras automatiskt.

## Spåra visningar {#track-impressions}

Kontrollera att händelsetypen och källan är följande:

**Typ av upplevelsehändelse:** `decisioning.propositionDisplay`
**Source:** Web.sdk/Alloy.js (`sendEvent command -> xdm : {eventType, interactionMixin}`) eller batchhantering
+++**Exempel på nyttolast:**

```
{
    "@id": "a7864a96-1eac-4934-ab44-54ad037b4f2b",
    "xdm:timestamp": "2023-09-26T15:52:25+00:00",
    "xdm:eventType": "decisioning.propositionDisplay",
    "https://ns.adobe.com/experience/decisioning/propositions":
    [
        {
            "xdm:items":
            [
                {
                    "xdm:id": "personalized-offer:f67bab756ed6ee4",
                },
                {
                    "xdm:id": "personalized-offer:f67bab756ed6ee5",
                }
            ],
            "xdm:id": "3cc33a7e-13ca-4b19-b25d-c816eff9a70a", //decision event id - taken from experience event for "nextBestOffer"
            "xdm:scope": "scope:12cfc3fa94281acb", //decision scope id - taken from experience event for "nextBestOffer"
        }
    ]
}
```

+++

## Spåra klick {#track-clicks}

Kontrollera att händelsetypen och källan är följande:

**Typ av upplevelsehändelse:** `decisioning.propositionInteract`
**Source:** Web.sdk/Alloy.js (`sendEvent command -> xdm : {eventType, interactionMixin}`) eller batchhantering
+++**Exempel på nyttolast:**

```
{
    "@id": "a7864a96-1eac-4934-ab44-54ad037b4f2b",
    "xdm:timestamp": "2023-09-26T15:52:25+00:00",
    "xdm:eventType": "decisioning.propositionInteract",
    "https://ns.adobe.com/experience/decisioning/propositions":
    [
        {
            "xdm:items":
            [
                {
                    "xdm:id": "personalized-offer:f67bab756ed6ee4"
                },
                {
                    "xdm:id": "personalized-offer:f67bab756ed6ee5"
                },
            ],
            "xdm:id": "3cc33a7e-13ca-4b19-b25d-c816eff9a70a", //decision event id
            "xdm:scope": "scope:12cfc3fa94281acb", //decision scope id
        }
    ]
}
```

+++

## Spåra anpassade händelser {#track-custom-events}

För anpassade händelser måste schemat som används i datauppsättningen också ha fältgruppen **[!UICONTROL Experience Event - Proposition Interactions]** associerad med den, men det finns inga specifika krav på händelsetypen för upplevelse som måste användas för att tagga dessa händelser.

>[!NOTE]
>
>Om du vill att dina anpassade händelser ska räknas med i [frekvensbegränsning](../offer-library/add-constraints.md#capping) måste du ansluta upplevelsehändelsen till Adobe Experience Platform-slutpunkter genom att skicka den till någon av dessa två Edge datainsamlingsslutpunkter:
>
>* POST /ee/v2/interact
>* POST /ee/v2/collect
>
>Om du använder [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html){target="_blank"} eller [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/platform-learn/data-collection/mobile-sdk/overview.html){target="_blank"} skapas anslutningen automatiskt.
