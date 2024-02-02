---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera SMS-kanalen
description: Lär dig hur du konfigurerar miljön för att skicka textmeddelanden med Journey Optimizer
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: 4dcd22ed-bf7e-4789-ab7b-33544c857db8
source-git-commit: 3fe533c9a1c2cd83d813d26288a2f1f63f84b2ad
workflow-type: tm+mt
source-wordcount: '1177'
ht-degree: 1%

---

# Konfigurera SMS-kanal {#sms-configuration}

Innan du skickar SMS eller MMS måste du konfigurera Adobe Journey Optimizer-miljön. Så här utför du det:

* [Integrera providerinställningarna](#create-api) med Journey Optimizer
* [Skapa en SMS-yta](#message-preset-sms) (t.ex. SMS-förinställning), används även för MMS

Dessa steg måste utföras av en Adobe Journey Optimizer [Systemadministratör](../start/path/administrator.md).

## Förutsättningar{#sms-prerequisites}

Adobe Journey Optimizer är för närvarande integrerat med tredjepartsleverantörer som erbjuder textmeddelandetjänster oberoende av Adobe Journey Optimizer. Leverantörer som stöds för textmeddelanden är: **Sinch**, **Twilio** och **Infobip**. MMS stöds endast med **Sinch**.

Innan du konfigurerar SMS-kanalen måste du skapa ett konto hos någon av dessa leverantörer för att få tillgång till **API-token** och **Tjänst-ID**, som du måste konfigurera anslutningen mellan Adobe Journey Optimizer och den tillämpliga leverantören.

Din användning av SMS-tjänster regleras av ytterligare villkor från tillämplig leverantör. Som tredjepartslösningar är Sinch, Twilio och Infobip tillgängliga för Adobe Journey Optimizer-användare via integrering. Adobe kontrollerar inte, och ansvarar inte för, tredjepartsprodukter. Kontakta din leverantör om du har problem eller vill ha hjälp med SMS/MMS.

>[!CAUTION]
>
>Om du vill komma åt och redigera SMS-underdomäner måste du ha **[!UICONTROL Manage SMS Subdomains]** behörighet i produktionssandlådan. Läs mer om behörigheter i [den här sidan](../administration/high-low-permissions.md#administration-permissions).
>

## Skapa nya API-autentiseringsuppgifter {#create-api}

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api_header"
>title="Konfigurera din SMS-leverantör med Journey Optimizer"
>abstract="Adobe Journey Optimizer skickar textmeddelanden via SMS-tjänstleverantörer. Välj leverantör och fyll i dina API-autentiseringsuppgifter."

>[!CONTEXTUALHELP]
>id="ajo_admin_mms_api_header"
>title="Konfigurera MMS-providern med Journey Optimizer"
>abstract="Adobe Journey Optimizer skickar mediematerial via MMS-tjänsteleverantörer. Välj leverantör och fyll i dina API-autentiseringsuppgifter."

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api"
>title="Konfigurera din SMS/MMS-leverantör med Journey Optimizer"
>abstract="Innan du skickar textmeddelanden (SMS/MMS) måste du integrera providerinställningarna med Journey Optimizer. När du är klar måste du skapa en SMS/MMS-yta. Dessa steg måste utföras av en Adobe Journey Optimizer-systemadministratör."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/sms/sms-configuration.html#message-preset-sms" text="Skapa en SMS-kanalyta"

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_configuration"
>title="Välj SMS-leverantörskonfiguration"
>abstract="Välj API-autentiseringsuppgifter som konfigurerats för din SMS-leverantör."

Så här konfigurerar du din SMS/MMS-leverantör med Journey Optimizer:

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** och väljer **[!UICONTROL API Credentials]** -menyn. Klicka på knappen **[!UICONTROL Create new API credentials]**.

   ![](assets/sms_6.png)

1. Konfigurera dina SMS API-autentiseringsuppgifter enligt instruktionerna nedan.

   ![](assets/sms_7.png)

   * +++ För **[!DNL Sinch]**

      * **[!UICONTROL Name]**: välj ett namn för API-autentiseringsuppgifterna.

      * **[!UICONTROL Service ID]** och **[!UICONTROL API Token]**: du kommer åt API:erna på fliken SMS. Läs mer i [Sänk dokumentation](https://developers.sinch.com/docs/sms/getting-started/){target="_blank"}.

      * **[!UICONTROL Opt-In Message]**: ange det anpassade svar som automatiskt skickas som **[!UICONTROL Opt-In Message]**.

      * **[!UICONTROL Opt-Out Message]**: ange det anpassade svar som automatiskt skickas som **[!UICONTROL Opt-Out Message]**.

      * **[!UICONTROL Help Message]**: ange det anpassade svar som automatiskt skickas som **Hjälpmeddelande**.

      * **[!UICONTROL Double Opt-In Keywords]**: anger de nyckelord som utlöser processen för dubbel anmälan. Om en användarprofil inte finns skapas den när den har bekräftats. Använd kommaseparerade värden för flera nyckelord. [Läs mer om SMS Double Opt-in](https://video.tv.adobe.com/v/3427129/?learn=on).

      * **[!UICONTROL Double Opt-In Message]**: ange det anpassade svar som automatiskt skickas som svar på bekräftelsen av dubbel anmälan.
+++

   * +++ För **[!DNL Sinch MMS]**

      * **[!UICONTROL Name]**: välj ett namn för API-autentiseringsuppgifterna.

      * **[!UICONTROL Project ID]**, **[!UICONTROL App ID]** och **[!UICONTROL API Token]**: på konversations-API-menyn hittar du dina inloggningsuppgifter på App-menyn. Läs mer i [Sänk dokumentation](https://docs.cc.sinch.com/cloud/service-configuration/en/oxy_ex-1/common/wln1620131604643.html){target="_blank"}.

+++

   * +++ För **[!DNL Twilio]**

      * **[!UICONTROL Name]**: välj ett namn för API-autentiseringsuppgifterna.

      * **[!UICONTROL Account SID]** och **[!UICONTROL Auth Token]**: gå till rutan Kontoinformation på kontrollpanelssidan för din Twilio Console för att hitta dina inloggningsuppgifter.

      * **[!UICONTROL Message SID]**: Ange den unika identifierare som tilldelats alla meddelanden som skapas av Twilios API. Läs mer i [Twilio-dokumentation](https://support.twilio.com/hc/en-us/articles/223134387-What-is-a-Message-SID-){target="_blank"}.

+++

   * +++ För **[!DNL Infobip]**

      * **[!UICONTROL Name]**: välj ett namn för API-autentiseringsuppgifterna.

      * **[!UICONTROL API base URL]** och **[!UICONTROL API token]**: gå till webbgränssnittets hemsida eller API-nyckelhanteringssidan för att hitta dina autentiseringsuppgifter. Läs mer i [Infobip-dokumentation](https://www.infobip.com/docs/api){target="_blank"}.

      * **[!UICONTROL Double Opt-In Keywords]**: anger de nyckelord som utlöser processen för dubbel anmälan. Om en användarprofil inte finns skapas den när den har bekräftats. Använd kommaseparerade värden för flera nyckelord.

      * **[!UICONTROL Double Opt-In Message]**: Ange det anpassade svar som automatiskt skickas som svar på bekräftelsen av dubbel anmälan.

      * **[!UICONTROL Principal Entity ID]**: ange ditt tilldelade enhets-ID för DLT-huvudnamn.

      * **[!UICONTROL Content Template ID]**: ange ditt registrerade ID för DLT-innehållsmall.

      * **[!UICONTROL Validity Period]**: Ange meddelandets giltighetsperiod i timmar. Om det inte går att leverera meddelanden inom den här tidsramen gör systemet ytterligare försök att skicka dem igen. Standardgiltighetsperioden är inställd på 48 timmar.

      * **[!UICONTROL Callback Data]**: Ange ytterligare klientdata som ska skickas på Notify URL.
+++

1. Klicka **[!UICONTROL Submit]** när du är klar med konfigurationen av dina API-autentiseringsuppgifter.

När du har skapat och konfigurerat API-autentiseringsuppgifterna måste du nu skapa en kanalyta (t.ex. meddelandeförinställning) för SMS-meddelanden.

## Skapa en SMS-yta {#message-preset-sms}

>[!CONTEXTUALHELP]
>id="ajo_admin_surface_sms_type"
>title="Definiera meddelandekategorin"
>abstract="Välj typ av textmeddelanden med den här ytan: Marknadsföring för marknadsföringsmeddelanden som kräver användarens samtycke eller Transaktionsmeddelanden för icke-kommersiella meddelanden, till exempel lösenordsåterställning."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/privacy/consent/opt-out.html#sms-opt-out-management" text="Avanmäl dig i marknadsföringstextmeddelanden"

När din SMS/MMS-kanal har konfigurerats måste du skapa en kanalyta för att kunna skicka SMS-meddelanden från **[!DNL Journey Optimizer]**.

Så här skapar du en kanalyta:

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** och markera **[!UICONTROL Branding]** > **[!UICONTROL Channel surfaces]**. Klicka på knappen **[!UICONTROL Create channel surface]**.

   ![](assets/preset-create.png)

1. Ange ett namn och en beskrivning (valfritt) för ytan och välj sedan SMS-kanalen.

   ![](assets/sms-create-surface.png)

   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt`.` och bindestreck `-` tecken.

1. Definiera **SMS-inställningar**.

   ![](assets/sms-surface-settings.png)

   Börja med att välja **[!UICONTROL SMS Type]** som ska skickas med ytan: **[!UICONTROL Transactional]** eller **[!UICONTROL Marketing]**.

   * Välj **Marknadsföring** för kampanjmeddelanden: dessa meddelanden kräver användarens samtycke.
   * Välj **Transactional** för icke-kommersiella meddelanden, t.ex. orderbekräftelse, meddelanden om lösenordsåterställning eller leveransinformation.

   När du skapar ett SMS/MMS-meddelande måste du välja en giltig kanalyta som matchar den kategori som du valde för meddelandet.

   >[!CAUTION]
   >
   >**Transactional** meddelanden kan skickas till profiler som avbeställer marknadskommunikation. Dessa meddelanden kan bara skickas i särskilda sammanhang.

1. Välj **[!UICONTROL SMS configuration]** för att associera med ytan.

   Mer information om hur du konfigurerar miljön för att skicka SMS-meddelanden finns i [det här avsnittet](#create-api).

1. Ange **[!UICONTROL Sender number]** &#x200B; som du vill använda för din kommunikation.

1. Välj **[!UICONTROL SMS Execution Field]** för att välja **[!UICONTROL Profile attribute]** som är kopplade till profilens telefonnummer.

1. Om du vill använda förkortningsfunktionen för URL i dina SMS-meddelanden väljer du ett alternativ på menyn **[!UICONTROL Subdomain]** lista.

   >[!NOTE]
   >
   >Om du vill kunna välja en underdomän kontrollerar du att du tidigare har konfigurerat minst en SMS/MMS-underdomän. [Lär dig mer](sms-subdomains.md)

1. Ange **[!UICONTROL Opt-out number]** som du vill använda för den här ytan. När profiler avanmäler sig från det här numret kan du fortfarande skicka meddelanden från andra nummer som du använder för att skicka ut textmeddelanden med [!DNL Journey Optimizer].

   >[!NOTE]
   >
   >I [!DNL Journey Optimizer], avanmälning för textmeddelanden hanteras inte längre på kanalnivå. Den är nu specifik för ett tal.

1. När alla parametrar har konfigurerats klickar du på **[!UICONTROL Submit]** för att bekräfta. Du kan också spara kanalytan som ett utkast och återuppta konfigurationen senare.

   ![](assets/sms-submit-surface.png)

1. När kanalytan har skapats visas den i listan med **[!UICONTROL Processing]** status.

   >[!NOTE]
   >
   >Om kontrollerna inte lyckas kan du läsa mer om orsakerna till eventuella fel i [det här avsnittet](#monitor-channel-surfaces).

1. När kontrollerna är klara får kanalytan **[!UICONTROL Active]** status. Den är klar att användas för att leverera meddelanden.

   ![](assets/preset-active.png)

Nu kan du skicka textmeddelanden med Journey Optimizer.

**Relaterade ämnen**

* [Skapa ett textmeddelande (SMS/MMS)](create-sms.md)
* [Lägg till ett meddelande i en resa](../building-journeys/journeys-message.md)
* [Lägg till ett meddelande i en kampanj](../campaigns/create-campaign.md)

