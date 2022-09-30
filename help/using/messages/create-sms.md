---
title: Skapa ett SMS-meddelande
description: Lär dig hur du skapar ett SMS-meddelande i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 1f88626a-b491-4b36-8e3f-57f2b7567dd0
source-git-commit: 9593ea40853221e0eec45f30f7635d8a116b03c1
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 1%

---

# Skapa ett SMS-meddelande {#create-sms}

>[!CONTEXTUALHELP]
>id="ajo_message_sms"
>title="SMS-skapande"
>abstract="Lägg till ditt textmeddelande och börja personalisera det med uttrycksredigeraren."

Använd [!DNL Journey Optimizer] för att skicka textmeddelanden till kunderna på deras mobila enheter. Du kan skapa, anpassa och förhandsgranska meddelanden i textformat från SMS-redigeraren.

SMS-leveranser kan skapas:

* I en **Resa**: När du har lagt till en SMS-aktivitet under resan och definierat grundläggande inställningar använder du **[!UICONTROL Actions: SMS]** höger ruta för att skapa innehållet för SMS-meddelandet.

   Mer information om hur du konfigurerar din resa finns i [page](../building-journeys/journey-gs.md).

* I en **Campaign**: När du har skapat en kampanj väljer du SMS som åtgärd och definierar grundläggande inställningar.

   Mer information om hur du konfigurerar kampanjen finns i [page](../campaigns/create-campaign.md#configure).

Om det är första gången du skapar ett SMS-meddelande kontrollerar du att SMS-kanalen har konfigurerats. [Läs mer](../configuration/sms-configuration.md).

## Definiera ditt SMS-innehåll{#sms-content}

Så här börjar du personalisera SMS-meddelandet:

1. Klicka på **[!UICONTROL Message]** för att öppna uttrycksredigeraren.

   ![](assets/sms-content.png)

1. Använd uttrycksredigeraren för att definiera innehåll och lägga till dynamiskt innehåll. Du kan använda alla attribut, till exempel profilnamnet eller stad. Läs mer om [personalisering](../personalization/personalize.md) och [dynamiskt innehåll](../personalization/get-started-dynamic-content.md) i uttrycksredigeraren.

1. Klicka **[!UICONTROL Save]** och kontrollera meddelandet i förhandsgranskningen.

   ![](assets/sms-content-preview.png)

## Validera ditt SMS{#sms-preview}

>[!NOTE]
>
> För bättre leverans bör du alltid använda telefonnumren i de format som stöds av leverantören. Twilio och Sinch har till exempel bara stöd för telefonnummer i E.164-format.

När meddelandeinnehållet har definierats kan du använda testprofiler för att förhandsgranska och testa det. Om du infogade [personaliserat innehåll](../personalization/personalize.md)kan du kontrollera hur det här innehållet visas i meddelandet och dra nytta av testprofildata.

Om du vill se hur SMS-meddelandet visas på mobila enheter klickar du på **[!UICONTROL Simulate content]** -fliken. Läs mer om simulering av innehåll i [det här avsnittet](../design/preview.md).

Du måste även kontrollera varningar i den övre delen av redigeraren.  Vissa av dem är enkla varningar, men andra kan hindra dig från att använda meddelandet. Läs mer i [det här avsnittet](alerts.md).

![](assets/sms-alert-button.png)


## Anmäl dig och avanmäl dig{#sms-opt-in-out}

För alla marknadsföringsmeddelanden måste SMS:et innehålla ett sätt för mottagarna att enkelt avbryta prenumerationen. När prenumerationen har avbrutits tas profilerna automatiskt bort från målgruppen för framtida marknadsföringsmeddelanden. Det är inte obligatoriskt att lägga till en länk för att avbryta prenumerationen för transaktionsmeddelanden.

SMS-mottagare kan svara med nyckelord för deltagande och avanmälan. I enlighet med branschens standarder och bestämmelser bearbetar Adobe Journey Optimizer automatiskt följande nyckelord i inkommande meddelanden: STARTA, STOPPA OCH AVSTOPPA. Dessa nyckelord utlöser automatiska standardsvar från SMS-providern.

Mer information om hur inbyggt stöd för inkommande nyckelord (start, stopp och stopp) fungerar för SMS finns i följande video.

>[!VIDEO](https://video.tv.adobe.com/v/344026?quality=12)

<!--
## How-to video

Learn how to configure, author, and include SMS messaging into your customer journeys.

>[!VIDEO](https://video.tv.adobe.com/v/344460?quality=12)
-->
**Relaterade ämnen**

* [Konfigurera SMS-kanal](../configuration/sms-configuration.md)
* [SMS-rapport](../reports/journey-global-report.md#sms-global)
* [Skapa ett nytt meddelande](get-started-content.md)
* [Lägg till ett meddelande i en resa](../building-journeys/journeys-message.md)
