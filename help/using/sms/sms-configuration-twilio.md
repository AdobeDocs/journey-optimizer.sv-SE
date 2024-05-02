---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera Twilio-provider
description: Lär dig hur du konfigurerar miljön för att skicka textmeddelanden med Journey Optimizer med Twilio
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
source-git-commit: 0571a11eabffeb5e318bebe341a8df18da7db598
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 3%

---

# Konfigurera Twilio-provider {#sms-configuration-twilio}

Om du vill konfigurera Twilio med Journey Optimizer måste du skapa nya API-autentiseringsuppgifter som används för Twilio:

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** och väljer **[!UICONTROL API Credentials]** -menyn. Klicka på knappen **[!UICONTROL Create new API credentials]**.

   ![](assets/sms_6.png)

1. Konfigurera dina SMS API-autentiseringsuppgifter enligt nedanstående:

   * **[!UICONTROL Name]**: välj ett namn för API-autentiseringsuppgifterna.

   * **[!UICONTROL Account SID]** och **[!UICONTROL Auth Token]**: åtkomst till **Kontoinformation** på Twilio Console Dashboard-sidan där du hittar dina inloggningsuppgifter.

   * **[!UICONTROL Message SID]**: Ange den unika identifierare som tilldelats alla meddelanden som skapas av Twilios API. Läs mer i [Twilio-dokumentation](https://support.twilio.com/hc/en-us/articles/223134387-What-is-a-Message-SID-){target="_blank"}.

1. Klicka **[!UICONTROL Submit]** när du är klar med konfigurationen av dina API-autentiseringsuppgifter.

När du har skapat och konfigurerat API-autentiseringsuppgifterna måste du nu skapa en kanal för SMS- och MMS-meddelanden. [Läs mer](sms-configuration-surface.md)

