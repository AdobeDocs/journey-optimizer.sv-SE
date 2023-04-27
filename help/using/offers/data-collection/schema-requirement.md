---
product: experience platform
solution: Experience Platform
title: Konfigurera händelsehämtning
description: Lär dig hur du konfigurerar ditt erbjudandeschema för att hämta händelser
feature: Ranking Formulas
role: User
level: Intermediate
exl-id: f70ba749-f517-4e09-a381-243b21713b48
source-git-commit: 803c9f9f05669fad0a9fdeeceef58652b6dccf70
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 1%

---

# Konfigurera datainsamling {#schema-requirements}

För att kunna få feedback om andra händelsetyper än beslutshändelser måste du ange rätt värde för varje händelsetyp i en **upplevelsehändelse** som skickas till Adobe Experience Platform.

>[!CAUTION]
>
>Kontrollera att schemat som används i datauppsättningen har **[!UICONTROL Experience Event - Proposition Interactions]** fältgrupp som är associerad med den. [Läs mer](create-dataset.md)

Nedan visas schemakraven som du måste implementera i JavaScript-koden.

>[!NOTE]
>
>Beslutsevenemang behöver inte skickas in eftersom beslutshanteringen automatiskt genererar dessa händelser och placerar dem i **[!UICONTROL ODE DecisionEvents]** datauppsättning<!--to check--> som genereras automatiskt.

## Spåra visningar

Kontrollera att händelsetypen och källan är följande:

**Typ av upplevelsehändelse:** `decisioning.propositionDisplay`
**Källa:** Web.sdk/Alloy.js (`sendEvent command -> xdm : {eventType, interactionMixin}`) eller batchförtäring
+++**Exempel på nyttolast:**

```
{
    "@id": "a7864a96-1eac-4934-ab44-54ad037b4f2b",
    "xdm:timestamp": "2020-09-26T15:52:25+00:00",
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

## Spåra klick

Kontrollera att händelsetypen och källan är följande:

**Typ av upplevelsehändelse:** `decisioning.propositionInteract`
**Källa:** Web.sdk/Alloy.js (`sendEvent command -> xdm : {eventType, interactionMixin}`) eller batchförtäring
+++**Exempel på nyttolast:**

```
{
    "@id": "a7864a96-1eac-4934-ab44-54ad037b4f2b",
    "xdm:timestamp": "2020-09-26T15:52:25+00:00",
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

## Spåra anpassade händelser

För anpassade händelser måste schemat som används i datauppsättningen också ha **[!UICONTROL Experience Event - Proposition Interactions]** fältgrupp som är associerad med den, men det finns inga specifika krav på händelsetypen upplevelse som måste användas för att tagga dessa händelser.

<!--
## Using a ranking strategy {#using-ranking}

To use the ranking strategy you created above, follow the steps below:

Once a ranking strategy has been created, you can assign it to a placement in a decision. For more on this, see [Configure offers selection in decisions](../offer-activities/configure-offer-selection.md).

1. Create a decision.
1. Add a placement.
1. Add a collection.
1. Choose to rank offers by AI ranking (select it from the drop-down list).
1. Click Add ranking.
1. Select the ranking strategy that you created. All the details of the ranking strategy are displayed.
1. Click Next to confirm.
1. Save your decision.

It is now ready to be used in a decision to rank eligible offers for a placement (see [Configure offers selection in decisions](../offer-activities/configure-offer-selection.md)).
-->
