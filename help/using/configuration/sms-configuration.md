---
title: SMS-konfiguration
description: Lär dig hur du konfigurerar miljön för att skicka SMS-meddelanden med Journey Optimizer
role: Admin
level: Intermediate
exl-id: 4dcd22ed-bf7e-4789-ab7b-33544c857db8
source-git-commit: e6924d1bffca7f56f2e5020a0af429b0f2b1c811
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 1%

---

# Konfigurera SMS-kanal {#sms-configuration}

[!DNL Journey Optimizer] kan ni skapa resor och skicka meddelanden till riktade målgrupper.

Konfigurera instansen innan du skickar SMS. Du måste [integrera providerinställningarna](#create-api) med Journey Optimizer och [skapa en SMS-förinställning](#message-preset-sms). Dessa steg måste utföras av en [Adobe Journey Optimizer systemadministratör](../start/path/administrator.md).

>[!AVAILABILITY]
>
>SMS-kanalen är för närvarande bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant om du vill ha mer information.

## Skapa nya API-autentiseringsuppgifter {#create-api}

Så här konfigurerar du din SMS-leverantör med Journey Optimizer:

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL API Credentials]** menyn och klicka sedan på **[!UICONTROL Create API credential]**.

   ![](assets/sms_4.png)

1. Välj **[!UICONTROL SMS vendor]**:

   * [!DNL Sinch]. För att hitta **[!UICONTROL Service ID]** och **[!UICONTROL API Token]**&#x200B;öppnar du SMS > API:er-menyn från ditt Sinch-konto.
   * [!DNL Twilio]. För att hitta **[!UICONTROL Service ID]** och **[!UICONTROL API Token]**&#x200B;öppnar du panelen Kontoinformation på sidan Konsolinstrumentpanel.

1. Ange **[!UICONTROL Name]** för dina API-autentiseringsuppgifter.

1. Ange **[!UICONTROL Service ID]** och **[!UICONTROL API Token]**.

   ![](assets/sms_5.png)

1. Klicka **[!UICONTROL Submit]** när du är klar med konfigurationen av dina API-autentiseringsuppgifter.

När du har skapat och konfigurerat dina API-autentiseringsuppgifter måste du nu skapa en meddelandeförinställning för SMS-meddelanden.

## Skapa en meddelandeförinställning för SMS-meddelanden {#message-preset-sms}

När SMS-kanalen har konfigurerats måste du skapa en meddelandeförinställning för att kunna skicka SMS-meddelanden från **[!DNL Journey Optimizer]**.

Så här skapar du en meddelandeförinställning:

1. Öppna **[!UICONTROL Channels]** > **[!UICONTROL Branding]** > **[!UICONTROL Message presets]** menyn och klicka sedan på **[!UICONTROL Create Message preset]**.

   ![](assets/preset-create.png)

1. Ange ett namn och en beskrivning (valfritt) för förinställningen och välj sedan SMS-kanalen.

   ![](assets/sms_preset.png)

   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt`.` och bindestreck `-` tecken.

1. Konfigurera **SMS** inställningar.

   ![](assets/preset-sms.png)

   * Välj **[!UICONTROL SMS Type]** som skickas med förinställningen: **[!UICONTROL Transactional]** eller **[!UICONTROL Marketing]**.

   * Välj **[!UICONTROL SMS configuration]** för att associera med förinställningen.

      Mer information om hur du konfigurerar miljön för att skicka SMS-meddelanden finns i [det här avsnittet](sms-configuration.md).

   * Ange **[!UICONTROL Sender number]** &#x200B; som du vill använda för din kommunikation.

   * Välj **[!UICONTROL SMS Execution Field]** för att välja **[!UICONTROL Profile attribute]** som är kopplade till profilens telefonnummer.

1. När alla parametrar har konfigurerats klickar du på **[!UICONTROL Submit]** för att bekräfta. Du kan också spara meddelandeförinställningen som utkast och återuppta konfigurationen senare.

   ![](assets/sms_preset_2.png)

1. När meddelandeförinställningen har skapats visas den i listan med **[!UICONTROL Processing]** status.

   >[!NOTE]
   >
   >Om kontrollerna inte lyckas kan du läsa mer om orsakerna till eventuella fel i [det här avsnittet](#monitor-message-presets).

1. När kontrollen är klar får meddelandeförinställningen **[!UICONTROL Active]** status. Den är klar att användas för att leverera meddelanden.

   ![](assets/preset-active.png)

Du kan nu skicka SMS-meddelanden med Journey Optimizer.

**Relaterade ämnen**

* [Skapa ett SMS-meddelande](../messages/create-sms.md)
* [Lägg till ett meddelande i en resa](../building-journeys/journeys-message.md)
