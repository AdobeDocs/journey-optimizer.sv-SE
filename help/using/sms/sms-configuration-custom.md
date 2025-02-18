---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera din anpassade leverantör
description: Lär dig hur du konfigurerar miljön för att skicka textmeddelanden med Journey Optimizer via en anpassad leverantör
feature: SMS, Channel Configuration
badge: label="Beta" type="Informative"
role: Admin
level: Intermediate
exl-id: fd713864-96b9-4687-91bd-84e3533273ff
source-git-commit: f41426bd41078b98a26c32ce259a848ab49d724c
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 1%

---

# Konfigurera en anpassad provider {#sms-configuration-custom}

>[!AVAILABILITY]
>
>Anpassade leverantörer är för närvarande endast tillgängliga som betaversioner för vissa användare. Kontakta Adobe om du vill vara med i Beta.
>
>Observera att denna Beta inte stöder inkommande meddelanden för hantering av anmälan/avanmälan och leveransrapportering.

Följ de här stegen för att skicka meddelanden i Journey Optimizer med en anpassad leverantör som inte är tillgänglig från Adobe (t.ex. Sinch, Infobip, Twilio):

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** och väljer menyn **[!UICONTROL API Credentials]**.

1. Klicka på knappen **[!UICONTROL Create new API credentials]**.

   ![](assets/sms_byo_1.png)

1. Konfigurera dina SMS API-autentiseringsuppgifter enligt nedanstående:

   * **[!UICONTROL SMS vendor]**: Anpassad.

   * **[!UICONTROL Name]**: Ange ett namn för API-autentiseringsuppgifterna.

   * **[!UICONTROL Provider AppId]**: Ange det program-ID som din SMS-leverantör har angett.

   * **[!UICONTROL Provider Name]**: Ange namnet på SMS-providern.

   * **[!UICONTROL Provider URL]**: Ange URL:en till SMS-providern.

   * **[!UICONTROL Auth Type&#x200B;]**: välj auktoriseringstyp. Auktoriseringstyper som stöds är **Bearer App** eller **Basic**.

   * **[!UICONTROL API Token]**: Ange API-token som tillhandahålls av din SMS-leverantör.

   * **[!UICONTROL Provider Payload]**: lägg till leverantörens nyttolast, t.ex. `{"from": "+1234XXXXXX", "to": "+1374XXXXXX", "content": "This is a test message", "contentType": "TEXT"}`.

     Kontrollera att nyttolasten innehåller `{{toNumber}}`, `{{fromNumber}}`, `{{message}}`.

1. Klicka på **[!UICONTROL Submit]** när du är klar med konfigurationen av dina API-autentiseringsuppgifter.

1. Klicka på bin-ikonen på menyn **[!UICONTROL API Credentials]** för att ta bort dina API-autentiseringsuppgifter.

1. Om du vill ändra befintliga autentiseringsuppgifter letar du reda på de API-autentiseringsuppgifter du vill ha och klickar på alternativet **[!UICONTROL Edit]** för att göra de ändringar som behövs.

När du har skapat och konfigurerat API-autentiseringsuppgifterna måste du nu skapa en kanal för SMS-meddelanden. [Läs mer](sms-configuration-surface.md)

När konfigurationen är klar kan ni utnyttja alla färdiga kanalfunktioner som meddelandeframställning, personalisering, länkspårning och rapportering.

## Instruktionsvideo {#video}

>[!VIDEO](https://video.tv.adobe.com/v/3431625)
