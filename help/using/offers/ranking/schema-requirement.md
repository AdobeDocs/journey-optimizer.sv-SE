---
product: experience platform
solution: Experience Platform
title: Konfigurera händelsehämtning
description: Lär dig hur du konfigurerar ditt erbjudandeschema för att hämta händelser
feature: Ranking Formulas
role: User
level: Intermediate
source-git-commit: 12b01cb9de84399e5ede987866609acc10b64c5f
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 0%

---

# Konfigurera händelsehämtning {#schema-requirements}

Nu måste du ha:

* skapade AI-modellen,
* definierade vilken typ av händelse du vill fånga - erbjudandet visas (intryck) och/eller erbjudandet klickas (konvertering),
* och i vilken datauppsättning du vill samla in händelsedata.

Varje gång ett erbjudande visas och/eller klickas vill du att motsvarande händelse ska spelas in automatiskt av **[!UICONTROL Experience Event - Proposition Interactions]** fältgrupp med [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/web-sdk-faq.html#what-is-adobe-experience-platform-web-sdk%3F){target=&quot;_blank&quot;} eller Mobile SDK.

För att kunna skicka i händelsetyper (erbjudandet visas eller erbjudandet klickas) måste du ange rätt värde för varje händelsetyp i en upplevelsehändelse som skickas till Adobe Experience Platform. Nedan följer schemakraven som du måste implementera i din JavaScript-kod:

### Visa scenario

**Händelsetyp:** `decisioning.propositionDisplay`
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
            "xdm:id": "3cc33a7e-13ca-4b19-b25d-c816eff9a70a", //decision event id - taken from experience event for “nextBestOffer”
            "xdm:scope": "scope:12cfc3fa94281acb", //decision scope id - taken from experience event for “nextBestOffer”
        }
    ]
}
```

+++

### Erbjud klickat scenario

**Händelsetyp:** `decisioning.propositionInteract`
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

