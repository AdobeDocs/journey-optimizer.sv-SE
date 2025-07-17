---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurationssteg
description: Lär dig hur du skapar ett relationsschema i Adobe Experience Platform genom att överföra en DDL
badge: label="Alpha"
hide: true
hidefromtoc: true
source-git-commit: 1aa4f3e24a4cb7594232c0b25da8c9fd2e62c1de
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 0%

---

# Filöverföring {#file-upload-schema}

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/>Skapa och hantera relationsscheman och datauppsättningar:</br> <ul><li>[Manuellt schema](manual-schema.md)</li><li>[Filöverföringsschema](file-upload-schema.md)</li><li>[Ingest data](ingest-data.md)</li></ul><br/><br/>[Få åtkomst till och hantera samordnade kampanjer](access-manage-orchestrated-campaigns.md)<br/><br/>[Viktiga steg för att skapa en strukturerad kampanj](gs-campaign-creation.md) | [Skapa och schemalägg kampanjen](create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](start-monitor-campaigns.md)<br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med regelbyggaren](orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md)<br/><br/>[Återmarknadsföring](retarget.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](activities/and-join.md) - [Bygg målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kanalaktiviteter](activities/channels.md) - [Kombinera](activities/combine.md) - [Deduplicering](activities/deduplication.md) - [Enrichment](activities/enrichment.md) - [Fork](activities/fork.md)  - [Avstämning](activities/reconciliation.md) - [Spara målgrupp](activities/save-audience.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

</br>

>[!BEGINSHADEBOX]

Innehållet på den här sidan är inte slutgiltigt och kan komma att ändras.

>[!ENDSHADEBOX]

Definiera relationsdatamodellen som krävs för samordnade kampanjer genom att skapa scheman som **Förmånsmedlemskap**, **Förmånstransaktioner** och **Förmånsbelöningar**. Varje schema måste innehålla en primärnyckel, ett versionsattribut och lämpliga relationer till referensentiteter som **Mottagare** eller **Varumärken**.

Scheman kan skapas manuellt via gränssnittet eller importeras i grupp med hjälp av en DDL-fil.

I det här avsnittet finns stegvisa anvisningar om hur du skapar ett relationsschema i Adobe Experience Platform genom att överföra en DDL-fil (Data Definition Language). Med hjälp av en DDL-fil kan du definiera datamodellens struktur i förväg, inklusive tabeller, attribut, nycklar och relationer.

## DDL-filöverföring {#ddl-upload}

1. Logga in på Adobe Experience Platform.

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

## Definiera relationer {#relationships}

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