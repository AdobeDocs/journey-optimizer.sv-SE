---
solution: Journey Optimizer
product: journey optimizer
title: Förhandsgranska och testa SMS-meddelandet
description: Lär dig hur du förhandsgranskar och testar SMS-meddelanden i Journey Optimizer
feature: SMS
topic: Content Management
role: User
level: Beginner
exl-id: 31c9b080-e334-4a11-af33-4c6f115c70a4
source-git-commit: 03c714833930511fa734662b637d2416728073c2
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 3%

---

# Förhandsgranska och testa SMS-meddelandet {#send-sms}

## Förhandsgranska ditt SMS {#preview-sms}

När meddelandeinnehållet har definierats kan du använda testprofiler för att förhandsgranska och testa det. Om du har infogat anpassat innehåll kan du kontrollera hur det här innehållet visas i meddelandet med hjälp av testprofildata.

1. Klicka på **[!UICONTROL Simulate content]**.

1. Klicka **[!UICONTROL Manage test profiles]** för att lägga till en testprofil.

1. Hitta din testprofil med **[!UICONTROL Identity namespace]** och **[!UICONTROL Identity value]** fält. Klicka sedan på **[!UICONTROL Add profile]**.

   ![](assets/sms_preview_3.png)

1. När du har valt din testprofil kan du stänga **[!UICONTROL Add test profile]** -fönstret.

1. Från **Förhandsgranska och testa** testprofildata läggs till i meddelandeinnehållet.

   ![](assets/sms_preview_2.png)


## Validera ditt SMS{#sms-validate}

Du måste kontrollera varningar i den övre delen av redigeraren. Vissa av dem är enkla varningar, men andra kan hindra dig från att skicka meddelandet. Två typer av varningar kan inträffa: varningar och fel.

* **Varningar** hänvisa till rekommendationer och bästa praxis. Ett varningsmeddelande visas till exempel om SMS-meddelandet är tomt.

* **Fel** hindra er från att testa eller aktivera resan, eller publicera kampanjen, så länge de inte är lösta. Ett felmeddelande varnar dig till exempel när ämnesraden saknas.

![](assets/sms-alert-button.png)

>[!NOTE]
>
> Använd telefonnumren i de format som stöds av leverantören för att förbättra leveransmöjligheterna. Twilio och Sinch har till exempel bara stöd för telefonnummer i E.164-format.

## Skicka SMS{#sms-send}

När SMS-meddelandet är klart slutför du konfigurationen av [resa](../building-journeys/journey-gs.md) eller [kampanj](../campaigns/create-campaign.md) för att skicka den.

**Relaterade ämnen**

* [Konfigurera SMS-kanal](sms-configuration.md)
* [SMS-rapport](../reports/journey-global-report.md#sms-global)
* [Skapa ett SMS-meddelande](create-sms.md)
* [Lägg till ett meddelande i en resa](../building-journeys/journeys-message.md)
