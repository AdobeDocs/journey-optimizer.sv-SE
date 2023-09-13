---
title: Konfiguration i appen
description: Lär dig hur du konfigurerar miljön för att skicka meddelanden i appen med Journey Optimizer
role: Admin
level: Intermediate
keywords: in-app, meddelande, konfiguration, plattform
exl-id: 469c05f2-652a-4899-a657-ddc4cebe3b42
source-git-commit: 6f92f9ce0a4785f0359658f00150d283f1326900
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 2%

---

# Konfigurera kanal i appen {#inapp-configuration}

Innan du skickar meddelanden i appen måste du konfigurera din kanal i appen i [!DNL Adobe Experience Platform Data Collection].

1. Från [!DNL Adobe Experience Platform Data Collection] konto, få åtkomst till **[!UICONTROL Datastream]** meny och klicka **[!UICONTROL New datastream]**. Mer information om hur du skapar data finns i [den här sidan](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html).

1. Välj [!DNL Adobe Experience Platform] service.

   [!DNL Edge Segmentation] och [!DNL Adobe Journey Optimizer] måste väljas.

   ![](assets/inapp_config_6.png)

   >[!NOTE]
   >
   >Om du vill aktivera innehållsexperiment för appkanalen måste du se till att [datauppsättning](../data/get-started-datasets.md) används i din app [datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html){target="_blank"} finns också i din rapportkonfiguration - annars visas inte data i appen i innehållsexperimentrapporter. [Lär dig lägga till datauppsättningar](../campaigns/reporting-configuration.md#add-datasets)
   >
   >Datauppsättningen används skrivskyddat av [!DNL Journey Optimizer] rapporteringssystem och påverkar inte datainsamling eller datainmatning.

1. Sedan öppnar du **[!UICONTROL App surfaces]** meny och klicka **[!UICONTROL Create App surface]**.

   >[!NOTE]
   >
   > Du behöver **Hantera appkonfiguration** behörighet att få åtkomst till **[!UICONTROL App surfaces]** -menyn. Mer information finns i [den här videon](#video).

   ![](assets/inapp_config_1.png)

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

**Relaterade ämnen:**

* [Skapa ett meddelande i appen](create-in-app.md)
* [Skapa en kampanj](../campaigns/create-campaign.md)
* [Design In-app-meddelande](design-in-app.md)
* [Rapport i appen](../reports/campaign-global-report.md#inapp-report)


## Instruktionsvideor{#video}

* I videon nedan visas hur du tilldelar **Hantera appkonfiguration** behörighet att komma åt appens ytmeny.

  +++Se video

  >[!VIDEO](https://video.tv.adobe.com/v/3421607)

+++


