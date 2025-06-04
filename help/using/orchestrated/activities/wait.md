---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Vänta i samordnade kampanjer
description: Lär dig hur du använder aktiviteten Vänta i samordnade kampanjer
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 11ef095b-77ec-4e2e-ab4d-49a248354f08
source-git-commit: 32b13d4fd62abc8052c1bf64d8a2d5e97bd0f464
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 17%

---

# Vänta {#wait}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_wait"
>title="Vänta på aktivitet"
>abstract="Aktiviteten **Wait** används för att fördröja övergången från en aktivitet till en annan."

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](../gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](../configuration-steps.md)<br/><br/>[Viktiga steg för att skapa samordnade kampanjer](../gs-campaign-creation.md) | [Skapa en orkestrerad kampanj](../create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](../orchestrate-activities.md)<br/><br/>[Skicka meddelanden med orkestrerade kampanjer](../send-messages.md)<br/><br/>[Starta och övervaka kampanjen](../start-monitor-campaigns.md)<br/><br/>[Rapportera](../reporting-campaigns.md) | [Arbeta med Query Modeler](../orchestrated-query-modeler.md)<br/><br/>[Skapa din första fråga](../build-query.md)<br/><br/>[Redigera uttryck](../edit-expressions.md) | [Kom igång med aktiviteter](about-activities.md)<br/><br/>Aktiviteter:<br/>[Och-join](and-join.md) - [Skapa målgrupp](build-audience.md) - [Ändra dimension](change-dimension.md) - [Kombinera](combine.md) - [Ta bort dubbletter](deduplication.md) - [Förbättra](enrichment.md) - [Förena](fork.md) - [Förena{1 ](reconciliation.md) - [Dela](split.md) - [Vänta](wait.md) |

{style="table-layout:fixed"}

+++

<br/><br/>

Aktiviteten **Wait** är en **Flow control**-aktivitet. Det används för att en viss tid ska kunna förflyta mellan två aktiviteter som utförs. Om du till exempel vill vänta flera dagar efter en aktivitet där e-post levererats så analyserar du de öppningar och klick som genereras under den här perioden innan du utför några uppföljningsåtgärder (påminnelser via e-post, målgruppsgenerering osv.).

## Konfiguration{#wait-configuration}

Följ de här stegen för att konfigurera aktiviteten **Wait**:

1. Lägg till en **Vänta**-aktivitet i din samordnade kampanj.

1. Ange **Varaktighet** för väntetiden mellan inkommande och utgående övergångar.

1. Välj tidsenhet i fältet **Perioder**: sekunder, minuter, timmar, dagar.

## Exempel{#wait-example}

I följande exempel visas aktiviteten **Wait** i ett typiskt fall. En e-postinbjudan till ett event skickas.  24 timmar efter att det skickats skickas ett SMS-meddelande till samma population.

![](../assets/workflow-wait-example.png)
