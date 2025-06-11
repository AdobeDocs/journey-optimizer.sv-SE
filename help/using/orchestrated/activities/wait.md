---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Vänta i samordnade kampanjer
description: Lär dig hur du använder aktiviteten Vänta i samordnade kampanjer
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 11ef095b-77ec-4e2e-ab4d-49a248354f08
source-git-commit: 5872e192c849b7a7909f0b50caa1331b15490d79
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 1%

---

# Vänta {#wait}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_wait"
>title="Vänta på aktivitet"
>abstract="Aktiviteten **Wait** används för att fördröja övergången från en aktivitet till en annan."

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](../gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](../configuration-steps.md)<br/><br/>[Viktiga steg för att skapa samordnade kampanjer](../gs-campaign-creation.md) | [Skapa en orkestrerad kampanj](../create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](../orchestrate-activities.md)<br/><br/>[Skicka meddelanden med orkestrerade kampanjer](../send-messages.md)<br/><br/>[Starta och övervaka kampanjen](../start-monitor-campaigns.md)<br/><br/>[Rapportera](../reporting-campaigns.md) | [Arbeta med Query Modeler](../orchestrated-rule-builder.md)<br/><br/>[Skapa din första fråga](../build-query.md)<br/><br/>[Redigera uttryck](../edit-expressions.md) | [Kom igång med aktiviteter](about-activities.md)<br/><br/>Aktiviteter:<br/>[Och-join](and-join.md) - [Skapa målgrupp](build-audience.md) - [Ändra dimension](change-dimension.md) - [Kombinera](combine.md) - [Ta bort dubbletter](deduplication.md) - [Förbättra](enrichment.md) - [Förena](fork.md) - [Förena&lbrace;1 ](reconciliation.md) - [Dela](split.md) - [Vänta](wait.md) |

{style="table-layout:fixed"}

+++

<br/>

**Wait**-aktiviteten är en **Flow control**-komponent som används för att skapa en fördröjning mellan två aktiviteter i en orkestrerad kampanj. Detta bidrar till att säkerställa att era uppföljningsaktiviteter är bättre tajmade och mer relevanta för användarengagemanget.

Du kan till exempel vänta några dagar efter en e-postleverans för att spåra öppningar och klickningar innan du skickar ett uppföljningsmeddelande.

## Konfiguration{#wait-configuration}

Följ de här stegen för att konfigurera aktiviteten **Wait**:

1. Lägg till en **Vänta**-aktivitet i din samordnade kampanj.

1. Välj den vänttyp som bäst passar dina behov:

   * **Varaktighet**: Ange en fördröjning i sekunder, minuter, timmar eller dagar innan du fortsätter till nästa aktivitet.

   * **Fast tid**: Ange ett specifikt datum och en speciell tid efter vilken nästa aktivitet startar.

   ![](../assets/wait_activity.png)

## Exempel{#wait-example}

I följande exempel visas aktiviteten **Wait** i ett typiskt fall.  Ett e-postmeddelande med en kampanjkod skickas till profiler som firar sina födelsedagar. Efter 29 dagar skickas ett SMS till samma grupp som en påminnelse om att deras födelsedagskod snart går ut.

![](../assets/wait-example.png)
