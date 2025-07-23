---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurationssteg
description: Lär dig hur du hämtar data till Adobe Experience Platform från källor som stöds, som SFTP, molnlagring eller databaser.
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 7f1e7985-b68e-43d6-9c8f-fea2469f8af9
source-git-commit: 6447f5d1a060037c0ceaa374db20966097585f9c
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 1%

---

# Ingrediera data {#ingest-data}

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/>Skapa och hantera relationsscheman och datauppsättningar</br> <ul><li>[Kom igång med scheman och datauppsättningar](gs-schemas.md)</li><li>[Manuellt schema](manual-schema.md)</li><li>[Filöverföringsschema](file-upload-schema.md)</li><li>[Ingest data](ingest-data.md)</li></ul>[Få åtkomst till och hantera samordnade kampanjer](access-manage-orchestrated-campaigns.md)<br/><br/>[Viktiga steg för att skapa en strukturerad kampanj](gs-campaign-creation.md) | [Skapa och schemalägg kampanjen](create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](start-monitor-campaigns.md)<br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med regelbyggaren](orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md)<br/><br/>[Återmarknadsföring](retarget.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](activities/and-join.md) - [Bygg målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kanalaktiviteter](activities/channels.md) - [Kombinera](activities/combine.md) - [Deduplicering](activities/deduplication.md) - [Enrichment](activities/enrichment.md) - [Fork](activities/fork.md)  - [Avstämning](activities/reconciliation.md) - [Spara målgrupp](activities/save-audience.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

</br>

>[!BEGINSHADEBOX]

</br>

Innehållet på den här sidan är inte slutgiltigt och kan komma att ändras.

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>Om du vill ändra datakällan för en datauppsättning måste du först ta bort det befintliga dataflödet innan du skapar ett nytt som refererar till samma datauppsättning och den nya källan.
>
>Adobe Experience Platform tillämpar en strikt personlig relation mellan dataflöden och datauppsättningar. På så sätt kan du upprätthålla synkroniseringen mellan källan och datauppsättningen för korrekt inkrementellt intag.

Med Adobe Experience Platform kan data hämtas från externa källor samtidigt som du kan strukturera, etikettera och förbättra inkommande data med hjälp av Experience Platform tjänster. Du kan importera data från en mängd olika källor, till exempel Adobe-program, molnbaserade lager, databaser och många andra.

## Källor som stöds för samordnade kampanjer {#supported}

Följande källor stöds för användning med Orchestrated-kampanjer:

<table>
  <thead>
    <tr>
      <th>Typ</th>
      <th>Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="3">molnlagring</td>
      <td><a href="https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/s3">Amazon S3</a></td>
    </tr>
    <tr>
      <td><a href="https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/google-cloud-storage">Google Cloud-lagring</a></td>
    </tr>
    <tr>
      <td><a href="https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/sftp">SFTP</a></td>
    </tr>
      <td rowspan="4">Datalager i molnet</td>
      <td><a href="https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/databases/snowflake">Snowflake</a></td>
    </tr>
    <tr>
      <td><a href="https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/databases/bigquery">Google BigQuery</a></td>
    </tr>
    <tr>
      <td><a href="https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/data-landing-zone">Datallandningszon<a></td>
    </tr>
    <tr>
      <td><a href="https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/databases/databricks">Azure-databaser</a></td>
    </tr>
    <tr>
      <td rowspan="3">Filbaserade överföringar</td>
      <td><a href="https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/local-system/local-file-upload">Lokal filöverföring<a></td>
    </tr>

</tbody>
</table>

## Konfigurera ett dataflöde

I det här exemplet visas hur du konfigurerar ett dataflöde som importerar strukturerade data till Adobe Experience Platform. Det konfigurerade dataflödet stöder automatiskt, schemalagt inmatning och möjliggör uppdateringar i realtid.

1. Öppna menyn **[!UICONTROL Connections]** på menyn **[!UICONTROL Sources]**.

1. Välj källa beroende på vilka [källor som stöds för samordnade kampanjer](#supported).

   ![](assets/admin_sources_1.png)

1. Anslut ditt konto för molnlagring eller Google Cloud-lagring om du väljer molnbaserade källor.

   ![](assets/admin_sources_2.png)

1. Välj de data du vill importera till Adobe Experience Platform.

   ![](assets/S3_config_1.png)

1. På sidan **[!UICONTROL Dataset details]** markerar du **[!UICONTROL Enable Change data capture]** om du bara vill visa datauppsättningar som är mappade till relationsscheman och innehåller både en primärnyckel och en versionsbeskrivning.

   >[!IMPORTANT]
   >
   > För **filbaserade källor endast** måste varje rad i datafilen innehålla en `_change_request_type`-kolumn med värdena `U` (upsert) eller `D` (delete). Utan den här kolumnen kan systemet inte identifiera data som stöd för ändringsspårning, och växlingsknappen för orchestrated Campaign visas inte, vilket förhindrar att datauppsättningen väljs för målinriktning.

   ![](assets/S3_config_6.png)

1. Markera den datauppsättning som du skapade tidigare och klicka på **[!UICONTROL Next]**.

   ![](assets/S3_config_3.png)

1. Om du bara använder en filbaserad källa överför du dina lokala filer från fönstret **[!UICONTROL Select data]** och förhandsgranskar deras struktur och innehåll.

   Observera att den största storlek som stöds är 100 MB.

1. I fönstret **[!UICONTROL Mapping]** kontrollerar du att varje källfilsattribut är korrekt mappat med motsvarande fält i målschemat.

   Klicka på **[!UICONTROL Next]** när du är klar.

   ![](assets/S3_config_4.png)

1. Konfigurera dataflödet **[!UICONTROL Schedule]** baserat på önskad frekvens.

1. Klicka på **[!UICONTROL Finish]** för att skapa dataflödet. Den körs automatiskt enligt angivet schema.

1. Välj **[!UICONTROL Connections]** på menyn **[!UICONTROL Sources]** och gå till fliken **[!UICONTROL Data Flows]** för att spåra flödeskörning, granska inkapslade poster och felsöka eventuella fel.

   ![](assets/S3_config_5.png)

