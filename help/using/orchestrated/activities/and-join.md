---
solution: Journey Optimizer
product: journey optimizer
title: Använda aktiviteten OCH-join
description: Lär dig använda AND-join-aktiviteten i en iscensatt kampanj
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 1b99313e-f131-44f7-a129-f85e1977fb05
source-git-commit: 38b65200435e0b997e79aefbb66549b9168188fd
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 0%

---

# AND-join {#join}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_and-join"
>title="AND-join activity"
>abstract="Med aktiviteten **And-join** kan du synkronisera flera körningsgrenar för en orkestrerad kampanj. Den aktiveras när alla föregående aktiviteter har slutförts. På så sätt kan du se till att vissa aktiviteter är slutförda innan du fortsätter att köra den orkestrerade kampanjen."

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](../gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](../configuration-steps.md)<br/><br/>[Viktiga steg för att skapa samordnade kampanjer](../gs-campaign-creation.md) | [Skapa en orkestrerad kampanj](../create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](../orchestrate-activities.md)<br/><br/>[Skicka meddelanden med orkestrerade kampanjer](../send-messages.md)<br/><br/>[Starta och övervaka kampanjen](../start-monitor-campaigns.md)<br/><br/>[Rapportera](../reporting-campaigns.md) | [Arbeta med Query Modeler](../orchestrated-rule-builder.md)<br/><br/>[Skapa din första fråga](../build-query.md)<br/><br/>[Redigera uttryck](../edit-expressions.md) | [Kom igång med aktiviteter](about-activities.md)<br/><br/>Aktiviteter:<br/>[Och-join](and-join.md) - [Skapa målgrupp](build-audience.md) - [Ändra dimension](change-dimension.md) - [Kombinera](combine.md) - [Ta bort dubbletter](deduplication.md) - [Förbättra](enrichment.md) - [Förena](fork.md) - [Förena&lbrace;1 ](reconciliation.md) - [Dela](split.md) - [Vänta](wait.md) |

{style="table-layout:fixed"}

+++

<br/>

Aktiviteten **[!UICONTROL And-join]** är en **[!UICONTROL Flow control]**-aktivitet. Det gör att ni kan synkronisera flera körningsgrenar för en orkestrerad kampanj.

Den här aktiviteten utlöser endast den utgående övergången när alla inkommande övergångar har aktiverats, det vill säga när alla föregående aktiviteter har slutförts. På så sätt kan du se till att vissa aktiviteter har slutförts innan du fortsätter att köra den orkestrerade kampanjen.

## Konfigurera aktiviteten Och-join{#and-join-configuration}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_and-join_merging"
>title="Sammanfogningsalternativ"
>abstract="Välj vilka aktiviteter du vill ansluta till. I listrutan **Primär uppsättning** väljer du vilken ingående övergångspopulation du vill behålla."

Så här konfigurerar du aktiviteten **[!UICONTROL AND-join]**:

![](../assets/workflow-andjoin.png)

1. Lägg till flera aktiviteter, till exempel kanalaktiviteter, för att skapa minst två distinkta körningsgrenar.

1. Infoga en **[!UICONTROL AND-join]**-aktivitet i en av grenarna.

1. Under avsnittet **[!UICONTROL Merging options]** väljer du alla föregående aktiviteter som du vill ansluta till.

1. I listrutan **[!UICONTROL Primary set]** väljer du den inkommande övergångspopulation som du vill behålla.

## Exempel{#and-join-example}

I det här exemplet illustreras två samordnade kampanjgrenar, där vart och ett innehåller en e-postleverans, en som riktar sig till guldmedlemmar och den andra silver. **[!UICONTROL AND-join]** aktiveras när båda inkommande övergångar aktiveras och SMS skickas först när båda e-postleveranserna har slutförts, efter en 7-dagars fördröjning.

![](../assets/workflow-andjoin-example.png){zoomable="yes"}
