---
title: Krav för kanaler i appen
description: Lär dig hur du konfigurerar miljön för att skicka meddelanden i appen med Journey Optimizer
role: Admin
feature: In App
level: Intermediate
keywords: in-app, meddelande, konfiguration, plattform
exl-id: 469c05f2-652a-4899-a657-ddc4cebe3b42
source-git-commit: 03c714833930511fa734662b637d2416728073c2
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 3%

---

# Krav för kanaler i appen {#inapp-configuration}

## Leveransvillkor {#delivery-prerequisites}

För att meddelanden i appen ska kunna levereras på rätt sätt måste följande inställningar definieras:

* I [Adobe Experience Platform Data Collection](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html){target="_blank"}kontrollerar du att du har en datastream definierad, till exempel under **[!UICONTROL Adobe Experience Platform]** har du Adobe Experience Platform Edge och **[!UICONTROL Adobe Journey Optimizer]** aktiverat alternativ.

  Detta säkerställer att Journey Optimizer inkommande händelser hanteras korrekt av Adobe Experience Platform Edge. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html){target="_blank"}

  ![](assets/inapp_config_6.png)

* I [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv){target="_blank"}, make sure you have the default merge policy with the **[!UICONTROL Active-On-Edge Merge Policy]** option enabled. To do this, select a policy under the **[!UICONTROL Customer]** > **[!UICONTROL Profiles]** > **[!UICONTROL Merge Policies]** Experience Platform menu. [Learn more](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html#configure){target="_blank"}

  Den här sammanfogningsprincipen används av [!DNL Journey Optimizer] inkommande kanaler för att korrekt aktivera och publicera inkommande kampanjer. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html){target="_blank"}

  ![](assets/inapp_config_8.png)

## Krav för kanalkonfiguration {#channel-prerequisites}

1. Öppna **[!UICONTROL App surfaces]** meny och klicka **[!UICONTROL Create App surface]**.

1. Lägg till ett namn i **[!UICONTROL App surface]**.

   ![](assets/inapp_config_2b.png)

1. Från **[!UICONTROL Apple iOS]** konfigurera ditt mobilprogram för Apple iOS.

+++ Läs mer

   1. Skriv in **[!UICONTROL iOS Bundle ID]**. Se [Apple-dokumentation](https://developer.apple.com/documentation/appstoreconnectapi/bundle_ids) för mer information om **Paket-ID**.

   1. (valfritt) Välj **[!UICONTROL Sandbox]** där du vill skicka push-meddelanden från. Observera att den nödvändiga åtkomstbehörigheten krävs för att du ska kunna välja en viss sandlåda.

      Mer information om sandlådehantering finns i [den här sidan](../administration/sandboxes.md#assign-sandboxes).

   1. Aktivera **[!UICONTROL Push credentials]** om du vill dra och släppa .p8-filen för autentiseringsnyckel.

      Du kan även aktivera **[!UICONTROL Manually enter push credentials]** om du vill kopiera och klistra in APN:er-auth-tangenten direkt.

   1. Ange **[!UICONTROL Key ID]** och **[!UICONTROL Team ID]**.

      ![](assets/inapp_config_2.png)

+++

1. Från **[!UICONTROL Android]** konfigurera ditt mobilprogram för Android-enheter.

+++ Läs mer

   1. Skriv in **[!UICONTROL Android package name]**. Se [Android-dokumentation](https://support.google.com/admob/answer/9972781?hl=en#:~:text=The%20package%20name%20of%20an,supported%20third%2Dparty%20Android%20stores) för mer information om **Paketnamn**.

   1. (valfritt) Välj **[!UICONTROL Sandbox]** där du vill skicka push-meddelanden från. Observera att den nödvändiga åtkomstbehörigheten krävs för att du ska kunna välja en viss sandlåda.

      Mer information om sandlådehantering finns i [den här sidan](../administration/sandboxes.md#assign-sandboxes).

   1. Aktivera **[!UICONTROL Push credentials]** om du vill dra och släppa .json-filen för privat nyckel.

      Du kan även aktivera **[!UICONTROL Manually enter push credentials]** kan du kopiera och klistra in den privata FCM-nyckeln direkt.

      ![](assets/inapp_config_7.png)

1. Klicka **[!UICONTROL Save]** när du är klar med konfigurationen av **[!UICONTROL App surface]**.

   ![](assets/inapp_config_3.png)

   Dina **[!UICONTROL App surface]** kommer nu att vara tillgängligt när du skapar en ny kampanj med ett meddelande i appen. [Läs mer](create-in-app.md)

1. När du har skapat appytan måste du nu skapa en mobil egenskap.

   Se [den här sidan](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html#for-mobile) för det detaljerade förfarandet.

   ![](assets/inapp_config_4.png)

1. Installera följande tillägg på menyn Tillägg för den nya egenskapen:

   * Adobe Experience Platform Edge Network
   * Adobe Journey Optimizer
   * AEP Assurance
   * Godkännande
   * Identitet
   * Mobile Core
   * Profil

   Se [den här sidan](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/extensions/overview.html#add-a-new-extension) för det detaljerade förfarandet.

   ![](assets/inapp_config_5.png)

Kanalen i appen är nu konfigurerad. Du kan börja skicka meddelanden i appen till dina användare.

## Förutsättningar för innehållsexperiment {#experiment-prerequisites}

Om du vill aktivera innehållsexperiment för appkanaler måste du se till att [datauppsättning](../data/get-started-datasets.md) som används i implementeringen i appen [datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html){target="_blank"} ingår även i din rapportkonfiguration.

Om du lägger till en datauppsättning som inte finns i webbdataströmmen när du konfigurerar experimentrapporter, kommer webbdata alltså inte att visas i innehållsexperimentrapporter.

Lär dig hur du lägger till datauppsättningar för att experimentera med innehåll i [det här avsnittet](../campaigns/reporting-configuration.md#add-datasets).

>[!NOTE]
>
>Datauppsättningen används skrivskyddat av [!DNL Journey Optimizer] rapporteringssystem och påverkar inte datainsamling eller datainmatning.

Om du **not** med följande fördefinierade [fältgrupper](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#field-group){target="_blank"} for your dataset schema: `AEP Web SDK ExperienceEvent` and `Consumer Experience Event` (as defined in [this page](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/initial-configuration/configure-schemas.html#add-field-groups){target="_blank"}) måste du lägga till följande fältgrupper: `Experience Event - Proposition Interactions`, `Application Details`, `Commerce Details`och `Web Details`. Dessa behövs av [!DNL Journey Optimizer] Experimentera med rapporter om vilka experiment och behandlingar respektive profil deltar i.

>[!NOTE]
>
>När du lägger till dessa fältgrupper påverkas inte den normala datainsamlingen. Den är bara additiv för de sidor där ett experiment pågår, och lämnar all annan spårning orörd.

## Instruktionsvideor{#video}

* I videon nedan visas hur du tilldelar **Hantera appkonfiguration** behörighet att komma åt appens ytmeny.

  +++Se video

  >[!VIDEO](https://video.tv.adobe.com/v/3421607)

+++

**Relaterade ämnen:**

* [Skapa ett meddelande i appen](create-in-app.md)
* [Skapa en kampanj](../campaigns/create-campaign.md)
* [Design In-app-meddelande](design-in-app.md)
* [Rapport i appen](../reports/campaign-global-report.md#inapp-report)

