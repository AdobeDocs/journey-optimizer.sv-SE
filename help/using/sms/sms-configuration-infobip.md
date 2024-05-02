---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera Infobip-provider
description: Lär dig hur du konfigurerar miljön för att skicka textmeddelanden och MMS med Journey Optimizer med Infobip
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
source-git-commit: 0571a11eabffeb5e318bebe341a8df18da7db598
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 1%

---

# Konfigurera Infobip-provider {#sms-configuration-infobip}

Så här konfigurerar du Infobip med Journey Optimizer:

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** `>` **[!UICONTROL Channels]** och väljer **[!UICONTROL API Credentials]** -menyn. Klicka på knappen **[!UICONTROL Create new API credentials]**.

   ![](assets/sms_6.png)

1. Konfigurera dina API-autentiseringsuppgifter enligt anvisningarna nedan.

   * **[!UICONTROL Name]**: välj ett namn för API-autentiseringsuppgifterna.

   * **[!UICONTROL API base URL]** och **[!UICONTROL API key]**: gå till webbgränssnittets hemsida eller API-nyckelhanteringssidan för att hitta dina autentiseringsuppgifter. Läs mer i [Infobip-dokumentation](https://www.infobip.com/docs/api){target="_blank"}.

   * **[!UICONTROL Opt-In Keywords]**: ange standardnyckelord eller egna nyckelord som automatiskt kommer att aktivera **[!UICONTROL Opt-In Message]**. Använd kommaseparerade värden för flera nyckelord.

   * **[!UICONTROL Opt-In Message]**: ange det anpassade svar som automatiskt skickas som **[!UICONTROL Opt-In Message]**.

   * **[!UICONTROL Opt-Out Keywords]**: ange standardvärdet eller nyckelorden som automatiskt kommer att aktivera **[!UICONTROL Opt-Out Message]**. Använd kommaseparerade värden för flera nyckelord.

   * **[!UICONTROL Opt-Out Message]**: ange det anpassade svar som automatiskt skickas som **[!UICONTROL Opt-Out Message]**.

   * **[!UICONTROL Help Keywords]**: ange standardnyckelord eller egna nyckelord som automatiskt kommer att aktivera **Hjälpmeddelande**. Använd kommaseparerade värden för flera nyckelord.

   * **[!UICONTROL Help Message]**: ange det anpassade svar som automatiskt skickas som **Hjälpmeddelande**.

   * **[!UICONTROL Double Opt-In Keywords]**: anger de nyckelord som utlöser processen för dubbel anmälan. Om en användarprofil inte finns skapas den när den har bekräftats. Använd kommaseparerade värden för flera nyckelord.

   * **[!UICONTROL Double Opt-In Message]**: Ange det anpassade svar som automatiskt skickas som svar på bekräftelsen av dubbel anmälan.

   * **[!UICONTROL Principal Entity ID]**: ange ditt tilldelade enhets-ID för DLT-huvudnamn.

   * **[!UICONTROL Content Template ID]**: ange ditt registrerade ID för DLT-innehållsmall.

   * **[!UICONTROL Validity Period]**: Ange meddelandets giltighetsperiod i timmar. Om det inte går att leverera meddelanden inom den här tidsramen gör systemet ytterligare försök att skicka dem igen. Standardgiltighetsperioden är inställd på 48 timmar.

   * **[!UICONTROL Callback Data]**: Ange ytterligare klientdata som ska skickas på Notify URL.

1. Klicka **[!UICONTROL Submit]** när du är klar med konfigurationen av dina API-autentiseringsuppgifter.

När du har skapat och konfigurerat API-autentiseringsuppgifterna måste du nu skapa en kanal för SMS- och MMS-meddelanden. [Läs mer](sms-configuration-surface.md)
