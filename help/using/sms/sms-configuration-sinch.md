---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera Sinch-provider
description: Lär dig hur du konfigurerar miljön för att skicka textmeddelanden med Journey Optimizer med Sinch
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: 85412a85-edf0-4069-8bc7-b80371375f1f
source-git-commit: 794ac45177e467be4bd5b8f7288e07c85e4d806a
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 1%

---

# Konfigurera Sinch-provider {#sms-configuration-sinch}

När du använder Sinch-providern med Journey Optimizer finns det två olika alternativ:

* **SMS-konfiguration**: Konfigurera dina Single API-autentiseringsuppgifter för att skicka SMS-meddelanden sömlöst.

* **MMS-konfiguration**: Konfigurera dina Single MMS API-autentiseringsuppgifter för multimediemeddelanden (MMS). Observera att spårning och svar på inkommande meddelanden hanteras av SMS-konfigurationen. MMS-konfigurationen är endast avsedd för utgående leverans av MMS-meddelandet.

## Referenser för Sinch API{#create-api}

Så här konfigurerar du din Sinch-leverantör för att skicka SMS-meddelanden och MMS med Journey Optimizer:

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** och väljer menyn **[!UICONTROL API Credentials]**. Klicka på knappen **[!UICONTROL Create new API credentials]**.

1. Konfigurera dina SMS API-autentiseringsuppgifter enligt nedanstående:

   * **[!UICONTROL SMS vendor]**: Dra.

   * **[!UICONTROL Name]**: välj ett namn för API-autentiseringsuppgifterna.

   * **[!UICONTROL Service ID]** och **[!UICONTROL API Token]**: gå till API:er-sidan och hitta dina autentiseringsuppgifter på fliken SMS. Läs mer i [Signera dokumentation](https://developers.sinch.com/docs/sms/getting-started/){target="_blank"}.

   * **[!UICONTROL Opt-In Keywords]**: ange standardnyckelord eller anpassade nyckelord som automatiskt kommer att utlösa **[!UICONTROL Opt-In Message]**. Använd kommaseparerade värden för flera nyckelord.

   * **[!UICONTROL Opt-In Message]**: Ange det anpassade svar som automatiskt skickas som **[!UICONTROL Opt-In Message]**.

   * **[!UICONTROL Opt-Out Keywords]**: ange standardnyckelord eller anpassade nyckelord som automatiskt kommer att utlösa **[!UICONTROL Opt-Out Message]**. Använd kommaseparerade värden för flera nyckelord.

   * **[!UICONTROL Opt-Out Message]**: Ange det anpassade svar som automatiskt skickas som **[!UICONTROL Opt-Out Message]**.

   * **[!UICONTROL Help Keywords]**: ange standardnyckelord eller anpassade nyckelord som automatiskt kommer att utlösa ditt **hjälpmeddelande**. Använd kommaseparerade värden för flera nyckelord.

   * **[!UICONTROL Help Message]**: ange det anpassade svar som automatiskt skickas som **hjälpmeddelande**.

   * **[!UICONTROL Double Opt-In Keywords]**: ange nyckelorden som utlöser processen för dubbel anmälan. Om en användarprofil inte finns skapas den när den har bekräftats. Använd kommaseparerade värden för flera nyckelord. [Läs mer om SMS-dubbelanmälan](https://video.tv.adobe.com/v/3427129/?learn=on).

   * **[!UICONTROL Double Opt-In Message]**: Ange det anpassade svar som skickas automatiskt som svar på bekräftelsen av dubbel anmälan.

   * **[!UICONTROL Inbound Number]**: lägg till ditt unika inkommande nummer. På så sätt kan du använda samma API-autentiseringsuppgifter för olika sandlådor, var och en med ett eget inkommande nummer.

1. Klicka på **[!UICONTROL Submit]** när du är klar med konfigurationen av dina API-autentiseringsuppgifter.

När du har skapat och konfigurerat API-autentiseringsuppgifterna måste du nu skapa en kanal för SMS-meddelanden. [Läs mer](sms-configuration-surface.md)

## Inaktivera MMS API-autentiseringsuppgifter {#sinch-mms}

>[!IMPORTANT]
>
> Förutom MMS-konfigurationen måste du också skapa autentiseringsuppgifter för Sinch API specifikt för att spåra inkommande meddelanden och hantera begäranden om samtycke.

Så här konfigurerar du Sinch MMS att skicka MMS med Journey Optimizer:

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** och väljer menyn **[!UICONTROL API Credentials]**. Klicka på knappen **[!UICONTROL Create new API credentials]**.

1. Konfigurera MMS API-autentiseringsuppgifterna enligt nedan:

   * **[!UICONTROL SMS vendor]**: Minska MMS.

   * **[!UICONTROL Name]**: välj ett namn för API-autentiseringsuppgifterna.

   * **[!UICONTROL Project ID]**, **[!UICONTROL App ID]** och **[!UICONTROL API Token]**: Följ stegen nedan för att samla in dina MMS API-autentiseringsuppgifter.

      * För **[!UICONTROL Project ID]** och **[!UICONTROL App ID]**: Gå till sidan [Översikt över konversation-API](https://dashboard.sinch.com/convapi/overview) i ditt Sinch-projekt på din Sinch-instrumentpanel.
      * För **[!UICONTROL API Token]**: Hämta [ Access-nycklarna ](https://community.sinch.com/t5/Customer-Dashboard/Sinch-Access-Keys/ta-p/12638) för ditt Sinch-projekt och generera en **Base64 API-token** från ditt Single Project **Access-nycklar**.

   * **[!UICONTROL Service Plan ID]** och **[!UICONTROL SMS API Token]**: din **[!UICONTROL Service Plan ID]** och **[!UICONTROL SMS API Token]** finns på fliken SMS på API:er-sidan.

1. Klicka på **[!UICONTROL Submit]** när du är klar med konfigurationen av dina API-autentiseringsuppgifter.

När du har skapat och konfigurerat API-autentiseringsuppgifterna måste du nu skapa en kanalyta för MMS-meddelanden. [Läs mer](sms-configuration-surface.md)
