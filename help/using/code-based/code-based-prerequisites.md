---
title: Kodbaserade upplevelsegarantier och förutsättningar
description: Om du vill kunna redigera program och webbsidor med den kodbaserade funktionen i Journey Optimizer följer du kraven på den här sidan
feature: Code-based Experiences
topic: Content Management
role: Admin
level: Experienced
exl-id: ac901f88-5fde-4220-88c6-fe05433866cc
source-git-commit: d2ac4dfe40559f01db59e314e8838f51b39a8659
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 0%

---

# Garantier och krav {#web-prerequisites}

Att kunna använda kodbaserade upplevelseåtgärder i [!DNL Journey Optimizer] och leverera kodinnehållsavgifter som kan användas av dina program, följ kraven nedan:

* Om du vill lägga till ändringar i dina program måste du ha en specifik implementering. [Läs mer](#implementation-prerequisites)

* För att de kodbaserade upplevelserna ska kunna levereras på rätt sätt måste du definiera Adobe Experience Platform-inställningarna i detalj [här](#delivery-prerequisites).

>[!CAUTION]
>
>* Den kodbaserade upplevelsekanalen är inte tillgänglig för organisationer som har köpt Adobe **Hälsovårdssköld** och **Sköld för skydd av privatlivet och säkerheten** tilläggserbjudanden.
>
>* Du kan bara skapa kodbaserade upplevelser i **kampanjer**. [Läs mer](../campaigns/create-campaign.md#configure


## Krav för implementering {#implementation-prerequisites}

Kodbaserad upplevelse stöder alla typer av kundimplementeringar som visas i alternativen nedan. Du kan antingen använda en implementeringsmetod på klientsidan, serversidan eller en hybridimplementeringsmetod för dina egenskaper:

* Endast på klientsidan - Om du vill lägga till ändringar på webbsidor eller mobilappar måste du implementera antingen [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html){target="_blank"} on your website or [Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/){target="_blank"} på era mobilappar.

* Hybridläge - Du kan använda [API för AEP Edge Network Server](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html){target="_blank"} to request for personalization server-side; the response is provided to the Adobe Experience Platform Web SDK to render the modifications client-side. Learn more in the Adobe Experience Platform [Edge Network Server API documentation](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html){target="_blank"}. You can find out more about the hybrid mode and check some implementation samples in [this blog post](https://blog.developer.adobe.com/hybrid-personalization-in-the-adobe-experience-platform-web-sdk-6a1bb674bf41){target="_blank"}.

* Serversidan - Du kan använda [API för AEP Edge Network Server](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html){target="_blank"} för att begära personalisering på serversidan. Utvecklingsteamet måste hantera svaret och återge ändringarna på klientsidan i appimplementeringen.

Du kan hitta exempel för var och en av implementeringsmetoderna ovan i [det här avsnittet](code-based-implementation-samples.md).

## Leveransvillkor {#delivery-prerequisites}

För att de kodbaserade upplevelserna ska kunna levereras på rätt sätt måste följande inställningar definieras:

* I [Adobe Experience Platform Data Collection](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html){target="_blank"}kontrollerar du att du har en datastream definierad, till exempel under **[!UICONTROL Adobe Experience Platform]** den tjänst du har **[!UICONTROL Adobe Journey Optimizer]** aktiverat alternativ.

  Detta säkerställer att Journey Optimizer inkommande händelser hanteras korrekt av Adobe Experience Platform Edge. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html){target="_blank"}

  ![](../web/assets/web-aep-datastream-ajo.png)

* I [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv){target="_blank"}, make sure you have one merge policy with the **[!UICONTROL Active-On-Edge Merge Policy]** option enabled. To do this, select a policy under the **[!UICONTROL Customer]** > **[!UICONTROL Profiles]** > **[!UICONTROL Merge Policies]** Experience Platform menu. [Learn more](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html#configure){target="_blank"}

  Den här sammanfogningsprincipen används av [!DNL Journey Optimizer] inkommande kanaler för att korrekt aktivera och publicera inkommande kampanjer. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html){target="_blank"}

  ![](../web/assets/web-aep-merge-policy.png)

## Förutsättningar för innehållsexperiment {#experiment-prerequisites}

Om du vill aktivera innehållsexperiment för den kodbaserade kanalen måste du se till att [datauppsättning](../data/get-started-datasets.md) som används i appimplementeringen [datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html){target="_blank"} ingår även i din rapportkonfiguration.

Om du lägger till en datauppsättning som inte finns i appens datastam, visas alltså inte appdata i innehållsexperimentrapporter när du konfigurerar experimentrapporter.

Lär dig hur du lägger till datauppsättningar för att experimentera med innehåll i [det här avsnittet](../campaigns/reporting-configuration.md#add-datasets).

>[!NOTE]
>
>Datauppsättningen används skrivskyddat av [!DNL Journey Optimizer] rapporteringssystem och påverkar inte datainsamling eller datainmatning.
