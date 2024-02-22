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

## Förutsättningar {#prerequisites}

* Säkerställ att du använder den senaste versionen för **Adobe Experience Platform Web SDK** tillägg.

* Installera **Adobe Experience Platform Web SDK** i din **Taggegenskaper** och aktivera **Personalisering av lagring** alternativ.

  Den här konfigurationen är nödvändig för att lagra händelsehistorik på klienten, vilket är en förutsättning för att regler för frekvens ska kunna implementeras i Regelbyggaren. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration.html?lang=en)

  ![](assets/configure_web_inapp_1.png)

## Konfigurera regel för skickade data till plattformen {#configure-sent-data-trigger}

1. Få åtkomst till dina **Adobe Experience Platform Data Collection** instansen och navigera till **Taggegenskaper** konfigurerad med **Adobe Experience Platform Web SDK** tillägg.

1. Från **Redigering** meny, välja **Regler** sedan **Skapa ny regel** eller **Lägg till regel**.

   ![](assets/configure_web_inapp_2.png)

1. I **Händelser** avsnitt, klicka **Lägg till** och konfigurera det enligt följande:

   * **Tillägg**: Kärna

   * **Händelsetyp**: Bibliotek inläst (sidan ovanpå).

   ![](assets/configure_web_inapp_3.png)

1. Klicka **Behåll ändringar** för att spara händelsekonfigurationen.

1. I **Åtgärder** avsnitt, klicka **Lägg till** och konfigurera det enligt följande:

   * **Tillägg**: Adobe Experience Platform Web SDK

   * **Åtgärdstyp**: Skicka-händelse

   ![](assets/configure_web_inapp_4.png)

1. I **Personalisering** i **Åtgärd** type, aktivera **Ge visuella personaliseringsbeslut** alternativ.

   ![](assets/configure_web_inapp_5.png)

1. I **Beslutskontext** -avsnittet, definiera **Nyckel** och **Värde** par som avgör vilka upplevelser som ska levereras.

   ![](assets/configure_web_inapp_6.png)

1. Spara **Åtgärd** genom att klicka på **Behåll ändringar**.

1. Navigera till **Publiceringsflöde** -menyn. Skapa ett nytt **Bibliotek** eller välja en befintlig **Bibliotek** och lägga till dina nyskapade **Regel** till den. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/libraries.html?lang=en#create-a-library)

1. Från **Bibliotek**, markera **Spara och bygg för utveckling**.

   ![](assets/configure_web_inapp_7.png)

## Konfigurera manuell regel {#configure-manual-trigger}

1. Få åtkomst till dina **Adobe Experience Platform Data Collection** instansen och navigera till **Taggegenskaper** konfigurerad med **Adobe Experience Platform Web SDK** tillägg.

1. Från **Redigering** meny, välja **Regler** sedan **Skapa ny regel** eller **Lägg till regel**.

   ![](assets/configure_web_inapp_8.png)

1. I **Händelser** avsnitt, klicka **Lägg till** och konfigurera det enligt följande:

   * **Tillägg**: Kärna

   * **Händelsetyp**: Klicka

   ![](assets/configure_web_inapp_9.png)

1. I **Klicka på konfiguration**, definierar **Väljare** som kommer att utvärderas.

   ![](assets/configure_web_inapp_10.png)

1. Klicka **Behåll ändringar** för att spara **Händelse** konfiguration.

1. I **Åtgärder** avsnitt, klicka **Lägg till** och konfigurera det enligt följande:

   * **Tillägg**: Adobe Experience Platform Web SDK

   * **Åtgärdstyp**: Utvärdera regeluppsättningar

   ![](assets/configure_web_inapp_11.png)

1. I **Åtgärden Utvärdera regeluppsättningar** i **Åtgärd** type, aktivera **Ge visuella personaliseringsbeslut** alternativ.

   ![](assets/configure_web_inapp_13.png)

1. I **Beslutskontext** -avsnittet, definiera **Nyckel** och **Värde** par som avgör vilka upplevelser som ska levereras.

1. Öppna **Publiceringsflöde** meny, skapa en ny **Bibliotek** eller välja en befintlig **Bibliotek** och lägga till dina nyskapade **Regel**. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/libraries.html?lang=en#create-a-library)

1. Från **Bibliotek**, markera **Spara och bygg för utveckling**.

   ![](assets/configure_web_inapp_14.png)

