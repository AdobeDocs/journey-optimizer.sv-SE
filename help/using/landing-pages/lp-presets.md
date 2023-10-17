---
solution: Journey Optimizer
product: journey optimizer
title: Definiera förinställningar för landningssidor
description: Lär dig konfigurera miljön för att skapa och använda landningssidor med Journey Optimizer
feature: Landing Pages, Channel Configuration
role: Admin
level: Experienced
keywords: landning, landningssida, konfigurera, miljö, underdomän, förinställningar
exl-id: 7cf1f083-bef0-40b5-8ddd-920a9d108eca
source-git-commit: 8579acfa881f29ef3947f6597dc11d4c740c3d68
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 2%

---

# Definiera förinställningar för landningssidor {#lp-presets}

>[!CONTEXTUALHELP]
>id="ajo_admin_config_lp_subdomain_header"
>title="Skapa en förinställning för landningssida"
>abstract="För att kunna bygga en landningssida och använda den via Journey Optimizer måste du skapa en förinställning för landningssidan som innehåller den underdomän som ska användas."

När [skapa en landningssida](../landing-pages/create-lp.md#create-a-lp)måste du välja en förinställning för landningssidan för att kunna bygga landningssidan och använda den **[!DNL Journey Optimizer]**.

## Åtkomst till förinställningar för landningssidor {#access-lp-presets}

Följ stegen nedan för att få tillgång till förinställningarna för landningssidan.

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** -menyn.

1. Välj **[!UICONTROL Branding]** > **[!UICONTROL Landing page presets]**.

   ![](assets/lp_presets-access.png)

1. Klicka på en förinställd etikett för att komma åt förinställningsinformationen för landningssidan.

   ![](assets/lp_preset-details.png)

## Skapa en förinställning för landningssida {#lp-create-preset}

Följ stegen nedan för att skapa en förinställning för landningssidan.

>[!NOTE]
>
>För att kunna skapa en förinställning måste du kontrollera att du tidigare har konfigurerat minst en underdomän för landningssida. [Lär dig mer](lp-subdomains.md)

1. Öppna **[!UICONTROL Administration]** > **[!UICONTROL Channels]** väljer du **[!UICONTROL Branding]** > **[!UICONTROL Landing page presets]**.

1. Välj **[!UICONTROL Create landing page preset]**.

   ![](assets/lp_create-preset-temp.png)

1. Ange ett namn och en beskrivning för förinställningen.

   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt`.` och bindestreck `-` tecken.

1. Välj en underdomän för landningssida i listrutan.

   ![](assets/lp_preset-subdomain.png)

   >[!NOTE]
   >
   >Om du vill kunna välja en underdomän kontrollerar du att du tidigare har konfigurerat minst en underdomän för landningssida. [Lär dig mer](#lp-subdomains)

   De inställningar som motsvarar den valda underdomänens visning.

1. Om du vill välja landningssidans underdomän för spårnings-URL:en kontrollerar du **[!UICONTROL Same as landing page subdomain]** alternativ. [Läs mer om spårning](../email/message-tracking.md)

   ![](assets/lp_preset-subdomain-settings-same.png)

   Om till exempel landningssidans URL är pages.mail.luma.com och spårnings-URL:en är data.mail.luma.com kan du välja pages.mail.luma.com som ska användas som spårningsunderdomän.

1. Klicka **[!UICONTROL Submit]** för att bekräfta att förinställningen för landningssidan har skapats. <!--You can also save the preset as draft and resume its configuration later on.-->

   <!--![](assets/lp_preset-subdomain-settings-submit.png)-->

1. När förinställningen för landningssidan har skapats visas den i listan med **[!UICONTROL Active]** status. Den är klar att användas för dina landningssidor.

   ![](assets/lp-preset-active-temp.png)

Du är nu redo att [skapa landningssidor](../landing-pages/create-lp.md) in [!DNL Journey Optimizer].
<!--
>[!NOTE]
>
>Learn how to create channel surfaces for push notifications and emails in [this section](channel-surfaces.md).-->

**Relaterade ämnen**:

* [Kom igång med landningssidor](../landing-pages/get-started-lp.md)
* [Skapa en landningssida](../landing-pages/create-lp.md#create-a-lp)
