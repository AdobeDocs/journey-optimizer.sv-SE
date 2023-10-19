---
solution: Journey Optimizer
product: journey optimizer
title: Kontrollera och testa SMS-meddelandet
description: Lär dig hur du kontrollerar och skickar SMS-meddelanden i Journey Optimizer
feature: SMS
topic: Content Management
role: User
level: Beginner
exl-id: 31c9b080-e334-4a11-af33-4c6f115c70a4
source-git-commit: 27447578dad6bd2612989d79cd0dc8ddbe78d629
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 2%

---

# Kontrollera och skicka SMS-meddelanden {#send-sms}

## Förhandsgranska ditt SMS {#preview-sms}

När meddelandeinnehållet har definierats kan du använda testprofiler för att förhandsgranska innehållet. Om du har infogat anpassat innehåll kan du kontrollera hur det här innehållet visas i meddelandet med hjälp av testprofildata.

Det gör du genom att klicka **[!UICONTROL Simulate content]** lägg sedan till en testprofil för att kontrollera meddelandet med testprofilsdata.

![](assets/sms_preview_2.png)

Detaljerad information om hur du väljer testprofiler och förhandsgranskar innehållet finns i [Innehållshantering](../content-management/preview-test.md) -avsnitt.

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
