---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera Twilio-provider
description: Lär dig hur du konfigurerar miljön för att skicka textmeddelanden med Journey Optimizer med Twilio
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: d6f74566-c913-4727-83b9-473a798a0158
source-git-commit: b9208544b08b474db386cce3d4fab0a4429a5f54
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 3%

---

# Konfigurera Twilio-provider {#sms-configuration-twilio}

Om du vill konfigurera Twilio med Journey Optimizer måste du skapa nya API-autentiseringsuppgifter som används för Twilio:

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** `>` **[!UICONTROL SMS Settings]** och väljer menyn **[!UICONTROL API Credentials]**. Klicka på knappen **[!UICONTROL Create new API credentials]**.

1. Konfigurera dina SMS API-autentiseringsuppgifter enligt nedanstående:

   * **[!UICONTROL SMS vendor]**: Twilio.

   * **[!UICONTROL Name]**: välj ett namn för API-autentiseringsuppgifterna.

   * **[!UICONTROL Account SID]** och **[!UICONTROL Auth Token]**: gå till rutan **Kontoinformation** på Twilio Console Dashboard-sidan för att hitta dina autentiseringsuppgifter.

   * **[!UICONTROL Message SID]**: Ange den unika identifierare som tilldelats alla meddelanden som skapats av Twilios API. Läs mer i [Twilio-dokumentation](https://support.twilio.com/hc/en-us/articles/223134387-What-is-a-Message-SID-){target="_blank"}.

   * **[!UICONTROL Inbound Number]**: lägg till ditt unika inkommande nummer. På så sätt kan du använda samma API-autentiseringsuppgifter för olika sandlådor, var och en med ett eget inkommande nummer.

1. Klicka på **[!UICONTROL Submit]** när du är klar med konfigurationen av dina API-autentiseringsuppgifter.

När du har skapat och konfigurerat API-autentiseringsuppgifterna måste du nu skapa en kanalkonfiguration för SMS- och MMS-meddelanden. [Läs mer](sms-configuration-surface.md)
