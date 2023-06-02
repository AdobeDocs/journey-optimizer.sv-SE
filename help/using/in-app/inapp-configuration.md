---
title: Konfiguration i appen
description: Lär dig hur du konfigurerar miljön för att skicka meddelanden i appen med Journey Optimizer
role: Admin
level: Intermediate
keywords: in-app, meddelande, konfiguration, plattform
exl-id: 469c05f2-652a-4899-a657-ddc4cebe3b42
source-git-commit: 21aeac323a43ac95d98f4798ff3d51ad32f2ebf9
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 3%

---

# Konfigurera kanal i appen {#inapp-configuration}

Innan du skickar meddelanden i appen måste du konfigurera din app-kanal i [!DNL Adobe Experience Platform Data Collection].

1. Från [!DNL Adobe Experience Platform Data Collection] konto, få åtkomst till **[!UICONTROL Datastream]** meny och klicka **[!UICONTROL New datastream]**. Mer information om hur du skapar data finns i [den här sidan](https://aep-sdks.gitbook.io/docs/getting-started/configure-datastreams).

1. Välj [!DNL Adobe Experience Platform] service.

   [!DNL Edge Segmentation] och [!DNL Adobe Journey Optimizer] måste väljas.

   ![](assets/inapp_config_6.png)

1. Sedan öppnar du **[!UICONTROL App surfaces]** menyn och klicka sedan på **[!UICONTROL Create App surface]**.

   ![](assets/inapp_config_1.png)

1. Lägg till ett namn i **[!UICONTROL App surface]**.

1. I listrutan Apple iOS skriver du **iOS Bundle-ID**. Se [Apple-dokumentation](https://developer.apple.com/documentation/appstoreconnectapi/bundle_ids) för mer information om **Paket-ID**.

   ![](assets/inapp_config_2.png)

1. I Android-listrutan skriver du in **Android-paketnamn**. Se [Android-dokumentation](https://support.google.com/admob/answer/9972781?hl=en#:~:text=The%20package%20name%20of%20an,supported%20third%2Dparty%20Android%20stores) för mer information om **Paketnamn**.

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
