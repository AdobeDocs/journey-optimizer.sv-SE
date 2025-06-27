---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurationssteg
description: Lär dig konfigurera samordnade kampanjer med Adobe Journey Optimizer.
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 8c785431-9a00-46b8-ba54-54a10e288141
source-git-commit: 4cc571b306058dc58454e488ba53bb69117a8b27
workflow-type: tm+mt
source-wordcount: '1088'
ht-degree: 0%

---

# Konfigurationssteg {#configuration-steps}

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/><b>[Konfigurationssteg](configuration-steps.md)</b><br/><br/>[Få åtkomst till och hantera samordnade kampanjer](access-manage-orchestrated-campaigns.md) | [Viktiga steg för att skapa samordnade kampanjer](gs-campaign-creation.md)<br/><br/>[Skapa och schemalägg kampanjen](create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/>[Skicka meddelanden med samordnade kampanjer](send-messages.md)<br/><br/>[Starta och övervaka kampanjen](start-monitor-campaigns.md)<br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med regelbyggaren](orchestrated-rule-builder.md)<br/><br/>[Skapa din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[Och-join](activities/and-join.md) - [Skapa målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kombinera](activities/combine.md) - [Ta bort dubbletter](activities/deduplication.md) - [Förbättra](activities/enrichment.md) - [Förena](activities/fork.md) - [Förena&lbrace;1 ](activities/reconciliation.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

</br>

>[!BEGINSHADEBOX]

Dokumentation pågår

>[!ENDSHADEBOX]

I den här guiden får du hjälp med att skapa ett relationsschema, konfigurera en datauppsättning för orkestrerade kampanjer, importera data via en S3-källa och fråga om inkapslade data i AP-plattformen.

I det här exemplet innehåller konfigurationen integrering av två nyckelentiteter, **Loyalty Transactions** och **Loyalty Rewards**, och länkning dem till befintliga kärnentiteter **Recipients** och **Brands**.

1. [Överför DDL-fil](#upload-ddl)

   Definiera relationsdatamodellen för samordnade kampanjer, inklusive entiteterna **Loyalty Transactions** och **Loyalty Rewards** tillsammans med nödvändiga nycklar och versionsattribut.

1. [Välj entiteter](#entities)

   Upprätta meningsfulla relationer mellan tabeller i schemat för att skapa en sammanhängande och sammankopplad datamodell.

1. [Länka schema](#link-schema)

   Länka entiteten **Loyalty Transactions** till **Mottagare** och **Loyalty Rewards** till **Varumärken** för att skapa en ansluten datamodell som stöder personaliserade kundresor.

1. [Ingrediera data](#ingest)

   Hämta in data till Adobe Experience Platform från källor som stöds, som SFTP, molnlagring eller databaser.

## Överför DDL-fil {#upload-ddl}

I det här avsnittet finns stegvisa anvisningar om hur du skapar ett relationsschema i Adobe Experience Platform genom att överföra en DDL-fil (Data Definition Language). Med hjälp av en DDL-fil kan du definiera datamodellens struktur i förväg, inklusive tabeller, attribut, nycklar och relationer.

1. Logga in på AP-plattformen.

1. Navigera till **Datahantering** > **Schema**.

1. Klicka på **Skapa schema**.

1. Du uppmanas att välja mellan två schematyper:

   * **Standard**
   * **Relation**, används specifikt för orkestrerade kampanjer

   ![](assets/admin_schema_1.png)

1. Välj **Överför DDL-fil** om du vill definiera ett entitetsrelationsdiagram och skapa scheman.

   Tabellstrukturen måste innehålla:
   * Minst en primärnyckel
   * En versionsidentifierare, till exempel ett `lastmodified`-fält av typen `datetime` eller `number`.

1. Dra och släpp din DDL-fil och klicka på **[!UICONTROL Next]**.

1. Skriv in din/ditt **[!UICONTROL Schema name]**.

1. Konfigurera varje schema och dess kolumner och se till att en primärnyckel anges.

   Ett attribut, till exempel `lastmodified`, måste anges som en versionsbeskrivare. Det här attributet, som vanligtvis är av typen `datetime`, `long` eller `int`, är nödvändigt för att matningsprocesser ska kunna säkerställa att datauppsättningen uppdateras med den senaste dataversionen.

   ![](assets/admin_schema_2.png)

1. Klicka på **[!UICONTROL Done]** när du är klar.

Nu kan du verifiera tabell- och fältdefinitionerna på arbetsytan. [Läs mer i avsnittet nedan](#entities)

## Välj enheter {#entities}

Följ stegen nedan för att definiera logiska anslutningar mellan tabeller i ditt schema.

1. Få åtkomst till arbetsytans vy av din datamodell och välj de två tabeller som du vill länka

1. Klicka på knappen ![](assets/do-not-localize/Smock_AddCircle_18_N.svg) bredvid Source Join och dra sedan pilen mot målhörnet för att upprätta anslutningen.

   ![](assets/admin_schema_5.png)

1. Fyll i det angivna formuläret för att definiera länken och klicka på **Använd** när du har konfigurerat den.

   ![](assets/admin_schema_3.png)

   **Kardinalitet**:

   * **1-N**: En förekomst av källtabellen kan ha flera motsvarande förekomster av måltabellen, men en förekomst av måltabellen kan ha högst en motsvarande förekomst av källtabellen.

   * **N-1**: en förekomst av måltabellen kan ha flera motsvarande förekomster av källtabellen, men en förekomst av källtabellen kan ha högst en motsvarande förekomst av måltabellen.

   * **1-1**: En förekomst av källtabellen kan ha högst en motsvarande förekomst av måltabellen.

1. Alla länkar som definieras i datamodellen representeras som pilar i arbetsytevyn. Klicka på en pil mellan två tabeller för att visa detaljer, göra ändringar eller ta bort länken efter behov.

   ![](assets/admin_schema_6.png)

1. Använd verktygsfältet för att anpassa och justera arbetsytan.

   ![](assets/toolbar.png)

   * **Zooma in**: Förstora arbetsytan så att du tydligare kan se information om datamodellen.

   * **Zooma ut**: Minska arbetsytans storlek för en bredare vy av datamodellen.

   * **Anpassa vy**: Justera zoomningen så att den passar alla scheman i det synliga området.

   * **Filter**: Välj vilket schema som ska visas på arbetsytan.

   * **Tvinga automatisk layout**: Ordna scheman automatiskt för bättre ordning.

   * **Visningsschema**: Växla en minimumöverlappning för att enklare kunna navigera i stora eller komplexa schemalayouter.

1. Klicka på **Spara** när du är klar. Den här åtgärden skapar scheman och associerade datauppsättningar och aktiverar datauppsättningen för användning i Orchestrated Campaigns.

1. Klicka på **[!UICONTROL Open Jobs]** för att övervaka förloppet för skapandet. Den här processen kan ta några minuter, beroende på hur många tabeller som har definierats i DDL-filen.

   ![](assets/admin_schema_4.png)

## Länka schema {#link-schema}

Upprätta en relation mellan schemat **lojalitetstransaktioner** och schemat **Mottagare** för att associera varje transaktion med rätt kundpost.

1. Navigera till **[!UICONTROL Schemas]** och öppna dina tidigare skapade **lojalitetstransaktioner**.

1. Klicka på **[!UICONTROL Add Relationship]** från kunden **[!UICONTROL Field properties]**.

   ![](assets/schema_1.png)

1. Välj **[!UICONTROL Many-to-One]** som relation **[!UICONTROL Type]**.

1. Länka till det befintliga **mottagarschemat**.

   ![](assets/schema_2.png)

1. Ange **[!UICONTROL Relationship name from current schema]** och **[!UICONTROL Relationship name from reference schema]**.

1. Klicka på **[!UICONTROL Apply]** om du vill spara ändringarna.

Fortsätt genom att skapa en relation mellan schemat **loyalty rewards** och schemat **Brands** för att associera varje belöningspost med rätt varumärke.

![](assets/schema_3.png)

## Ingrediera data {#ingest}

Med Adobe Experience Platform kan data hämtas från externa källor samtidigt som du kan strukturera, etikettera och förbättra inkommande data med hjälp av Experience Platform tjänster. Du kan importera data från en mängd olika källor, till exempel Adobe-program, molnbaserade lager, databaser och många andra.

1. Öppna menyn **[!UICONTROL Sources]** på menyn **[!UICONTROL Connections]**.

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

1. Välj **[!UICONTROL Sources]** på menyn **[!UICONTROL Connections]** och gå till fliken **[!UICONTROL Data Flows]** för att spåra flödeskörning, granska inkapslade poster och felsöka eventuella fel.

   ![](assets/S3_config_5.png)

<!--manual
## Create a relational schema manual


1. Log in to the AP Platform.
1. Navigate to the **Schema Management** section.
1. Click on **Create Schema**.

1. You will be prompted to select between two schema types:
    * **Standard**
    * **Relational** (used specifically for AGO campaigns)

1. Click on **Create Manual**.
1. Provide a **Schema Name** (e.g., `test_demo_ck001`).
1. Choose **Schema Type**:
    - **Record Type** (required for AGO campaigns)
    - **Time Series** (not applicable here)
1. Click **Finish** to proceed to the schema design canvas.

## Select entities and fields to import

1. In the canvas, add attributes (fields) to your schema.
1. Add a **Primary Key** (mandatory).
1. Add a **Version Descriptor** attribute (for CDC support):
    - This must be of type **DateTime** or **Numeric** (Integer, Long, Short, Byte).
    - Common example: `last_modified`

> **Why?** The **Primary Key** uniquely identifies each record, and the **Version Descriptor** tracks changes, supporting CDC (Change Data Capture) and data mirroring.

1. Mark the appropriate fields as **Primary Key** and **Version Descriptor**.
1. Click **Save**.

---




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