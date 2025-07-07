---
solution: Journey Optimizer
product: journey optimizer
title: Använda aktiviteten Grupp
description: Lär dig hur du använder gaffelaktiviteten i en orkestrerad kampanj
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 52e8057b-dac1-45f5-9dd0-1b28a59adde9
source-git-commit: a19fe429d34a88c6159ab3b2b4dfa3768bcd24ad
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# Förgrening {#fork}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_fork"
>title="Gaffelaktivitet"
>abstract="Med aktiviteten **Förena** kan du skapa utgående övergångar och starta flera aktiviteter samtidigt."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_fork_transitions"
>title="Fork-aktivitetsövergångar"
>abstract="Som standard skapas två övergångar med en **Förgrening**-aktivitet. Klicka på knappen **Lägg till övergång** för att definiera ytterligare en utgående övergång och ange dess etikett."

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](../gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](../configuration-steps.md)<br/><br/>[Få åtkomst till och hantera samordnade kampanjer](../access-manage-orchestrated-campaigns.md) | [Viktiga steg för att skapa en orkestrerad kampanj](../gs-campaign-creation.md)<br/><br/>[Skapa och schemalägg kampanjen](../create-orchestrated-campaign.md)<br/><br/>[Orchestrate-aktiviteter](../orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](../start-monitor-campaigns.md)<br/><br/>[Rapportera](../reporting-campaigns.md) | [Arbeta med regelbyggaren](../orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](../build-query.md)<br/><br/>[Redigera uttryck](../edit-expressions.md)<br/><br/>[Återmarknadsföring](../retarget.md) | [Kom igång med aktiviteter](about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](and-join.md) - [Bygg målgrupp](build-audience.md) - [Ändra dimension](change-dimension.md) - [Kanalaktiviteter](channels.md) - [Kombinera](combine.md) - [Deduplicering](deduplication.md) - [Enrichment](enrichment.md) - <b>[Fork](fork.md)</b>  - [Avstämning](reconciliation.md) - [Spara målgrupp](save-audience.md) - [Dela](split.md) - [Vänta](wait.md) |

{style="table-layout:fixed"}

+++


<br/>

Aktiviteten **[!UICONTROL Fork]** är en **[!UICONTROL Flow control]**-komponent som gör att du kan skapa flera utgående övergångar, vilket gör att flera aktiviteter kan köras parallellt.

## Konfigurera gaffelaktiviteten{#fork-configuration}

Så här konfigurerar du aktiviteten **[!UICONTROL Fork]**:

![](../assets/workflow-fork.png)

1. Lägg till en **[!UICONTROL Fork]**-aktivitet i din samordnade kampanj.

1. Definiera en **[!UICONTROL Label]**.

1. Tilldela en etikett till varje utgående övergång. Som standard finns det två övergångar.

1. Klicka på ikonen ![](../assets/do-not-localize/Smock_Delete_18_N.svg) om du vill ta bort en övergång.

1. Om det behövs klickar du på **[!UICONTROL Add transition]** för att lägga till ytterligare en utgående övergång.
