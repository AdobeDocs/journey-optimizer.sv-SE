---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera Sinch-provider
description: Lär dig hur du konfigurerar miljön för att skicka textmeddelanden med Journey Optimizer med Sinch
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: 85412a85-edf0-4069-8bc7-b80371375f1f
source-git-commit: 342b9210f79266cb11628dcdc411f90844a84e37
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 0%

---

# Konfigurera Sinch-provider {#sms-configuration-sinch}

När du använder Sinch-providern med Journey Optimizer finns det två olika alternativ:

* **SMS-konfiguration**: Konfigurera dina autentiseringsuppgifter för Sinch API för att skicka SMS-meddelanden sömlöst.

* **MMS-konfiguration**: För MMS (multimedia messaging) konfigurerar du dina Single MMS API-autentiseringsuppgifter. Observera att spårning och svar på inkommande meddelanden hanteras av SMS-konfigurationen. MMS-konfigurationen är endast avsedd för utgående leverans av MMS-meddelandet.

## Referenser för Sinch API{#create-api}

Så här konfigurerar du din Sinch-leverantör för att skicka SMS-meddelanden och MMS med Journey Optimizer:

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** och väljer **[!UICONTROL API Credentials]** -menyn. Klicka på **[!UICONTROL Create new API credentials]** -knappen.

1. Konfigurera dina SMS API-autentiseringsuppgifter enligt nedanstående:

   * **[!UICONTROL SMS vendor]**: Sinch.

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

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** och väljer **[!UICONTROL API Credentials]** -menyn. Klicka på **[!UICONTROL Create new API credentials]** -knappen.

1. Konfigurera MMS API-autentiseringsuppgifterna enligt nedan:

   * **[!UICONTROL SMS vendor]**: Sinch MMS.

   * **[!UICONTROL Name]**: välj ett namn för API-autentiseringsuppgifterna.

   * **[!UICONTROL Project ID]**, **[!UICONTROL App ID]** och **[!UICONTROL API Token]**: följ stegen nedan för att samla in dina MMS API-autentiseringsuppgifter.

      * För **[!UICONTROL Project ID]** och **[!UICONTROL App ID]**: Använd [Översikt över konversation-API](https://dashboard.sinch.com/convapi/overview) sidan i ditt Sinch-projekt på din Sinch Dashboard.
      * För **[!UICONTROL API Token]**: Hämta [Åtkomstnycklar](https://community.sinch.com/t5/Customer-Dashboard/Sinch-Access-Keys/ta-p/12638) för ditt Sinch-projekt och generera en **Base64 API-token** från ditt Sinch-projekt **Åtkomstnycklar**.

   * **[!UICONTROL Service Plan ID]** och **[!UICONTROL SMS API Token]**: din **[!UICONTROL Service Plan ID]** och **[!UICONTROL SMS API Token]** finns på fliken SMS på API-sidan.

1. Klicka **[!UICONTROL Submit]** när du är klar med konfigurationen av dina API-autentiseringsuppgifter.

När du har skapat och konfigurerat API-autentiseringsuppgifterna måste du nu skapa en kanalyta för MMS-meddelanden. [Läs mer](sms-configuration-surface.md)
