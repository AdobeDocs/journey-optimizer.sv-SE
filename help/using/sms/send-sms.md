---
solution: Journey Optimizer
product: journey optimizer
title: Förhandsgranska SMS-meddelandet
description: Lär dig hur du förhandsgranskar och testar SMS-meddelanden i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 31c9b080-e334-4a11-af33-4c6f115c70a4
source-git-commit: d1c11881654580247e8d7c92237cad130f11f749
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 3%

---

# Skicka SMS {#send-sms}

## Förhandsgranska SMS-meddelandet {#preview-sms}

När meddelandeinnehållet har definierats kan du använda testprofiler för att förhandsgranska och testa det. Om du har infogat anpassat innehåll kan du kontrollera hur det här innehållet visas i meddelandet genom att utnyttja testprofildata.

1. Klicka på **[!UICONTROL Simulate content]**.

1. Klicka **[!UICONTROL Manage test profiles]** för att lägga till en testprofil.

1. Hitta din testprofil med **[!UICONTROL Identity namespace]** och **[!UICONTROL Identity value]** fält. Klicka sedan på **[!UICONTROL Add profile]**.

   ![](assets/sms_preview_3.png)

1. När du har valt din testprofil kan du stänga **[!UICONTROL Add test profile]** -fönstret.

   ![](assets/sms_preview_1.png)

1. I förhandsgransknings- och testfönstret används testprofildata i meddelandeinnehållet.

   För det här SMS-meddelandet är till exempel både meddelandeinnehållet anpassat:

   ![](assets/sms_preview_2.png)

## Validera ditt SMS{#sms-preview}

>[!NOTE]
>
> För bättre leverans bör du alltid använda telefonnumren i de format som stöds av leverantören. Twilio och Sinch har till exempel bara stöd för telefonnummer i E.164-format.

Du måste även kontrollera varningar i den övre delen av redigeraren.  Vissa av dem är enkla varningar, men andra kan hindra dig från att använda meddelandet. Två typer av varningar kan inträffa:

* **Varningar** hänvisa till rekommendationer och bästa praxis. Ett meddelande visas till exempel om SMS-meddelandet är tomt.

* **Fel** hindra dig från att testa eller aktivera resan så länge som de inte är lösta. Du får t.ex. en varning om att ämnesraden saknas.

![](assets/sms-alert-button.png)

När SMS-meddelandet är klart slutför du konfigurationen av [resa](../building-journeys/journey-gs.md) eller [kampanj](../campaigns/create-campaign.md) för att skicka den.

**Relaterade ämnen**

* [Konfigurera SMS-kanal](sms-configuration.md)
* [SMS-rapport](../reports/journey-global-report.md#sms-global)
* [Skapa ett SMS-meddelande](create-sms.md)
* [Lägg till ett meddelande i en resa](../building-journeys/journeys-message.md)
