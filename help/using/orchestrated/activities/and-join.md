---
solution: Journey Optimizer
product: journey optimizer
title: Använda aktiviteten OCH-join
description: Lär dig använda AND-join-aktiviteten i en orkestrerad kampanj
exl-id: 1b99313e-f131-44f7-a129-f85e1977fb05
version: Campaign Orchestration
source-git-commit: 07ec28f7d64296bdc2020a77f50c49fa92074a83
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 0%

---


# AND-join {#join}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_and-join"
>title="AND-join activity"
>abstract="Med aktiviteten **And-join** kan du synkronisera flera körningsgrenar för en Orchestrated-kampanj. Den aktiveras när alla föregående aktiviteter har slutförts. På så sätt kan du se till att vissa aktiviteter är slutförda innan du fortsätter att köra den Orchestrated-kampanjen."

Aktiviteten **[!UICONTROL And-join]** är en **[!UICONTROL Flow control]**-aktivitet. Med den kan ni synkronisera flera körningsgrenar för en orchestrerad-kampanj.

Den här aktiviteten utlöser endast den utgående övergången när alla inkommande övergångar har aktiverats, det vill säga när alla föregående aktiviteter har slutförts. På så sätt kan du se till att vissa aktiviteter har slutförts innan du fortsätter att köra den Orchestrated-kampanjen.

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
