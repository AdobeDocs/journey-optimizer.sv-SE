---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera din SMS-webkrok
description: Lär dig hur du konfigurerar webhooks för att hämta inkommande svar för hantering av anmälan och avanmälan
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
source-git-commit: 4278d8c8294b1413788402cd8eac5959996ad3f5
workflow-type: tm+mt
source-wordcount: '1099'
ht-degree: 0%

---

# Skapa webkrok {#webhook}

>[!BEGINSHADEBOX]

Om nyckelord för anmälan eller avanmälan inte anges används standardmeddelanden för godkännande för att respektera användarens integritet. Om du lägger till anpassade nyckelord åsidosätts standardvärdena automatiskt.

**Standardnyckelord:**

* **Opt-In**: SUBSCRIBE, YES, UNSTOP, START, FORTSÄTT, RESUME, BEGIN
* **Opt-Out**: STOP, QUIT, CANCEL, END, UNSUBSCRIBE, NO
* **Hjälp**: HJÄLP

>[!ENDSHADEBOX]

När API-autentiseringsuppgifterna har skapats kan du nu konfigurera Webhooks så att inkommande svar hämtas för hantering av godkännande av anmälan och avanmälan, och så att du får leveransrapporter som läskvitton när de är tillgängliga.

När du konfigurerar en webkrok kan du definiera dess syfte baserat på den typ av data som du vill hämta:

* **[!UICONTROL Inbound]**: Använd det här alternativet om du vill samla in medgivandesvar, t.ex. anmälan eller avanmälan, och samla in användarinställningar.

* **[!UICONTROL Feedback]**: Välj det här alternativet om du vill spåra leverans- och engagemangshändelser, inklusive läskvitton och användarinteraktioner, som stöd för rapportering och analys.

Bläddra bland flikarna nedan beroende på vilka SMS-leverantörer du har:

>[!BEGINTABS]

>[!TAB Egen]

1. Navigera till **[!UICONTROL Administration]** `>` **[!UICONTROL Channels]** i den vänstra listen, välj menyn **[!UICONTROL SMS Webhooks]** under **[!UICONTROL SMS settings]** och klicka på knappen **[!UICONTROL Create Webhook]**.

   ![](assets/sms_byo_5.png){zoomable="yes"}

1. Konfigurera webkrosinställningarna enligt anvisningarna nedan:

   * **[!UICONTROL Name]**: Ange ett namn för din webkrok.

   * **[!UICONTROL Select SMS vendor]**: Anpassad.

   * **[!UICONTROL Type]**: Inkommande.

   * **[!UICONTROL API credentials]**: Välj i listrutan [tidigare konfigurerade API-autentiseringsuppgifter](sms-configuration-custom.md#api-credential).

   * **[!UICONTROL Sender Phone Number &#x200B;]**: Ange det &#x200B; för avsändarens telefonnummer som du vill använda för kommunikationen.

     ![](assets/webhook-inbound.png){zoomable="yes"}

1. Klicka på ![](assets/do-not-localize/Smock_Add_18_N.svg) om du vill lägga till dina nyckelordskategorier och konfigurera dem sedan beroende på din SMS-leverantör:

   * **[!UICONTROL Inbound Keyword Category]**: Välj dina nyckelordskategorier antingen **[!UICONTROL Opt-In]**, **[!UICONTROL Opt-Out]**, **[!UICONTROL Double Opt-In]**, **[!UICONTROL Help]** eller **[!UICONTROL Custom]**.

   * **[!UICONTROL Enter a keyword]**: Ange standardnyckelord eller anpassade nyckelord som automatiskt kommer att utlösa ditt meddelande. Klicka på ![](assets/do-not-localize/Smock_Add_18_N.svg) om du vill lägga till flera nyckelord.

     Använd icke-medgivande-relaterade nyckelord för gruppbaserade åtgärder inom en resa för **[!UICONTROL Custom keyword]**.

   * **[!UICONTROL Reply Message]**: Välj det anpassade svar som skickas automatiskt i listrutan.

   * **[!UICONTROL Fuzzy Opt-out]**: Aktivera det här alternativet om du vill skicka ett automatiskt svar när ett nyckelord för avanmälan som nästan matchar identifieras.

   ![](assets/sms_byo_6.png){zoomable="yes"}

1. Ange en **[!UICONTROL Default Reply Message]** som skickas automatiskt när ett inkommande meddelande inte matchar något konfigurerat nyckelord eller någon konfigurerad kategori.

1. Klicka på **[!UICONTROL View payload editor]** för att validera och anpassa dina begärandataströmmar.

   Du kan dynamiskt anpassa din nyttolast med hjälp av profilattribut och säkerställa att korrekta data skickas för bearbetning och svarsgenerering med hjälp av inbyggda hjälpfunktioner.

1. Klicka på **[!UICONTROL Submit]** när du är klar med konfigurationen av din webkrok.

1. Om du vill skapa en **[!UICONTROL Feedback]**-webkrok följer du stegen ovan och väljer **[!UICONTROL Feedback]** som webkrok **[!UICONTROL Type]**.

1. På menyn **[!UICONTROL Webhooks]** kan du redigera eller ta bort befintliga webbböcker eller komma åt och kopiera **[!UICONTROL Webhook URL]** för integrering med din SMS-leverantör.

   ![](assets/sms_byo_7.png){zoomable="yes"}

När du har skapat och konfigurerat inställningarna för webkroken måste du nu skapa en [kanalkonfiguration](sms-configuration-surface.md) för SMS-meddelanden.

När konfigurationen är klar kan ni utnyttja alla färdiga kanalfunktioner som meddelandeframställning, personalisering, länkspårning och rapportering.

>[!TAB Infobip]

1. Navigera till **[!UICONTROL Administration]** `>` **[!UICONTROL Channels]** i den vänstra listen, välj menyn **[!UICONTROL SMS Webhooks]** under **[!UICONTROL SMS settings]** och klicka på knappen **[!UICONTROL Create Webhook]**.

   ![](assets/sms_byo_5.png){zoomable="yes"}

1. Konfigurera webkrosinställningarna enligt anvisningarna nedan:

   * **[!UICONTROL Name]**: Ange ett namn för din webkrok.

   * **[!UICONTROL Select SMS vendor]**: Infobip.

   * **[!UICONTROL Type]**: Inkommande.

   * **[!UICONTROL API credentials]**: Välj i listrutan [tidigare konfigurerade API-autentiseringsuppgifter](sms-configuration-infobip.md#api-credential).

   * **[!UICONTROL Sender Phone Number &#x200B;]**: Ange det &#x200B; för avsändarens telefonnummer som du vill använda för kommunikationen.

     ![](assets/webhook-infobip-1.png){zoomable="yes"}

1. Klicka på ![](assets/do-not-localize/Smock_Add_18_N.svg) om du vill lägga till dina nyckelordskategorier och konfigurera dem sedan beroende på din SMS-leverantör:

   * **[!UICONTROL Inbound Keyword Category]**: Välj dina nyckelordskategorier antingen **[!UICONTROL Opt-In]**, **[!UICONTROL Opt-Out]**, **[!UICONTROL Double Opt-In]**, **[!UICONTROL Help]** eller **[!UICONTROL Custom]**.

   * **[!UICONTROL Enter a keyword]**: Ange standardnyckelord eller anpassade nyckelord som automatiskt kommer att utlösa ditt meddelande. Klicka på ![](assets/do-not-localize/Smock_Add_18_N.svg) om du vill lägga till flera nyckelord.

     Använd icke-medgivande-relaterade nyckelord för gruppbaserade åtgärder inom en resa för **[!UICONTROL Custom keyword]**.

   * **[!UICONTROL Reply Message]**: Välj det anpassade svar som skickas automatiskt i listrutan.

   * **[!UICONTROL Fuzzy Opt-out]**: Aktivera det här alternativet om du vill skicka ett automatiskt svar när ett nyckelord för avanmälan som nästan matchar identifieras.

   ![](assets/webhook-infobip-2.png){zoomable="yes"}

1. Ange en **[!UICONTROL Default Reply Message]** som skickas automatiskt när ett inkommande meddelande inte matchar något konfigurerat nyckelord eller någon konfigurerad kategori.

1. Klicka på **[!UICONTROL Submit]** när du är klar med konfigurationen av din webkrok.

1. Om du vill skapa en **[!UICONTROL Feedback]**-webkrok följer du stegen ovan och väljer **[!UICONTROL Feedback]** som webkrok **[!UICONTROL Type]**.

1. På menyn **[!UICONTROL Webhooks]** kan du redigera eller ta bort befintliga webbböcker eller komma åt och kopiera **[!UICONTROL Webhook URL]** för integrering med din SMS-leverantör.

   ![](assets/sms_byo_7.png){zoomable="yes"}

När du har skapat och konfigurerat inställningarna för inkommande trafik för webkroken måste du nu skapa en [kanalkonfiguration](sms-configuration-surface.md) för SMS-meddelanden.

När konfigurationen är klar kan ni utnyttja alla färdiga kanalfunktioner som meddelandeframställning, personalisering, länkspårning och rapportering.

>[!TAB Dra]

1. Navigera till **[!UICONTROL Administration]** `>` **[!UICONTROL Channels]** i den vänstra listen, välj menyn **[!UICONTROL SMS Webhooks]** under **[!UICONTROL SMS settings]** och klicka på knappen **[!UICONTROL Create Webhook]**.

   ![](assets/sms_byo_5.png){zoomable="yes"}

1. Konfigurera webkrosinställningarna enligt anvisningarna nedan:

   * **[!UICONTROL Name]**: Ange ett namn för din webkrok.

   * **[!UICONTROL Select SMS vendor]**: Dra.

   * **[!UICONTROL Type]**: Inkommande.

   * **[!UICONTROL API credentials]**: Välj i listrutan [tidigare konfigurerade API-autentiseringsuppgifter](sms-configuration-sinch.md#create-api).

   * **[!UICONTROL Sender Phone Number &#x200B;]**: Ange det &#x200B; för avsändarens telefonnummer som du vill använda för kommunikationen.

     ![](assets/webhook-sinch-1.png){zoomable="yes"}

1. Klicka på ![](assets/do-not-localize/Smock_Add_18_N.svg) om du vill lägga till dina nyckelordskategorier och konfigurera dem sedan beroende på din SMS-leverantör:

   * **[!UICONTROL Inbound Keyword Category]**: Välj dina nyckelordskategorier antingen **[!UICONTROL Opt-In]**, **[!UICONTROL Opt-Out]**, **[!UICONTROL Double Opt-In]**, **[!UICONTROL Help]** eller **[!UICONTROL Custom]**.

   * **[!UICONTROL Enter a keyword]**: Ange standardnyckelord eller anpassade nyckelord som automatiskt kommer att utlösa ditt meddelande. Klicka på ![](assets/do-not-localize/Smock_Add_18_N.svg) om du vill lägga till flera nyckelord.

     Använd icke-medgivande-relaterade nyckelord för gruppbaserade åtgärder inom en resa för **[!UICONTROL Custom keyword]**.

   * **[!UICONTROL Reply Message]**: Välj det anpassade svar som skickas automatiskt i listrutan.

   * **[!UICONTROL Fuzzy Opt-out]**: Aktivera det här alternativet om du vill skicka ett automatiskt svar när ett nyckelord för avanmälan som nästan matchar identifieras.

   ![](assets/webhook-sinch-2.png){zoomable="yes"}

1. Ange en **[!UICONTROL Default Reply Message]** som skickas automatiskt när ett inkommande meddelande inte matchar något konfigurerat nyckelord eller någon konfigurerad kategori.

1. Klicka på **[!UICONTROL Submit]** när du är klar med konfigurationen av din webkrok.

1. Klicka på ikonen **[!UICONTROL Webhooks]** bin![ på menyn ](assets/do-not-localize/Smock_Delete_18_N.svg) för att ta bort webkroken.

1. Om du vill ändra den befintliga konfigurationen letar du reda på önskad webbkrok och klickar på alternativet **[!UICONTROL Edit]** för att göra de ändringar som behövs.

1. Få åtkomst till och kopiera din nya **[!UICONTROL Webhook URL]** från din tidigare inskickade **[!UICONTROL Webhook]**.

   ![](assets/sms_byo_7.png){zoomable="yes"}

När du har skapat och konfigurerat inställningarna för inkommande trafik för webkroken måste du nu skapa en [kanalkonfiguration](sms-configuration-surface.md) för SMS-meddelanden.

När konfigurationen är klar kan ni utnyttja alla färdiga kanalfunktioner som meddelandeframställning, personalisering, länkspårning och rapportering.

>[!TAB Twilio]

1. Navigera till **[!UICONTROL Administration]** `>` **[!UICONTROL Channels]** i den vänstra listen, välj menyn **[!UICONTROL SMS Webhooks]** under **[!UICONTROL SMS settings]** och klicka på knappen **[!UICONTROL Create Webhook]**.

   ![](assets/sms_byo_5.png){zoomable="yes"}

1. Konfigurera webkrosinställningarna enligt anvisningarna nedan:

   * **[!UICONTROL Name]**: Ange ett namn för din webkrok.

   * **[!UICONTROL Select SMS vendor]**: Twilio.

   * **[!UICONTROL Type]**: Inkommande.

   * **[!UICONTROL API credentials]**: Välj i listrutan [tidigare konfigurerade API-autentiseringsuppgifter](sms-configuration-twilio.md#create-api).

   * **[!UICONTROL Sender Phone Number &#x200B;]**: Ange det &#x200B; för avsändarens telefonnummer som du vill använda för kommunikationen.

1. Klicka på ![](assets/do-not-localize/Smock_Add_18_N.svg) om du vill lägga till dina nyckelordskategorier och konfigurera dem sedan beroende på din SMS-leverantör:

   * **[!UICONTROL Inbound Keyword Category]**: Välj dina nyckelordskategorier antingen **[!UICONTROL Opt-In]**, **[!UICONTROL Opt-Out]**, **[!UICONTROL Double Opt-In]**, **[!UICONTROL Help]** eller **[!UICONTROL Custom]**.

   * **[!UICONTROL Enter a keyword]**: Ange standardnyckelord eller anpassade nyckelord som automatiskt kommer att utlösa ditt meddelande. Klicka på ![](assets/do-not-localize/Smock_Add_18_N.svg) om du vill lägga till flera nyckelord.

     Använd icke-medgivande-relaterade nyckelord för gruppbaserade åtgärder inom en resa för **[!UICONTROL Custom keyword]**.

   * **[!UICONTROL Reply Message]**: Välj det anpassade svar som skickas automatiskt i listrutan.

   * **[!UICONTROL Fuzzy Opt-out]**: Aktivera det här alternativet om du vill skicka ett automatiskt svar när ett nyckelord för avanmälan som nästan matchar identifieras.

1. Ange en **[!UICONTROL Default Reply Message]** som skickas automatiskt när ett inkommande meddelande inte matchar något konfigurerat nyckelord eller någon konfigurerad kategori.

1. Klicka på **[!UICONTROL Submit]** när du är klar med konfigurationen av din webkrok.

1. Klicka på ikonen **[!UICONTROL Webhooks]** bin![ på menyn ](assets/do-not-localize/Smock_Delete_18_N.svg) för att ta bort webkroken.

1. Om du vill ändra den befintliga konfigurationen letar du reda på önskad webbkrok och klickar på alternativet **[!UICONTROL Edit]** för att göra de ändringar som behövs.

1. Få åtkomst till och kopiera din nya **[!UICONTROL Webhook URL]** från din tidigare inskickade **[!UICONTROL Webhook]**.

När du har skapat och konfigurerat inställningarna för inkommande trafik för webkroken måste du nu skapa en [kanalkonfiguration](sms-configuration-surface.md) för SMS-meddelanden.

När konfigurationen är klar kan ni utnyttja alla färdiga kanalfunktioner som meddelandeframställning, personalisering, länkspårning och rapportering.


>[!ENDTABS]


## Instruktionsvideo {#video}

>[!VIDEO](https://video.tv.adobe.com/v/3431625)

