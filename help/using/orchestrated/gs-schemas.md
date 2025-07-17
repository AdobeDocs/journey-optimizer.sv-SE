---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurationssteg
description: Lär dig hur du skapar ett relationsschema i Adobe Experience Platform genom att överföra en DDL
badge: label="Alpha"
hide: true
hidefromtoc: true
source-git-commit: 1a9ea09fcbf304b1649a5ae88da34bd209e9ac8b
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# Kom igång med scheman och datauppsättningar{#gs-schemas}

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/>Skapa och hantera relationsscheman och datauppsättningar:</br> <ul><li>[Kom igång med scheman och datauppsättningar](gs-schemas.md)</li><li>[Manuellt schema](manual-schema.md)</li><li>[Filöverföringsschema](file-upload-schema.md)</li><li>[Ingest data](ingest-data.md)</li></ul>[Få åtkomst till och hantera samordnade kampanjer](access-manage-orchestrated-campaigns.md)<br/><br/>[Viktiga steg för att skapa en strukturerad kampanj](gs-campaign-creation.md) | [Skapa och schemalägg kampanjen](create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](start-monitor-campaigns.md)<br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med regelbyggaren](orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md)<br/><br/>[Återmarknadsföring](retarget.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](activities/and-join.md) - [Bygg målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kanalaktiviteter](activities/channels.md) - [Kombinera](activities/combine.md) - [Deduplicering](activities/deduplication.md) - [Enrichment](activities/enrichment.md) - [Fork](activities/fork.md)  - [Avstämning](activities/reconciliation.md) - [Spara målgrupp](activities/save-audience.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

</br>

>[!BEGINSHADEBOX]

</br>

Innehållet

Innehållet på den här sidan är inte slutgiltigt och kan komma att ändras.

>[!ENDSHADEBOX]

I den här guiden får du hjälp med att skapa ett relationsschema, konfigurera en datauppsättning för orkestrerade kampanjer, importera data via en S3-källa och fråga om inkapslade data i AP-plattformen.

I det här exemplet innehåller konfigurationen integrering av två nyckelentiteter, **Loyalty Transactions** och **Loyalty Rewards**, och länkning dem till befintliga kärnentiteter **Recipients** och **Brands**.

![](assets/do-not-localize/schema_admin.png)

1. [Skapa relationsschema och associerad datauppsättning](#schema)

   Definiera relationsdatamodellen för samordnade kampanjer, inklusive entiteterna **Förmånsmedlemskap**, **Förmånstransaktioner** och **Förmånsbelöningar**, tillsammans med nödvändiga nycklar och versionsattribut.

1. [Länka schema](#link-schema)

   Länka entiteten **Loyalty Transactions** till **Mottagare** och **Loyalty Rewards** till **Varumärken** för att skapa en ansluten datamodell som stöder personaliserade kundresor.

1. [Ingrediera data](#ingest)

   Hämta in data till Adobe Experience Platform från källor som stöds, som SFTP, molnlagring eller databaser.


<!--### Setting Up Change data capture ingestion {#cdc-ingestion}

If you need to change the data source, you must delete the existing dataflow and create a new one pointing to the same dataset with the new source.

When using Change Data Capture (CDC), it is essential that the source and dataset remain in sync to ensure accurate incremental updates. Follow the steps below:

1. **Schema Requirements**
   - Your schema must include:
     - A **primary key** (e.g., `transaction_id`)
     - A **versioning field** (e.g., `lastmodified` or an incrementing `version_id`)
   - Enable the dataset for **Orchestrated Campaigns** if needed.

2. **CDC Dataflow Setup**
   - During dataflow creation, after choosing your source and files:
     - **Enable the CDC option**
     - Select your CDC-ready dataset
     - Confirm field mappings (especially version field)

3. **Keep Source and Target in Sync**
   - The source system must consistently update the version field so the platform can detect changes accurately.

Once set up, the platform will automatically ingest **only changed or new records** each time the flow runs.
-->
