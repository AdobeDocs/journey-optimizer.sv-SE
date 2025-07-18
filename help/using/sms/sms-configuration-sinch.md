---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera Sinch-provider
description: Lär dig hur du konfigurerar miljön för att skicka textmeddelanden med Journey Optimizer med Sinch
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: 85412a85-edf0-4069-8bc7-b80371375f1f
source-git-commit: 604af3a0ac9febb62f2e2b1705e2751b2c476e04
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 1%

---

# Konfigurera Sinch-provider {#sms-configuration-sinch}

När du använder Sinch-providern med Journey Optimizer finns det tre olika alternativ:

* **SMS-konfiguration**: Konfigurera dina Single API-autentiseringsuppgifter för att skicka SMS-meddelanden sömlöst.

* **MMS-konfiguration**: Konfigurera dina Single MMS API-autentiseringsuppgifter för multimediemeddelanden (MMS). Observera att spårning och svar på inkommande meddelanden hanteras av SMS-konfigurationen. MMS-konfigurationen är endast avsedd för utgående leverans av MMS-meddelandet.

* **RCS-konfiguration**: Konfigurera dina Single API-autentiseringsuppgifter för att skicka RCS-meddelanden sömlöst.

## Konfigurera API-autentiseringsuppgifter för SMS{#create-api}

>[!BEGINSHADEBOX]

Om nyckelord för anmälan eller avanmälan inte anges används standardmeddelanden för godkännande för att respektera användarens integritet. Om du lägger till anpassade nyckelord åsidosätts standardvärdena automatiskt.

**Standardnyckelord:**

* **Opt-In**: SUBSCRIBE, YES, UNSTOP, START, FORTSÄTT, RESUME, BEGIN
* **Opt-Out**: STOP, QUIT, CANCEL, END, UNSUBSCRIBE, NO
* **Hjälp**: HJÄLP

>[!ENDSHADEBOX]

Så här konfigurerar du din Sinch-leverantör för att skicka SMS-meddelanden och MMS med Journey Optimizer:

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** `>` **[!UICONTROL SMS Settings]** och väljer menyn **[!UICONTROL API Credentials]**. Klicka på knappen **[!UICONTROL Create new API credentials]**.

1. Konfigurera dina SMS API-autentiseringsuppgifter enligt nedanstående:

+++ Lista över SMS-autentiseringsuppgifter för konfiguration

   | Konfigurationsfält | Beskrivning |
   |---|---|    
   | SMS-leverantör | Sinch |
   | Namn | Välj ett namn för API-autentiseringsuppgifterna. |
   | Tjänst-ID och API-token | Du hittar dina autentiseringsuppgifter på fliken SMS på API:er-sidan. Läs mer i [Signera dokumentation](https://developers.sinch.com/docs/sms/getting-started/){target="_blank"}. |
   | Nyckelord för deltagande | Ange standardnyckelord eller anpassade nyckelord som automatiskt kommer att utlösa ditt meddelande om att anmäla dig. Använd kommaseparerade värden för flera nyckelord. |
   | Opt-in-meddelande | Ange det anpassade svar som automatiskt skickas som ditt meddelande. |
   | Avanmäl nyckelord | Ange standardnyckelord eller anpassade nyckelord som automatiskt utlöser ditt avanmälningsmeddelande. Använd kommaseparerade värden för flera nyckelord. |
   | Avanmäl meddelande | Ange det anpassade svar som automatiskt skickas som ditt avanmälningsmeddelande. |
   | Hjälpnyckelord | Ange standardnyckelord eller anpassade nyckelord som automatiskt kommer att utlösa ditt **hjälpmeddelande**. Använd kommaseparerade värden för flera nyckelord. |
   | Hjälpmeddelande | Ange det anpassade svar som automatiskt skickas som **hjälpmeddelande**. |
   | Nyckelord för dubbel anmälan | Ange de nyckelord som utlöser processen för dubbel anmälan. Om en användarprofil inte finns skapas den när den har bekräftats. Använd kommaseparerade värden för flera nyckelord. [Läs mer om SMS-dubbelanmälan](https://video.tv.adobe.com/v/3440280/?learn=on&captions=swe). |
   | Dubbelt meddelande om anmälan | Ange det anpassade svar som automatiskt skickas som svar på bekräftelsen av dubbel anmälan. |
   | Ingående nummer | Lägg till ditt unika inkommande nummer eller din korta kod. På så sätt kan du använda samma API-autentiseringsuppgifter för olika sandlådor, var och en med ett eget inkommande nummer eller kort kod. |
   | Anpassade inkommande nyckelord | Definiera unika nyckelord för specifika åtgärder, t.ex. RABATT, ERBJUDANDEN, REGISTRERING. Dessa nyckelord fångas in och lagras som attribut i profilen, vilket gör att du kan aktivera en segmentkvalificering för direktuppspelning under resan och leverera ett anpassat svar eller en anpassad åtgärd. |
   | Standardsvarsmeddelande för inkommande trafik | Ange standardsvaret som skickas när en slutanvändare skickar ett inkommande SMS som inte matchar något av de definierade nyckelorden. |
   | Åsidosätt URL | Ange din anpassade URL för att ersätta standardslutpunkterna för SMS-leveransrapporter, feedbackdata, inkommande meddelanden eller händelsemeddelanden. Sinch skickar alla relevanta uppdateringar till den här URL:en i stället för de fördefinierade. |

+++

1. Klicka på **[!UICONTROL Submit]** när du är klar med konfigurationen av dina API-autentiseringsuppgifter.

1. Klicka på bin-ikonen på menyn **[!UICONTROL API Credentials]** för att ta bort dina API-autentiseringsuppgifter.

1. Om du vill ändra befintliga autentiseringsuppgifter letar du reda på de API-autentiseringsuppgifter du vill ha och klickar på alternativet **[!UICONTROL Edit]** för att göra de ändringar som behövs.

När du har skapat och konfigurerat dina API-autentiseringsuppgifter måste du nu skapa en kanalkonfiguration för SMS-meddelanden. [Läs mer](sms-configuration-surface.md)

## Konfigurera API-autentiseringsuppgifter för MMS{#sinch-mms}

>[!IMPORTANT]
>
> Förutom MMS-konfigurationen måste du också skapa autentiseringsuppgifter för Sinch API specifikt för att spåra inkommande meddelanden och hantera begäranden om samtycke.

Så här konfigurerar du Sinch MMS att skicka MMS med Journey Optimizer:

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** `>` **[!UICONTROL SMS Settings]** och väljer menyn **[!UICONTROL API Credentials]**. Klicka på knappen **[!UICONTROL Create new API credentials]**.

1. Konfigurera MMS API-autentiseringsuppgifterna enligt nedan:

   * **[!UICONTROL SMS vendor]**: Minska MMS.

   * **[!UICONTROL Name]**: välj ett namn för API-autentiseringsuppgifterna.

   * **[!UICONTROL Project ID]**, **[!UICONTROL App ID]** och **[!UICONTROL API Token]**: Följ stegen nedan för att samla in dina MMS API-autentiseringsuppgifter.

      * För **[!UICONTROL Project ID]** och **[!UICONTROL App ID]**: Gå till sidan [Översikt över konversation-API](https://dashboard.sinch.com/convapi/overview) i ditt Sinch-projekt på din Sinch-instrumentpanel.
      * För **[!UICONTROL API Token]**: Hämta [ Access-nycklarna ](https://community.sinch.com/t5/Customer-Dashboard/Sinch-Access-Keys/ta-p/12638) för ditt Sinch-projekt och generera en **Base64 API-token** från ditt Single Project **Access-nycklar**.

1. Klicka på **[!UICONTROL Submit]** när du är klar med konfigurationen av dina API-autentiseringsuppgifter.

1. Klicka på bin-ikonen på menyn **[!UICONTROL API Credentials]** för att ta bort dina API-autentiseringsuppgifter.

1. Om du vill ändra befintliga autentiseringsuppgifter letar du reda på de API-autentiseringsuppgifter du vill ha och klickar på alternativet **[!UICONTROL Edit]** för att göra de ändringar som behövs.

När du har skapat och konfigurerat API-autentiseringsuppgifterna måste du nu skapa en kanalkonfiguration för MMS-meddelanden. [Läs mer](sms-configuration-surface.md)

## Konfigurera API-autentiseringsuppgifter för RCS

<!--![](assets/do-not-localize/rcs-sms.png)-->

RCS-meddelanden (Rich Communication Services) stöds i Journey Optimizer via Sinch, vilket innebär att du kan skicka grundläggande meddelanden med verifierade affärsprofiler med varumärken som logotyper och avsändarnamn.

Observera att meddelanden automatiskt återgår till SMS när profilens enhet inte stöder RCS eller är tillfälligt oåtkomlig via RCS.

➡️ [Se hur Sinch stöder RCS i Sinch-dokumentation](https://sinch.com/blog/rcs-api-guide/)

Så här konfigurerar du RCS med Sinch:

1. **Konfigurera din profilerade RCS-agent**

   Kontakta din Adobe-representant för att få en varumärkesprofilerad RCS-agent. [Läs mer om varumärkesprofilerad RCS-agent](https://community.sinch.com/t5/RCS/Getting-Started-with-RCS-using-Conversation-API/ta-p/17844)

1. **Konfigurera dina [singch API-autentiseringsuppgifter](#create-api)**

   När din RCS-agent har godkänts måste du ange dina Single API-autentiseringsuppgifter, som innehåller din åtkomstnyckel, hemlighet och ditt serviceplan-ID. Dessa inloggningsuppgifter kommer att användas av Journey Optimizer för att autentisera och skicka meddelanden via Sinchs plattform.

1. **Skapa en [kanalkonfiguration](sms-configuration-surface.md) för dina RCS-meddelanden**

   Konfigurera en kanalyta i Journey Optimizer genom att länka dina signeringsuppgifter och definiera meddelandeparametrarna. Med den här installationen kan du skriva och skicka RCS-meddelanden från Journey Optimizer.

