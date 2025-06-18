---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera SMS-konfigurationen
description: Lär dig hur du konfigurerar din SMS/MMS-konfiguration för att skicka textmeddelanden med Journey Optimizer
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: 0d541520-016e-468f-b011-808712847556
source-git-commit: 25b1e6050e0cec3ae166532f47626d99ed68fe80
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 0%

---

# Skapa en SMS/MMS/RCS-konfiguration {#message-preset-sms}

>[!CONTEXTUALHELP]
>id="ajo_admin_surface_sms_type"
>title="Definiera meddelandekategorin"
>abstract="Välj typ av textmeddelanden med den här konfigurationen: Marknadsföring för kampanjmeddelanden som kräver användarens samtycke eller Transaktionsmeddelanden för icke-kommersiella meddelanden, till exempel lösenordsåterställning."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/privacy/consent/opt-out.html?lang=sv-SE#sms-opt-out-management" text="Avanmäl dig i marknadsföringstextmeddelanden"

När din SMS/MMS/RCS-kanal har konfigurerats måste du skapa en kanalkonfiguration för att kunna skicka SMS-, RCS- och MMS-meddelanden från **[!DNL Journey Optimizer]**.

Så här skapar du en kanalkonfiguration:

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** och väljer **[!UICONTROL General settings]** > **[!UICONTROL Channel configurations]**. Klicka på knappen **[!UICONTROL Create channel configuration]**.

   ![](assets/preset-create.png)

1. Ange ett namn och en beskrivning (valfritt) för konfigurationen och välj sedan SMS-kanalen.

   ![](assets/sms-create-surface.png)

   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt `.` och bindestreck `-`.

1. Definiera **SMS-inställningarna**.

   ![](assets/sms-surface-settings.png)

   Börja med att markera **[!UICONTROL SMS Type]** som ska skickas med konfigurationen: **[!UICONTROL Transactional]** eller **[!UICONTROL Marketing]**.

   * Välj **Marknadsföring** för kampanjtextmeddelanden: dessa meddelanden kräver användarens samtycke.
   * Välj **Transaktionell** för icke-kommersiella meddelanden, till exempel orderbekräftelse, meddelanden om lösenordsåterställning eller leveransinformation.

   När du skapar ett SMS/MMS måste du välja en giltig kanalkonfiguration som matchar den kategori som du valde för meddelandet.

   >[!CAUTION]
   >
   >**Transaktionsmeddelanden** kan skickas till profiler som avbeställt marknadskommunikation. Dessa meddelanden kan bara skickas i särskilda sammanhang.

1. Markera **[!UICONTROL SMS configuration]** som ska associeras med konfigurationen.

   Mer information om hur du konfigurerar miljön för att skicka SMS-meddelanden finns i [det här avsnittet](#create-api).

1. Ange den **[!UICONTROL Sender number]**-&#x200B; som du vill använda för kommunikationen.

1. Välj din **[!UICONTROL SMS Execution Field]** för att välja **[!UICONTROL Profile attribute]** som är associerad med profilens telefonnummer.

1. Om du vill använda förkortningsfunktionen för URL i dina SMS-meddelanden väljer du ett objekt i listan **[!UICONTROL Subdomain]**.

   >[!NOTE]
   >
   >Om du vill kunna välja en underdomän kontrollerar du att du tidigare har konfigurerat minst en SMS/MMS-underdomän. [Lär dig hur](sms-subdomains.md)

1. När alla parametrar har konfigurerats klickar du på **[!UICONTROL Submit]** för att bekräfta. Du kan också spara kanalkonfigurationen som utkast och återuppta konfigurationen senare.

   ![](assets/sms-submit-surface.png)

1. När kanalkonfigurationen har skapats visas den i listan med statusen **[!UICONTROL Processing]**.

   >[!NOTE]
   >
   >Om kontrollerna inte lyckas kan du läsa mer om möjliga felorsaker i [det här avsnittet](../configuration/channel-surfaces.md).

1. När kontrollerna har slutförts får kanalkonfigurationen statusen **[!UICONTROL Active]**. Den är klar att användas för att leverera meddelanden.

   ![](assets/preset-active.png)

Nu kan du skicka textmeddelanden med Journey Optimizer.
