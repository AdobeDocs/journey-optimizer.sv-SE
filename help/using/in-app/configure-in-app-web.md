---
title: Skapa ett webbmeddelande i appen i Journey Optimizer
description: Lär dig hur du skapar ett webbmeddelande i appen i Journey Optimizer
feature: In App
topic: Content Management
role: User
level: Beginner
keywords: i appen, meddelande, skapa, börja
source-git-commit: d3f0adab52ed8e44a6097c5079396d1e9c06e0a7
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 1%

---


# Konfigurera webbkanalen i appen {#configure-in-app-web}

## Förhandskrav {#prerequisites}

* Kontrollera att du använder den senaste versionen för ditt **Adobe Experience Platform Web SDK**-tillägg.

* Installera tillägget **Adobe Experience Platform Web SDK** i **taggegenskaperna** och aktivera alternativet **Personalization Storage**.

  Den här konfigurationen är nödvändig för att lagra händelsehistorik på klienten, vilket är en förutsättning för att regler för frekvens ska kunna implementeras i Regelbyggaren. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration.html?lang=en)

  ![](assets/configure_web_inapp_1.png)

## Konfigurera regel för skickade data till plattformen {#configure-sent-data-trigger}

1. Få åtkomst till din **Adobe Experience Platform Data Collection**-instans och navigera till **Taggegenskaper** som konfigurerats med **Adobe Experience Platform Web SDK**-tillägget.

1. Välj **Regler** och sedan **Skapa ny regel** eller **Lägg till regel** på menyn **Redigering**.

   ![](assets/configure_web_inapp_2.png)

1. I avsnittet **Händelser** klickar du på **Lägg till** och konfigurerar det enligt följande:

   * **Tillägg**: Kärna

   * **Händelsetyp**: Biblioteket har lästs in (sidan överst).

   ![](assets/configure_web_inapp_3.png)

1. Klicka på **Behåll ändringar** för att spara händelsekonfigurationen.

1. Klicka på **Lägg till** i avsnittet **Åtgärder** och konfigurera det på följande sätt:

   * **Tillägg**: Adobe Experience Platform Web SDK

   * **Åtgärdstyp**: Skicka händelse

   ![](assets/configure_web_inapp_4.png)

1. Aktivera alternativet **Återge visuella personaliseringsbeslut** i **Personalization**-avsnittet av din **åtgärdstyp**.

   ![](assets/configure_web_inapp_5.png)

1. I avsnittet **Beslutskontext** definierar du de **Key** - och **Value** -par som avgör vilken upplevelse som ska levereras.

   ![](assets/configure_web_inapp_6.png)

1. Spara din **Åtgärdskonfiguration** genom att klicka på **Behåll ändringar**.

1. Navigera till menyn **Publiceringsflöde**. Skapa ett nytt **bibliotek** eller markera ett befintligt **bibliotek** och lägg till din nya **regel** i det. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/libraries.html?lang=en#create-a-library)

1. Välj **Spara och bygg till utveckling** i ditt **bibliotek**.

   ![](assets/configure_web_inapp_7.png)

## Konfigurera manuell regel {#configure-manual-trigger}

1. Få åtkomst till din **Adobe Experience Platform Data Collection**-instans och navigera till **Taggegenskaper** som konfigurerats med **Adobe Experience Platform Web SDK**-tillägget.

1. Välj **Regler** och sedan **Skapa ny regel** eller **Lägg till regel** på menyn **Redigering**.

   ![](assets/configure_web_inapp_8.png)

1. I avsnittet **Händelser** klickar du på **Lägg till** och konfigurerar det enligt följande:

   * **Tillägg**: Kärna

   * **Händelsetyp**: Klicka

   ![](assets/configure_web_inapp_9.png)

1. I **Klicka på konfigurationen** och definiera den **väljare** som ska utvärderas.

   ![](assets/configure_web_inapp_10.png)

1. Klicka på **Behåll ändringar** för att spara **Event**-konfigurationen.

1. Klicka på **Lägg till** i avsnittet **Åtgärder** och konfigurera det på följande sätt:

   * **Tillägg**: Adobe Experience Platform Web SDK

   * **Åtgärdstyp**: Utvärdera regeluppsättningar

   ![](assets/configure_web_inapp_11.png)

1. Aktivera alternativet **Återge visuella personaliseringsbeslut** i **Utvärdera regeluppsättningsåtgärd** för **åtgärdstypen**.

   ![](assets/configure_web_inapp_13.png)

1. I avsnittet **Beslutskontext** definierar du de **Key** - och **Value** -par som avgör vilken upplevelse som ska levereras.

1. Gå till menyn **Publiceringsflöde**, skapa ett nytt **bibliotek** eller välj ett befintligt **bibliotek** och lägg till din nya **regel**. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/libraries.html?lang=en#create-a-library)

1. Välj **Spara och bygg till utveckling** i ditt **bibliotek**.

   ![](assets/configure_web_inapp_14.png)

