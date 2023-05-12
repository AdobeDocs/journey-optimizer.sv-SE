---
solution: Journey Optimizer
product: journey optimizer
title: Skapa ett SMS-meddelande
description: Lär dig hur du skapar ett SMS-meddelande i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 1f88626a-b491-4b36-8e3f-57f2b7567dd0
source-git-commit: 33dccf32b60a6afb58931823016821fc1effcbd8
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 4%

---

# Skapa ett SMS-meddelande {#create-sms}

>[!CONTEXTUALHELP]
>id="ajo_message_sms"
>title="Skapa ett SMS-meddelande"
>abstract="Lägg till ditt SMS-meddelande och börja personalisera det med uttrycksredigeraren."

## Lägg till ett SMS-meddelande {#create-sms-journey-campaign}

Bläddra bland flikarna nedan för att lära dig hur du lägger till ett SMS-meddelande i en kampanj eller en resa.

>[!BEGINTABS]

>[!TAB Lägga till ett SMS-meddelande på en resa]

1. Öppna resan och dra och släpp en SMS-aktivitet från **Åtgärder** på paletten.

   ![](assets/sms_create_1.png)

1. Ange grundläggande information i meddelandet (etikett, beskrivning, kategori) och välj sedan den meddelandeyta som ska användas.

   ![](assets/sms_create_2.png)

   Mer information om hur du konfigurerar en resa finns i [den här sidan](../building-journeys/journey-gs.md)

   The **[!UICONTROL Surface]** som standard är fältet förifyllt med den sista yta som användaren använder för den kanalen.

Nu kan du börja designa ditt SMS-meddelande via **[!UICONTROL Edit content]** -knappen. [Definiera ditt SMS-innehåll](#sms-content)

>[!TAB Lägga till ett SMS-meddelande i en kampanj]

1. Skapa en ny schemalagd eller API-utlöst kampanj, välj **[!UICONTROL SMS]** som din åtgärd och väljer **[!UICONTROL App surface]** att använda. [Läs mer om SMS-konfiguration](sms-configuration.md).

   ![](assets/sms_create_3.png)

1. Klicka på **[!UICONTROL Create]**.

1. Från **[!UICONTROL Properties]** redigerar du Campaigns **[!UICONTROL Title]** och **[!UICONTROL Description]**.

   ![](assets/sms_create_4.png)

1. I **[!UICONTROL Actions tracking]** anger du om du vill spåra klickningar på länkar i SMS-meddelandet.

1. Klicka på **[!UICONTROL Select audience]** för att definiera målgruppen i listan över tillgängliga Adobe Experience Platform-segment. [Läs mer](../segment/about-segments.md).

1. I **[!UICONTROL Identity namespace]** väljer du det namnutrymme som ska användas för att identifiera individerna från det valda segmentet. [Läs mer](../event/about-creating.md#select-the-namespace).

   ![](assets/sms_create_5.png)

1. Kampanjer är utformade för att köras ett visst datum eller med en återkommande frekvens. Lär dig hur du konfigurerar **[!UICONTROL Schedule]** av kampanjen i [det här avsnittet](../campaigns/create-campaign.md#schedule).

1. Från **[!UICONTROL Action triggers]** väljer du **[!UICONTROL Frequency]** av SMS-meddelandet:

   * En gång
   * Dagligen
   * Veckovis
   * Month

Nu kan du börja designa ditt SMS-meddelande via **[!UICONTROL Edit content]** -knappen. [Designa ditt SMS-innehåll](#sms-content)

>[!ENDTABS]

## Definiera ditt SMS-innehåll{#sms-content}

1. Klicka på **[!UICONTROL Edit content]** för att konfigurera SMS-innehållet.

1. Klicka på **[!UICONTROL Message]** för att öppna uttrycksredigeraren.

   ![](assets/sms-content.png)

1. Använd uttrycksredigeraren för att definiera innehåll och lägga till dynamiskt innehåll. Du kan använda alla attribut, till exempel profilnamnet eller stad. Läs mer om [personalisering](../personalization/personalize.md) och [dynamiskt innehåll](../personalization/get-started-dynamic-content.md) i uttrycksredigeraren.

1. När du har definierat innehållet kan du lägga till URL:er för ditt spår i meddelandet. Om du vill göra det går du till **[!UICONTROL Helper functions]** meny och välj **[!UICONTROL Helpers]**.

   Observera att för att kunna använda funktionen för förkortning av URL-adresser måste du först konfigurera en underdomän som sedan länkas till din yta. [Läs mer](sms-subdomains.md)

   >[!CAUTION]
   >
   > Om du vill komma åt och redigera SMS-underdomäner måste du ha **[!UICONTROL Manage SMS Subdomains]** behörighet i produktionssandlådan.

   ![](assets/sms_tracking_1.png)

1. I **[!UICONTROL Helper functions]** meny, klicka **[!UICONTROL URL function]** och sedan markera **[!UICONTROL Add URL]**.

   ![](assets/sms_tracking_2.png)

1. I `originalUrl` klistra in den URL som du vill förkorta.

1. Klicka **[!UICONTROL Save]** och kontrollera meddelandet i förhandsgranskningen. Du kan använda **[!UICONTROL Simulate content]** för att förhandsgranska dina förkortade URL:er eller personaliserat innehåll.

   ![](assets/sms-content-preview.png)

Nu kan du testa och skicka SMS-meddelanden till din målgrupp. [Läs mer](send-sms.md)
När ni har skickat det kan ni mäta effekten av ert SMS i kampanjrapporten eller reserapporten. Mer information om rapportering finns i [det här avsnittet](../reports/campaign-global-report.md#sms-tab).

>[!NOTE]
>
>I enlighet med branschens standarder och bestämmelser måste alla SMS-marknadsföringsmeddelanden innehålla ett sätt för mottagarna att enkelt avbryta prenumerationen. För att göra detta kan SMS-mottagare svara med nyckelord för deltagande och avanmälan. [Lär dig hur du hanterar avanmälan](../privacy/opt-out.md#sms-opt-out-management-sms-opt-out-management)

**Relaterade ämnen**

* [Förhandsgranska, testa och skicka SMS-meddelanden](send-sms.md)
* [Konfigurera SMS-kanal](sms-configuration.md)
* [SMS-rapport](../reports/journey-global-report.md#sms-global)
* [Lägg till ett meddelande i en resa](../building-journeys/journeys-message.md)
* [Lägg till ett meddelande i en kampanj](../campaigns/create-campaign.md)
