---
solution: Journey Optimizer
product: journey optimizer
title: Designa material från grunden i Journey Optimizer
description: Lär dig designa ditt innehåll från grunden
feature: Email Design
topic: Content Management
role: User
level: Beginner, Intermediate
keywords: innehåll, redigerare, e-post, börja
exl-id: 151594f2-85e4-4c79-9c15-334fbd3768c4
source-git-commit: 27447578dad6bd2612989d79cd0dc8ddbe78d629
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 0%

---

# Designa innehåll från grunden {#content-from-scratch}

>[!CONTEXTUALHELP]
>id="ac_structure_components_email"
>title="Lägg till strukturkomponenter"
>abstract="Strukturkomponenter definierar layouten för e-postmeddelandet. Dra och släpp en **Struktur** på arbetsytan för att börja designa ditt e-postinnehåll."

>[!CONTEXTUALHELP]
>id="ac_structure_components_landing_page"
>title="Lägg till strukturkomponenter"
>abstract="Strukturkomponenter definierar landningssidans layout. Dra och släpp en **Struktur** till arbetsytan för att börja designa innehållet på landningssidan."

>[!CONTEXTUALHELP]
>id="ac_structure_components_fragment"
>title="Lägg till strukturkomponenter"
>abstract="Strukturkomponenter definierar fragmentets layout. Dra och släpp en **Struktur** till arbetsytan för att börja designa innehållet i fragmentet."

>[!CONTEXTUALHELP]
>id="ac_structure_components_template"
>title="Lägg till strukturkomponenter"
>abstract="Strukturkomponenter definierar mallens layout. Dra och släpp en **Struktur** på arbetsytan för att börja designa innehållet i mallen."


>[!CONTEXTUALHELP]
>id="ac_edition_columns_email"
>title="Definiera e-postkolumner"
>abstract="Med e-postdesignern kan du enkelt definiera layouten för e-postmeddelandet genom att välja kolumnstrukturen."

>[!CONTEXTUALHELP]
>id="ac_edition_columns_landing_page"
>title="Definiera landningssidans kolumner"
>abstract="Med Designer kan du enkelt definiera layouten för landningssidan genom att välja kolumnstrukturen."

>[!CONTEXTUALHELP]
>id="ac_edition_columns_fragment"
>title="Definiera fragmentkolumner"
>abstract="Med Designer kan du enkelt definiera fragmentets layout genom att välja kolumnstrukturen."

>[!CONTEXTUALHELP]
>id="ac_edition_columns_template"
>title="Definiera mallkolumner"
>abstract="Med Designer kan du enkelt definiera mallens layout genom att välja kolumnstrukturen."


Använd Adobe Journey Optimizer Designer för att enkelt definiera innehållsstrukturen. Genom att lägga till och flytta strukturella element med enkla dra och släpp-åtgärder kan du designa formen på innehållet på några sekunder.

Följ stegen nedan när du vill börja skapa ditt innehåll:

1. På startsidan för Designer väljer du **[!UICONTROL Design from scratch]** alternativ.

   ![](assets/email_designer.png)

1. Börja designa ditt innehåll genom att dra och släppa **[!UICONTROL Structures]** på arbetsytan för att definiera layouten för e-postmeddelandet.

   >[!NOTE]
   >
   >Det går inte att stapla kolumner i alla e-postprogram. Om det inte finns stöd för det här alternativet staplas inte kolumner.

   <!--Once placed in the email, you cannot move nor remove your components unless there is already a content component or a fragment placed inside. This is not true in AJO - TBC?-->

1. Lägg till så många **[!UICONTROL Structures]** vid behov och redigera inställningarna i den dedikerade rutan till höger.

   ![](assets/email_designer_structure_components.png)

   Välj **[!UICONTROL n:n column]** -komponent för att definiera hur många kolumner du vill ha (mellan 3 och 10). Du kan också definiera bredden på varje kolumn genom att flytta pilarna längst ned i varje kolumn.

   >[!NOTE]
   >
   >Varje kolumnstorlek får inte vara mindre än 10 % av strukturkomponentens totala bredd. Du kan inte ta bort en kolumn som inte är tom.

1. Expandera **[!UICONTROL Contents]** och lägg till så många element du behöver i en eller flera strukturkomponenter. [Läs mer om innehållskomponenter](content-components.md)

1. Varje komponent kan anpassas ytterligare med **[!UICONTROL Settings]** eller **[!UICONTROL Style]** i den högra menyn. Du kan till exempel ändra textstil, utfyllnad eller marginal för varje komponent. [Läs mer om justering och utfyllnad](alignment-and-padding.md)

   ![](assets/email_designer_structure_component.png)

1. Från **[!UICONTROL Asset picker]** kan du välja resurser som lagras i **[!UICONTROL Assets library]**. [Läs mer om resurshantering](../content-management/assets-essentials.md)

   Dubbelklicka på den mapp som innehåller dina resurser. Dra och släpp dem i en strukturkomponent.

   ![](assets/email_designer_asset_picker.png)

1. Infoga anpassningsfält för att anpassa innehållet utifrån profilattribut, målgruppsmedlemskap, sammanhangsbaserade attribut med mera. [Läs mer om innehållspersonalisering](../personalization/personalize.md)

   ![](assets/email_designer_personalization.png)

1. Klicka **[!UICONTROL Enable condition content]** för att lägga till dynamiskt innehåll och anpassa innehållet till målprofilerna baserat på villkorliga regler. [Kom igång med dynamiskt innehåll](../personalization/get-started-dynamic-content.md)

   ![](assets/email_designer_dynamic-content.png)

1. Klicka på **[!UICONTROL Links]** från den vänstra panelen för att visa alla URL:er för ditt innehåll som ska spåras. Du kan ändra deras **[!UICONTROL Tracking Type]** eller **[!UICONTROL Label]** och lägga till **[!UICONTROL Tags]** vid behov. [Läs mer om länkar och spårning](message-tracking.md)

   ![](assets/email_designer_links.png)

1. Om det behövs kan du anpassa e-postmeddelandet ytterligare genom att klicka på **[!UICONTROL Switch to code editor]** på den avancerade menyn. På så sätt kan du redigera e-postkällkoden, till exempel för att lägga till spårningstaggar eller anpassade HTML-taggar. [Läs mer om kodredigeraren](code-content.md)

   >[!CAUTION]
   >
   >Du kan inte återgå till den visuella designern för det här e-postmeddelandet efter att du har växlat till kodredigeraren.

1. Klicka på **[!UICONTROL Simulate content]** för att kontrollera återgivningen. Du kan välja skrivbordsvy eller mobilvy. Detaljerad information om hur du väljer testprofiler och förhandsgranskar innehållet finns i [Innehållshantering](../content-management/preview-test.md) -avsnitt.

   ![](assets/email_designer_simulate_content.png)

1. När innehållet är klart klickar du **[!UICONTROL Save]**.
