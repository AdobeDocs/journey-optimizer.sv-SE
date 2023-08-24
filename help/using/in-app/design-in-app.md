---
title: Designa ditt innehåll i appen
description: Lär dig hur du utformar innehåll i appen i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
keywords: i appen, meddelande, design, formatering
exl-id: 7d7aa721-96aa-4ebc-a51c-e693f893f34f
source-git-commit: 39953bb09a699ed4fd07db26a3f2e54f4e2cacd7
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 9%

---

# Designa ditt innehåll i appen {#design-content}

Du kan redigera innehållet i appen för att konfigurera upplevelsealternativ:

* I en **[!UICONTROL Campaign]**, från **[!UICONTROL Action]** för att konfigurera meddelandeinnehållet klickar du på **[!UICONTROL Edit content]** -knappen.

  ![](assets/edit-in-app-content.png)

* I en **[!UICONTROL Journey]**, från den avancerade menyn i ditt program **[!UICONTROL Action]** kan du börja designa ditt innehåll med **[!UICONTROL Edit content]** -knappen.

  ![](assets/design_inapp_journey.png)

The **[!UICONTROL Advanced formatting]** växlar aktiverar ytterligare alternativ för att anpassa upplevelsen.

När ditt meddelande i appen har skapats och dess innehåll har definierats och anpassats kan du granska och aktivera det. Meddelanden skickas sedan enligt kampanjschemat. Läs mer i [den här sidan](send-in-app.md).

## Meddelandelayout {#message-layout}

Från **[!UICONTROL Message Layout]** väljer du ett av de fyra olika layoutalternativen som du kan välja mellan beroende på ditt meddelandebehov.

![](assets/in_app_content_1.png)

* **[!UICONTROL Fullscreen]**: Den här typen av layout täcker hela skärmen på målenheterna.

  Den stöder medie- (bild, video), text- och knappkomponenter.

* **[!UICONTROL Modal]**: Layouten visas i ett stort varningsfönster och programmet visas fortfarande i bakgrunden.

  Den stöder medie- (bild, video), text- och knappkomponenter.

* **[!UICONTROL Banner]**: Den här typen av layout visas som ett systemspecifikt varningsmeddelande.

  Du kan bara lägga till en **[!UICONTROL Header]** och **[!UICONTROL Body]** till ditt meddelande.

* **[!UICONTROL Custom]**: I det anpassade meddelandeläget kan du importera och redigera ett av dina förkonfigurerade HTML-meddelanden direkt.

   * Välj **[!UICONTROL Compose]** för att ange eller klistra in HTML-koden i Raw-format.

     Använd den vänstra rutan för att utnyttja Journey Optimizer personaliseringsfunktioner. Mer information om detta finns i [det här avsnittet](../personalization/personalize.md).

   * Välj **[!UICONTROL Import]** om du vill importera HTML- eller ZIP-filen med HTML.

## Fliken Innehåll {#content-tab}

Från **Innehåll** kan du definiera och anpassa: meddelandets innehåll och formatet för **Stäng** -knappen. Du kan också lägga till media i meddelanden i appen och lägga till åtgärdsknappar på den här fliken.

### Knappen Stäng {#close-button}

![](assets/in_app_content_2.png)

Välj **[!UICONTROL Style]** på **[!UICONTROL Close button]**.

Tillgängliga format är:

* **[!UICONTROL Simple]**
* **[!UICONTROL Circle]**
* **[!UICONTROL Custom image]** från en medie-URL eller dina resurser.

+++Fler alternativ med avancerad formatering

Om **[!UICONTROL Advanced formatting mode]** är aktiverad kan du kontrollera **[!UICONTROL Color]** om du vill välja färg och opacitet för knappen.

+++

### Media {#add-media}

The **[!UICONTROL Media]** I kan du lägga till media i dina meddelanden i appen för att skapa en övertygande upplevelse för slutanvändaren.

![](assets/in_app_content_3.png)

Ange din medie-URL eller klicka på **[!UICONTROL Select Assets]** om du vill lägga till resurser som lagras i ditt resursbibliotek direkt i ditt meddelande i appen. [Läs mer om resurshantering](../content-management/assets-essentials.md).
Du kan också lägga till en **[!UICONTROL Alternative text]** för skärmläsningsprogram.

+++Fler alternativ med avancerad formatering

Om **[!UICONTROL Advanced formatting mode]** är aktiverat kan du anpassa **[!UICONTROL Max height]** och **[!UICONTROL Max width]** av era medier.

+++

### Huvud och brödtext {#title-body}

Skriv innehållet i **[!UICONTROL Header]** och **[!UICONTROL Body]** fält.

![](assets/in_app_content_4.png)

Använd **[!UICONTROL Personalization]** ikon för att lägga till personalisering. Läs mer om personalisering i Adobe Journey Optimizer Expression Editor [i det här avsnittet](../personalization/personalize.md).

+++Fler alternativ med avancerad formatering

Om **[!UICONTROL Advanced formatting mode]** är aktiverat kan du välja för **[!UICONTROL Header]** och **[!UICONTROL Body]**:

* den **[!UICONTROL Font]**
* den **[!UICONTROL Pt size]**
* den **[!UICONTROL Font Color]**
* den **[!UICONTROL Alignment]**
+++

### Knapparna {#add-buttons}

Lägg till knappar så att användarna kan interagera med meddelandet i appen.

![](assets/in_app_content_5.png)

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

### Förhandsgranskning {#preview-tab}

![](assets/in_app_content_6.png)

The **[!UICONTROL App Preview]** I kan du lägga till en bakgrund bakom ditt meddelande i appen:

* Ett medium från en URL-länk.

* En resurs från ditt resursbibliotek.

* En bakgrundsfärg.

### Layout {#layout-options}

![](assets/in_app_content_7.png)

The **[!UICONTROL Background image]** I kan du lägga till en bakgrund i meddelandet i appen:

* Ett medium från en URL-länk.

* En bakgrundsfärg.

### Meddelande {#message-tab}

![](assets/in_app_content_8.png)

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
