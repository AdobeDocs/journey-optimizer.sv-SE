---
solution: Journey Optimizer
product: journey optimizer
title: Arbeta med Adobe Stock-bilder
description: Kom igång med Adobe Stock
feature: Assets, Integrations
topic: Content Management
role: User
level: Beginner
keywords: stock, bilder, integration, foton
exl-id: 0715f65f-04bd-4dc2-a152-98111f4c42e6
source-git-commit: 4899dbe71243184b6283a32a4fe7eb2edb82f872
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 1%

---

# Arbeta med [!DNL Adobe Stock] bilder {#stock}

## Kom igång med [!DNL Adobe Stock] {#get-started-stock}

The [!DNL Adobe Stock] och [!DNL Adobe Journey Optimizer] Integrationspluginen för e-postdesignern ger kunderna ett enkelt sätt att navigera, licensiera och spara bilder för användning i meddelanderedigering.

[Adobe Stock](https://helpx.adobe.com/stock/get-started.html){target="_blank"} ger tillgång till miljontals utvalda och royaltyfria foton, videor, illustrationer och vektorbilder av hög kvalitet. Du kan välja att köpa ett kreditpaket för att licensiera mediefiler eller bara köpa en Standard- eller Extended-licens för den mediefil du behöver. Adobe Stock erbjuder också en kostnadsfri samling resurser.

Med [!DNL Adobe Journey Optimizer]kan du överföra bilder till e-postmeddelanden direkt från [!DNL Adobe Stock] och lägga in **[!UICONTROL Assets]** mapp med **[!UICONTROL Find Adobe Stock photos]** alternativ. Dessutom är **[!UICONTROL Find Similar Stock photos]** hjälper dig att hitta bilder som matchar innehållet, färgen och kompositionen för resursen som används i leveransen.

## Behörigheter{#stock-permissions}

The **[!UICONTROL Find Adobe Stock photos]** och **[!UICONTROL Find Similar Image]** är tillgängliga för användare med tillgång till en AEM Assets Essentials-produktprofil.

Mer information finns i [Experience Manager Assets-dokumentation](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/get-started-admins/deploy-administer.html#add-users-to-essentials){target="_blank"}.

## Infoga en bild från [!DNL Adobe Stock] {#add-stock-image}

Lägga till bilder från [!DNL Adobe Stock] Följ stegen nedan om du vill visa ditt innehåll:

1. Från **[!UICONTROL Content components]** i e-postdesignern drar och släpper du en **Bild**.

1. Klicka på **[!UICONTROL Find Adobe Stock photos]** till vänster om e-postdesignern.

   ![](assets/stock-find-photos.png)

1. Bläddra i biblioteket eller ange en term i sökfältet.

   ![](assets/stock-select-from-lib.png)

1. Markera den valda bilden och klicka på **[!UICONTROL Save]**.

   Om bilden du valde inte är licensierad måste du [skaffa licensen](#license-stock-image).

## Söka efter liknande foton {#similar-stock-image}

Du kan ersätta en befintlig bild i ditt e-postinnehåll med ett foto från [!DNL Adobe Stock]. Observera att det här alternativet är tillgängligt för alla bilder: licensierade/ej licensierade Stock-bilder och bilder från mappen Resurser.

Följ stegen nedan om du vill bläddra bland liknande foton:

1. Markera bilden som ska ersättas.
1. Klicka på **[!UICONTROL Find similar Stock photos]** knapp för att visa resurser i [!DNL Adobe Stock] som matchar bildens innehåll, färg och komposition.

   ![](assets/stock-similar.png)

1. Markera den valda bilden och klicka på **[!UICONTROL Save]**.

   ![](assets/stock-similar-results.png)

   Om bilden du valde inte är licensierad måste du [skaffa licensen](#license-stock-image).

1. Anpassa vid behov bilden med **[!UICONTROL Settings]** och **[!UICONTROL Styles]** -tabbar. [Läs mer om komponentinställningar](../email/content-components.md).

## Hämta licensen från [!DNL Adobe Stock] {#license-stock-image}

Om din bild redan är licensierad visas den av ![](assets/stock_10.png) -ikon. Annars måste du licensiera den.

Följ stegen nedan för att licensiera och hämta din bild:

1. Markera den och klicka på **[!UICONTROL License Adobe Stock image]** -ikon.

   ![](assets/stock-license-icon.png)

   Du omdirigeras sedan till [!DNL Adobe Stock] för att köpa licensen.

   ![](assets/stock-license-photo.png)

1. Från [!DNL Adobe Stock] måste du köpa resursen för att kunna hämta bilden och ta bort vattenstämpeln.

   Köpet beror på din Adobe Stock-prenumeration. Observera att om du har flera Adobe Stock-konton kommer du att omdirigeras till det senast använda Stock ID:t. I så fall måste du se till att du är inloggad på rätt konto innan du licensierar resursen.

   Läs mer om Adobe Stock planer och priser i [Adobe Stock-dokumentation](https://stock.adobe.com/plans){target="_blank"}.

   >[!WARNING]
   > Om ett e-postmeddelande med en olicensierad bild skickas behåller bilden sin olicensierade form med vattenstämpeln.

1. När köpet är klart kan du gå tillbaka till e-postmeddelandet i [!DNL Adobe Journey Optimizer] och markera **[!UICONTROL Import stock image]** för att importera din licensierade bild till dina resurser.

   ![](assets/stock_6.png)

1. Välj i vilken mapp resursen ska lagras. Mer information om [!DNL Experience Manager Assets], se det här [page](assets.md#get-started-assets).

## Relaterade ämnen{#stock-related-topics}

* [E-postdesign i Journey Optimizer](../email/get-started-email-design.md)
* [Komponentinställningar för e-postdesign](../email/content-components.md)
* [Kom igång med Adobe Stock](https://helpx.adobe.com/stock/get-started.html){target="_blank"}.

