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
hide: true
hidefromtoc: true
exl-id: 327a0c45-0805-4f64-9bab-02d67276eff8
badge: label="Beta" type="Informative"
source-git-commit: 160e4ce03d3be975157c30fbe511875a85b00551
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 2%

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

>[!BEGINSHADEBOX]

Vad du hittar i den här dokumentationen:

* [Kom igång med innehållsexperiment](get-started-experiment.md)
* [Skapa ett innehållsexperiment](content-experiment.md)
* [Förstå statistiska beräkningar](experiment-calculations.md)
* **[Konfigurera experimentrapporter](reporting-configuration.md)**
* [Statistiska beräkningar i experimentrapporten](experiment-report-calculations.md)

>[!ENDSHADEBOX]

<!--The reporting data source configuration allows you to define a connection to a system in order to retrieve additional information that will be used in your reports.-->

Med rapportdatakällans konfiguration kan du hämta ytterligare mått som ska användas i **[!UICONTROL Objectives]** fliken med kampanjrapporter. [Läs mer](content-experiment.md#objectives-global)

>[!NOTE]
>
>Rapportkonfigurationen måste utföras av en teknisk användare. <!--Rights?-->

För den här konfigurationen måste du lägga till en eller flera datauppsättningar som innehåller ytterligare element som du vill använda för dina rapporter. Gör så här: [nedan](#add-datasets).

<!--
➡️ [Discover this feature in video](#video)
-->

## Förutsättningar


Innan du kan lägga till en datauppsättning i rapportkonfigurationen måste du skapa den datauppsättningen. Läs mer i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=en#create){target="_blank"}.

* Du kan bara lägga till datamängder av händelsetyp.

* Dessa datauppsättningar måste innehålla minst ett av följande [fältgrupper](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#field-group){target="_blank"}: **Programinformation**, **Handelsinformation**, **Webbinformation**.

   >[!NOTE]
   >
   >Endast dessa fältgrupper stöds för närvarande.

   Om du till exempel vill veta vilken effekt en e-postkampanj har på e-handelsdata som inköp eller beställningar måste du skapa en händelsedatamängd för upplevelser med **Handelsinformation** fältgrupp.

   Om du vill rapportera om mobilinteraktioner måste du också skapa en upplevelsehändelsedatauppsättning med **Programinformation** fältgrupp.

   De mått som motsvarar varje fältgrupp visas [här](#objective-list).

* Du kan lägga till dessa fältgrupper i ett eller flera scheman som ska användas i en eller flera datauppsättningar.

>[!NOTE]
>
>Läs mer om XDM-scheman och fältgrupper i [Översikt över XDM-systemet - dokumentation](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target="_blank"}.

## Mål som motsvarar varje fältgrupp {#objective-list}

Tabellen nedan visar vilka mätvärden som kommer att läggas till i **[!UICONTROL Objectives]** -fliken i era kampanjrapporter för varje fältgrupp.

| Fältgrupp | Mål |
|--- |--- |
| Handelsinformation | Prissumma<br>Betalningsbelopp<br>(Unik) utcheckningar<br>(Unikt) Produktlista lägger till<br>(Unikt) Produktlistan öppnas<br>(Unik) Borttagning av produktlista<br>(Unik) Produktlistvyer<br>(Unik) Produktvyer<br>(Unikt) Inköp<br>(Unikt) Spara för senare<br>Totalt produktpris<br>Produktkvantitet |
| Programinformation | (Unikt) Applanseringar<br>Första programstarten<br>(Unik) Appinstallationer<br>(Unikt) Appuppgraderingar |
| Webbinformation | (Unik) Sidvyer |

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

   Läs mer om namnutrymmen i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html){target="_blank"}.

1. Spara ändringarna och lägg till den valda datauppsättningen i rapportkonfigurationslistan.

   >[!CAUTION]
   >
   >Om du valde en datauppsättning som inte är av händelsetyp kan du inte fortsätta.

När ni skapar kampanjrapporter kan ni nu se mätvärden som motsvarar fältgrupperna som används i de datamängder ni har lagt till. Gå till **[!UICONTROL Objectives]** och välj de mätvärden du vill ha för att finjustera dina rapporter. [Läs mer](content-experiment.md#objectives-global)

![](assets/reporting-config-objectives.png)

>[!NOTE]
>
>Om du lägger till flera datauppsättningar blir alla data från alla datauppsättningar tillgängliga för rapportering.

<!--
## How-to video {#video}

Understand how to configure Experience Platform reporting data sources.

>[!VIDEO]()
-->
