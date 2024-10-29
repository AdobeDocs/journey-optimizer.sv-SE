---
title: Redigera innehåll med den icke-visuella redigeraren
description: Lär dig hur du skapar en webbsida och redigerar dess innehåll med den icke-visuella Journey Optimizer-redigeraren
feature: Web Channel
topic: Content Management
role: User
level: Experienced
source-git-commit: 4b822eb45857556359ba9444e9bf7379608f1dff
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 1%

---

# Använda den icke-visuella webbredigeraren {#web-non-visual-editor}

Förutom den [!DNL Journey Optimizer] visuella [webbdesignern](web-visual-editor.md) kan du även lägga till ändringar på dina webbsidor med en **icke-visuell redigerare** .

Detta kan vara användbart om du inte kan, eller inte tillåts, installera webbläsartillägg som [Adobe Experience Cloud Visual Helper](web-prerequisites.md#visual-authoring-prerequisites) , som krävs för att läsa in sidorna i webbdesignern.

I vissa fall kan det också vara enklare att använda en icke-visuell redigerare för att göra ändringar i en viss CSS-väljare, utan att riskera att ändra andra element på en webbsida eller ändra sidstrukturen.

Följ stegen nedan för att skapa webbupplevelser med den icke-visuella redigeraren.

1. Avmarkera alternativet **[!UICONTROL Visual editor]** på skärmen **[!UICONTROL Edit content]** i resan eller kampanjen.

1. Klicka på **[!UICONTROL Add a modification]** för att börja redigera ditt webbinnehåll.

   ![](assets/web-campaign-add-modification-button.png)

1. Den icke-visuella redigeraren visas. Du kan lägga till den första ändringen i den vänstra rutan.

   ![](assets/web-non-visual-editor.png)

1. Välj ändringstyp:

   * **[!UICONTROL CSS Selector]** - [Läs mer](manage-web-modifications.md#css-selector)
   * **[!UICONTROL Page `<Head>`]** - [Läs mer](manage-web-modifications.md#page-head)

1. Klicka på knappen **[!UICONTROL Advanced editing options]**. Anpassningsredigeraren öppnas.

   Du kan utnyttja personaliseringsredigeraren [!DNL Journey Optimizer] med alla dess funktioner för personalisering och redigering. [Läs mer](../personalization/personalization-build-expressions.md)

1. Ange ditt innehåll och **[!UICONTROL Save]** dina ändringar.

   ![](assets/web-non-visual-editor-ex-save.png)

1. Den första ändringen visas ovanpå rutan **[!UICONTROL Modifications]**.

   Klicka på knappen **[!UICONTROL More actions]** bredvid din ändring och välj **[!UICONTROL Info]** för att visa informationen. Du kan också **[!UICONTROL Edit]** eller **[!UICONTROL Delete]** ändra.

   ![](assets/web-non-visual-editor-ex-more.png)

   >[!NOTE]
   >
   >**[!UICONTROL Modifications]**-rutan är densamma som när du använder [webbdesignern](web-visual-editor.md). Alla åtgärder du kan utföra med den beskrivs i [det här avsnittet](manage-web-modifications.md#use-modifications-pane).

1. Klicka på knappen **[!UICONTROL More actions]** ovanför rutan **[!UICONTROL Modifications]** till **[!UICONTROL Add a modification]** och upprepa stegen ovan. [Läs mer](manage-web-modifications.md#add-modifications)

   ![](assets/web-non-visual-editor-more.png)

1. Välj pilen längst upp till vänster på skärmen för att komma tillbaka till skärmen för resan eller kampanjutgåvan. Du kan se det aktuella antalet ändringar och lägga till fler.

   ![](assets/web-campaign-modifications.png)

   Du kan också växla till webbdesignern om du vill. Alla ändringar bevaras.


1. Du kan aktivera klickspårning och definiera vilka åtgärder som ska spåras från den andra ikonen på den vänstra listen, enligt nedan:

   ![](assets/web-campaign-click.png)

   Klicka på knappen **Lägg till komponent** för att välja en ny åtgärd att spåra.
