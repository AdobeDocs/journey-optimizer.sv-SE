---
title: Skapa ett SMS-meddelande
description: Lär dig hur du skapar ett SMS-meddelande i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 1f88626a-b491-4b36-8e3f-57f2b7567dd0
source-git-commit: 47b1c2832f82a5c168cd03f1d1b43a9223c945b3
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 4%

---

# Skapa ett SMS-meddelande {#create-sms}

>[!CONTEXTUALHELP]
>id="ajo_message_sms"
>title="SMS-skapande"
>abstract="Lägg till ditt textmeddelande och börja personalisera det med Uttrycksredigeraren."

En gång [skapade ett meddelande](get-started-content.md), använder du **[!UICONTROL SMS]** för att definiera inställningar och innehåll för SMS-meddelandet.


>[!AVAILABILITY]
>
>SMS-kanalen är för närvarande bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant om du vill ha mer information.

![](assets/sms_1.png)

Om det är första gången du skapar ett SMS-meddelande kontrollerar du att SMS-kanalen har konfigurerats. [Läs mer](../configuration/sms-configuration.md).

## Definiera ditt SMS-innehåll{#sms-content}

Så här börjar du personalisera SMS-meddelandet:

1. Klicka på **[!UICONTROL Add text message]** för att öppna uttrycksredigeraren.

   ![](assets/sms_3.png)

1. Använd uttrycksredigeraren för att definiera innehåll. Du kan använda alla attribut för att anpassa innehåll, till exempel profilnamnet eller staden. Läs mer om personalisering i Expression Editor i [det här avsnittet](../personalization/personalize.md)

   >[!NOTE]
   >
   > Ett SMS-meddelande kan innehålla upp till 160 tecken, inklusive mellanslag och radbrytningar.

   ![](assets/sms_2.png)

1. Klicka **[!UICONTROL Save]** när meddelandet är klart.

## Validera ditt SMS{#sms-preview}

När meddelandeinnehållet har definierats kan du använda testprofiler för att förhandsgranska och testa det. Om du infogade [personaliserat innehåll](../personalization/personalize.md)kan du kontrollera hur det här innehållet visas i meddelandet och dra nytta av testprofildata.

Om du vill se hur ditt SMS-meddelande visas på mobila enheter går du till **[!UICONTROL Preview]** -fliken.

Mer information om detta finns i [det här avsnittet](../design/preview.md).

## Publicera ditt SMS {#sms-publish}

När meddelandet är klart kan du publicera det för att göra det tillgängligt för körning med **[!UICONTROL Publish]** -knappen. Den här åtgärden publicerar den nya versionen av meddelandet som ska användas för nästa körning på dina resor.

Ditt SMS-meddelande kan nu användas under en resa. [Lär dig skapa resor](../building-journeys/journey-gs.md).

## Anmäl dig och avanmäl dig{#sms-opt-in-out}

För alla marknadsföringsmeddelanden måste SMS:et innehålla ett sätt för mottagarna att enkelt avbryta prenumerationen. När prenumerationen har avbrutits tas profilerna automatiskt bort från målgruppen för framtida marknadsföringsmeddelanden. Det är inte obligatoriskt att lägga till en länk för att avbryta prenumerationen för transaktionsmeddelanden.

SMS-mottagare kan svara med nyckelord för deltagande och avanmälan. I enlighet med branschens standarder och bestämmelser bearbetar Adobe Journey Optimizer automatiskt följande nyckelord i inkommande meddelanden: STARTA, STOPPA OCH AVSTOPPA. Dessa nyckelord utlöser automatiska standardsvar från SMS-providern.

**Relaterade ämnen**

* [Konfigurera SMS-kanal](../configuration/sms-configuration.md)
* [SMS-rapport](../reports/journey-global-report.md#sms-global)
* [Skapa ett nytt meddelande](get-started-content.md)
* [Lägg till ett meddelande i en resa](../building-journeys/journeys-message.md)
