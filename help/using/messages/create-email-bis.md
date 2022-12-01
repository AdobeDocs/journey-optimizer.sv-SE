---
solution: Journey Optimizer
product: journey optimizer
title: Skapa ett e-postmeddelande
description: Lär dig hur du skapar e-postmeddelanden i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: b7b333e96e0f4b32a0f94c3f1e67f0f3d3fc2816
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 5%

---

# Skapa ett e-postmeddelande {#create-email-bis}

Följ stegen nedan för att skapa ett e-postmeddelande.

## 1. Skapa ett e-postmeddelande i en resa eller kampanj

Lägg till en **[!UICONTROL Email]** till en resa eller en kampanj och följ stegen nedan utifrån ditt fall.

>[!BEGINTABS]

>[!TAB Lägg till ett e-postmeddelande till en resa]

1. Öppna din resa och dra och släpp en **[!UICONTROL Email]** aktivitet från **[!UICONTROL Actions]** på paletten.

1. Ange grundläggande information i meddelandet (etikett, beskrivning, kategori).

1. Välj [e-postyta] att använda.

   ![](assets/email_journey.png)

Mer information om hur du konfigurerar en resa finns i [den här sidan](../building-journeys/journey-gs.md).

>[!TAB Lägga till ett e-postmeddelande till en kampanj]

1. Skapa en ny schemalagd eller API-utlöst kampanj och välj **[!UICONTROL Email]** som er handling.

1. Välj [e-postyta] att använda.

   ![](assets/email_campaign.png)

1. Klicka på **[!UICONTROL Create]**.

1. Slutför stegen för att skapa en e-postkampanj.

   ![](assets/email_campaign_steps.png)

<!--
From the **[!UICONTROL Action]** section, specify if you want to track how your recipients react to your delivery: you can track email opens, and/or clicks on links and buttons in your email.

![](assets/email_campaign_tracking.png)
-->

Mer information om hur du konfigurerar en kampanj finns i [den här sidan](../campaigns/get-started-with-campaigns.md).

>[!ENDTABS]

## Definiera ditt e-postinnehåll

1. Klicka på **[!UICONTROL Edit content]** för att konfigurera e-postinnehållet. [Läs mer]

   ![](assets/email_campaign_edit_content.png)

1. I **[!UICONTROL Header]** i **[!UICONTROL Edit content]** skärm, **[!UICONTROL From name]**, **[!UICONTROL From email]** och **[!UICONTROL BCC]** fältet kommer från den e-postyta som du valde. [Läs mer] <!--check if same for journey-->

   ![](assets/email_designer_edit_content_header.png)

1. Du kan lägga till en ämnesrad. Skriv oformaterad text direkt i motsvarande fält eller använd [Uttrycksredigerare](../personalization/personalization-build-expressions.md) för att personalisera ämnesraden.

1. Klicka på **[!UICONTROL Edit email body]** för att börja bygga innehåll med [!DNL Journey Optimizer] E-postdesigner. [Läs mer]

   ![](assets/email_designer_edit_email_body.png)

   Du kan också klicka på **[!UICONTROL Code Editor]** om du vill koda ditt eget innehåll i HTML med hjälp av popup-fönstret som visas.

   ![](assets/email_designer_edit_code_editor.png)

   >[!NOTE]
   >
   >Om du redan har skapat eller importerat innehåll via e-postdesignern visas det här innehållet i HTML.

## Förhandsgranska din e-post

När meddelandeinnehållet har definierats kan du förhandsgranska det för att kontrollera återgivningen av ditt e-postmeddelande och kontrollera personaliseringsinställningarna med testprofiler. [Läs mer]

![](assets/email_designer_edit_simulate.png)

Du måste även kontrollera varningar i den övre delen av redigeraren.  Vissa av dem är enkla varningar, men andra kan hindra dig från att använda meddelandet. [Läs mer](alerts.md).

## Validera ditt e-postinnehåll

När din e-post är klar slutför du konfigurationen av [resa](../building-journeys/journey-gs.md) eller [kampanj](../campaigns/create-campaign.md) och aktivera för att skicka meddelandet.

>[!NOTE]
>
>Om du vill spåra mottagarnas beteende via e-postöppningar och/eller interaktioner kontrollerar du att de dedikerade alternativen i dialogrutan **[!UICONTROL Tracking]** -avsnittet är aktiverat i resans [e-postaktivitet](../building-journeys/journeys-message.md) eller i e-postmeddelandet [kampanj](../campaigns/create-campaign.md).

Du måste även kontrollera varningar i den övre delen av redigeraren.  Vissa av dem är enkla varningar, men andra kan hindra dig från att använda meddelandet. [Läs mer](alerts.md)

