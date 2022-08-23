---
title: SMS-konfiguration
description: Lär dig hur du konfigurerar miljön för att skicka SMS-meddelanden med Journey Optimizer
role: Admin
level: Intermediate
exl-id: 4dcd22ed-bf7e-4789-ab7b-33544c857db8
source-git-commit: f44638ac7cfb078b6914635433feedb0f48ef099
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# Konfigurera SMS-kanal {#sms-configuration}

[!DNL Journey Optimizer] kan ni skapa resor och skicka meddelanden till riktade målgrupper.

Konfigurera instansen innan du skickar SMS. Du måste [integrera providerinställningarna](#create-api) med Journey Optimizer och [skapa en SMS-yta](#message-preset-sms) (t.ex. SMS-förinställning). Dessa steg måste utföras av en [Adobe Journey Optimizer systemadministratör](../start/path/administrator.md).

>[!AVAILABILITY]
>
>SMS-kanalen är för närvarande bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant om du vill ha mer information.

## Skapa nya API-autentiseringsuppgifter {#create-api}

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api"
>title="Konfigurera SMS-leverantören"
>abstract="Välj leverantör och fyll i dina SMS API-autentiseringsuppgifter."

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

När du har skapat och konfigurerat API-autentiseringsuppgifterna måste du nu skapa en kanalyta (t.ex. meddelandeförinställning) för SMS-meddelanden.

## Skapa en kanalyta för SMS-meddelanden {#message-preset-sms}

>[!CONTEXTUALHELP]
>id="ajo_admin_surface_sms_type"
>title="Definiera SMS-kategorin"
>abstract="Välj den typ av SMS-meddelanden som ska skickas när den här ytan används: Marknadsföring för SMS-kampanjmeddelanden, som kräver användarens samtycke, eller Transactional för icke-kommersiella SMS-meddelanden, som också kan skickas till avabonnerade profiler i specifika sammanhang."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/messages/create-sms.html#sms-opt-in-out" text="Avanmäl dig i SMS-marknadsföringsmeddelanden"

När SMS-kanalen har konfigurerats måste du skapa en kanalyta för att kunna skicka SMS-meddelanden från **[!DNL Journey Optimizer]**.

Så här skapar du en kanalyta:

1. Öppna **[!UICONTROL Channels]** > **[!UICONTROL Branding]** > **[!UICONTROL Channel surfaces]** menyn och klicka sedan på **[!UICONTROL Create channel surface]**.

   ![](assets/preset-create.png)

1. Ange ett namn och en beskrivning (valfritt) för ytan och välj sedan SMS-kanalen.

   ![](assets/sms_preset.png)

   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt`.` och bindestreck `-` tecken.

1. Konfigurera **SMS** inställningar.

   ![](assets/preset-sms.png)

   * Välj **[!UICONTROL SMS Type]** som ska skickas med ytan: **[!UICONTROL Transactional]** eller **[!UICONTROL Marketing]**.

   * Välj **[!UICONTROL SMS configuration]** för att associera med ytan.

      Mer information om hur du konfigurerar miljön för att skicka SMS-meddelanden finns i [det här avsnittet](#create-api).

   * Ange **[!UICONTROL Sender number]** &#x200B; som du vill använda för din kommunikation.

   * Välj **[!UICONTROL SMS Execution Field]** för att välja **[!UICONTROL Profile attribute]** som är kopplade till profilens telefonnummer.

1. När alla parametrar har konfigurerats klickar du på **[!UICONTROL Submit]** för att bekräfta. Du kan också spara kanalytan som ett utkast och återuppta konfigurationen senare.

   ![](assets/sms_preset_2.png)

1. När kanalytan har skapats visas den i listan med **[!UICONTROL Processing]** status.

   >[!NOTE]
   >
   >Om kontrollerna inte lyckas kan du läsa mer om orsakerna till eventuella fel i [det här avsnittet](#monitor-channel-surfaces).

1. När kontrollerna är klara får kanalytan **[!UICONTROL Active]** status. Den är klar att användas för att leverera meddelanden.

   ![](assets/preset-active.png)

Du kan nu skicka SMS-meddelanden med Journey Optimizer.

**Relaterade ämnen**

* [Skapa ett SMS-meddelande](../messages/create-sms.md)
* [Lägg till ett meddelande i en resa](../building-journeys/journeys-message.md)
