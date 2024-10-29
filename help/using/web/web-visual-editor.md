---
title: Redigera innehåll med webbdesignern
description: Lär dig hur du skapar en webbsida och redigerar dess innehåll med Journey Optimizer webbredigerare
feature: Web Channel
topic: Content Management
role: User
level: Beginner
source-git-commit: 72959e1079b59d51042cdf6843f1a9fb7dd37f9c
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 1%

---

# Arbeta med webbdesignern {#work-with-web-designer}
<!--
>[!CONTEXTUALHELP]
>id="ajo_web_url_to_edit_surface"
>title="Confirm the URL to edit"
>abstract="Confirm the URL of the specific web page to use for editing the content that will be applied on the web configuration defined above. The web page must be implemented using the Adobe Experience Platform Web SDK."
>additional-url="https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html" text="Learn more"

>[!CONTEXTUALHELP]
>id="ajo_web_url_to_edit_rule"
>title="Enter the URL to edit"
>abstract="Enter the URL of a specific web page to use for editing the content that will be applied to all pages matching the rule. The web page must be implemented using Adobe Experience Platform Web SDK."
>additional-url="https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html" text="Learn more"
-->

I [!DNL Journey Optimizer] drivs visuell webbredigering av webbläsartillägget **Adobe Experience Cloud Visual Helper**. [Läs mer](web-prerequisites.md#visual-authoring-prerequisites)

>[!CAUTION]
>
>Om du vill kunna komma åt och redigera webbsidor i användargränssnittet för [!DNL Journey Optimizer] måste du följa de krav som anges i [det här avsnittet](web-prerequisites.md).

## Börja skapa en webbupplevelse

Följ stegen nedan för att börja skapa din webbupplevelse med den visuella webbdesignern.

>[!CAUTION]
>
>[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html){target="_blank"} måste inkluderas på din webbsida. [Läs mer](web-prerequisites.md#implementation-prerequisites)

1. Öppna webbdesignern genom att klicka på **[!UICONTROL Edit web page]** på skärmen **[!UICONTROL Edit content]**.

   ![](assets/web-campaign-edit-web-page.png)

   <!--![](assets/web-designer.png)-->

   >[!NOTE]
   >
   >Om du försöker läsa in en webbplats som inte kan läsas in visas ett meddelande om att du har installerat webbläsartillägget [Visuell redigeringshjälp](#install-visual-editing-helper). Se några tips om felsökning i [det här avsnittet](web-prerequisites.md#troubleshooting).
   >
   >Du kan även redigera webbinnehåll utan att läsa in den visuella redigeraren. Om du vill göra det avmarkerar du alternativet **[!UICONTROL Visual editor]** om du vill använda det icke-visuella versionsläget i stället. [Läs mer](web-non-visual-editor.md)

1. I webbdesignern markerar du ett element på arbetsytan, till exempel bild, knapp, stycke, text, behållare, rubrik, länk osv. [Läs mer](#content-components)

1. Så här redigerar du ett element:

   * Snabbmenyn för att redigera innehåll, layout, infoga länkar eller anpassning osv.

     ![](assets/web-designer-contextual-bar.png)

   * Ikonerna ovanpå den högra panelen om du vill redigera, duplicera, ta bort eller dölja varje element.

     ![](assets/web-designer-right-panel-icons.png)

   * Den högra panelen som ändras dynamiskt enligt det valda elementet. Du kan till exempel redigera bakgrunden, typografin, kanten, storleken, positionen, mellanrummet, effekterna eller textbundna format för ett element.

     ![](assets/web-designer-right-panel.png)

>[!NOTE]
>
>Webbinnehållsdesignern liknar oftast e-postdesignern. Läs mer om [att utforma innehåll med  [!DNL Journey Optimizer]](../email/get-started-email-design.md).

När du har redigerat webbinnehållet kan du hantera ändringarna. [Läs mer](manage-web-modifications.md)

## Använda komponenter {#content-components}

>[!CONTEXTUALHELP]
>id="ajo_web_designer_components"
>title="Lägga till komponenter på din webbsida"
>abstract="Du kan lägga till ett antal komponenter på din webbsida och redigera dem efter behov."

1. Markera ett objekt i rutan **[!UICONTROL Components]** till vänster. Du kan lägga till följande komponenter på webbsidan och redigera dem efter behov:

   * [Delare](../email/content-components.md#divider)
   * [HTML](../email/content-components.md#HTML)
   * [Bild](../email/content-components.md#image)
   * Rubrik - Att använda den här komponenten påminner om att använda komponenten **[!UICONTROL Text]** i e-postdesignern. [Läs mer](../email/content-components.md#text)
   * Stycke - Att använda den här komponenten påminner om att använda komponenten **[!UICONTROL Text]** i e-postdesignern. [Läs mer](../email/content-components.md#text)
   * Länk

   ![](assets/web-designer-components.png)

1. Håll muspekaren på sidan och klicka på knappen **[!UICONTROL Insert before]** eller **[!UICONTROL Insert after]** för att lägga till komponenten i ett befintligt element på sidan.

   ![](assets/web-designer-insert-components.png)

   >[!NOTE]
   >
   >Om du vill avmarkera en komponent klickar du på knappen **[!UICONTROL ESC]** i den kontextuella blå banderollen som visas ovanpå arbetsytan.

1. Redigera komponenten efter behov direkt i innehållet på sidan.

   ![](assets/web-designer-edit-header.png)

1. Justera formaten som visas i det sammanhangsberoende fönstret till höger, t.ex. bakgrund, textfärg, kant, storlek och placering. - beroende på den valda komponenten.

   ![](assets/web-designer-header-style.png)

## Lägg till anpassning

Om du vill lägga till anpassning väljer du en behållare och väljer anpassningsikonen på snabbmenyraden som visas. Lägg till dina ändringar med anpassningsredigeraren. [Läs mer](../personalization/personalization-build-expressions.md)

![](assets/web-designer-personalization.png)

## Navigera i webbdesignern {#navigate-web-designer}

I det här avsnittet beskrivs olika sätt att navigera i webbdesignern. Om du vill visa och hantera ändringarna som lagts till i webbupplevelsen kan du läsa mer i [det här avsnittet](manage-web-modifications.md).

### Använd brödsmulor {#breadcrumbs}

1. Markera ett element på arbetsytan.

1. Klicka på knappen **[!UICONTROL Expand/Collapse Breadcrumbs]** längst ned till vänster på skärmen för att snabbt visa information om det valda elementet.

   ![](assets/web-designer-breadcrumbs.png)

1. När du hovrar över brödsmulorna markeras motsvarande element i redigeraren.

1. Med den kan du enkelt navigera till alla överordnade, jämställda eller underordnade element i den visuella redigeraren.

### Växla till bläddringsläge {#browse-mode}

>[!CONTEXTUALHELP]
>id="ajo_web_designer_browse"
>title="Använda bläddringsläget"
>abstract="I det här läget kan du navigera till den exakta sidan från den valda konfigurationen som du vill anpassa."

Du kan växla från standardläget **[!UICONTROL Design]** till läget **[!UICONTROL Browse]** med den dedikerade knappen.

![](assets/web-designer-browse-mode.png)

Från läget **[!UICONTROL Browse]** kan du navigera till den exakta sidan från den valda konfigurationen som du vill anpassa.

Det är särskilt användbart när det handlar om sidor som ligger bakom autentisering eller som inte är tillgängliga från början vid en viss URL. Du kan till exempel autentisera, gå till kontosidan eller kundvagnssidan och sedan växla tillbaka till läget **[!UICONTROL Design]** för att utföra ändringarna på den önskade sidan.

Genom att använda läget **[!UICONTROL Browse]** kan du också navigera i alla vyer på webbplatsen när du redigerar enkelsidiga program. [Läs mer](web-spa.md)

### Ändra enhetsstorlek {#change-device-size}

Du kan ändra enhetsstorleken för webbdesignervisningen till en fördefinierad storlek som **[!UICONTROL Tablet]** eller **[!UICONTROL Mobile landscape]**, eller definiera en anpassad storlek genom att ange önskat antal pixlar.

Du kan också ändra zoomfokus - från 25 % till 400 %.

![](assets/web-designer-device.png)

Möjligheten att ändra enhetsstorleken är utformad för responsiva sajter som återges bra på olika enheter, fönster och skärmstorlekar. Responsiva sajter justeras och anpassas automatiskt efter alla skärmstorlekar, inklusive stationära datorer, bärbara datorer, surfplattor och mobiltelefoner.

>[!CAUTION]
>
>Du kan redigera en webbupplevelse med en viss enhetsstorlek. Så länge väljarna är desamma gäller dock dessa ändringar för alla storlekar och enheter, inte bara för den enhetsstorlek som du arbetar i. När du redigerar en upplevelse i den normala skrivbordsvyn tillämpas ändringarna på samma sätt på alla skärmstorlekar, inte bara på skrivbordet.
>
>För närvarande stöder inte [!DNL Journey Optimizer] enhetsstorleksspecifika sidändringar. Det innebär att om du till exempel har en separat mobilwebbplats med en separat webbplatsstruktur, bör du göra ändringarna specifika för din mobilwebbplats i en annan kampanj.

## Instruktionsvideo{#video}

I videon nedan visas hur du skapar en webbupplevelse med webbdesignern i [!DNL Journey Optimizer]-kampanjer.

>[!VIDEO](https://video.tv.adobe.com/v/3418803/?quality=12&learn=on)