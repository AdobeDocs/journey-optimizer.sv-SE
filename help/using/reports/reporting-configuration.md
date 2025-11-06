---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera Journey Optimizer-rapportering för experiment
description: Lär dig hur du ställer in rapportdatakälla
feature: Experimentation, Reporting
topic: Administration
role: Admin
level: Intermediate
keywords: konfiguration, experiment, rapportering, optimering
exl-id: 327a0c45-0805-4f64-9bab-02d67276eff8
source-git-commit: d772ef2d98775446618bd6614a26b9f352e073bd
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 1%

---

# Krav för rapportering och experimenterande {#reporting-configuration}

>[!CONTEXTUALHELP]
>id="ajo_admin_reporting_config"
>title="Ställ in datauppsättningar för rapportering"
>abstract="Med rapportkonfigurationen kan ni hämta ytterligare mätvärden som ska användas i kampanjrapporterna. Den måste utföras av en teknisk användare."

>[!CONTEXTUALHELP]
>id="ajo_admin_reporting_dataset"
>title="Välj en datauppsättning"
>abstract="Du kan bara välja en datamängd av händelsetyp, som måste innehålla minst en av de fältgrupper som stöds: Programinformation, Commerce-information, Webbinformation."

>[!NOTE]
>
>Rapportkonfigurationen måste utföras av en teknisk användare.

Med rapportdatakällans konfiguration kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas i dina rapporter.

För den här konfigurationen måste du lägga till en eller flera datauppsättningar som innehåller ytterligare element som du vill använda för dina rapporter. Gör detta genom att följa stegen [nedan](#add-datasets).

Observera att för webbkanaler, kodbaserade kanaler och appkanaler måste du se till att den [datamängd](../data/get-started-datasets.md) som konfigurerats för datainsamling också läggs till i den här rapportkonfigurationen. I annat fall visas inte webb- och appdata i innehållsexperimentrapporter.

## Förhandskrav

Innan du kan lägga till en datauppsättning i rapportkonfigurationen måste du skapa den datauppsättningen. Läs mer i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=sv-SE#create){target="_blank"}.

* Du kan bara lägga till datamängder av händelsetyp.

* Dessa datauppsättningar måste innehålla `Experience Event - Proposition Interactions` [fältgruppen](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=sv-SE#field-group){target="_blank"}.

* Dessa datauppsättningar kan även innehålla en av följande [fältgrupper](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=sv-SE#field-group){target="_blank"}: `Application Details`, `Commerce Details`, `Web Details`.

  >[!NOTE]
  >
  >Andra fältgrupper kan också inkluderas, men endast de ovanstående fältgrupperna stöds för närvarande i Journey Optimizer-rapporter.

  Om du till exempel vill veta vilken effekt en e-postkampanj har på e-handelsdata som inköp eller order måste du skapa en upplevelsehändelsedatamängd med fältgruppen `Commerce Details`.

  Om du vill rapportera om mobilinteraktioner måste du också skapa en upplevelsehändelsedatauppsättning med fältgruppen `Application Details`.

  <!--The metrics corresponding to each field group are listed [here](#objective-list).-->

* Du kan lägga till de här fältgrupperna i ett eller flera scheman som ska användas i en eller flera datauppsättningar.

>[!NOTE]
>
>Läs mer om XDM-scheman och fältgrupper i [översiktsdokumentationen för XDM-systemet](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target="_blank"}.

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

>[!NOTE]
>
>Alla nya datauppsättningar är bara tillgängliga i Customer Journey Analytics-rapporter.

1. Välj **[!UICONTROL Administration]** på menyn **[!UICONTROL Configurations]**. Klicka på **[!UICONTROL Reporting]** i avsnittet **[!UICONTROL Manage]**.

   ![](assets/reporting-config-menu.png)

   Listan med datauppsättningar som redan har lagts till visas.

1. Klicka på **[!UICONTROL Add dataset]** på fliken **[!UICONTROL Dataset]**.

   ![](assets/reporting-config-add.png)

   >[!NOTE]
   >
   >Om du väljer fliken **[!UICONTROL System dataset]** visas endast datauppsättningar som har skapats av systemet. Du kan inte lägga till andra datauppsättningar.

1. I listrutan **[!UICONTROL Dataset]** väljer du den datauppsättning som du vill använda för dina rapporter.

   >[!CAUTION]
   >
   >Du kan bara välja en datamängd av händelsetyp, som måste innehålla minst en av de [fältgrupper som stöds](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=sv-SE#field-group){target="_blank"}: **Programinformation**, **Commerce-information**, **Webbinformation**. Om du väljer en datauppsättning som inte matchar dessa villkor, kommer du inte att kunna spara ändringarna.

   ![](assets/reporting-config-datasets.png)

   Läs mer om datauppsättningar i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=sv-SE){target="_blank"}.

1. I listrutan **[!UICONTROL Profile ID]** väljer du det datamängdsfältsattribut som ska användas för att identifiera varje profil i dina rapporter.

   ![](assets/reporting-config-profile-id.png)

   >[!NOTE]
   >
   >Endast ID:n som är tillgängliga för rapportering visas.

1. Alternativet **[!UICONTROL Use Primary ID namespace]** är aktiverat som standard. Om den markerade **[!UICONTROL Profile ID]** är **[!UICONTROL Identity Map]** kan du inaktivera det här alternativet och välja ett annat namnutrymme i listrutan som visas.

   ![](assets/reporting-config-namespace.png)

   Läs mer om namnutrymmen i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=sv){target="_blank"}.

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
