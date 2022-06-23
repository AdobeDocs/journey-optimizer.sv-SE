---
title: Skapa ett SMS-meddelande
description: Lär dig hur du skapar ett SMS-meddelande i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 1f88626a-b491-4b36-8e3f-57f2b7567dd0
source-git-commit: 067453ee3c19c7f269b4b1791ead8b5421adf95b
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 5%

---

# Skapa ett SMS-meddelande {#create-sms}

>[!CONTEXTUALHELP]
>id="ajo_message_sms"
>title="SMS-skapande"
>abstract="Lägg till ditt textmeddelande och börja personalisera det med Uttrycksredigeraren."

>[!NOTE]
>
>SMS-kanalen är för närvarande bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant om du vill ha mer information.

En gång [skapade ett meddelande](get-started-content.md), använder du **[!UICONTROL SMS]** för att definiera inställningar och innehåll för SMS-kanalen.

![](assets/sms_1.png)

Så här börjar du personalisera SMS-meddelandet:

1. Klicka på **[!UICONTROL Add text message]** för att öppna uttrycksredigeraren.

   ![](assets/sms_3.png)

1. Använd uttrycksredigeraren för att definiera innehåll och personaliseringsdata. Läs mer om personalisering i Expression Editor i [det här avsnittet](../personalization/personalize.md)

   >[!NOTE]
   >
   > SMS-meddelanden får innehålla högst 160 tecken.

   ![](assets/sms_2.png)

1. Klicka **[!UICONTROL Save]** när ditt personaliserade meddelande är klart.

1. Klicka **[!UICONTROL Preview]** för att visualisera hur SMS-meddelandet kommer att visas på mobila enheter. Mer information om detta finns i [det här avsnittet](../design/preview.md).

1. När meddelandet är klart kan du publicera det för att göra det tillgängligt för körning med **[!UICONTROL Publish]** -knappen. Den här åtgärden kommer att publicera den nya versionen av meddelandet som ska användas för nästa körning på dina resor.

Ditt SMS-meddelande kan nu användas under en resa. [Lär dig skapa resor](../building-journeys/journey-gs.md).

## Anmäl dig och avanmäl dig{#sms-opt-in-out}

SMS-mottagare kan svara med nyckelord för deltagande och avanmälan. I enlighet med branschens standarder och bestämmelser bearbetar Adobe Journey Optimizer automatiskt följande nyckelord i inkommande meddelanden: STARTA, STOPPA OCH AVSTOPPA. Dessa nyckelord utlöser automatiska standardsvar från SMS-providern.

**Relaterade ämnen**

* [Konfigurera SMS-kanal](../configuration/sms-configuration.md)
* [SMS-rapport](../reports/journey-global-report.md#sms-global)
* [Skapa ett nytt meddelande](get-started-content.md)
* [Lägg till ett meddelande i en resa](../building-journeys/journeys-message.md)
