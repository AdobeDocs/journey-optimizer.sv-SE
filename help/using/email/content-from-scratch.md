---
solution: Journey Optimizer
product: journey optimizer
title: Designa e-postmeddelanden i Journey Optimizer
description: Lär dig designa e-postinnehåll från grunden
feature: Overview
topic: Content Management
role: User
level: Intermediate
exl-id: 151594f2-85e4-4c79-9c15-334fbd3768c4
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 0%

---

# Börja från början {#content-from-scratch}

>[!CONTEXTUALHELP]
>id="ac_structure_components_email"
>title="Om strukturkomponenter"
>abstract="Strukturkomponenter definierar layouten för e-postmeddelandet."

>[!CONTEXTUALHELP]
>id="ac_structure_components_landing_page"
>title="Om strukturkomponenter"
>abstract="Strukturkomponenter definierar landningssidans layout."

>[!CONTEXTUALHELP]
>id="ac_structure_components_fragment"
>title="Om strukturkomponenter"
>abstract="Strukturkomponenter definierar fragmentets layout."

>[!CONTEXTUALHELP]
>id="ac_structure_components_template"
>title="Om strukturkomponenter"
>abstract="Strukturkomponenter definierar mallens layout."


>[!CONTEXTUALHELP]
>id="ac_edition_columns_email"
>title="Definiera e-postkolumner"
>abstract="Med e-postdesignern kan du enkelt definiera layouten för e-postmeddelandet genom att definiera kolumnstrukturen."

>[!CONTEXTUALHELP]
>id="ac_edition_columns_landing_page"
>title="Definiera landningssidans kolumner"
>abstract="Med e-postdesignern kan du enkelt definiera layouten för landningssidan genom att definiera kolumnstrukturen."

>[!CONTEXTUALHELP]
>id="ac_edition_columns_fragment"
>title="Definiera fragmentkolumner"
>abstract="Med e-postdesignern kan du enkelt definiera fragmentets layout genom att definiera kolumnstrukturen."

>[!CONTEXTUALHELP]
>id="ac_edition_columns_template"
>title="Definiera mallkolumner"
>abstract="Med e-postdesignern kan du enkelt definiera mallens layout genom att definiera kolumnstrukturen."


Med e-postdesignern kan du enkelt definiera e-postens struktur. Genom att lägga till och flytta strukturella element med enkla dra-och-släpp-åtgärder kan du designa formen på e-postmeddelandet på några sekunder.

Följ stegen nedan när du vill börja skapa e-postinnehåll:

1. På e-postdesignerns hemsida väljer du **[!UICONTROL Design from scratch]** alternativ.

   ![](assets/email_designer.png)

1. Börja designa e-postinnehåll genom att dra och släppa **[!UICONTROL Structure components]** på arbetsytan för att definiera layouten för e-postmeddelandet.

   >[!NOTE]
   >
   >Det går inte att stapla kolumner i alla e-postprogram. Om det inte finns stöd för det här alternativet staplas inte kolumner.

   <!--Once placed in the email, you cannot move nor remove your components unless there is already a content component or a fragment placed inside. This is not true in AJO - TBC?-->

1. Lägg till så många **[!UICONTROL Structure components]** vid behov och redigera inställningarna i den dedikerade rutan till höger.

   ![](assets/email_designer_structure_components.png)

   Välj **[!UICONTROL n:n column]** -komponent för att definiera hur många kolumner du vill ha (mellan 3 och 10). Du kan också definiera bredden på varje kolumn genom att flytta pilarna längst ned i varje kolumn.

   ![](assets/email_designer_structure_n-n-colum.png)

   >[!NOTE]
   >
   >Varje kolumnstorlek får inte vara mindre än 10 % av strukturkomponentens totala bredd. Du kan inte ta bort en kolumn som inte är tom.

1. Expandera **[!UICONTROL Content components]** och lägg till så många element du behöver i en eller flera strukturkomponenter. [Läs mer om innehållskomponenter](content-components.md)

1. Varje komponent kan anpassas ytterligare med **[!UICONTROL Component settings]** till höger. Du kan till exempel ändra textstil, utfyllnad eller marginal för varje komponent. [Läs mer om justering och utfyllnad](alignment-and-padding.md)

   ![](assets/email_designer_structure_component.png)

1. Från **[!UICONTROL Asset picker]** kan du välja resurser som lagras i **[!UICONTROL Assets library]**. [Läs mer om resurshantering](assets-essentials.md)

   Dubbelklicka på den mapp som innehåller dina resurser. Dra och släpp dem i en strukturkomponent.

   ![](assets/email_designer_asset_picker.png)

1. Infoga anpassningsfält för att anpassa ditt e-postinnehåll från profildata. [Läs mer om innehållspersonalisering](../personalization/personalize.md)

   ![](assets/email_designer_personalization.png)

1. Lägg till dynamiskt innehåll för att anpassa innehållet till målprofilerna baserat på villkorliga regler. [Kom igång med dynamiskt innehåll](../personalization/get-started-dynamic-content.md)

   ![](assets/email_designer_dynamic-content.png)

1. Klicka på **[!UICONTROL Links]** från den vänstra panelen för att visa alla URL:er för ditt innehåll som ska spåras. Du kan ändra deras **[!UICONTROL Tracking Type]** eller **[!UICONTROL Label]** och lägga till **[!UICONTROL Tags]** vid behov. [Läs mer om länkar och meddelandespårning](message-tracking.md)

   ![](assets/email_designer_links.png)

1. Om det behövs kan du anpassa e-postmeddelandet ytterligare genom att klicka på **[!UICONTROL Switch to code editor]** på den avancerade menyn. [Läs mer om kodredigeraren](code-content.md)

   ![](assets/email_designer_switch-to-code.png)

   >[!CAUTION]
   >
   >Du kan inte återgå till den visuella designern för det här e-postmeddelandet efter att du har växlat till kodredigeraren.

1. När innehållet är klart klickar du på **[!UICONTROL Simulate content]** för att kontrollera din e-poståtergivning. Du kan välja skrivbordsvy eller mobilvy. [Läs mer om hur du förhandsgranskar ditt e-postmeddelande](preview.md)

   ![](assets/email_designer_simulate_content.png)

1. När e-postmeddelandet är klart klickar du på **[!UICONTROL Save]**.
