---
title: Designa ditt innehåll i appen
description: Lär dig hur du utformar innehåll i appen i Journey Optimizer
feature: In App
topic: Content Management
role: User
level: Beginner
keywords: i appen, meddelande, design, formatering
exl-id: 7d7aa721-96aa-4ebc-a51c-e693f893f34f
source-git-commit: 8a1ec5acef067e3e1d971deaa4b10cffa6294d75
workflow-type: tm+mt
source-wordcount: '1053'
ht-degree: 0%

---

# Designa ditt innehåll i appen {#design-content}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_inapp_content"
>title="Definiera innehåll i appen"
>abstract="Anpassa innehåll och format för meddelanden i appen. Du kan också lägga till media och åtgärdsknappar för att göra budskapen mer engagerande och effektiva."

Du kan redigera innehållet i appen för att konfigurera upplevelsealternativ:

* I en **[!UICONTROL Campaign]**, från **[!UICONTROL Action]** för att konfigurera meddelandeinnehållet klickar du på **[!UICONTROL Edit content]** -knappen.

  ![](assets/edit-in-app-content.png)

* I en **[!UICONTROL Journey]**, från den avancerade menyn i ditt program **[!UICONTROL Action]** kan du börja designa ditt innehåll med **[!UICONTROL Edit content]** -knappen.

  ![](assets/design_inapp_journey.png)

The **[!UICONTROL Advanced formatting]** växlar aktiverar ytterligare alternativ för att anpassa upplevelsen.

När ditt meddelande i appen har skapats och dess innehåll har definierats och anpassats kan du granska och aktivera det. Meddelanden skickas sedan enligt kampanjschemat. Läs mer i [den här sidan](send-in-app.md).

## Meddelandelayout {#message-layout}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_inapp_authoring_message_layout"
>title="Definiera innehåll i appen"
>abstract="Meddelandelayouten innehåller mallar som du använder ofta för att rama in meddelandet. Anpassad layout innehåller alternativ för att överföra eller skapa anpassade HTML-meddelanden."

Från **[!UICONTROL Message Layout]** väljer du ett av de fyra olika layoutalternativen som du kan välja mellan beroende på ditt meddelandebehov.

![](assets/in_app_web_design_1.png)

* **[!UICONTROL Fullscreen]**: Den här typen av layout täcker hela skärmen på målenheterna.

  Den stöder medie- (bild, video), text- och knappkomponenter.

* **[!UICONTROL Modal]**: Den här layouten visas i ett stort varningsfönster och programmet visas fortfarande i bakgrunden.

  Den stöder medie- (bild, video), text- och knappkomponenter.

* **[!UICONTROL Banner]**: Den här typen av layout visas som ett systemspecifikt varningsmeddelande.

  Du kan bara lägga till en **[!UICONTROL Header]** och **[!UICONTROL Body]** till ditt meddelande.

* **[!UICONTROL Custom]**: I det anpassade meddelandeläget kan du importera och redigera ett av dina förkonfigurerade HTML-meddelanden direkt.

   * Välj **[!UICONTROL Compose]** för att ange eller klistra in HTML-koden i Raw-format.

     Använd den vänstra rutan för att utnyttja Journey Optimizer personaliseringsfunktioner. Mer information finns i [det här avsnittet](../personalization/personalize.md).

   * Välj **[!UICONTROL Import]** om du vill importera HTML- eller ZIP-filen med HTML.

## Fliken Innehåll {#content-tab}

Från **Innehåll** kan du definiera och anpassa innehållet i meddelandet och formatet för **Stäng** -knappen. Du kan också lägga till media i meddelanden i appen och lägga till åtgärdsknappar på den här fliken.

### Knappen Stäng {#close-button}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_inapp_authoring_close"
>title="Välj en stil för knappen Stäng."
>abstract="I avsnittet med stängningsknappar finns alternativ för att välja varianter av meddelandestängningsknappen och ett alternativ för att överföra en anpassad bild."

![](assets/in_app_web_design_2.png)

Välj **[!UICONTROL Style]** på **[!UICONTROL Close button]**.

Tillgängliga format är:

* **[!UICONTROL Simple]**
* **[!UICONTROL Circle]**
* **[!UICONTROL Custom image]** från en medie-URL eller dina resurser.

+++Fler alternativ med avancerad formatering

Om **[!UICONTROL Advanced formatting mode]** är aktiverad kan du kontrollera **[!UICONTROL Color]** om du vill välja färg och opacitet för knappen.

+++

### Media {#add-media}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_inapp_authoring_media"
>title="Lägg till media i ditt meddelande i appen för att skapa en övertygande upplevelse för slutanvändaren."
>abstract="Ange antingen en direkt länk till innehållet eller använd resursväljaren för att välja media i Resurser Essentials som ska läggas till i meddelandet."

The **[!UICONTROL Media]** I kan du lägga till media i dina meddelanden i appen för att skapa en övertygande upplevelse för slutanvändaren.

![](assets/in_app_web_design_3.png)

Ange din medie-URL eller klicka på **[!UICONTROL Select Assets]** om du vill lägga till resurser som lagras i ditt resursbibliotek direkt i ditt meddelande i appen. [Läs mer om resurshantering](../content-management/assets.md).
Du kan också lägga till en **[!UICONTROL Alternative text]** för skärmläsningsprogram.

+++Fler alternativ med avancerad formatering

Om **[!UICONTROL Advanced formatting mode]** är aktiverat kan du anpassa **[!UICONTROL Max height]** och **[!UICONTROL Max width]** av era medier.

+++

### Innehåll {#title-body}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_inapp_authoring_content"
>title="Skriv innehållet i fälten Rubrik och Brödtext för att skapa meddelandet."
>abstract="Både rubrik och brödtext kan läggas till här. Om du vill ta med personaliseringstoken öppnar du dialogrutan för personalisering."

Skriv innehållet i **[!UICONTROL Header]** och **[!UICONTROL Body]** fält.

![](assets/in_app_web_design_4.png)

Använd **[!UICONTROL Personalization]** ikon för att lägga till personalisering. Läs mer om personalisering i Adobe Journey Optimizer personaliseringsredigerare [i det här avsnittet](../personalization/personalize.md).

+++Fler alternativ med avancerad formatering

Om **[!UICONTROL Advanced formatting mode]** är aktiverat kan du välja för **[!UICONTROL Header]** och **[!UICONTROL Body]**:

* den **[!UICONTROL Font]**
* den **[!UICONTROL Pt size]**
* den **[!UICONTROL Font Color]**
* den **[!UICONTROL Alignment]**
+++

### Knappar {#add-buttons}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_inapp_authoring_buttons"
>title="Lägg till knappar så att användarna kan interagera med meddelandet i appen."
>abstract="I det här avsnittet kan du lägga till knappar för att ringa upp och utföra åtgärder i meddelandet. Du kan inkludera egen text och mål för varje knapp."

Lägg till knappar så att användarna kan interagera med meddelandet i appen.

![](assets/in_app_web_design_5.png)

Så här anpassar du knappen:

1. Redigera textfältet Knapp 1 (primär). Du kan också använda **[!UICONTROL Personalization]** -ikon för att definiera innehåll och personaliseringsdata.

1. Välj **[!UICONTROL Interact event]** som definierar knappens åtgärd efter att användarna interagerat med den.

1. Ange webb-URL:en eller länken till **[!UICONTROL Target]** fält.

1. Om du vill lägga till flera knappar klickar du **[!UICONTROL Add button]**.

+++Fler alternativ med avancerad formatering

Om **[!UICONTROL Advanced formatting mode]** är aktiverat kan du välja för **[!UICONTROL Buttons]**:

* den **[!UICONTROL Font]**
* den **[!UICONTROL Pt size]**
* den **[!UICONTROL Font Color]**
* den **[!UICONTROL Alignment]**
* den **[!UICONTROL Button style]**
* den **[!UICONTROL Radius]**
* den **[!UICONTROL Button color]**

+++

## Fliken Inställningar {#settings-tab}

Från **Inställningar** kan du definiera meddelandelayouten och förhandsgranska meddelandet i appen. Du kan även komma åt avancerade formateringsalternativ.

### Förhandsgranska {#preview-tab}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_inapp_authoring_preview"
>title="Förhandsgranska meddelandet i appen."
>abstract="Det här är den förhandsvisningsbild som visas när meddelandet skickas till enhetens meddelandesammanfattning."

>[!NOTE]
>
>Förhandsgranskning är bara tillgängligt för meddelanden i appen för mobiler.

![](assets/in_app_content_6.png)

The **[!UICONTROL App Preview]** I kan du lägga till en bakgrund bakom ditt meddelande i appen:

* Ett medium från en URL-länk.

* En resurs från ditt resursbibliotek.

* En bakgrundsfärg.

### Layout {#layout-options}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_inapp_authoring_layout"
>title="Definiera meddelandelayouten för ditt meddelande i appen."
>abstract="I det här avsnittet kan du lägga till en bakgrund i meddelandet i appen. Detta kräver att övertagandet av användargränssnittet är aktiverat."

![](assets/in_app_web_design_6.png)

The **[!UICONTROL Background image]** I kan du lägga till en bakgrund i meddelandet i appen:

* Ett medium från en URL-länk.

* En bakgrundsfärg.

### Meddelande {#message-tab}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_inapp_authoring_message_advanced"
>title="Definiera de avancerade inställningarna för meddelandet."
>abstract="I det här avsnittet kan du förbättra personaliseringen av ditt innehåll i appen, särskilt när avancerad formatering är aktiverat."

![](assets/in_app_web_design_7.png)

Med alternativet för övertagande av användargränssnitt, som är aktiverat som standard, kan du göra bakgrunden bakom ditt meddelande i appen mörkare för att framhäva fokus på ditt innehåll.

+++Fler alternativ med avancerad formatering

Om **[!UICONTROL Advanced formatting mode]** är aktiverat kan du anpassa meddelandet ytterligare med följande alternativ:

* **[!UICONTROL Customize gestures]**: gör att du kan anpassa vad användaren ska svepa. Om du väljer Avvisa kan du lägga till en anpassad interaktionshändelse och/eller målmål.

* **[!UICONTROL Customize UI takeover]**: låter dig välja en färg som ska visas i bakgrunden och dess opacitet.

* **[!UICONTROL Customize size]**: låter dig justera bredd och höjd för meddelanden i appen.

* **[!UICONTROL Customize position]**: låter dig anpassa positionen för dina meddelanden i appen på användarnas skärm. Du kan ändra justeringarna Lodrätt och Vågrätt.

* **[!UICONTROL Customize animation]**: låter dig anpassa dina Display- och Dismiss-animeringar, t.ex. om du får meddelanden i appen från vänster eller överst på användarens enhet.

* **[!UICONTROL Message round corner]**: gör att du kan lägga till runda hörn i meddelanden i appen genom att ändra **[!UICONTROL Corner radius]**.

+++

**Relaterade ämnen:**

* [Skapa meddelande i appen](create-in-app.md)
* [Rapport i appen](../reports/campaign-global-report.md#inapp-report)
* [Konfiguration i appen](inapp-configuration.md)

## Instruktionsvideo{#video}

I videon nedan visas hur du skapar och testar meddelanden i appen.

>[!VIDEO](https://video.tv.adobe.com/v/3410471?quality=12&learn=on)
