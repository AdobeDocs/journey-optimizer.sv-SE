---
title: Skapa single-page-appar
description: Lär dig hur du redigerar SPA och tillämpar ändringar på olika vyer i Journey Optimizer
feature: Web Channel
topic: Content Management
role: User
level: Intermediate
exl-id: b33e4bca-d2e9-4610-9f04-008d47f686d0
source-git-commit: 45f19563c79d298eeec6cb757636a9ce47e54adf
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 3%

---

# Skapa single-page-appar {#web-author-spas}

## Om vyer {#about-views}

>[!CONTEXTUALHELP]
>id="ajo_web_designer_modifications_views"
>title="Tillämpa ändringar på markerade vyer"
>abstract="Ändringarna används bara för de valda vyerna. Vyer kan identifieras med **Bläddra** och navigera till dem. Hittar du inte den vy du söker?"
>additional-url="https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html" text="Läs mer"

**Single-page applications** (SPA) kan nu redigeras i webbdesignerns visuella redigerare. Detta gör att du kan välja vilken specifik **vyer** du vill använda dina webbsidesändringar på.

[Lär dig hur du skapar enkelsidiga program i den här videon](#video)

En vy kan definieras som en hel webbplats eller som en grupp visuella element på en webbplats, till exempel hemsidan, hela produktwebbplatsen eller leveransinställningsramen på alla utcheckningssidor.

Det krävs en engångsinstallation av utvecklare för att definiera vyerna i implementeringen av Adobe Experience Platform Web SDK. På så sätt kan ni skapa och köra Adobe Journey Optimizer webbkampanjer SPA.

## Definiera vyer i Web SDK-implementeringen {#define-views}

XDM-vyer kan användas i Adobe [!DNL Journey Optimizer] för att göra det möjligt för marknadsförare att köra webbpersonaliserings- och experimenteringskampanjer på SPA via den webbaserade visuella redigeraren. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/ajo/web-spa-implementation.html){target="_blank"}

För att kunna komma åt och redigera vyer i [!DNL Journey Optimizer] -användargränssnittet bör du följa stegen i [det här avsnittet](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/ajo/web-spa-implementation.html#implement-xdm-views){target="_blank"}.

## Upptäck vyer i webbdesignern {#discover-views}

När SPA har konfigurerats i Adobe Experience Platform Web SDK-implementeringen måste du navigera bland alla vyer på webbplatsen som du vill ändra. Följ stegen nedan.

1. [Skapa en webbkampanj](create-web.md) och få tillgång till [webbdesigner](edit-web-content.md).

   Den vy du befinner dig i visas längst upp till vänster.

   ![](assets/web-designer-view-home.png)

1. Växla till **[!UICONTROL Browse]** läge. [Läs mer](../web/edit-web-content.md#browse-mode)

   ![](assets/web-designer-view-browse.png)

1. Navigera mellan de olika sidorna på webbplatsen för att identifiera alla. Vynamnet som visas överst ändras när du går igenom en annan sida.

   ![](assets/web-designer-other-view.png)

## Använda ändringar i andra vyer {#apply-modifications-views}

När du har lagt till en ändring i en viss vy kan du använda den i andra markerade vyer. Följ stegen nedan.

>[!CAUTION]
>
>Om du inte har upptäckt vyer med **[!UICONTROL Browse]** kan du inte markera dem för att tillämpa ändringarna. [Läs mer](#discover-views)

1. Välj **[!UICONTROL Modifications]** om du vill visa motsvarande ruta till vänster.

   ![](assets/web-designer-view-modifications-pane.png)

1. Markera en ändring och klicka på **[!UICONTROL More actions]** intill den. Välj **[!UICONTROL Apply to more views]**.

   ![](assets/web-designer-modifications-more-actions.png)

1. Markera de vyer som du vill använda ändringarna på.

   ![](assets/web-designer-modifications-apply-to.png)

1. Klicka på **[!UICONTROL Apply]**.

1. Växla till **[!UICONTROL Browse]** läge för att kontrollera om ändringarna används på de önskade sidorna.

   ![](assets/web-designer-modifications-applied-view.png)

## Instruktionsvideo{#video}

I den här videon beskrivs hur du:

* Upptäck SPA vyer med **[!UICONTROL Browse]** läge
* Utför redigering i den aktuella vyn
* Använd webbplatsändringar på flera vyer eller på alla vyer som identifierats
* Göra satsåtgärder på ändringar

>[!VIDEO](https://video.tv.adobe.com/v/3424536/?quality=12&learn=on)
