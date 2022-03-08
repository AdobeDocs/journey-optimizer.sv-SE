---
title: SMS-konfiguration
description: Lär dig hur du konfigurerar miljön för att skicka SMS-meddelanden med Journey Optimizer
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
exl-id: 4dcd22ed-bf7e-4789-ab7b-33544c857db8
source-git-commit: 68407db81224e9c2b6930c800e57b65e081781fe
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 1%

---

# Konfigurera SMS-kanal {#sms-configuration}

>[!CAUTION]
>
> SMS-kanalen är för närvarande tillgänglig i ett tidigt skede och endast för utvalda användare. Om du vill använda den här funktionen kontaktar du din kontoansvarige på Adobe.

[!DNL Journey Optimizer] kan ni skapa resor och skicka meddelanden till riktade målgrupper.

## Skapa nya API-autentiseringsuppgifter {#create-api}

Så här konfigurerar du din SMS-leverantör med Journey Optimizer:

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL API Credentials]** menyn och klicka sedan på **[!UICONTROL Create API credential]**.

   ![](../assets/sms_4.png)

1. Välj Sinch som **[!UICONTROL SMS vendor]**.

1. Ange **[!UICONTROL Name]** för dina API-autentiseringsuppgifter.

1. Ange **[!UICONTROL Service ID]** och **[!UICONTROL API Token]**.

   >[!NOTE]
   >
   > Sinch kräver speciella API-autentiseringsuppgifter. För att hitta **[!UICONTROL Service ID]** och **[!UICONTROL API Token]**, gå till SMS > API:er-menyn från ditt Sinch-konto,

   ![](../assets/sms_5.png)

1. Klicka **[!UICONTROL Submit]** när du är klar med konfigurationen av dina API-autentiseringsuppgifter.

När du har skapat och konfigurerat dina API-autentiseringsuppgifter måste du nu skapa en meddelandeförinställning för SMS-meddelanden.

## Skapa en meddelandeförinställning för SMS-meddelanden {#message-preset-sms}

När SMS-kanalen har konfigurerats måste du skapa en meddelandeförinställning för att kunna skicka SMS-meddelanden från **[!DNL Journey Optimizer]**.

Så här skapar du en meddelandeförinställning:

1. Öppna **[!UICONTROL Channels]** > **[!UICONTROL Branding]** > **[!UICONTROL Message presets]** menyn och klicka sedan på **[!UICONTROL Create Message preset]**.

   ![](../assets/preset-create.png)

1. Ange ett namn och en beskrivning (valfritt) för förinställningen och välj sedan SMS-kanalen.

   ![](../assets/sms_preset.png)

   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt`.` och bindestreck `-` tecken.

1. Konfigurera **SMS** inställningar.

   ![](../assets/preset-sms.png)

   * Välj **[!UICONTROL SMS Type]** som skickas med förinställningen: **[!UICONTROL Transactional]** eller **[!UICONTROL Marketing]**.

   * Välj **[!UICONTROL SMS configuration]** för att associera med förinställningen.

      Mer information om hur du konfigurerar miljön för att skicka SMS-meddelanden finns i [det här avsnittet](sms-configuration.md).

   * Ange **[!UICONTROL Sender number]** &#x200B; som du vill använda för din kommunikation.

1. När alla parametrar har konfigurerats klickar du på **[!UICONTROL Submit]** för att bekräfta. Du kan också spara meddelandeförinställningen som utkast och återuppta konfigurationen senare.

   ![](../assets/sms_preset_2.png)

1. När meddelandeförinställningen har skapats visas den i listan med **[!UICONTROL Processing]** status.

   >[!NOTE]
   >
   >Om kontrollerna inte lyckas kan du läsa mer om orsakerna till eventuella fel i [det här avsnittet](#monitor-message-presets).

1. När kontrollen är klar får meddelandeförinställningen **[!UICONTROL Active]** status. Den är klar att användas för att leverera meddelanden.

   ![](../assets/preset-active.png)

Du kan nu skicka SMS-meddelanden med Journey Optimizer.

**Relaterade ämnen**

* [Skapa ett SMS-meddelande](../messages/create-sms.md)
* [Lägg till ett meddelande i en resa](../building-journeys/journeys-message.md)
