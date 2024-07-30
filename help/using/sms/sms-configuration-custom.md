---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera din anpassade leverantör
description: Lär dig hur du konfigurerar miljön för att skicka textmeddelanden med Journey Optimizer via en anpassad leverantör
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
source-git-commit: af03ad62c2c7b29d695670f083e0dfb6d0c71b93
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 2%

---

# Konfigurera en anpassad leverantör (Beta) {#sms-configuration-custom}

>[!AVAILABILITY]
>
>Anpassade leverantörer är för närvarande endast tillgängliga som betaversioner för vissa användare. Kontakta din Adobe-representant för att få delta i Beta.
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

När du har skapat och konfigurerat API-autentiseringsuppgifterna måste du nu skapa en kanal för SMS-meddelanden. [Läs mer](sms-configuration-surface.md)

När konfigurationen är klar kan ni utnyttja alla färdiga kanalfunktioner som meddelandeframställning, personalisering, länkspårning och rapportering.

## Instruktionsvideo {#video}

>[!VIDEO](https://video.tv.adobe.com/v/3431625)
