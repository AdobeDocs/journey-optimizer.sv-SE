---
title: Kodbaserade upplevelsegarantier och förutsättningar
description: Om du vill kunna redigera program och webbsidor med den kodbaserade funktionen i Journey Optimizer följer du kraven på den här sidan
feature: Code-based Experiences
topic: Content Management
role: Admin
level: Experienced
exl-id: ac901f88-5fde-4220-88c6-fe05433866cc
source-git-commit: 6adad3dfc9a0ec23c26be2027b0e1b3e2b757f6a
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 1%

---

# Garantier och krav {#web-prerequisites}

Om du vill kunna använda kodbaserade upplevelseåtgärder i [!DNL Journey Optimizer] och leverera kodinnehållets nyttolast som kan användas av dina program följer du kraven nedan:

* Om du vill lägga till ändringar i dina program måste du ha en specifik implementering. [Läs mer](#implementation-prerequisites)

* För att de kodbaserade upplevelserna ska kunna levereras på rätt sätt måste du definiera Adobe Experience Platform-inställningarna som anges [här](#delivery-prerequisites).

>[!CAUTION]
>
>Du kan bara skapa kodbaserade upplevelser i **kampanjer**. [Läs mer](../campaigns/create-campaign.md#configure).

## Krav för implementering {#implementation-prerequisites}

Kodbaserad upplevelse stöder alla typer av kundimplementeringar som visas i alternativen nedan. Du kan antingen använda en implementeringsmetod på klientsidan, serversidan eller en hybridimplementeringsmetod för dina egenskaper:

* Endast på klientsidan - Om du vill lägga till ändringar på dina webbsidor eller mobilappar måste du implementera [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html){target="_blank"} på din webbplats eller [Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/){target="_blank"} på dina mobilappar.

* Hybridläge - Du kan använda [API:t för AEP Edge Network-servern](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html){target="_blank"} för att begära anpassning på serversidan. Svaret ges till Adobe Experience Platform Web SDK för att återge ändringarna på klientsidan. Läs mer i Adobe Experience Platform [Edge Network Server API-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html){target="_blank"}. Du kan ta reda på mer om hybridläget och kontrollera några implementeringsexempel i [det här blogginlägget](https://blog.developer.adobe.com/hybrid-personalization-in-the-adobe-experience-platform-web-sdk-6a1bb674bf41){target="_blank"}.

* Serversidan - Du kan använda [API:t för AEP Edge Network-servern](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html){target="_blank"} för att begära anpassning på serversidan. Utvecklingsteamet måste hantera svaret och återge ändringarna på klientsidan i appimplementeringen.

Du kan hitta exempel för varje implementeringsmetod ovan i [det här avsnittet](code-based-implementation-samples.md).

## Leveransvillkor {#delivery-prerequisites}

För att de kodbaserade upplevelserna ska kunna levereras på rätt sätt måste följande inställningar definieras:

* I [Adobe Experience Platform Data Collection](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html){target="_blank"} kontrollerar du att du har en datastream definierad, till exempel under **[!UICONTROL Adobe Experience Platform]**-tjänsten som du har alternativet **[!UICONTROL Adobe Journey Optimizer]** aktiverat.

  Detta säkerställer att Journey Optimizer inkommande händelser hanteras korrekt av Adobe Experience Platform Edge. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html){target="_blank"}

  ![](../web/assets/web-aep-datastream-ajo.png)

* I [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv){target="_blank"} kontrollerar du att du har en sammanfogningsprincip med alternativet **[!UICONTROL Active-On-Edge Merge Policy]** aktiverat. Om du vill göra det väljer du en profil under menyn **[!UICONTROL Customer]** > **[!UICONTROL Profiles]** > **[!UICONTROL Merge Policies]** Experience Platform. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html#configure){target="_blank"}

  Den här sammanfogningsprincipen används av [!DNL Journey Optimizer] inkommande kanaler för att aktivera och publicera inkommande kampanjer korrekt. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html){target="_blank"}

  ![](../web/assets/web-aep-merge-policy.png)

* Om du vill felsöka leveransen av Journey Optimizer webbupplevelser kan du använda vyn **Edge Delivery** i **Adobe Experience Platform Assurance**. Med denna plugin kan du granska detaljerade förfrågningar, verifiera om förväntade gränsanrop inträffar och undersöka profildata, inklusive identitetskartor, segmentmedlemskap och inställningar för samtycke. Dessutom kan du granska de aktiviteter som begäran är kvalificerad för och identifiera de som den inte gjorde.

  Genom att använda plugin-programmet **Edge Delivery** får du de insikter du behöver för att förstå och felsöka dina inkommande implementeringar effektivt.

  [Läs mer om Edge Delivery-vyn](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/view/edge-delivery)

## Förutsättningar för innehållsexperiment {#experiment-prerequisites}

Om du vill aktivera innehållsexperiment för den kodbaserade kanalen måste du se till att den [datamängd](../data/get-started-datasets.md) som används i appimplementeringen [datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html){target="_blank"} också ingår i rapportkonfigurationen.

Om du lägger till en datauppsättning som inte finns i appens datastam, visas alltså inte appdata i innehållsexperimentrapporter när du konfigurerar experimentrapporter.

Lär dig hur du lägger till datauppsättningar för rapportering av innehållsexperiment i [det här avsnittet](../content-management/reporting-configuration.md#add-datasets).

>[!NOTE]
>
>Datauppsättningen används skrivskyddat av rapportsystemet [!DNL Journey Optimizer] och påverkar inte datainsamling eller datainmatning.
