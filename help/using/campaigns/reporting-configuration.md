---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera Journey Optimizer-rapportering för experimenterande
description: Lär dig hur du ställer in rapportdatakälla
feature: Data Sources
topic: Administration
role: Admin
level: Intermediate
keywords: konfiguration, experiment, rapportering, optimering
exl-id: 327a0c45-0805-4f64-9bab-02d67276eff8
source-git-commit: dc48cc6d95e4af288727961fd9f7761dee4f2552
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Konfigurera rapportering för experiment {#reporting-configuration}

>[!CONTEXTUALHELP]
>id="ajo_admin_reporting_config"
>title="Ställ in datauppsättningar för rapportering"
>abstract="Med rapportkonfigurationen kan du hämta ytterligare mätvärden som ska användas på fliken Mål i kampanjrapporterna. Den måste utföras av en teknisk användare."

>[!CONTEXTUALHELP]
>id="ajo_admin_reporting_dataset"
>title="Välj en datauppsättning"
>abstract="Du kan bara välja en datamängd av händelsetyp, som måste innehålla minst en av de fältgrupper som stöds: Programinformation, handelsinformation, webbinformation."

Med rapportdatakällans konfiguration kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas i dina rapporter.

<!--The reporting data source configuration allows you to retrieve additional metrics that will be used in the **[!UICONTROL Objectives]** tab of your campaign reports. [Learn more](content-experiment.md#objectives-global)-->

>[!NOTE]
>
>Rapportkonfigurationen måste utföras av en teknisk användare. <!--Rights?-->

För den här konfigurationen måste du lägga till en eller flera datauppsättningar som innehåller ytterligare element som du vill använda för dina rapporter. Gör så här: [nedan](#add-datasets).

<!--
➡️ [Discover this feature in video](#video)
-->

## Förutsättningar


Innan du kan lägga till en datauppsättning i rapportkonfigurationen måste du skapa den datauppsättningen. Läs mer i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#create){target="_blank"}.

* Du kan bara lägga till datamängder av händelsetyp.

* Dessa datauppsättningar måste innehålla minst ett av följande [fältgrupper](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#field-group){target="_blank"}: **Programinformation**, **Handelsinformation**, **Webbinformation**.

   >[!NOTE]
   >
   >Endast dessa fältgrupper stöds för närvarande.

   Om du till exempel vill veta vilken effekt en e-postkampanj har på e-handelsdata som inköp eller beställningar måste du skapa en händelsedatamängd för upplevelser med **Handelsinformation** fältgrupp.

   Om du vill rapportera om mobilinteraktioner måste du också skapa en upplevelsehändelsedatauppsättning med **Programinformation** fältgrupp.

   <!--The metrics corresponding to each field group are listed [here](#objective-list).-->

* Du kan lägga till dessa fältgrupper i ett eller flera scheman som ska användas i en eller flera datauppsättningar.

>[!NOTE]
>
>Läs mer om XDM-scheman och fältgrupper i [Översikt över XDM-systemet - dokumentation](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target="_blank"}.

<!--
## Objectives corresponding to each field group {#objective-list}

The table below shows which metrics will be added to the **[!UICONTROL Objectives]** tab of your campaign reports for each field group.

| Field group | Objectives |
|--- |--- |
| Commerce Details | Price Total<br>Payment Amount<br>(Unique) Checkouts<br>(Unique) Product List Adds<br>(Unique) Product List Opens<br>(Unique) Product List Removal<br>(Unique) Product List Views<br>(Unique) Product Views<br>(Unique) Purchases<br>(Unique) Save For Laters<br>Product Price Total<br>Product Quantity |
| Application Details | (Unique) App Launches<br>First App Launches<br>(Unique) App Installs<br>(Unique) App Upgrades |
| Web Details | (Unique) Page Views |
-->

## Lägg till datauppsättningar {#add-datasets}

1. Från **[!UICONTROL ADMINISTRATION]** meny, välja **[!UICONTROL Configurations]**. I  **[!UICONTROL Reporting]** avsnitt, klicka **[!UICONTROL Manage]**.

   ![](assets/reporting-config-menu.png)

   Listan med datauppsättningar som redan har lagts till visas.

1. Klicka på **[!UICONTROL Add dataset]** på fliken **[!UICONTROL Dataset]**.

   ![](assets/reporting-config-add.png)

   >[!NOTE]
   >
   >Om du väljer **[!UICONTROL System dataset]** visas bara datauppsättningar som har skapats av systemet. Du kommer inte att kunna lägga till andra datauppsättningar.

1. Från **[!UICONTROL Dataset]** väljer du den datauppsättning som du vill använda för dina rapporter.

   >[!CAUTION]
   >
   >Du kan bara välja en datamängd av händelsetyp, som måste innehålla minst en av de data som stöds [fältgrupper](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#field-group){target="_blank"}: **Programinformation**, **Handelsinformation**, **Webbinformation**. Om du väljer en datauppsättning som inte matchar dessa villkor, kommer du inte att kunna spara ändringarna.

   ![](assets/reporting-config-datasets.png)

   Läs mer om datauppsättningar i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html){target="_blank"}.

1. Från **[!UICONTROL Profile ID]** väljer du det datamängdsfältsattribut som ska användas för att identifiera varje profil i dina rapporter.

   ![](assets/reporting-config-profile-id.png)

   >[!NOTE]
   >
   >Endast ID:n som är tillgängliga för rapportering visas.

1. The **[!UICONTROL Use Primary ID namespace]** är aktiverat som standard. Om det markerade **[!UICONTROL Profile ID]** är **[!UICONTROL Identity Map]** kan du inaktivera det här alternativet och välja ett annat namnutrymme i listrutan som visas.

   ![](assets/reporting-config-namespace.png)

   Läs mer om namnutrymmen i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=sv){target="_blank"}.

1. Spara ändringarna och lägg till den valda datauppsättningen i rapportkonfigurationslistan.

   >[!CAUTION]
   >
   >Om du valde en datauppsättning som inte är av händelsetyp kan du inte fortsätta.

<!--
When building your campaign reports, you can now see the metrics corresponding to the field groups used in the datasets you added. Go to the **[!UICONTROL Objectives]** tab and select the metrics of your choice to better fine-tune your reports. [Learn more](content-experiment.md#objectives-global)

![](assets/reporting-config-objectives.png)

>[!NOTE]
>
>If you add several datasets, all data from all datasets will be available for reporting.


## How-to video {#video}

Understand how to configure Experience Platform reporting data sources.

>[!VIDEO]()
-->
