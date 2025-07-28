---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurationssteg
description: Lär dig hur du skapar ett relationsschema i Adobe Experience Platform genom att överföra en DDL
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 88eb1438-0fe5-4a19-bfb6-2968a427e9e8
source-git-commit: 3be1b238962fa5d0e2f47b64f6fa5ab4337272a5
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 0%

---

# Skapa relationsscheman med en DDL-fil {#file-upload-schema}

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/>Skapa och hantera relationsscheman och datauppsättningar:</br> <ul><li>[Kom igång med scheman och datauppsättningar](gs-schemas.md)</li><li>[Manuellt schema](manual-schema.md)</li><li>[Filöverföringsschema](file-upload-schema.md)</li><li>[Ingest data](ingest-data.md)</li></ul>[Få åtkomst till och hantera samordnade kampanjer](access-manage-orchestrated-campaigns.md)<br/><br/>[Viktiga steg för att skapa en orkestrerad kampanj](gs-campaign-creation.md) | [Skapa och schemalägg kampanjen](create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](start-monitor-campaigns.md)<br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med regelbyggaren](orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md)<br/><br/>[Återmarknadsföring](retarget.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](activities/and-join.md) - [Bygg målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kanalaktiviteter](activities/channels.md) - [Kombinera](activities/combine.md) - [Deduplicering](activities/deduplication.md) - [Enrichment](activities/enrichment.md) - [Fork](activities/fork.md)  - [Avstämning](activities/reconciliation.md) - [Spara målgrupp](activities/save-audience.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

</br>

>[!BEGINSHADEBOX]

</br>

Innehållet på den här sidan är inte slutgiltigt och kan komma att ändras.

>[!ENDSHADEBOX]

Definiera relationsdatamodellen som krävs för Orchestrated-kampanjer genom att skapa scheman som **Loyalty Memberships**, **Loyalty Transactions** och **Loyalty Rewards**. Varje schema måste innehålla en primärnyckel, ett versionsattribut och lämpliga relationer till referensentiteter som **Mottagare** eller **Varumärken**.

Scheman kan skapas manuellt via gränssnittet eller importeras i grupp med hjälp av en DDL-fil.

I det här avsnittet finns stegvisa anvisningar om hur du skapar ett relationsschema i Adobe Experience Platform genom att överföra en DDL-fil (Data Definition Language). Med hjälp av en DDL-fil kan du definiera datamodellens struktur i förväg, inklusive tabeller, attribut, nycklar och relationer.

1. [Överför en DDL-fil](#ddl-upload) för att skapa relationsscheman och definiera deras struktur.

1. [Definiera relationer](#relationships) mellan tabeller i datamodellen.

1. [Länka scheman](#link-schema) för att koppla relationsdata till befintliga profilentiteter som mottagare eller varumärken.

1. [Infoga data](ingest-data.md) i datauppsättningen från källor som stöds.

## Överföra en DDL-fil{#ddl-upload}

Genom att överföra en DDL-fil kan du definiera datamodellens struktur i förväg, inklusive tabeller, attribut, nycklar och relationer.

Överföringar av Excel-baserade schemabilder stöds. Hämta [tillhandahållen mall](assets/template.zip) för att enkelt förbereda dina schemadefinitioner.

+++Följande funktioner stöds när du skapar relationsscheman i Adobe Experience Platform

* **ENUM**\
  ENUM-fält stöds i både DDL-baserade och manuella schemagenereringar, vilket gör att du kan definiera attribut med en fast uppsättning tillåtna värden.

* **Schemaetikett för datastyrning**\
  Etikettering stöds på schemafältnivå för att tillämpa datastyrningsprinciper som åtkomstkontroll och användningsbegränsningar. Mer information finns i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv).

* **Sammansatt nyckel**\
  Sammansatta primärnycklar stöds i relationsschemadefinitioner, vilket gör det möjligt att använda flera fält tillsammans för att unikt identifiera poster.

+++

1. Logga in på Adobe Experience Platform.

1. Navigera till menyn **Datahantering** > **Schema** .

1. Klicka på **Skapa schema**.

1. Välj **[!UICONTROL Relational]** som **schematyp**.

   ![](assets/admin_schema_1.png)

1. Välj **[!UICONTROL Upload DDL file]** om du vill definiera ett entitetsrelationsdiagram och skapa scheman.

   Tabellstrukturen måste innehålla:
   * Minst en primärnyckel
   * En versionsidentifierare, till exempel ett `lastmodified`-fält av typen `datetime` eller `number`.
   * För CDC-inmatning (Change Data Capture) är det en specialkolumn med namnet `_change_request_type` av typen `String` som anger typen av dataändring (t.ex. infoga, uppdatera, ta bort) och möjliggör inkrementell bearbetning


   >[!IMPORTANT]
   >
   > Alla scheman som används som mål måste innehålla minst ett identitetsfält av typen `String` med ett associerat **identitetsnamnområde**.\
   >Detta garanterar kompatibilitet med Adobe Journey Optimizer verktyg för målinriktning och identitetsupplösning.

1. Dra och släpp din DDL-fil och klicka på **[!UICONTROL Next]**.

   Observera att den största tillåtna storleken för en DDL-fil är 10 MB.

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

   Du kan även komma åt dina relationsjobb genom att öppna fönstret **[!UICONTROL Upload DDL file]** och välja **[!UICONTROL View all relational Jobs]**.

   ![](assets/admin_schema_4.png)

## Länka scheman {#link-schema}

>[!IMPORTANT]
>
> Det är bara relationer som uttryckligen definieras i DDL-filen som identifieras av systemet. Alla entitetsrelationer som finns utanför DDL-filen ignoreras och bearbetas inte.

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
