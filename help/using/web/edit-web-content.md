---
title: Redigera webbinnehåll
description: Lär dig skapa en webbsida och redigera dess innehåll i Journey Optimizer
feature: Web Channel
topic: Content Management
role: User
level: Beginner
exl-id: 3847ac1d-2c0a-4f80-8df9-e8e304faf261
source-git-commit: 11cae07d061b67136f50201e89c0e349e919620d
workflow-type: tm+mt
source-wordcount: '1032'
ht-degree: 1%

---

# Redigera webbinnehåll {#edit-web-content}

En gång [lade till en webbåtgärd](create-web.md#create-web-campaign) till er kampanj kan ni redigera innehållet på er webbplats med webbdesignern.

[Lär dig hur du skapar en webbkampanj i den här videon](#video)

I [!DNL Journey Optimizer], används webbutveckling av **Adobe Experience Cloud Visual Helper** webbläsartillägg för fönsterstandard. [Läs mer](web-prerequisites.md#visual-authoring-prerequisites)

>[!CAUTION]
>
>För att kunna komma åt och skriva webbsidor i [!DNL Journey Optimizer] måste du följa de krav som anges i [det här avsnittet](web-prerequisites.md).

Gå till följande avsnitt för att lära dig mer om varje ämne:

* [Hantera ändringar](manage-web-modifications.md)

* [Övervaka era webbkampanjer](monitor-web-campaigns.md)

## Arbeta med webbdesignern {#work-with-web-designer}

>[!CONTEXTUALHELP]
>id="ajo_web_url_to_edit_surface"
>title="Bekräfta den URL som ska redigeras"
>abstract="Bekräfta URL-adressen till den specifika webbsida som ska användas för att redigera innehållet som ska användas på den webbyta som definieras ovan. Webbsidan måste implementeras med Adobe Experience Platform Web SDK."
>additional-url="https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html" text="Läs mer"

>[!CONTEXTUALHELP]
>id="ajo_web_url_to_edit_rule"
>title="Ange den URL som ska redigeras"
>abstract="Ange URL-adressen till en viss webbsida som ska användas för att redigera innehållet som ska användas på alla sidor som matchar regeln. Webbsidan måste implementeras med Adobe Experience Platform Web SDK."
>additional-url="https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html" text="Läs mer"

Följ stegen nedan när du vill börja skapa webbkampanjer.

1. Från **[!UICONTROL Action]** -fliken i [kampanj](create-web.md#create-web-campaign), markera **[!UICONTROL Edit content]**.<!--change screen with rule-->

   ![](assets/web-campaign-edit-content.png)

1. Om du har skapat en sidmatchningsregel måste du ange en URL-adress som matchar den här regeln: ändringarna kommer att gälla för alla sidor som matchar regeln. Innehållet på sidan visas.

   >[!NOTE]
   >
   >Om du angav en enda URL som webbyta fylls URL:en som ska anpassas redan i.

   ![](assets/web-edit-enter-url.png)

   >[!CAUTION]
   >
   >Webbsidan måste innehålla [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html){target="_blank"}. [Läs mer](web-prerequisites.md#implementation-prerequisites)

1. Klicka **[!UICONTROL Edit web page]** för att börja skapa det. Webbdesignern visas.

   ![](assets/web-designer.png)

   >[!NOTE]
   >
   >Om du försöker läsa in en webbplats som inte kan läsas in visas ett meddelande om att du har installerat [Webbläsartillägg för hjälp för visuell redigering](#install-visual-editing-helper). Se några tips om felsökning i [det här avsnittet](web-prerequisites.md#troubleshooting).

1. Markera ett element på arbetsytan, till exempel bild, knapp, stycke, text, behållare, rubrik, länk osv. [Läs mer](#content-components)

1. Använd:

   * Den sammanhangsbaserade menyn där du kan redigera innehåll, layout, infoga länkar eller personalisering, osv.

     ![](assets/web-designer-contextual-bar.png)

   * Ikonerna överst på den högra panelen för att redigera, duplicera, ta bort eller dölja varje element.

     ![](assets/web-designer-right-panel-icons.png)

   * Den högra panelen som ändras dynamiskt enligt det valda elementet. Du kan till exempel redigera bakgrunden, typografin, kanten, storleken, positionen, mellanrummet, effekterna eller textbundna format för ett element.

     ![](assets/web-designer-right-panel.png)

>[!NOTE]
>
>Webbinnehållsdesignern liknar oftast e-postdesignern. Läs mer på [designa innehåll med [!DNL Journey Optimizer]](../email/get-started-email-design.md).

## Använda komponenter {#content-components}

>[!CONTEXTUALHELP]
>id="ajo_web_designer_components"
>title="Lägga till komponenter på webbsidan"
>abstract="Du kan lägga till ett antal komponenter på webbsidan och redigera dem efter behov."

1. Från **[!UICONTROL Components]** till vänster markerar du ett objekt. Du kan lägga till följande komponenter på webbsidan och redigera dem efter behov:

   * [Delare](../email/content-components.md#divider)
   * [HTML](../email/content-components.md#HTML)
   * [Bild](../email/content-components.md#image)
   * Rubrik - Att använda den här komponenten påminner om att använda **[!UICONTROL Text]** i e-postdesignern. [Läs mer](../email/content-components.md#text)
   * Stycke - Att använda den här komponenten påminner om att använda **[!UICONTROL Text]** i e-postdesignern. [Läs mer](../email/content-components.md#text)
   * Länk

   ![](assets/web-designer-components.png)

1. Hovra på sidan och klicka på **[!UICONTROL Insert before]** eller **[!UICONTROL Insert after]** om du vill lägga till komponenten i ett befintligt element på sidan.

   ![](assets/web-designer-insert-components.png)

   >[!NOTE]
   >
   >Avmarkera en komponent genom att klicka på **[!UICONTROL ESC]** i den kontextuella blå banderollen som visas ovanpå arbetsytan.

1. Redigera komponenten efter behov direkt i innehållet på sidan.

   ![](assets/web-designer-edit-header.png)

1. Justera de format som visas i rutan till höger, t.ex. bakgrund, textfärg, kant, storlek, position. - beroende på vald komponent.

   ![](assets/web-designer-header-style.png)

## Lägg till personalisering

Om du vill lägga till personalisering markerar du en behållare och väljer personaliseringsikonen på den snabbmenyrad som visas. Lägg till ändringarna med personaliseringsredigeraren. [Läs mer](../personalization/personalization-build-expressions.md)

![](assets/web-designer-personalization.png)

## Navigera i webbdesignern {#navigate-web-designer}

I det här avsnittet beskrivs olika sätt att navigera i webbdesignern. Information om hur du visar och hanterar de ändringar som har lagts till i webbupplevelsen finns i [det här avsnittet](manage-web-modifications.md).

### Använd vägbeskrivningar {#breadcrumbs}

1. Markera ett element på arbetsytan.

1. Klicka på **[!UICONTROL Expand/Collapse Breadcrumbs]** på skärmens nedre vänstra sida för att snabbt visa information om det markerade elementet.

   ![](assets/web-designer-breadcrumbs.png)

1. När du håller muspekaren över vägbeskrivningarna markeras motsvarande element i redigeraren.

1. Med den kan du enkelt navigera till alla överordnade, jämställda eller underordnade element i den visuella redigeraren.

### Växla till bläddringsläge {#browse-mode}

>[!CONTEXTUALHELP]
>id="ajo_web_designer_browse"
>title="Använda bläddringsläget"
>abstract="I det här läget kan du navigera till den exakta sidan från den markerade ytan som du vill anpassa."

Du kan växla från standardinställningen **[!UICONTROL Design]** till **[!UICONTROL Browse]** läge med den dedikerade knappen.

![](assets/web-designer-browse-mode.png)

Från **[!UICONTROL Browse]** kan du navigera till den exakta sidan från den markerade ytan som du vill anpassa.

Det är särskilt användbart när du hanterar sidor som är bakom autentisering eller som inte är tillgängliga från början på en viss URL. Du kan till exempel autentisera, navigera till din kontosida eller till kundvagnssidan och sedan växla tillbaka till **[!UICONTROL Design]** för att utföra ändringarna på den önskade sidan.

Använda **[!UICONTROL Browse]** I kan du även navigera i alla vyer på webbplatsen när du skapar enkelsidiga program. [Läs mer](web-spa.md)

### Ändra enhetsstorlek {#change-device-size}

Du kan ändra enhetsstorleken för webbdesignerskärmen till en fördefinierad storlek, till exempel **[!UICONTROL Tablet]** eller **[!UICONTROL Mobile landscape]** eller definiera en egen storlek genom att ange önskat antal pixlar.

Du kan också ändra zoomfokus - från 25 % till 400 %.

![](assets/web-designer-device.png)

Möjligheten att ändra enhetsstorleken är utformad för responsiva sajter som återges bra på olika enheter, fönster och skärmstorlekar. Responsiva sajter justeras och anpassas automatiskt efter alla skärmstorlekar, inklusive stationära datorer, bärbara datorer, surfplattor och mobiltelefoner.

>[!CAUTION]
>
>Du kan redigera en webbupplevelse med en viss enhetsstorlek. Så länge väljarna är desamma gäller dock dessa ändringar för alla storlekar och enheter, inte bara för den enhetsstorlek som du arbetar i. På samma sätt tillämpas ändringarna på alla skärmstorlekar, inte bara på skrivbordsvyn, när du redigerar en upplevelse i den normala skrivbordsvyn.
>
>För närvarande [!DNL Journey Optimizer] stöder inte enhetsstorleksspecifika sidändringar. Det innebär att om du till exempel har en separat mobilwebbplats med en separat webbplatsstruktur, bör du göra ändringarna specifika för din mobilwebbplats i en annan kampanj.

## Instruktionsvideo{#video}

I videon nedan visas hur du skapar en webbupplevelse med webbdesignern i [!DNL Journey Optimizer] kampanjer.

>[!VIDEO](https://video.tv.adobe.com/v/3418803/?quality=12&learn=on)