---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Vänta i orkestrerade kampanjer
description: Lär dig hur du använder aktiviteten Vänta i orkestrerade kampanjer
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 11ef095b-77ec-4e2e-ab4d-49a248354f08
source-git-commit: 3be1b238962fa5d0e2f47b64f6fa5ab4337272a5
workflow-type: tm+mt
source-wordcount: '303'
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
| [Kom igång med samordnade kampanjer](../gs-orchestrated-campaigns.md)<br/><br/>Skapa och hantera relationsscheman och datauppsättningar:</br> <ul><li>[Kom igång med scheman och datauppsättningar](../gs-schemas.md)</li><li>[Manuellt schema](../manual-schema.md)</li><li>[Filöverföringsschema](../file-upload-schema.md)</li><li>[Ingest data](../ingest-data.md)</li></ul>[Få åtkomst till och hantera samordnade kampanjer](../access-manage-orchestrated-campaigns.md) | [Viktiga steg för att skapa en orkestrerad kampanj](../gs-campaign-creation.md)<br/><br/>[Skapa och schemalägg kampanjen](../create-orchestrated-campaign.md)<br/><br/>[Orchestrate-aktiviteter](../orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](../start-monitor-campaigns.md)<br/><br/>[Rapportera](../reporting-campaigns.md) | [Arbeta med regelbyggaren](../orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](../build-query.md)<br/><br/>[Redigera uttryck](../edit-expressions.md)<br/><br/>[Återmarknadsföring](../retarget.md) | [Kom igång med aktiviteter](about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](and-join.md) - [Bygg målgrupp](build-audience.md) - [Ändra dimension](change-dimension.md) - [Kanalaktiviteter](channels.md) - [Kombinera](combine.md) - [Deduplicering](deduplication.md) - [Enrichment](enrichment.md) - [Fork](fork.md)  - [Avstämning](reconciliation.md) - [Spara målgrupp](save-audience.md) - [Dela](split.md) - <b>[Vänta](wait.md)</b> |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

</br>

Innehållet på den här sidan är inte slutgiltigt och kan komma att ändras.

>[!ENDSHADEBOX]

Aktiviteten **[!UICONTROL Wait]** är en **[!UICONTROL Flow control]**-komponent som används för att skapa en fördröjning mellan två aktiviteter i en orchestrerad kampanj. Detta bidrar till att säkerställa att era uppföljningsaktiviteter är bättre tajmade och mer relevanta för användarengagemanget.

Du kan till exempel vänta några dagar efter en e-postleverans för att spåra öppningar och klickningar innan du skickar ett uppföljningsmeddelande.

## Konfiguration{#wait-configuration}

Så här konfigurerar du aktiviteten **[!UICONTROL Wait]**:

1. Lägg till en **[!UICONTROL Wait]**-aktivitet i din Orchestrated-kampanj.

1. Välj den vänttyp som bäst passar dina behov:

   * **[!UICONTROL Duration]**: Ange en fördröjning i sekunder, minuter, timmar eller dagar innan du fortsätter till nästa aktivitet.

   * **[!UICONTROL Fixed time]**: Ange ett specifikt datum och en speciell tid efter vilket nästa aktivitet startar.

   ![](../assets/wait_activity.png)

## Exempel{#wait-example}

I följande exempel visas aktiviteten **[!UICONTROL Wait]** i ett typiskt användningsfall.  Ett e-postmeddelande med en kampanjkod skickas till profiler som firar sina födelsedagar. Efter 29 dagar skickas ett SMS till samma grupp som en påminnelse om att deras födelsedagskod snart går ut.

![](../assets/wait-example.png)
