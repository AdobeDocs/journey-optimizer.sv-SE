---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera SMS-ytan
description: Lär dig hur du konfigurerar din SMS/MMS-yta för att skicka textmeddelanden med Journey Optimizer
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: 0d541520-016e-468f-b011-808712847556
source-git-commit: 080928d14a9d6ec116286386748b77a6a25e76f8
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 0%

---

# Skapa en SMS/MMS-yta {#message-preset-sms}

>[!CONTEXTUALHELP]
>id="ajo_admin_surface_sms_type"
>title="Definiera meddelandekategorin"
>abstract="Välj typ av textmeddelanden med den här ytan: Marknadsföring för marknadsföringsmeddelanden som kräver användarens samtycke eller Transaktionsmeddelanden för icke-kommersiella meddelanden, till exempel lösenordsåterställning."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/privacy/consent/opt-out.html#sms-opt-out-management" text="Avanmäl dig i marknadsföringstextmeddelanden"

När din SMS/MMS-kanal har konfigurerats måste du skapa en kanal för att kunna skicka SMS- och MMS-meddelanden från **[!DNL Journey Optimizer]**.

Så här skapar du en kanalyta:

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** och väljer **[!UICONTROL Branding]** > **[!UICONTROL Channel surfaces]**. Klicka på knappen **[!UICONTROL Create channel surface]**.

   ![](assets/preset-create.png)

1. Ange ett namn och en beskrivning (valfritt) för ytan och välj sedan SMS-kanalen.

   ![](assets/sms-create-surface.png)

   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt `.` och bindestreck `-`.

1. Definiera **SMS-inställningarna**.

   ![](assets/sms-surface-settings.png)

   Börja med att markera **[!UICONTROL SMS Type]** som ska skickas med ytan: **[!UICONTROL Transactional]** eller **[!UICONTROL Marketing]**.

   * Välj **Marknadsföring** för kampanjtextmeddelanden: dessa meddelanden kräver användarens samtycke.
   * Välj **Transaktionell** för icke-kommersiella meddelanden, till exempel orderbekräftelse, meddelanden om lösenordsåterställning eller leveransinformation.

   När du skapar ett SMS/MMS måste du välja en giltig kanalyta som matchar den kategori som du valde för meddelandet.

   >[!CAUTION]
   >
   >**Transaktionsmeddelanden** kan skickas till profiler som avbeställt marknadskommunikation. Dessa meddelanden kan bara skickas i särskilda sammanhang.

1. Markera **[!UICONTROL SMS configuration]** som ska associeras med ytan.

   Mer information om hur du konfigurerar miljön för att skicka SMS-meddelanden finns i [det här avsnittet](#create-api).

1. Ange den **[!UICONTROL Sender number]**-&#x200B; som du vill använda för kommunikationen.

1. Välj din **[!UICONTROL SMS Execution Field]** för att välja **[!UICONTROL Profile attribute]** som är associerad med profilens telefonnummer.

1. Om du vill använda förkortningsfunktionen för URL i dina SMS-meddelanden väljer du ett objekt i listan **[!UICONTROL Subdomain]**.

   >[!NOTE]
   >
   >Om du vill kunna välja en underdomän kontrollerar du att du tidigare har konfigurerat minst en SMS/MMS-underdomän. [Lär dig hur](sms-subdomains.md)

1. När alla parametrar har konfigurerats klickar du på **[!UICONTROL Submit]** för att bekräfta. Du kan också spara kanalytan som ett utkast och återuppta konfigurationen senare.

   ![](assets/sms-submit-surface.png)

1. När kanalytan har skapats visas den i listan med statusen **[!UICONTROL Processing]**.

   >[!NOTE]
   >
   >Om kontrollerna inte lyckas kan du läsa mer om möjliga felorsaker i [det här avsnittet](#monitor-channel-surfaces).

1. När kontrollerna har slutförts får kanalytan statusen **[!UICONTROL Active]**. Den är klar att användas för att leverera meddelanden.

   ![](assets/preset-active.png)

Nu kan du skicka textmeddelanden med Journey Optimizer.
