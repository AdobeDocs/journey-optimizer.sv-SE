---
solution: Journey Optimizer
product: journey optimizer
title: Skapa ett e-postmeddelande
description: Lär dig hur du skapar ett e-postmeddelande i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
keywords: skapa, e-post, start, resa, kampanj
exl-id: c77dc420-a375-4376-ad86-ac740e214c3c
source-git-commit: 803c9f9f05669fad0a9fdeeceef58652b6dccf70
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 3%

---

# Skapa ett e-postmeddelande {#create-email}

>[!CONTEXTUALHELP]
>id="ajo_message_email"
>title="Skapa e-post"
>abstract="Definiera e-postparametrar i endast tre enkla steg."

Skapa ett e-postmeddelande i [!DNL Journey Optimizer]följer du stegen nedan.

## Skapa ett e-postmeddelande i en resa eller kampanj {#create-email-journey-campaign}

Lägg till en **[!UICONTROL Email]** till en resa eller en kampanj och följ stegen nedan utifrån ditt fall.

>[!BEGINTABS]

>[!TAB Lägg till ett e-postmeddelande till en resa]

1. Öppna din resa och dra och släpp en **[!UICONTROL Email]** aktivitet från **[!UICONTROL Actions]** på paletten.

1. Ange grundläggande information i meddelandet (etikett, beskrivning, kategori).

1. Välj [e-postyta](email-settings.md) att använda.

   ![](assets/email_journey.png)

   Fältet är som standard förifyllt med den sista ytan som används av användaren för den kanalen.

>[!NOTE]
>
>Om du skickar ett e-postmeddelande från en resa kan du utnyttja Adobe Journey Optimizer funktion för optimering av sändningstid för att förutsäga den bästa tidpunkten för att skicka meddelandet för att maximera engagemanget baserat på tidigare öppnings- och klickfrekvenser. [Lär dig hur du arbetar med optimering vid sändning](../building-journeys/journeys-message.md#send-time-optimization)

Mer information om hur du konfigurerar en resa finns i [den här sidan](../building-journeys/journey-gs.md).

>[!TAB Lägga till ett e-postmeddelande till en kampanj]

1. Skapa en ny schemalagd eller API-utlöst kampanj och välj **[!UICONTROL Email]** som er handling.

1. Välj [e-postyta](email-settings.md) att använda.

   ![](assets/email_campaign.png)

1. Klicka på **[!UICONTROL Create]**.

1. Slutför stegen för att skapa en e-postkampanj, till exempel kampanjegenskaperna, [publik](../segment/about-segments.md)och [schema](../campaigns/create-campaign.md#schedule).

   ![](assets/email_campaign_steps.png)

<!--
From the **[!UICONTROL Action]** section, specify if you want to track how your recipients react to your delivery: you can track email opens, and/or clicks on links and buttons in your email.

![](assets/email_campaign_tracking.png)
-->

Mer information om hur du konfigurerar en kampanj finns i [den här sidan](../campaigns/get-started-with-campaigns.md).

>[!ENDTABS]

## Definiera ditt e-postinnehåll {#define-email-content}

<!-- update the quarry component with right ID value-->

>[!CONTEXTUALHELP]
>id="test_id"
>title="Konfigurera e-postinnehåll"
>abstract="Skapa innehållet i e-postmeddelandet. Definiera ämnet och använd sedan e-postdesignern för att skapa och anpassa e-postmeddelandets brödtext."

1. Klicka på **[!UICONTROL Edit content]** för att konfigurera e-postinnehållet. [Läs mer](get-started-email-design.md)

   ![](assets/email_campaign_edit_content.png)

1. I **[!UICONTROL Header]** i **[!UICONTROL Edit content]** skärm, **[!UICONTROL From name]**, **[!UICONTROL From email]** och **[!UICONTROL BCC]** fältet kommer från den e-postyta som du valde. [Läs mer](email-settings.md) <!--check if same for journey-->

   ![](assets/email_designer_edit_content_header.png)

1. Du kan lägga till en ämnesrad. Skriv oformaterad text direkt i motsvarande fält eller använd [Uttrycksredigerare](../personalization/personalization-build-expressions.md) för att personalisera ämnesraden.

1. Klicka på **[!UICONTROL Edit email body]** för att börja bygga innehåll med [!DNL Journey Optimizer] E-postdesigner. [Läs mer](get-started-email-design.md)

   ![](assets/email_designer_edit_email_body.png)

1. Om du deltar i en kampanj kan du även klicka på **[!UICONTROL Code Editor]** om du vill koda ditt eget innehåll i HTML med hjälp av popup-fönstret som visas.

   ![](assets/email_designer_edit_code_editor.png)

   >[!NOTE]
   >
   >Om du redan har skapat eller importerat innehåll via e-postdesignern visas det här innehållet i HTML.

## Kontrollera aviseringar {#check-email-alerts}

När du utformar meddelanden visas varningar i gränssnittet (längst upp till höger på skärmen) när nyckelinställningarna saknas.

![](assets/email_journey_alerts_details.png)

>[!NOTE]
>
>Om knappen inte visas har ingen varning identifierats.

De inställningar och element som kontrolleras av systemet visas nedan. Du hittar även information om hur du anpassar konfigurationen för att lösa motsvarande problem.

Två typer av varningar kan inträffa:

* **Varningar** hänvisa till rekommendationer och bästa praxis, t.ex.

   * **[!UICONTROL The opt-out link is not present in the email body]**: det är bra att lägga till en länk för att avbryta prenumerationen i e-postmeddelandet. Lär dig hur du konfigurerar det i [det här avsnittet](../privacy/opt-out.md#opt-out-management).

      >[!NOTE]
      >
      >E-postmeddelanden av marknadsföringstyp måste innehålla en länk för avanmälan, vilket inte krävs för transaktionsmeddelanden. Meddelandekategorin (**[!UICONTROL Marketing]** eller **[!UICONTROL Transactional]**) definieras i [kanalyta](email-settings.md#email-type) nivå och när [skapar meddelandet](#create-email-journey-campaign) från en resa eller en kampanj.

   * **[!UICONTROL Text version of HTML is empty]**: Glöm inte att definiera en textversion av e-posttexten, eftersom den kommer att användas när HTML inte kan visas. Lär dig hur du skapar textversionen i [det här avsnittet](text-version-email.md).

   * **[!UICONTROL Empty link is present in email body]**: kontrollera att alla länkar i e-postmeddelandet är korrekta. Lär dig hantera innehåll och länkar i [det här avsnittet](content-from-scratch.md).

   * **[!UICONTROL Email size has exceeded the limit of 100KB]**: för optimal leverans bör du kontrollera att e-postens storlek inte överstiger 100 kB. Lär dig hur du redigerar e-postinnehåll i [det här avsnittet](content-from-scratch.md).

* **Fel** hindra dig från att testa eller aktivera resan/kampanjen så länge som de inte är lösta, till exempel:

   * **[!UICONTROL The subject line is missing]**: Ämnesraden för e-post är obligatorisk. Lär dig definiera och personalisera det i [det här avsnittet](create-email.md).

   <!--HTML is empty when Amp HTML is present-->

   * **[!UICONTROL The email version of the message is empty]**: det här felet visas när e-postinnehållet inte har konfigurerats. Lär dig designa e-postinnehåll i [det här avsnittet](get-started-email-design.md).

   * **[!UICONTROL Surface doesn't exist]**: Du kan inte använda meddelandet om den yta som du har markerat tas bort efter att meddelandet har skapats. Om det här felet inträffar väljer du en annan yta i meddelandet **[!UICONTROL Properties]**. Läs mer om kanalytor i [det här avsnittet](../configuration/channel-surfaces.md).


>[!CAUTION]
>
>För att kunna testa eller aktivera resan/kampanjen med e-postmeddelandet måste du lösa alla **fel** varningar.

## Förhandsgranska och skicka e-post

När meddelandeinnehållet har definierats kan du förhandsgranska det för att kontrollera återgivningen av ditt e-postmeddelande och kontrollera personaliseringsinställningarna med testprofiler. [Läs mer](preview.md)

![](assets/email_designer_edit_simulate.png)

När din e-post är klar slutför du konfigurationen av [resa](../building-journeys/journey-gs.md) eller [kampanj](../campaigns/create-campaign.md)och aktivera det för att skicka meddelandet.

>[!NOTE]
>
>Om du vill spåra mottagarnas beteende via e-postöppningar och/eller interaktioner kontrollerar du att de dedikerade alternativen i dialogrutan **[!UICONTROL Tracking]** -avsnittet är aktiverat i resans [e-postaktivitet](../building-journeys/journeys-message.md) eller i e-postmeddelandet [kampanj](../campaigns/create-campaign.md).<!--to move?-->

<!--

## Define your email content {#email-content}

Use [!DNL Journey Optimizer] Email Designer to [design your email from scratch](../email/content-from-scratch.md). If you have an existing content, you can [import it in the Email Designer](../email/existing-content.md), or [code your own content](../email/code-content.md) in [!DNL Journey Optimizer]. 

[!DNL Journey Optimizer] comes with a set of [built-in templates](email-templates.md) to help you start. Any email can also be saved as a template.

Use [!DNL Journey Optimizer] Expression editor to personalize your messages with profiles' data. For more on personalization, refer to [this section](../personalization/personalize.md).

Adapt the content of your messages to the targeted profiles by using [!DNL Journey Optimizer] dynamic content capabilities. [Get started with dynamic content](../personalization/get-started-dynamic-content.md)

## Email tracking {#email-tracking}

If you want to track the behavior of your recipients through openings and/or clicks on links, enable the following options: **[!UICONTROL Email opens]** and **[!UICONTROL Click on email]**. 

Learn more about tracking in [this section](message-tracking.md).

## Validate your email content {#email-content-validate}

Control the rendering of your email, and check personalization settings with test profiles, using the preview section on the left-hand side. For more on this, refer to [this section](preview.md).

![](assets/messages-simple-preview.png)

You must also check alerts in the upper section of the editor.  Some of them are simple warnings, but others can prevent you from using the message. 

-->

