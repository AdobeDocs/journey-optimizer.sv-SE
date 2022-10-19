---
solution: Journey Optimizer
product: journey optimizer
title: Skapa ett e-postmeddelande
description: Lär dig hur du skapar e-postmeddelanden i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: c77dc420-a375-4376-ad86-ac740e214c3c
source-git-commit: 63c52f04da9fd1a5fafc36ffb5079380229f885e
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 4%

---

# Skapa ett e-postmeddelande {#configure-email}

>[!CONTEXTUALHELP]
>id="ajo_message_email"
>title="Skapa e-post"
>abstract="Definiera e-postparametrar i endast tre enkla steg."

Du kan skapa e-postmeddelanden:

* I en **Resa**: När du har lagt till en e-postaktivitet under resan och definierat grundläggande inställningar använder du **[!UICONTROL Actions: Email]** till höger för att skapa innehåll för push-meddelanden.

   Mer information om hur du konfigurerar din resa finns i [page](../building-journeys/journey-gs.md).

   ![](assets/email-edit-content.png)

* I en **Campaign**: När du har skapat en kampanj väljer du E-post som åtgärd och definierar grundläggande inställningar.

   Mer information om hur du konfigurerar kampanjen finns i [page](../campaigns/create-campaign.md#configure).

   ![](assets/email_campaign.png)

## Definiera ditt e-postinnehåll{#email-content}

Använd [!DNL Journey Optimizer] E-postdesigner till [designa din e-post från grunden](../design/create-email-content.md). Om du har ett befintligt innehåll kan du [importera det till e-postdesignern](../design/existing-content.md), eller [koda eget innehåll](../design/code-content.md) in [!DNL Journey Optimizer].

[!DNL Journey Optimizer] innehåller en uppsättning [inbyggda mallar](../design/email-templates.md) för att hjälpa dig att komma igång. Alla e-postmeddelanden kan också sparas som mallar.

Använd [!DNL Journey Optimizer] Uttrycksredigeraren för att anpassa dina meddelanden med profildata. Mer information om personalisering finns i [det här avsnittet](../personalization/personalize.md).

Anpassa innehållet i era meddelanden till målprofilerna genom att utnyttja [!DNL Journey Optimizer] funktioner för dynamiskt innehåll. [Kom igång med dynamiskt innehåll](../personalization/get-started-dynamic-content.md)

## E-postspårning{#email-tracking}

Aktivera följande alternativ om du vill spåra mottagarnas beteende genom att öppna och/eller klicka på länkar: **[!UICONTROL Email opens]** och **[!UICONTROL Click on email]**.

Läs mer om spårning i [det här avsnittet](../design/message-tracking.md).

## Validera ditt e-postinnehåll{#email-content-validate}

Styr återgivningen av e-postmeddelandet och kontrollera personaliseringsinställningarna med testprofiler med förhandsgranskningsavsnittet till vänster. Mer information om detta finns i [det här avsnittet](../design/preview.md).

![](assets/messages-simple-preview.png)


Du måste även kontrollera varningar i den övre delen av redigeraren.  Vissa av dem är enkla varningar, men andra kan hindra dig från att använda meddelandet. Läs mer i [det här avsnittet](alerts.md).


>[!NOTE]
>
>The **[!UICONTROL From email]** och **[!UICONTROL From name]** bestäms av **[!UICONTROL Surface]** som har markerats när [skapar meddelandet](get-started-content.md).

