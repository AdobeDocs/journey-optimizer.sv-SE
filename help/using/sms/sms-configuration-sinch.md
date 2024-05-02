---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera Sinch-provider
description: Lär dig hur du konfigurerar miljön för att skicka textmeddelanden med Journey Optimizer med Sinch
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
source-git-commit: 0571a11eabffeb5e318bebe341a8df18da7db598
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 2%

---

# Konfigurera Sinch-provider {#sms-configuration-sinch}

När du använder Sinch-providern med Journey Optimizer finns det två olika alternativ:

* **SMS-konfiguration**: Konfigurera dina autentiseringsuppgifter för Sinch API för att skicka SMS-meddelanden sömlöst.

* **MMS-konfiguration**: För MMS (multimedia messaging) konfigurerar du dina Single MMS API-autentiseringsuppgifter. Observera att spårning och svar på inkommande meddelanden hanteras av SMS-konfigurationen. MMS-konfigurationen är endast avsedd för utgående leverans av MMS-meddelandet.

## Referenser för Sinch API{#create-api}

Så här konfigurerar du din Sinch-leverantör för att skicka SMS-meddelanden och MMS med Journey Optimizer:

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** och väljer **[!UICONTROL API Credentials]** -menyn. Klicka på knappen **[!UICONTROL Create new API credentials]**.

   ![](assets/sms_6.png)

1. Konfigurera dina SMS API-autentiseringsuppgifter enligt nedanstående:

   * **[!UICONTROL Name]**: välj ett namn för API-autentiseringsuppgifterna.

   * **[!UICONTROL Service ID]** och **[!UICONTROL API Token]**: du kommer åt API:erna på fliken SMS. Läs mer i [Sänk dokumentation](https://developers.sinch.com/docs/sms/getting-started/){target="_blank"}.

   * **[!UICONTROL Opt-In Keywords]**: ange standardnyckelord eller egna nyckelord som automatiskt kommer att aktivera **[!UICONTROL Opt-In Message]**. Använd kommaseparerade värden för flera nyckelord.

   * **[!UICONTROL Opt-In Message]**: ange det anpassade svar som automatiskt skickas som **[!UICONTROL Opt-In Message]**.

   * **[!UICONTROL Opt-Out Keywords]**: ange standardnyckelord eller egna nyckelord som automatiskt kommer att aktivera **[!UICONTROL Opt-Out Message]**. Använd kommaseparerade värden för flera nyckelord.

   * **[!UICONTROL Opt-Out Message]**: ange det anpassade svar som automatiskt skickas som **[!UICONTROL Opt-Out Message]**.

   * **[!UICONTROL Help Keywords]**: ange standardnyckelord eller egna nyckelord som automatiskt kommer att aktivera **Hjälpmeddelande**. Använd kommaseparerade värden för flera nyckelord.

   * **[!UICONTROL Help Message]**: ange det anpassade svar som automatiskt skickas som **Hjälpmeddelande**.

   * **[!UICONTROL Double Opt-In Keywords]**: anger de nyckelord som utlöser processen för dubbel anmälan. Om en användarprofil inte finns skapas den när den har bekräftats. Använd kommaseparerade värden för flera nyckelord. [Läs mer om SMS Double Opt-in](https://video.tv.adobe.com/v/3427129/?learn=on).

   * **[!UICONTROL Double Opt-In Message]**: ange det anpassade svar som automatiskt skickas som svar på bekräftelsen av dubbel anmälan.

1. Klicka **[!UICONTROL Submit]** när du är klar med konfigurationen av dina API-autentiseringsuppgifter.

När du har skapat och konfigurerat API-autentiseringsuppgifterna måste du nu skapa en kanal för SMS-meddelanden. [Läs mer](sms-configuration-surface.md)

## Inaktivera MMS API-autentiseringsuppgifter {#sinch-mms}

>[!IMPORTANT]
>
> Förutom MMS-konfigurationen måste du också skapa autentiseringsuppgifter för Sinch API specifikt för att spåra inkommande meddelanden och hantera begäranden om samtycke.

Så här konfigurerar du Sinch MMS att skicka MMS med Journey Optimizer:

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** och väljer **[!UICONTROL API Credentials]** -menyn. Klicka på knappen **[!UICONTROL Create new API credentials]**.

   ![](assets/sms_6.png)

1. Konfigurera dina SMS API-autentiseringsuppgifter enligt nedanstående:

   * **[!UICONTROL Name]**: välj ett namn för API-autentiseringsuppgifterna.

   * **[!UICONTROL Project ID]**, **[!UICONTROL App ID]** och **[!UICONTROL API Token]**: på konversations-API-menyn hittar du dina inloggningsuppgifter på App-menyn. Läs mer i [Sänk dokumentation](https://docs.cc.sinch.com/cloud/service-configuration/en/oxy_ex-1/common/wln1620131604643.html){target="_blank"}.

   * **[!UICONTROL Service Plan ID]** och **[!UICONTROL SMS API Token]**: din **[!UICONTROL Service Plan ID]** och **[!UICONTROL SMS API Token]** finns på fliken SMS på API-sidan.

1. Klicka **[!UICONTROL Submit]** när du är klar med konfigurationen av dina API-autentiseringsuppgifter.

När du har skapat och konfigurerat API-autentiseringsuppgifterna måste du nu skapa en kanalyta för MMS-meddelanden. [Läs mer](sms-configuration-surface.md)
