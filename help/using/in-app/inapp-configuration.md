---
title: Krav och konfiguration för kanaler i appen
description: Lär dig hur du konfigurerar miljön för att skicka meddelanden i appen med Journey Optimizer
role: Admin
feature: In App
level: Intermediate
keywords: in-app, meddelande, konfiguration, plattform
exl-id: 469c05f2-652a-4899-a657-ddc4cebe3b42
source-git-commit: 0ec43a204f5fcf0bddf38cfd381f0ea496c7de70
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 1%

---

# Krav och konfiguration {#inapp-configuration}

## Konfigurationssteg {#inapp-steps}

Om du vill skicka meddelanden i appen under dina resor och kampanjer med [!DNL Journey Optimizer] måste du gå igenom följande konfigurationssteg.

1. Se till att du har rätt behörigheter för Journey Optimizer-kampanjer innan du startar, även om du bara tänker använda meddelanden i appen under resor. Kampanjbehörigheter krävs fortfarande. [Läs mer](../campaigns/get-started-with-campaigns.md#campaign-prerequisites).
1. Aktivera Adobe Journey Optimizer i datastream för Adobe Experience Platform Data Collection och kontrollera din standardpolicy för sammanslagning i Adobe Experience Platform, enligt beskrivningen i [Leveranskrav](#delivery-prerequisites) nedan.
1. Skapa en konfiguration för meddelandekanal i appen i Administration > Kanaler > Kanalkonfigurationer, vilket beskrivs i [det här avsnittet](#channel-prerequisites).
1. Om du använder innehållsexperiment måste du följa de krav som anges i [det här avsnittet](#experiment-prerequisite).

När du är klar kan du skapa, konfigurera och skicka ditt första meddelande i appen. Lär dig hur du uppnår detta i [det här avsnittet](create-in-app.md).

## Leveransvillkor {#delivery-prerequisites}

För att meddelanden i appen ska kunna levereras på rätt sätt måste följande inställningar definieras:

* I [Adobe Experience Platform Data Collection](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=sv-SE){target="_blank"} kontrollerar du att du har en datastream definierad, till exempel under tjänsten **[!UICONTROL Adobe Experience Platform]** som du har Adobe Experience Platform Edge och alternativet **[!UICONTROL Adobe Journey Optimizer]** aktiverat.

  Detta säkerställer att Journey Optimizer inkommande händelser hanteras korrekt av Adobe Experience Platform Edge. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=sv-SE){target="_blank"}

  ![](assets/inapp_config_6.png)

* I [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv){target="_blank"} kontrollerar du att standardprincipen för sammanslagning är aktiverad med alternativet **[!UICONTROL Active-On-Edge Merge Policy]** . Om du vill göra det väljer du en princip på menyn **[!UICONTROL Customer]** > **[!UICONTROL Profiles]** > **[!UICONTROL Merge Policies]** Experience Platform. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=sv-SE#configure){target="_blank"}

  Den här sammanfogningsprincipen används av [!DNL Journey Optimizer] inkommande kanaler för att aktivera och publicera inkommande kampanjer korrekt. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=sv-SE){target="_blank"}

  >[!NOTE]
  >
  >När du använder en anpassad **[!UICONTROL Dataset preference]**-sammanfogningsprincip måste du lägga till **[!UICONTROL Journey Inbound]**-datauppsättningen i den angivna sammanfogningsprincipen.

  ![](assets/inapp_config_8.png)

* Om du vill felsöka leveransen av Journey Optimizer mobilupplevelser kan du använda vyn **Edge Delivery** i **Adobe Experience Platform Assurance**. Med denna plugin kan du granska detaljerade förfrågningar, verifiera om förväntade gränsanrop inträffar och undersöka profildata, inklusive identitetskartor, segmentmedlemskap och inställningar för samtycke. Dessutom kan du granska de aktiviteter som begäran är kvalificerad för och identifiera de som den inte gjorde.

  Genom att använda plugin-programmet **Edge Delivery** får du de insikter du behöver för att förstå och felsöka dina inkommande implementeringar effektivt.

  [Läs mer om Edge Delivery-vyn](https://experienceleague.adobe.com/sv/docs/experience-platform/assurance/view/edge-delivery){target="_blank"}

## Skapa en konfiguration i appen {#channel-prerequisites}

Så här skapar du en konfiguration i appen i Journey Optimizer:

1. Gå till menyn **[!UICONTROL Channels]** > **[!UICONTROL General settings]** > **[!UICONTROL Channel configurations]** och klicka sedan på **[!UICONTROL Create channel configuration]**.

   ![](assets/inapp_config_1.png)

1. Ange ett namn och en beskrivning (valfritt) för konfigurationen och välj sedan den kanal som ska konfigureras.

   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt `.` och bindestreck `-`.

1. Om du vill tilldela anpassade eller grundläggande dataanvändningsetiketter till konfigurationen kan du välja **[!UICONTROL Manage access]**. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md).

1. Välj **[!UICONTROL Marketing action]** om du vill associera medgivandeprinciper till meddelanden som använder den här konfigurationen. Alla policyer för samtycke som är kopplade till marknadsföringsåtgärden utnyttjas för att ta hänsyn till kundernas preferenser. [Läs mer](../action/consent.md#surface-marketing-actions)

1. Välj **Meddelandekanal i appen**.

   ![](assets/inapp_config_9.png)

1. Välj den plattform som du vill definiera inställningarna för. På så sätt kan ni ange målappen för varje plattform och säkerställa enhetlig innehållsleverans på flera plattformar.

   >[!NOTE]
   >
   >För iOS- och Android-plattformar baseras leveransen enbart på program-ID:t. Om båda apparna har samma program-ID levereras innehåll till båda, oavsett vilken plattform som valts i **[!UICONTROL Channel configuration]**.

   ![](assets/inapp_config_10.png)

1. För webben:

   * Du kan antingen ange en **[!UICONTROL Page URL]** för att tillämpa ändringar på en viss sida.

   * Du kan skapa en regel för flera URL:er som följer samma mönster.

     +++ Så här skapar du en sidmatchningsregel.

      1. Välj **[!UICONTROL Pages matching rule]** som appkonfiguration och ange **[!UICONTROL Page URL]**.

      1. I fönstret **[!UICONTROL Edit configuration rule]** definierar du dina villkor för fälten **[!UICONTROL Domain]** och **[!UICONTROL Page]**.
      1. I listrutorna kan du anpassa villkoren ytterligare.

         Här kan du till exempel redigera element som visas på alla försäljningsproduktsidor på Luma-webbplatsen genom att välja Domän > Börjar med > luma och Sida > Innehåller > Försäljning.

         ![](assets/in_app_web_surface_4.png)

      1. Klicka på **[!UICONTROL Add another page rule]** om du vill skapa en annan regel om det behövs.

      1. Markera **[!UICONTROL Default authoring and preview URL]**.

      1. Spara ändringarna. Regeln visas på skärmen **[!UICONTROL Create campaign]**.

     +++

1. För iOS och Android:

   * Ange din **[!UICONTROL App id]**.

1. Skicka in ändringarna.

Du kan nu välja din konfiguration när du skapar ett meddelande i appen.

## Krav för rapportering {#experiment-prerequisites}

>[!NOTE]
>
>Datauppsättningen används skrivskyddat av rapportsystemet [!DNL Journey Optimizer] och påverkar inte datainsamling eller datainmatning.

Om du vill aktivera rapportering för in-app-kanal måste du se till att den [datamängd](../data/get-started-datasets.md) som används i implementeringen av [datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=sv-SE){target="_blank"} också ingår i rapportkonfigurationen. Om du lägger till en datauppsättning som inte finns i appens datastam visas med andra ord inte appdata i dina rapporter när du konfigurerar rapporter. Lär dig hur du lägger till datauppsättningar för rapportering i [det här avsnittet](../reports/reporting-configuration.md#add-datasets).

Om du **inte** använder följande fördefinierade [fältgrupper](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=sv-SE#field-group){target="_blank"} för datamängdsschemat: `AEP Web SDK ExperienceEvent` och `Consumer Experience Event` (enligt definition på [den här sidan](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/initial-configuration/configure-schemas.html?lang=sv-SE#add-field-groups){target="_blank"}) måste du lägga till följande fältgrupper: `Experience Event - Proposition Interactions`, `Application Details`, `Commerce Details` och `Web Details`. Dessa behövs av [!DNL Journey Optimizer] som rapporterar när de spårar vilka kampanjer och resor varje profil deltar i.

[Läs mer om rapportkonfiguration](../reports/reporting-configuration.md)

>[!NOTE]
>
>När du lägger till dessa fältgrupper påverkas inte den normala datainsamlingen. Den är bara additiv för de sidor där en kampanj eller resa pågår, så att all annan spårning inte påverkas

**Relaterade ämnen:**

* [Skapa ett meddelande i appen](create-in-app.md)
* [Skapa en kampanj](../campaigns/create-campaign.md)
* [Design In-app-meddelande](design-in-app.md)
* [Rapport i appen](../reports/campaign-global-report-cja-inapp.md)

