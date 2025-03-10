---
solution: Journey Optimizer
product: journey optimizer
title: Använda aktiviteten OCH-join
description: Lär dig hur du använder AND-join-aktiviteten i en flerstegskampanj
hide: true
hidefromtoc: true
source-git-commit: dfa6c6e11db10f3e843035d32e322b212361548c
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# AND-join {#join}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_and-join"
>title="AND-join activity"
>abstract="Med aktiviteten **And-join** kan du synkronisera flera körningsgrenar för en flerstegskampanj. Den aktiveras när alla föregående aktiviteter har slutförts. På så sätt kan du se till att vissa aktiviteter är slutförda innan du fortsätter att köra flerstegskampanjen."

Aktiviteten **And-join** är en **Flow control** -aktivitet. Med den kan ni synkronisera flera körningsgrenar för en flerstegskampanj.

Den här aktiviteten utlöser endast den utgående övergången när alla inkommande övergångar har aktiverats, det vill säga när alla föregående aktiviteter har slutförts. På så sätt kan du se till att vissa aktiviteter har slutförts innan du fortsätter att köra flerstegskampanjen.

## Konfigurera aktiviteten Och-join{#and-join-configuration}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_and-join_merging"
>title="Sammanfogningsalternativ"
>abstract="Välj vilka aktiviteter du vill ansluta till. I listrutan **Primär uppsättning** väljer du vilken ingående övergångspopulation du vill behålla."

Följ de här stegen för att konfigurera aktiviteten **AND-join**:

![](../assets/workflow-andjoin.png)

1. Lägg till flera aktiviteter, till exempel kanalaktiviteter, för att bilda minst två olika utförandegrenar.
1. Lägg till en **AND-join**-aktivitet i någon av grenarna.
1. I avsnittet **Sammanfogningsalternativ** markerar du alla tidigare aktiviteter som du vill ansluta till.
1. I listrutan **Primär uppsättning** väljer du vilken ingående övergångspopulation du vill behålla. Den utgående övergången kan bara innehålla en av de ingående övergångspopulationerna.

## Exempel{#and-join-example}

I följande exempel visas två kampanjgrenar i flera steg med e-post och SMS-leverans. AND-join utlöses när båda inkommande övergångar är aktiverade. Push-meddelandena skickas sedan först när båda leveranserna är klara.

![](../assets/workflow-andjoin-example.png){zoomable="yes"}
