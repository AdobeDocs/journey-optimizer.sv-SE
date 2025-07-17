---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurationssteg
description: Lär dig hur du skapar relationsscheman direkt via användargränssnittet.
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 8c785431-9a00-46b8-ba54-54a10e288141
source-git-commit: aefc95b755074dfa043bad7dfd4acbd8dfb8e939
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 0%

---

# Manuellt schema {#manual-schema}

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/>Skapa och hantera relationsscheman och datauppsättningar:</br><ul><li>[Manuellt schema](manual-schema.md)</li><li>[Filöverföringsschema](file-upload-schema.md)</li><li>[Ingest data](ingest-data.md)</li></ul><br/><br/>[Få åtkomst till och hantera samordnade kampanjer](access-manage-orchestrated-campaigns.md)<br/><br/>[Viktiga steg för att skapa en strukturerad kampanj](gs-campaign-creation.md) | [Skapa och schemalägg kampanjen](create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](start-monitor-campaigns.md)<br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med regelbyggaren](orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md)<br/><br/>[Återmarknadsföring](retarget.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](activities/and-join.md) - [Bygg målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kanalaktiviteter](activities/channels.md) - [Kombinera](activities/combine.md) - [Deduplicering](activities/deduplication.md) - [Enrichment](activities/enrichment.md) - [Fork](activities/fork.md)  - [Avstämning](activities/reconciliation.md) - [Spara målgrupp](activities/save-audience.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

</br>

>[!BEGINSHADEBOX]

Innehållet på den här sidan är inte slutgiltigt och kan komma att ändras.

>[!ENDSHADEBOX]

Relationsscheman kan skapas direkt via användargränssnittet, vilket möjliggör detaljerad konfiguration av attribut, primärnycklar, versionsfält och relationer.

I följande exempel definieras schemat för lojalitetsmedlemskap manuellt för att illustrera den struktur som krävs för samordnade kampanjer.

1. Logga in på Adobe Experience Platform.

1. Navigera till **Datahantering** > **Schema**.

1. Klicka på **Skapa schema**.

1. Du uppmanas att välja mellan två schematyper:

   * **Standard**
   * **Relation**, används specifikt för orkestrerade kampanjer

   ![](assets/admin_schema_1.png)

1. Ange ett **schemanamn** (t.ex. `test_demo_ck001`).
1. Välj **schematyp**:
   **Posttyp** (krävs för AGO-kampanjer)
   **Tidsserie** (gäller inte här)
1. Klicka på **Slutför** för att fortsätta till arbetsytan för schemadesign.

## Välj enheter och fält som ska importeras

1. Lägg till attribut (fält) i schemat på arbetsytan.
1. Lägg till en **primärnyckel** (obligatoriskt).
1. Lägg till ett **Version Descriptor**-attribut (för CDC-stöd):
Det här måste vara av typen **DateTime** eller **Numeric** (Integer, Long, Short, Byte).
Gemensamt exempel: `last_modified`

> **Varför?** **Primärnyckeln** identifierar varje post unikt och **Versionsbeskrivningen** spårar ändringar som stöds av CDC (Change Data Capture) och dataregling.

1. Markera fälten som **Primär nyckel** och **Versionsbeskrivning**.
1. Klicka på **Spara**.


<!--

## 5. Creating a Dataset

1. Navigate to **Datasets**.
1. Click on **Create Dataset**.
1. Select the schema you just created.
1. Assign a **Dataset Name** (same as schema is fine).
1. Optionally, add tags (e.g., `AGO_campaigns`).
6. Ensure the checkbox **"Relational Schema"** is checked.
7. Click **Finish**.

> **Note:** Only one dataset can be created per relational schema.


## 6. Enabling the Dataset

1. Click **Enable** for the dataset.
1. Wait a few moments for the status to show **Enabled**.

> **Why?** Without enabling, the dataset cannot be used in orchestrated campaigns or ingest data.

## 7. Creating a Data Source (S3)

1. Navigate to **Sources**.
1. Click **Create Source**.
1. Choose the source type (e.g., **S3 Bucket**).
1. Provide connection details:
    - Bucket Path (optionally include subfolder path)
1. Save the source.

## 8. Preparing and Uploading Data

1. Prepare your CSV file with:
    - Column headers matching your schema attributes
    - `last_modified` column
    - `change_type` column (`U`/`DU` for upsert, `D` for delete)

> **Important:** `change_type` is required but does not need to be defined in the schema.

1. Save the file as `.csv`.

1. Upload the file to the specified folder in your S3 bucket.


## 9. Ingesting Data from S3

1. Go to **Sources** and find your S3 source.
1. Click **Add Data**.
1. Select the uploaded file.
1. Specify the file format as **CSV** and any compression type if applicable.
1. Review the data preview (ensure `change_type`, `last_modified`, and primary key are visible).
1. Click **Next**.

### Enable Change Data Capture (CDC)

- Check **Enable Change Data Capture**.
- Select the dataset enabled for AGO campaigns.

### Field Mapping

- Fields are auto-mapped (note that `change_type` is not mapped and that's expected).
- Click **Next**.

### Scheduling

- Schedule ingestion frequency (minute, hour, day, week).
- Set start time (immediate or future).
- Click **Finish** to create the data flow.

## 10. Monitoring Data Flow

1. Navigate back to **Sources > Data Flows**.
1. Wait 4–5 minutes for the first run (initial overhead).
1. Monitor:
    - Status (Started, Completed)
    - Number of records ingested
    - Errors (if any)

> **Tip:** Ingested data first lands in the **Data Lake**.

## 11. Data Replication to Data Store

The **Data Store** is updated:

- Every **15 minutes**, or

- If **Data Lake size exceeds 5MB**

This is a background replication process.


## 12. Querying the Dataset

1. Navigate to **Query Services**.
1. Click **Create Query**.
1. Example query:

   ```sql
   SELECT * FROM test_demo_ck001;
   ```

1. Run the query.

> **Note:** If ingestion is incomplete, query will return an error. Check data flow status.

-->