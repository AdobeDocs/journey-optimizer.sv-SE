---
title: Skapa webbsidor
description: Lär dig hur du skapar en webbsida och redigerar dess innehåll i Journey Optimizer
feature: Web Channel
topic: Content Management
role: User
level: Beginner
exl-id: 3847ac1d-2c0a-4f80-8df9-e8e304faf261
source-git-commit: 803c9f9f05669fad0a9fdeeceef58652b6dccf70
workflow-type: tm+mt
source-wordcount: '1574'
ht-degree: 1%

---

# Skapa webbsidor {#author-web}

En gång [lade till en webbåtgärd](create-web.md#create-web-campaign) till er kampanj kan ni redigera innehållet på er webbplats med webbdesignern.

I [!DNL Journey Optimizer], används webbutveckling av **Adobe Experience Cloud Visual Helper** webbläsartillägg för fönsterstandard. [Läs mer](web-prerequisites.md#visual-authoring-prerequisites)

>[!CAUTION]
>
>För att kunna komma åt och skriva webbsidor i [!DNL Journey Optimizer] måste du följa de krav som anges i [det här avsnittet](web-prerequisites.md).

[Lär dig hur du skapar en webbkampanj i den här videon](#video)

## Redigera webbsidesinnehåll {#edit-web-content}

>[!CONTEXTUALHELP]
>id="ajo_web_url_to_edit_surface"
>title="Bekräfta den URL som ska redigeras"
>abstract="Bekräfta webbadressen till den specifika webbsida som ska användas för att redigera innehållet som ska användas på den webbyta som definieras ovan. Webbsidan måste implementeras med Adobe Experience Platform Web SDK."
>additional-url="https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html" text="Läs mer"

>[!CONTEXTUALHELP]
>id="ajo_web_url_to_edit_rule"
>title="Ange den URL som ska redigeras"
>abstract="Ange URL-adressen till en viss webbsida som ska användas för att redigera innehållet som ska användas på alla sidor som matchar regeln. Webbsidan måste implementeras med Adobe Experience Platform Web SDK."
>additional-url="https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html" text="Läs mer"

Följ stegen nedan när du vill börja skapa webbkampanjer.

1. Från **[!UICONTROL Action]** -fliken i [kampanj](create-web.md#create-web-campaign), markera **[!UICONTROL Edit content]**.<!--change screen with rule-->

   ![](assets/web-campaign-edit-content.png)

1. Om du har skapat en sidmatchningsregel måste du ange en URL som matchar den här regeln: ändringarna tillämpas på alla sidor som matchar regeln. Innehållet på sidan visas.

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

   * Ikonerna ovanför den högra panelen för att redigera, duplicera, ta bort eller dölja varje element.

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
   * [Beslut om erbjudandet](../email/add-offers-email.md)

   ![](assets/web-designer-components.png)

1. Hovra på sidan och klicka på **[!UICONTROL Insert before]** eller **[!UICONTROL Insert after]** om du vill lägga till komponenten i ett befintligt element på sidan.

   ![](assets/web-designer-insert-components.png)

   >[!NOTE]
   >
   >Om du vill avmarkera en komponent klickar du på knappen **[!UICONTROL ESC]** i den kontextuella blå banderollen som visas ovanpå arbetsytan.

1. Redigera komponenten efter behov direkt i innehållet på sidan.

   ![](assets/web-designer-edit-header.png)

1. Justera de format som visas i rutan till höger, t.ex. bakgrund, textfärg, kant, storlek, position. - beroende på vald komponent.

   ![](assets/web-designer-header-style.png)

## Lägg till personalisering och erbjudanden

Om du vill lägga till personalisering markerar du en behållare och väljer personaliseringsikonen på den snabbmenyrad som visas. Lägg till ändringarna med uttrycksredigeraren. [Läs mer](../personalization/personalization-build-expressions.md)

![](assets/web-designer-personalization.png)

Använd **[!UICONTROL Offer decision]** komponent som ska infogas [erbjudanden](../offers/get-started/starting-offer-decisioning.md) till dina webbsidor. Processen är densamma som när [lägga till ett erbjudande i ett e-postmeddelande](../email/add-offers-email.md). Det kommer att utnyttja Beslutshantering för att välja det bästa erbjudandet att leverera till era kunder.

![](assets/web-designer-offer.png)

## Hantera ändringar {#manage-modifications}

>[!CONTEXTUALHELP]
>id="ajo_web_designer_modifications"
>title="Hantera enkelt alla ändringar"
>abstract="I den här rutan kan du navigera och hantera alla justeringar och format som du har lagt till på webbsidan."

Du kan enkelt hantera alla komponenter, justeringar och format som du har lagt till på webbsidan.

1. Välj **[!UICONTROL Modifications]** om du vill visa motsvarande ruta till vänster.

   ![](assets/web-designer-modifications-pane.png)

1. Du kan granska alla ändringar du har gjort på sidan.

1. Markera en oönskad ändring och klicka på ikonen Ta bort för att ta bort den.

   ![](assets/web-designer-modifications-delete.png)

   >[!CAUTION]
   >
   >Var försiktig när du tar bort en åtgärd eftersom den kan påverka efterföljande åtgärder.

1. Använd **[!UICONTROL More actions]** överst på **[!UICONTROL Modifications]** om du vill ta bort alla ändringar samtidigt.

   ![](assets/web-designer-delete-modifications.png)

1. Från **[!UICONTROL More actions]** kan du även ta bort endast de ogiltiga ändringarna, det vill säga de ändringar som åsidosatts av andra ändringar. Om du till exempel ändrar färgen på en text och sedan tar bort den texten, blir färgändringen ogiltig eftersom texten inte längre finns.

1. Du kan även avbryta och göra om åtgärder med **[!UICONTROL Undo/Redo]** överst till höger på skärmen.

   ![](assets/web-designer-undo-redo.png)

   Klicka och håll ned knappen för att växla mellan **[!UICONTROL Undo]** och **[!UICONTROL Redo]** alternativ. Klicka sedan på själva knappen för att utföra den önskade åtgärden.

## Använda klickspårning {#use-click-tracing}

Med den här funktionen i webbdesignern kan du markera valfritt element på webbplatsen och spåra klick på det elementet.

När kampanjen är aktiv kan du kontrollera antalet klick för varje element i kampanjwebbrapporten. Den här informationen kan vara användbar för att förbättra webbplatsens användarupplevelse. Om [webbrapporter](../reports/campaign-global-report.md#web-tab) visa att många användare klickar på ett element som inte är klickbart, kanske du vill lägga till en länk till det elementet.

1. Markera ett element på sidan och välj **[!UICONTROL Click track element]** på snabbmenyn.

   ![](assets/web-designer-click-track.png)

   >[!NOTE]
   >
   >Alla objekt, klickbara eller inte, kan markeras.

1. Motsvarande spårade åtgärd visas automatiskt i **[!UICONTROL Click track]** till vänster.

   ![](assets/web-designer-click-track-pane.png)

1. Lägg till en meningsfull etikett för att hantera alla spårade element och hitta dem enkelt i rapporterna. The **[!UICONTROL CSS selector]** -fältet visar information för att hitta det markerade elementet.

1. Upprepa stegen ovan om du vill markera så många andra element som behövs för klickspårning. Alla motsvarande åtgärder visas i den vänstra rutan.

   ![](assets/web-designer-click-tracking-actions.png)

1. Om du vill ta bort klickspårning för ett element markerar du motsvarande borttagningsikon.

När kampanjen är aktiv kan du kontrollera kampanjrapporten **[!UICONTROL Web]** om du vill jämföra antalet visningar klickar du på frekvens och antal klick per element. [Läs mer](../reports/campaign-global-report.md#web-tab)

## Navigera i webbdesignern {#navigate-web-designer}

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

### Ändra enhetsstorlek {#change-device-size}

Du kan ändra enhetsstorleken för webbdesignerskärmen till en fördefinierad storlek, till exempel **[!UICONTROL Tablet]** eller **[!UICONTROL Mobile landscape]** eller definiera en anpassad storlek genom att ange önskat antal pixlar.

Du kan också ändra zoomfokus - från 25 % till 400 %.

![](assets/web-designer-device.png)

Möjligheten att ändra enhetsstorleken är utformad för responsiva sajter som återges bra på olika enheter, fönster och skärmstorlekar. Responsiva sajter justeras och anpassas automatiskt efter alla skärmstorlekar, inklusive stationära datorer, bärbara datorer, surfplattor och mobiltelefoner.

>[!CAUTION]
>
>Du kan redigera en webbupplevelse med en viss enhetsstorlek. Så länge väljarna är desamma gäller dock dessa ändringar för alla storlekar och enheter, inte bara för den enhetsstorlek som du arbetar i. På samma sätt tillämpas ändringarna på alla skärmstorlekar, inte bara på skrivbordsvyn, när du redigerar en upplevelse i den normala skrivbordsvyn.
>
>För närvarande [!DNL Journey Optimizer] stöder inte enhetsstorleksspecifika sidändringar. Det innebär att om du till exempel har en separat mobilwebbplats med en separat webbplatsstruktur, bör du göra ändringarna specifika för din mobilwebbplats i en annan kampanj.

## Testa webbkampanjen {#test-web-campaign}

>[!CONTEXTUALHELP]
>id="ajo_web_designer_preview"
>title="Förhandsgranska webbupplevelsen"
>abstract="Få en simulering av hur webbupplevelsen kommer att se ut."

Följ stegen nedan för att visa en förhandsvisning av den ändrade webbupplevelsen.

>[!CAUTION]
>
>Du måste ha testprofiler tillgängliga för att simulera vilka erbjudanden som ska levereras till dem. Lär dig hur [skapa testprofiler](../segment/creating-test-profiles.md).

1. Välj **[!UICONTROL Simulate content]**.

   <!--![](assets/web-designer-simulate.png)-->

   ![](assets/web-campaign-simulate.png)

1. Klicka **[!UICONTROL Manage test profiles]** om du vill välja en eller flera testprofiler.
1. En förhandsgranskning av den ändrade webbsidan visas.

   ![](assets/web-designer-preview.png)

1. Du kan även öppna den i standardwebbläsaren eller kopiera test-URL:en och klistra in den i valfri webbläsare. På så sätt kan ni dela länken med teamet och intressenter som kan förhandsgranska den nya webbupplevelsen i vilken webbläsare som helst innan kampanjen blir aktiv.

   >[!NOTE]
   >
   >När du kopierar test-URL:en är det innehåll som visas anpassat för testprofilen som användes när innehållssimuleringen genererades i [!DNL Journey Optimizer].

## Instruktionsvideo{#video}

I videon nedan visas hur du skapar en webbupplevelse med hjälp av webbdesignern i [!DNL Journey Optimizer] kampanjer.

>[!VIDEO](https://video.tv.adobe.com/v/3418803/?quality=12&learn=on)
