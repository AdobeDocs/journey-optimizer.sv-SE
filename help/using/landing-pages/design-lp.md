---
title: Utforma en landningssida
description: Lär dig hur du utformar innehållet på en landningssida i Journey Optimizer
feature: Landing Pages
topic: Content Management
role: User
level: Beginner
exl-id: c61b8d80-17e1-4fdd-a739-efcee032dc23
source-git-commit: 40c42303b8013c1d9f4dd214ab1acbec2942e094
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 0%

---

# Utforma innehållet på landningssidan {#design-lp-content}

Börja skapa innehåll för landningen [primär sida](create-lp.md#configure-primary-page) eller [undersida](create-lp.md#configure-subpages)håller du muspekaren över det primära sidinnehållet och klickar **[!UICONTROL Open Designer]**. Du kan också klicka på motsvarande knapp på den högra paletten.

![](assets/lp_open-designer.png)

Därifrån kan man

* **Designa landningssidan från grunden** genom innehållsdesignerns gränssnitt och utnyttja bilder från [Adobe Experience Manager Assets Essentials](../design/assets-essentials.md). Lär dig hur du utformar innehåll eller använder inbyggda mallar [i det här avsnittet](../design/create-email-content.md).

* **Kod eller klistra in Raw HTML** direkt in i innehållsdesignern. Lär dig koda eget innehåll [i det här avsnittet](../design/code-content.md).

* **Importera befintligt HTML-innehåll** från en fil eller en ZIP-mapp. Lär dig importera innehåll [i det här avsnittet](../design/existing-content.md).

>[!NOTE]
>
>Innehållsdesignern för landningssidan liknar oftast e-postdesignern. Läs mer på [designa innehåll med [!DNL Journey Optimizer]](../design/design-emails.md).

## Definiera landningssidspecifikt innehåll {#define-lp-specific-content}

Följ stegen nedan för att definiera specifikt innehåll som gör det möjligt för användare att välja och skicka sina val från din landningssida.

1. Dra och släpp den specifika landningssidan **[!UICONTROL Form]** från den vänstra paletten till huvudarbetsytan.

   ![](assets/lp_designer-form-component.png)

   >[!NOTE]
   >
   >The **[!UICONTROL Form]** -komponenten kan bara användas en gång på samma sida.

1. Markera den. The **[!UICONTROL Form content]** visas på den högra paletten så att du kan redigera de olika fälten i formuläret.

   ![](assets/lp_designer-form-content-options.png)

   >[!NOTE]
   >
   >Växla till **[!UICONTROL Form style]** när som helst för att redigera formaten för formulärkomponentens innehåll. [Läs mer](#define-lp-styles)

1. Från **[!UICONTROL Checkbox 1]** kan du redigera etiketten för den här kryssrutan.

1. Ange om den här kryssrutan ska avanmäla användare till eller från: samtycker de till att ta emot meddelanden eller ber de att inte bli kontaktade längre?

   ![](assets/lp_designer-form-update.png)

1. Välj vad som ska uppdateras mellan följande tre alternativ:

   ![](assets/lp_designer-form-update-options.png)

   * **[!UICONTROL Subscription list]**: Du måste välja den prenumerationslista som ska uppdateras om profilen markerar den här kryssrutan. Läs mer på [prenumerationslistor](subscription-list.md).

      ![](assets/lp_designer-form-subs-list.png)

   * **[!UICONTROL Channel (email)]**: Avanmälningen eller avanmälningen gäller hela kanalen. Om en profil som avanmäls till exempel har två e-postadresser, kommer båda adresserna att uteslutas från all kommunikation.

   * **[!UICONTROL Email identity]**: Avanmälan eller avanmälan gäller endast den e-postadress som användes för att få åtkomst till landningssidan. Om en profil till exempel har två e-postadresser kommer bara den som användes att välja att ta emot meddelanden från varumärket.

1. Klicka **[!UICONTROL Add field]** > **[!UICONTROL Checkbox]** om du vill lägga till ytterligare en kryssruta. Upprepa stegen ovan för att definiera dess egenskaper.

   ![](assets/lp_designer-form-checkbox-2.png)

1. När du har lagt till alla önskade kryssrutor klickar du på **[!UICONTROL Call to action]** för att expandera motsvarande avsnitt. Här kan du definiera hur knappen ska fungera i **[!UICONTROL Form]** -komponenten.

   ![](assets/lp_designer-form-call-to-action.png)

1. Definiera vad som ska hända när du klickar på knappen:

   * **[!UICONTROL Redirect URL]**: Ange URL-adressen till sidan som användarna ska omdirigeras till.
   * **[!UICONTROL Confirmation text]**: Skriv den bekräftelsetext som ska visas.
   * **[!UICONTROL Link to a subpage]**: Konfigurera en [undersida](create-lp.md#configure-subpages) och välj den i listrutan som visas.

   ![](assets/lp_designer-form-confirmation-action.png)

1. Definiera vad som ska hända när du klickar på knappen om ett fel inträffar:

   * **[!UICONTROL Redirect URL]**: Ange URL-adressen till sidan som användarna ska omdirigeras till.
   * **[!UICONTROL Error text]**: Skriv den feltext som ska visas. Du kan förhandsgranska feltexten när du definierar [formulärformat](#define-lp-styles).

   * **[!UICONTROL Link to a subpage]**: Konfigurera en [undersida](create-lp.md#configure-subpages) och välj den i listrutan som visas.

   ![](assets/lp_designer-form-error.png)

1. Om du vill göra ytterligare uppdateringar när du skickar formuläret väljer du **[!UICONTROL Opt in]** eller **[!UICONTROL Opt out]** och ange om du vill uppdatera en prenumerationslista, kanalen eller bara den e-postadress som används.

   ![](assets/lp_designer-form-additionnal-update.png)

1. Spara innehållet och klicka på pilen bredvid sidnamnet för att gå tillbaka till [egenskaper för landningssida](create-lp.md#configure-primary-page).

   ![](assets/lp_designer-form-save.png)

<!--Will the name Email Designer be kept if you can also design LP with the same tool? > To modify in Messages section > content designer or Designer-->

## Definiera format för landningssidor {#define-lp-styles}

1. Om du vill ändra formaten för formulärkomponentens innehåll växlar du när som helst till **[!UICONTROL Form style]** -fliken.

   ![](assets/lp_designer-form-style.png)

1. Expandera **[!UICONTROL Checkboxes]** för att definiera utseendet på kryssrutorna och motsvarande text. Du kan till exempel justera teckensnittsfamiljen eller storleken och kryssrutans kantlinjefärg.

   ![](assets/lp_designer-form-style-checkboxes.png)

1. Expandera **[!UICONTROL Buttons]** för att ändra utseendet på knappen i komponentformuläret. Du kan till exempel lägga till en kant, redigera etikettfärgen vid hovring eller justera justeringen av knappen.

   ![](assets/lp_designer-form-style-buttons.png)

   Du kan förhandsgranska vissa inställningar, t.ex. knappetikettfärg vid hovring med hjälp av **[!UICONTROL Preview]** -knappen. Läs mer om testning av landningssidor [här](create-lp.md#test-landing-page).

   ![](assets/lp_designer-form-style-buttons-preview.png)

1. Expandera **[!UICONTROL Form layout]** om du vill redigera layoutinställningar som bakgrundsfärg, utfyllnad eller marginal.

   ![](assets/lp_designer-form-style-layout.png)

1. Expandera **[!UICONTROL Form error]** för att justera visningen av felmeddelandet som visas om ett problem uppstår. Markera motsvarande alternativ för att förhandsgranska feltexten i formuläret.

   ![](assets/lp_designer-form-error-preview.png)

