---
solution: Journey Optimizer
product: journey optimizer
title: Dynamiska medier
description: Använd dynamiska medier med Journey Optimizer
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
badge: label="Beta" type="Informative"
exl-id: 3e777cc5-a935-4e68-9de7-60b241e78f63
source-git-commit: 3a10f8440515bd569f9def6d15ac74d57427c1cf
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---

# Arbeta med Dynamic Media {#aem-dynamic}

>[!AVAILABILITY]
>
>Den här integreringen är exklusiv för kunder som använder Dynamic Media Manager as a Cloud Service.

Resursväljaren har nu stöd för dynamiska medier, vilket gör att du sömlöst kan välja och använda godkända dynamiska medierenderingar i Journey Optimizer. Ändringar som görs i Adobe Experience Manager återspeglas direkt i ditt Journey Optimizer-innehåll, vilket säkerställer att de senaste versionerna alltid används utan att manuella uppdateringar krävs.

Mer information om Dynamic Media i Adobe Experience Manager as a Cloud Service finns i [Experience Manager-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/dynamicmedia/dynamic-media).

## Lägga till och hantera dynamiska medier

Förbättra och optimera materialet för alla skärmar och webbläsare genom att infoga dynamiska medier från Adobe Experience Manager as a Cloud Service direkt i Journey Optimizer-materialet.  Du kan sedan ändra storlek, beskära, förbättra och göra andra justeringar efter behov.

1. Dra och släpp en **[!UICONTROL HTML component]** i ditt innehåll.

1. Välj **[!UICONTROL Show the source code]**.

   ![](assets/dynamic-media-1.png)

1. Navigera till **[!UICONTROL Assets]** på menyn **[!UICONTROL Edit HTML]** och klicka sedan på **[!UICONTROL Open asset selector]**.

   Du kan också kopiera och klistra in resursens URL.

   ![](assets/dynamic-media-2.png)

1. Bläddra bland dina AEM-resurser och välj den du vill lägga till i ditt innehåll.

1. Justera bildparametrarna (t.ex. höjd, bredd, rotering, vändning, intensitet, nyans) efter behov för att uppfylla dina mediebehov.

   En omfattande lista över bildparametrar som kan läggas till i URL:en finns i [Experience Manager-dokumentationen](https://experienceleague.adobe.com/en/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/http-protocol-reference/command-reference/c-command-reference).

   ![](assets/dynamic-media-3.png)

1. Klicka på **[!UICONTROL Save]**.

Innehållet innehåller nu dynamiska medier. Alla uppdateringar du gör i Experience Manager visas automatiskt i Journey Optimizer.

## Anpassa textöverlägget

Anpassa enkelt alla dynamiska medier genom att ersätta den befintliga textövertäckningen med valfri ny text, vilket möjliggör smidiga uppdateringar och personalisering.

Med experimenteringsfunktionen kan du till exempel uppdatera den befintliga textövertäckningen genom att ersätta den med en annan text för varje behandling, så att den anpassas för varje profil när de öppnar sina meddelanden.

![](assets/dynamic-media-layout-1.png)

1. Dra och släpp en **[!UICONTROL HTML component]** i ditt innehåll.

1. Välj **[!UICONTROL Show the source code]**.

1. Öppna **[!UICONTROL Assets]** och sedan **[!UICONTROL Open asset selector]** på menyn **[!UICONTROL Edit HTML]**.

   Du kan också kopiera och klistra in resursens URL.

1. Bläddra bland dina AEM-resurser och välj den du vill lägga till i ditt innehåll.

1. Ersätt övertäckningen med den önskade texten.

   ![](assets/do-not-localize/dynamic_media_layout.gif)

1. Uppdatera bildparametrarna:

   * **Lager**: Ange baselementet där texten ska placeras.
   * **Storlek**: uppdatera storleken på textblocket.
   * **TextAttr**: justera storleken på textteckensnittet.
   * **Pos**: Ange textens position i bilden.

   >[!WARNING]
   >
   >Parametern Layer krävs för att uppdatera dynamiska medier.

   ![](assets/dynamic-media-layout-2.png)

1. Klicka på **[!UICONTROL Save]**.

Innehållet innehåller nu din uppdaterade textövertäckning.

![](assets/dynamic-media-layout-3.png)

<!--
## Personalization with Text Overlay

Easily customize any dynamic media by replacing the existing text overlay with new text of your choice, allowing for seamless updates and personalization.

In this example, our goal is to update the existing text overlay by replacing it with a new validity date and adding a personalization block, ensuring it is customized for each profile when they open their messages.

1. Drag and drop an **[!UICONTROL HTML component]** into your content.

1. Select **[!UICONTROL Show the source code]**.

1. From the **[!UICONTROL Edit HTML]** menu, access **[!UICONTROL Assets]** then **[!UICONTROL Open asset selector]**.

    You can also simply copy and paste your assets URL.

1. Browse through your AEM assets and select the one you want to add to your content.

1. Replace the overlay with the desired text.

    Here we change the validity date from 31st December 2024 to the 1st July 2025.

1. Add the required personalization fields to your image.

1. Click **[!UICONTROL Save]**.

Your content now includes your updated text overlay and personalization.

## Add Dynamic media conditional content

Enable conditional content in your dynamic media to better target your audience and deliver a more personalized experience.

1. Drag and drop an **[!UICONTROL HTML component]** into your content.

1. Select **[!UICONTROL Show the source code]**.

1. From the **[!UICONTROL Edit HTML]** menu, access **[!UICONTROL Assets]** then **[!UICONTROL Open asset selector]**.

    You can also simply copy and paste your assets URL.

1. Browse through your AEM assets and select the one you want to add to your content.

1. Once your dynamic media is inserted to your content, select **[!UICONTROL Enable conditional]** content from your HTML component toolbar to create your different user experiences. 

1. From the Variant - 1, click **[!UICONTROL Select condition]** to fine tune your audience.

1. Choose your condition or create a new one if needed and click **[!UICONTROL Select]**.

    [Learn more on conditions](../personalization/create-conditions.md)

1. Select your **[!UICONTROL Component]** and access the **[!UICONTROL Settings]** menu.

1. In the **[!UICONTROL Custom Attributes]** menu, populate the Dynamic Media text and personalization fields to customize the content for your audience.

-->
