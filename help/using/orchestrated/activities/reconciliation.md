---
solution: Journey Optimizer
product: journey optimizer
title: Använd avstämningsaktiviteten
description: Lär dig använda avstämningsaktiviteten i en orkestrerad kampanj
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 0d5cfffe-bc6c-40bc-b3e1-5b44368ac76f
source-git-commit: d59643f18a335fe1e094156a1cfee65b717b9fce
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 0%

---

# Avstämning {#reconciliation}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_reconciliation"
>title="Avstämningsaktivitet"
>abstract="Aktiviteten **Avstämning** är en **målaktivitet** som gör att du kan definiera länken mellan Adobe Journey Optimizer och data i en arbetstabell."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_reconciliation_field"
>title="Avstämningsmarkeringsfält"
>abstract="Avstämningsmarkeringsfält"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_reconciliation_condition"
>title="Avstämning skapa villkor"
>abstract="Avstämning skapa villkor"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_reconciliation_complement"
>title="Avstämning genererar komplementtal"
>abstract="Avstämning genererar komplementtal"

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](../gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](../configuration-steps.md)<br/><br/>[Viktiga steg för att skapa samordnade kampanjer](../gs-campaign-creation.md) | [Skapa en orkestrerad kampanj](../create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](../orchestrate-activities.md)<br/><br/>[Skicka meddelanden med orkestrerade kampanjer](../send-messages.md)<br/><br/>[Starta och övervaka kampanjen](../start-monitor-campaigns.md)<br/><br/>[Rapportera](../reporting-campaigns.md) | [Arbeta med Query Modeler](../orchestrated-rule-builder.md)<br/><br/>[Skapa din första fråga](../build-query.md)<br/><br/>[Redigera uttryck](../edit-expressions.md) | [Kom igång med aktiviteter](about-activities.md)<br/><br/>Aktiviteter:<br/>[Och-join](and-join.md) - [Skapa målgrupp](build-audience.md) - [Ändra dimension](change-dimension.md) - [Kombinera](combine.md) - [Ta bort dubbletter](deduplication.md) - [Förbättra](enrichment.md) - [Förena](fork.md) - [Förena&lbrace;1 ](reconciliation.md) - [Dela](split.md) - [Vänta](wait.md) |

{style="table-layout:fixed"}

+++

<br/>

Aktiviteten **Avstämning** är en **målaktivitet** som gör att du kan definiera länken mellan data i Adobe Journey Optimizer och data i en arbetstabell, till exempel data som lästs in från en extern fil.

Med Enrichment-aktiviteten kan ni lägga till ytterligare data till den samordnade kampanjen, till exempel genom att kombinera data från flera källor eller länka till en tillfällig resurs. Avstämningsaktiviteten används däremot för att matcha oidentifierade eller externa data med befintliga resurser i databasen.

Avstämningen kräver att de relaterade posterna redan finns i systemet. Om du till exempel importerar en inköpsfillista med produkter, tidsstämplar och kundinformation måste både produkterna och kunderna finnas i databasen för att länken ska kunna skapas.

## Konfigurera avstämningsaktiviteten {#reconciliation-configuration}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_reconciliation_targeting"
>title="Måldimension"
>abstract="Välj den nya måldimensionen. Med en dimension kan du definiera målpopulationen: mottagare, appprenumeranter, operatorer, prenumeranter osv. Som standard är den aktuella måldimensionen markerad."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_reconciliation_rules"
>title="Avstämningsregler"
>abstract="Välj avstämningsregler som ska användas för dedupliceringen. Om du vill använda attribut markerar du alternativet **Enkla attribut** och väljer käll- och målfälten. Om du vill skapa ett eget avstämningsvillkor med frågemodelleraren väljer du alternativet **Avancerade avstämningsvillkor** ."
>additional-url="https://experienceleague.adobe.com/sv/docs/campaign-web/v8/query-database/query-modeler-overview" text="Arbeta med frågemodelleraren"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_reconciliation_targeting_selection"
>title="Välj måldimension"
>abstract="Välj måldimension för inkommande data som ska förenas med."
>additional-url="https://experienceleague.adobe.com/docs/campaign-web/v8/audiences/gs-audiences-recipients.html?lang=sv-SE#targeting-dimensions" text="Måldimensioner"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_keep_unreconciled_data"
>title="Behåll ej avstämda data"
>abstract="Som standard behålls ej avstämda data i den utgående övergången och är tillgängliga i arbetstabellen för framtida bruk. Om du vill ta bort ej avstämda data inaktiverar du alternativet **Behåll ej avstämda data**."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_reconciliation_attribute"
>title="Avstämningsattribut"
>abstract="Markera attributet som ska användas för att avstämma data och klicka på Bekräfta."

Så här konfigurerar du aktiviteten **Avstämning**:

1. Lägg till en **avstämningsaktivitet** i din samordnade kampanj.

1. Välj den nya måldimensionen. Med en dimension kan du definiera målpopulationen: mottagare, appprenumeranter, operatorer, prenumeranter osv.

1. Välj de fält som ska användas för avstämningen. Du kan använda ett eller flera avstämningskriterier.

   1. Om du vill använda attribut för att stämma av data markerar du alternativet **Enkla attribut**. I fältet **Source** visas de fält som är tillgängliga i indataövergången och som ska avstämas. Fältet **Mål** motsvarar fälten i den valda måldimensionen. Data avstäms när källan och målet är lika. Markera till exempel fälten **E-post** för att ta bort dubbletter av profiler baserat på deras e-postadress.

      Om du vill lägga till ytterligare avstämningsvillkor klickar du på knappen **Lägg till regel** . Om flera kopplingsvillkor anges måste ALLA verifieras så att data kan länkas ihop.

      ![](../assets/workflow-reconciliation-criteria.png)

   1. Om du vill använda andra attribut för att stämma av data väljer du alternativet **Avancerade avstämningsvillkor** . Du kan sedan skapa ett eget avstämningsvillkor med frågemodelleraren.

1. Du kan filtrera data för avstämning med knappen **Skapa filter** . Detta gör att du kan skapa ett anpassat villkor med hjälp av frågemodelleraren.

Som standard lagras ej avstämda data i den utgående övergången och är tillgängliga i arbetsboken för framtida bruk. Om du vill ta bort ej avstämda data inaktiverar du alternativet **Behåll ej avstämda data**.
