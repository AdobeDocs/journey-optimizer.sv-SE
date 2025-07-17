---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurationssteg
description: Lär dig hur du hämtar data till Adobe Experience Platform från källor som stöds, som SFTP, molnlagring eller databaser.
badge: label="Alpha"
hide: true
hidefromtoc: true
source-git-commit: 25120dd71159d0233783ac4c189f528ff2c93ae3
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# Ingrediera data {#ingest-data}

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/>Skapa och hantera relationsscheman och datauppsättningar</br> <ul><li>[Manuellt schema](manual-schema.md)</li><li>[Filöverföringsschema](file-upload-schema.md)</li><li>[Ingest data](ingest-data.md)</li></ul>[Få åtkomst till och hantera samordnade kampanjer](access-manage-orchestrated-campaigns.md)<br/><br/>[Viktiga steg för att skapa en strukturerad kampanj](gs-campaign-creation.md) | [Skapa och schemalägg kampanjen](create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](start-monitor-campaigns.md)<br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med regelbyggaren](orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md)<br/><br/>[Återmarknadsföring](retarget.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](activities/and-join.md) - [Bygg målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kanalaktiviteter](activities/channels.md) - [Kombinera](activities/combine.md) - [Deduplicering](activities/deduplication.md) - [Enrichment](activities/enrichment.md) - [Fork](activities/fork.md)  - [Avstämning](activities/reconciliation.md) - [Spara målgrupp](activities/save-audience.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

</br>

>[!BEGINSHADEBOX]

Innehållet på den här sidan är inte slutgiltigt och kan komma att ändras.

>[!ENDSHADEBOX]

Med Adobe Experience Platform kan data hämtas från externa källor samtidigt som du kan strukturera, etikettera och förbättra inkommande data med hjälp av Experience Platform tjänster. Du kan importera data från en mängd olika källor, till exempel Adobe-program, molnbaserade lager, databaser och många andra.

## Med molnlagring {#ingest}

<!--
>[!IMPORTANT]
>
>Each dataset in Adobe Experience Platform supports only one active dataflow at a time. For detailed setup guidance on how to switch data sources, refer to this [section](#cdc-ingestion).
-->

Du kan konfigurera ett dataflöde för att importera data från en Amazon S3-källa till Adobe Experience Platform. När dataflödet har konfigurerats möjliggör det automatiserat, schemalagt inmatning av strukturerade data och stöder uppdateringar i realtid.

1. Öppna menyn **[!UICONTROL Connections]** på menyn **[!UICONTROL Sources]**.

1. Välj kategorin **[!UICONTROL Cloud storage]**, sedan Amazon S3 och klicka på **[!UICONTROL Add Data]**.

   ![](assets/admin_sources_1.png)

1. Anslut ditt S3-konto:

   * Med ett befintligt konto

   * Med ett nytt konto

   [Läs mer i Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3#connect)

   ![](assets/admin_sources_2.png)

1. Välj din mapp **[!UICONTROL Data format]**, **[!UICONTROL Delimiter]** och **[!UICONTROL Compression type]**.

1. Navigera genom den anslutna S3-källan tills du hittar de två mappar som har skapats tidigare, dvs. **lojalitetsbelöningar** och **lojalitetstransaktioner**.

1. Markera mappen som innehåller dina data.

   Om du väljer en mapp behandlas alla aktuella och framtida filer med samma struktur automatiskt. Om du väljer en enskild fil måste du dock överföra varje nytt datasteg manuellt.

   ![](assets/S3_config_2.png)

1. Välj din mapp **[!UICONTROL Data format]**, **[!UICONTROL Delimiter]** och **[!UICONTROL Compression type]**. Granska exempeldata och klicka sedan på **[!UICONTROL Next]**.

   ![](assets/S3_config_1.png)

1. Markera **[!UICONTROL Enable Change data capture]** om du vill välja bland datauppsättningar som är mappade till relationsscheman och som har både en primärnyckel och en versionsbeskrivare definierad.

1. Markera din [tidigare skapade datauppsättning](#entities) och klicka på **[!UICONTROL Next]**.

   ![](assets/S3_config_3.png)

1. I fönstret **[!UICONTROL Mapping]** kontrollerar du att varje källfilsattribut är korrekt mappat med motsvarande fält i målschemat.

   Klicka på **[!UICONTROL Next]** när du är klar.

   ![](assets/S3_config_4.png)

1. Konfigurera dataflödet **[!UICONTROL Schedule]** baserat på önskad frekvens.

1. Klicka på **[!UICONTROL Finish]** för att skapa dataflödet. Den körs automatiskt enligt angivet schema.

1. Välj **[!UICONTROL Connections]** på menyn **[!UICONTROL Sources]** och gå till fliken **[!UICONTROL Data Flows]** för att spåra flödeskörning, granska inkapslade poster och felsöka eventuella fel.

   ![](assets/S3_config_5.png)

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