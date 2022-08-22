---
title: Rapporteringskonfiguration
description: Lär dig hur du ställer in rapportdatakälla
feature: Data Sources
topic: Administration
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
source-git-commit: 11f7ce37dc1a99de4ed29fa7793f126e259f518d
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 3%

---

# Rapporteringskonfiguration {#reporting-configuration}

>[!CONTEXTUALHELP]
>id="ajo_admin_reporting_config"
>title="Ställ in datauppsättningar för rapportering"
>abstract="Med rapportkonfigurationen kan du definiera en anslutning till ett system för att hämta ytterligare anpassad information som ska användas i dina rapporter. Den måste utföras av en teknisk användare."

>[!CONTEXTUALHELP]
>id="ajo_admin_reporting_dataset"
>title="Välj en datauppsättning"
>abstract="Du kan bara välja en datamängd av händelsetyp som måste innehålla minst en av de fältgrupper som stöds: experience-event-web, experience-event-application, experience-event-commerce."

Med rapportdatakällans konfiguration kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas i dina rapporter.

>[!NOTE]
>
>Datakällans konfiguration måste utföras av en teknisk användare. <!--Rights?-->

För den här konfigurationen måste du lägga till en eller flera datauppsättningar som innehåller de attribut som du vill använda för dina rapporter. Följ stegen nedan för att göra detta.

>[!CAUTION]
>
>Innan du kan lägga till en datauppsättning i rapportkonfigurationen måste du skapa den. Läs mer i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=en#create){target=&quot;_blank&quot;}.
>
>Du kan bara lägga till datamängder av händelsetyp, som måste innehålla minst en av de datamängder som stöds [fältgrupper](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#field-group){target=&quot;_blank&quot;}: **experience-event-web**, **experience-event-application**, **experience-event-commerce**.

<!--
➡️ [Discover this feature in video](#video)
-->

Om du till exempel vill veta vilken effekt en e-postkampanj har på e-handelsdata som inköp eller beställningar måste du skapa en händelsedatamängd för upplevelser med **experience-event-commerce** fältgrupp. Om du vill rapportera om mobilinteraktioner måste du också skapa en upplevelsehändelsedatauppsättning med **experience-event-application** fältgrupp. <!--If you want to report on web interactions then you need to include the web field group.--> Du kan lägga till de här fältgrupperna i ett eller flera scheman som ska användas i en datauppsättning eller i olika datauppsättningar.

>[!NOTE]
>
>Läs mer om XDM-scheman och fältgrupper i [Översikt över XDM-systemet - dokumentation](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target=&quot;_blank&quot;}.

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
   >Du kan bara välja en datamängd av händelsetyp, som måste innehålla minst en av de data som stöds [fältgrupper](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#field-group){target=&quot;_blank&quot;}: **experience-event-web**, **experience-event-application**, **experience-event-commerce**. Om du väljer en datauppsättning som inte matchar dessa villkor, kommer du inte att kunna spara ändringarna.

   ![](assets/reporting-config-datasets.png)

   Läs mer om datauppsättningar i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html){target=&quot;_blank&quot;}.

1. Från **[!UICONTROL Profile ID]** väljer du det datamängdsfältsattribut som ska användas för att identifiera varje profil i dina rapporter.

   ![](assets/reporting-config-profile-id.png)

   >[!NOTE]
   >
   >Endast ID:n som är tillgängliga för rapportering visas.

1. The **[!UICONTROL Use Primary ID namespace]** är aktiverat som standard. Om det markerade **[!UICONTROL Profile ID]** är **[!UICONTROL Identity Map]** kan du inaktivera det här alternativet och välja ett annat namnutrymme i listrutan som visas.

   ![](assets/reporting-config-namespace.png)

   Läs mer om namnutrymmen i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html){target=&quot;_blank&quot;}.

1. Spara ändringarna och lägg till den valda datauppsättningen i rapportkonfigurationslistan.

   >[!CAUTION]
   >
   >Om du valde en datauppsättning som inte är av händelsetyp kan du inte fortsätta.

När du skapar leveransrapporter kan du nu använda data från den här datauppsättningen för att hämta ytterligare anpassad information och finjustera dina rapporter bättre. [Läs mer](campaign-global-report.md#objectives-global)

>[!NOTE]
>
>Om du lägger till flera datauppsättningar blir alla data från alla datauppsättningar tillgängliga för rapportering.


<!--
## How-to video {#video}

Understand how to configure Experience Platform reporting data sources.

>[!VIDEO]()
-->
