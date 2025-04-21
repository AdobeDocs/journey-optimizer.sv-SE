---
solution: Journey Optimizer
product: journey optimizer
title: Använda aktiviteten OCH-join
description: Lär dig använda AND-join-aktiviteten i en iscensatt kampanj
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 1b99313e-f131-44f7-a129-f85e1977fb05
source-git-commit: bdc584c1aae0c735d81dfc95e11f96f755bea26a
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 0%

---

# AND-join {#join}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_and-join"
>title="AND-join activity"
>abstract="Med aktiviteten **And-join** kan du synkronisera flera körningsgrenar för en orkestrerad kampanj. Den aktiveras när alla föregående aktiviteter har slutförts. På så sätt kan du se till att vissa aktiviteter är slutförda innan du fortsätter att köra den orkestrerade kampanjen."

Aktiviteten **And-join** är en **Flow control** -aktivitet. Det gör att ni kan synkronisera flera körningsgrenar för en orkestrerad kampanj.

Den här aktiviteten utlöser endast den utgående övergången när alla inkommande övergångar har aktiverats, det vill säga när alla föregående aktiviteter har slutförts. På så sätt kan du se till att vissa aktiviteter har slutförts innan du fortsätter att köra den orkestrerade kampanjen.

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

I följande exempel visas två samordnade kampanjgrenar med e-post och SMS-leverans. AND-join utlöses när båda inkommande övergångar är aktiverade. Push-meddelandena skickas sedan först när båda leveranserna är klara.

![](../assets/workflow-andjoin-example.png){zoomable="yes"}
