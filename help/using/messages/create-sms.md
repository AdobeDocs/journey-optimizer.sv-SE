---
title: Skapa ett SMS-meddelande
description: Lär dig hur du skapar ett SMS-meddelande i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 1f88626a-b491-4b36-8e3f-57f2b7567dd0
source-git-commit: 0e978d0eab570a28c187f3e7779c450437f16cfb
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 2%

---

# Skapa ett SMS-meddelande {#create-sms}

>[!CONTEXTUALHELP]
>id="ajo_message_sms"
>title="SMS-skapande"
>abstract="Lägg till ditt textmeddelande och börja personalisera det med uttrycksredigeraren."

Använd [!DNL Journey Optimizer] för att skicka textmeddelanden till kunderna på deras mobila enheter. Du kan skapa, anpassa och förhandsgranska meddelanden i textformat från SMS-redigeraren.

En gång [lade till ett SMS](get-started-content.md) -aktiviteten på din resa och definierade grundläggande inställningar, använd **[!UICONTROL Actions: SMS]** höger ruta för att skapa innehållet för SMS-meddelandet.

>[!AVAILABILITY]
>
>SMS-kanalen är för närvarande bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant om du vill ha mer information.

![](assets/sms-edit-content.png)

Om det är första gången du skapar ett SMS-meddelande kontrollerar du att SMS-kanalen har konfigurerats. [Läs mer](../configuration/sms-configuration.md).

## Definiera ditt SMS-innehåll{#sms-content}

Så här börjar du personalisera SMS-meddelandet:

1. Klicka på **[!UICONTROL Message]** för att öppna uttrycksredigeraren.

   ![](assets/sms-content.png)

1. Använd uttrycksredigeraren för att definiera innehåll. Du kan använda alla attribut för att anpassa innehåll, till exempel profilnamnet eller staden. Läs mer om personalisering i uttrycksredigeraren i [det här avsnittet](../personalization/personalize.md).

1. Klicka **[!UICONTROL Save]** och kontrollera meddelandet i förhandsgranskningen.

   ![](assets/sms-content-preview.png)


## Validera ditt SMS{#sms-preview}

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
