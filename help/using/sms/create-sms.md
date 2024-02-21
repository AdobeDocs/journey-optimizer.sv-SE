---
solution: Journey Optimizer
product: journey optimizer
title: Skapa ett SMS-meddelande
description: Lär dig skapa ett SMS-meddelande i Journey Optimizer
feature: SMS
topic: Content Management
role: User
level: Beginner
exl-id: 1f88626a-b491-4b36-8e3f-57f2b7567dd0
source-git-commit: f275820c3f79bb4c9aca8593c2c761ccd4283795
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 3%

---

# Skapa ett textmeddelande {#create-sms}

>[!CONTEXTUALHELP]
>id="ajo_message_sms"
>title="Skapa ett textmeddelande"
>abstract="Om du vill skapa ett textmeddelande lägger du till en SMS-åtgärd på en resa eller i en kampanj och börjar anpassa det med uttrycksredigeraren."

Du kan utforma och skicka text (SMS) med Adobe Journey Optimizer. Du måste först lägga till en SMS-åtgärd på en resa eller i en kampanj och sedan definiera innehållet i textmeddelandet, enligt beskrivningen nedan. Adobe Journey Optimizer har också funktioner för att testa textmeddelanden innan de skickas, så att du kan kontrollera återgivning, anpassningsattribut och alla andra inställningar.

>[!NOTE]
>
>I enlighet med branschens standarder och bestämmelser måste alla SMS-marknadsföringsmeddelanden innehålla ett sätt för mottagarna att enkelt avbryta prenumerationen. För att göra detta kan SMS-mottagare svara med nyckelord för deltagande och avanmälan. [Lär dig hur du hanterar avanmälan](../privacy/opt-out.md#sms-opt-out-management-sms-opt-out-management)


## Lägga till ett textmeddelande {#create-sms-journey-campaign}

Bläddra bland flikarna nedan för att lära dig hur du lägger till ett textmeddelande i en kampanj eller en resa.

>[!BEGINTABS]

>[!TAB Lägga till ett textmeddelande på en resa]

1. Öppna resan och dra och släpp en SMS-aktivitet från **Åtgärder** på paletten.

   ![](assets/sms_create_1.png)

1. Ange grundläggande information i meddelandet (etikett, beskrivning, kategori) och välj sedan den meddelandeyta som ska användas.

   ![](assets/sms_create_2.png)

   Mer information om hur du konfigurerar en resa finns i [den här sidan](../building-journeys/journey-gs.md)

   The **[!UICONTROL Surface]** som standard är fältet förifyllt med den sista yta som användaren använder för den kanalen.

Nu kan du börja designa ditt SMS-meddelande via **[!UICONTROL Edit content]** som beskrivs nedan.

>[!TAB Lägga till ett textmeddelande i en kampanj]

1. Skapa en ny schemalagd eller API-utlöst kampanj, välj **[!UICONTROL SMS]** som din åtgärd och väljer **[!UICONTROL App surface]** att använda. Läs mer om SMS-konfiguration i [den här sidan](sms-configuration.md).

   ![](assets/sms_create_3.png)

1. Klicka på **[!UICONTROL Create]**.

1. Från **[!UICONTROL Properties]** redigerar du Campaigns **[!UICONTROL Title]** och **[!UICONTROL Description]**.

   ![](assets/sms_create_4.png)

1. Klicka på **[!UICONTROL Select audience]** för att definiera målgruppen i listan över tillgängliga Adobe Experience Platform-målgrupper. [Läs mer](../audience/about-audiences.md).

1. I **[!UICONTROL Identity namespace]** väljer du det namnutrymme som ska användas för att identifiera personer från den valda målgruppen. [Läs mer](../event/about-creating.md#select-the-namespace).

   ![](assets/sms_create_5.png)

1. Klicka **[!UICONTROL Create experiment]** för att börja konfigurera ert innehållsexperiment och skapa behandlingar för att mäta deras prestanda och identifiera det bästa alternativet för er målgrupp. [Läs mer](../campaigns/content-experiment.md)

1. I **[!UICONTROL Actions tracking]** anger du om du vill spåra klickningar på länkar i SMS-meddelandet.

1. Kampanjer är utformade för att köras ett visst datum eller med en återkommande frekvens. Lär dig hur du konfigurerar **[!UICONTROL Schedule]** av kampanjen i [det här avsnittet](../campaigns/create-campaign.md#schedule).

1. Från **[!UICONTROL Action triggers]** väljer du **[!UICONTROL Frequency]** av SMS-meddelandet:

   * En gång
   * Dagligen
   * Veckovis
   * Månad

Nu kan du börja designa textmeddelandets innehåll från **[!UICONTROL Edit content]** som beskrivs nedan.

>[!ENDTABS]

## Definiera ditt SMS-innehåll{#sms-content}

>[!CONTEXTUALHELP]
>id="ajo_message_sms_content"
>title="Definiera ditt SMS-innehåll"
>abstract="Anpassa och anpassa dina textmeddelanden genom att använda uttrycksredigeraren för att definiera innehållet och införliva dynamiska element."

Följ stegen nedan för att konfigurera ditt SMS-innehåll.

1. Klicka på **[!UICONTROL Edit content]** för att konfigurera textmeddelandets innehåll.

1. Klicka på **[!UICONTROL Message]** för att öppna uttrycksredigeraren.

   ![](assets/sms-content.png)

1. Använd uttrycksredigeraren för att definiera innehåll, lägga till personalisering och dynamiskt innehåll. Du kan använda alla attribut, till exempel profilnamnet eller stad. Du kan också definiera villkorliga regler. Bläddra till följande sidor om du vill veta mer om [personalisering](../personalization/personalize.md) och [dynamiskt innehåll](../personalization/get-started-dynamic-content.md) i uttrycksredigeraren.

1. När du har definierat innehållet kan du lägga till spårade URL:er i meddelandet. Om du vill göra det går du till **[!UICONTROL Helper functions]** meny och välj **[!UICONTROL Helpers]**.

   Observera att för att kunna använda funktionen för förkortning av URL-adresser måste du först konfigurera en underdomän som sedan länkas till din yta. [Läs mer](sms-subdomains.md)

   >[!CAUTION]
   >
   > Om du vill komma åt och redigera SMS-underdomäner måste du ha **[!UICONTROL Manage SMS Subdomains]** behörighet i produktionssandlådan. Läs mer om behörigheter i [det här avsnittet](../administration/high-low-permissions.md).

   ![](assets/sms_tracking_1.png)

1. I **[!UICONTROL Helper functions]** meny, klicka **[!UICONTROL URL function]** och sedan **[!UICONTROL Add URL]**.

   ![](assets/sms_tracking_2.png)

1. I `originalUrl` klistra in den URL som du vill förkorta och klicka på **[!UICONTROL Save]**.

1. Klicka **[!UICONTROL Save]** och kontrollera meddelandet i förhandsgranskningen. Nu kan du testa och kontrollera meddelandeinnehållet enligt [det här avsnittet](#sms-mms-test).

<!--
## Define your MMS content{#mms-content}

You can enhance your communication by sending Multimedia Message Service (MMS) messages, enabling the sharing of media such as videos, pictures, audio clips and GIFs, and more. Additionally, MMS allows for up to 1600 characters of text in your message.


>[!NOTE]
>
>* This feature is currently available with **Sinch** only.
>
>* MMS channel comes with a few limitations listed in [this page](../start/guardrails.md#sms-guardrails).
>

To create MMS content, follow these steps:

1. Create a SMS as described in [this section](#create-sms-journey-campaign).

1. Edit your SMS content as detailed in [this section](#sms-content).

1. Enable the MMS option to add media to your SMS content.

    ![](assets/sms_create_6.png)

1. Add a **[!UICONTROL Title]** to your media.

1. Enter the URL of your media in the **[!UICONTROL Media]** field.

    ![](assets/sms_create_7.png)

1. Click **[!UICONTROL Save]** and check your message in the preview. You can now test and check your message content as detailed below.
-->

## Testa och skicka meddelanden {#sms-mms-test}

Använd **[!UICONTROL Simulate content]** för att förhandsgranska textmeddelandeinnehåll, förkortade URL:er och anpassat innehåll.

![](assets/sms-content-preview.png)

När du har utfört testerna och validerat innehållet kan du skicka textmeddelandet till mottagarna. Dessa steg beskrivs i [den här sidan](send-sms.md)

När ni har skickat det kan ni mäta effekten av ert SMS i kampanjrapporten eller reserapporten. Mer information om rapportering finns i [det här avsnittet](../reports/campaign-global-report.md#sms-tab).

**Relaterade ämnen**

* [Förhandsgranska, testa och skicka ditt textmeddelande](send-sms.md)
* [Konfigurera SMS-kanal](sms-configuration.md)
* [SMS-rapporter](../reports/journey-global-report.md#sms-global)
* [Lägg till ett meddelande i en resa](../building-journeys/journeys-message.md)
* [Lägg till ett meddelande i en kampanj](../campaigns/create-campaign.md)
