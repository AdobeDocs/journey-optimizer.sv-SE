---
title: Utforma innehållskort
description: Lär dig designa innehåll för innehållskort
topic: Content Management
feature: Content Cards
role: User
level: Beginner
exl-id: b83bdade-7275-4eef-9c49-fc1d157cee0d
source-git-commit: 0ec43a204f5fcf0bddf38cfd381f0ea496c7de70
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 0%

---

# Utforma innehåll för innehållskort {#design-content-card}

Utvecklingskonstruktionen för kort är en formulärbaserad redigeringsfunktion som ger marknadsförarna grundläggande information som kan återges av utvecklare.

När innehållet är definierat och personaliserat kan du granska och aktivera det. Din kampanj skickas enligt angivet schema. [Läs mer på den här sidan](../campaigns/review-activate-campaign.md).

## Innehållskortets layout

![](assets/content-card-image.png)

I avsnittet **[!UICONTROL Content card layout]** väljer du ett av de tre bildlayoutalternativen baserat på dina meddelandekrav.

* **[!UICONTROL Small image]**: Visar en kompakt bild tillsammans med text, vilket är idealiskt för meddelanden där innehåll prioriteras framför visuella.

  Mer information finns i Adobe Developer-dokumentationen [&#x200B; för iOS](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/content-card-ui/iOS/templates/smallimage-template/) och [&#x200B; för Android](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/content-card-ui/Android/public-classes/state/smallimagecarduistate/).

* **[!UICONTROL Large image]**: Innehåller en framträdande bild ovanför eller bredvid texten, vilket gör visuellt till huvudfokus för ditt meddelande.

  Mer information finns i Adobe Developer-dokumentationen [&#x200B; för iOS](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/content-card-ui/iOS/templates/largeimage-template/) och [&#x200B; för Android](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/content-card-ui/Android/public-classes/state/largeimagecarduistate/).

* **[!UICONTROL Image only]**: Visar bilden utan tillhörande text, perfekt för visuella meddelanden eller fristående bilder.

  Mer information finns i Adobe Developer-dokumentationen [&#x200B; för iOS](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/content-card-ui/iOS/templates/imageonly-template/) och [&#x200B; för Android](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/content-card-ui/Android/public-classes/state/imageonlycarduistate/).

## Fliken Innehåll {#content-tab}

På fliken **[!UICONTROL Content]** kan du anpassa dina innehållskort genom att definiera innehåll och lägga till media och åtgärdsknappar direkt från den här fliken.

### Textinnehåll {#title-body}

![](assets/content-card-design-2.png)

Skriv texten i fälten **[!UICONTROL Title]** och **[!UICONTROL Body]** för att skapa meddelandet.

Om du vill anpassa meddelandet ytterligare kan du använda ikonen **[!UICONTROL Personalization]** för att lägga till anpassade element. Detaljerade instruktioner om hur du använder personaliseringsfunktionerna finns i [det här avsnittet](../personalization/personalize.md).

### Media {#add-media}

![](assets/content-card-design-3.png)

I fältet **[!UICONTROL Media]** kan du förbättra dina innehållskort genom att lägga till media, vilket kan göra presentationen mer engagerande för slutanvändarna.

Om du vill ta med media skriver du antingen in URL-adressen för det medium som du vill använda eller klickar på ikonen **[!UICONTROL Select Assets]** för att välja bland resurser som lagras i ditt Assets-bibliotek. [Läs mer om resurshantering](../integrations/assets.md).

+++Fler alternativ med avancerad formatering

Om **[!UICONTROL Advanced formatting mode]** är aktiverat kan du lägga till en **[!UICONTROL Alternative text]** för skärmläsarprogram och en annan resurs i fältet **[!UICONTROL Dark Mode Media URL]**.

+++

### Knappar {#add-buttons}

![](assets/content-card-design-4.png)

Lägg till knappar så att användarna kan interagera med dina innehållskort.

1. Klicka på **[!UICONTROL Add button]** om du vill skapa en ny åtgärdsknapp.

1. Redigera knappfältet **[!UICONTROL Title]** för att ange etiketten som ska visas på knappen.

1. Välj en **[!UICONTROL Interact event]** för att definiera vilken åtgärd som ska utlösas när användarna klickar på eller interagerar med knappen.

1. I fältet **[!UICONTROL Target]** anger du webb-URL:en eller länken till den plats där användarna ska dirigeras efter att ha interagerat med knappen.

<!--
+++More options with advanced formatting

If the **[!UICONTROL Advanced formatting mode]** is switched on, you can choose for your **[!UICONTROL Buttons]**:

* the **[!UICONTROL Font]**
* the **[!UICONTROL Pt size]**
* the **[!UICONTROL Font Color]**
* the **[!UICONTROL Alignment]**

+++
-->

### Knappen Stäng {#close-button}

![](assets/content-card-design-1.png)

Välj **[!UICONTROL Style]** för **[!UICONTROL Dismiss button]** om du vill anpassa utseendet.

Du kan välja bland följande format:

* **[!UICONTROL None]**
* **[!UICONTROL Simple]**
* **[!UICONTROL Circle]**



<!--
+++More options with advanced formatting

If the **[!UICONTROL Advanced formatting mode]** is switched on, you can choose for your **[!UICONTROL Header]** and **[!UICONTROL Body]**:

* the **[!UICONTROL Font]**
* the **[!UICONTROL Pt size]**
* the **[!UICONTROL Font Color]**
* the **[!UICONTROL Alignment]**
+++
-->



### Vid klickning, beteende

![](assets/content-card-design-5.png)

I fältet **[!UICONTROL Target URL]** anger du webb-URL:en eller dee-linken som dirigerar användarna till önskad destination efter att de interagerat med ditt innehållskort. Det kan vara en extern webbplats, en specifik sida i din app eller någon annan plats där du vill att användarna ska hamna baserat på deras interaktion.

## Fliken Data

## Anpassade data {#custom-data}

![](assets/content-card-design-6.png)

Klicka på **[!UICONTROL Custom data]** i avsnittet **[!UICONTROL Add Key/Value pair]** om du vill ta med anpassade variabler i nyttolasten. Med dessa nyckel-/värdepar kan du skicka ytterligare data beroende på din konfiguration. På så sätt kan ni lägga till personaliserat eller dynamiskt innehåll, spårningsinformation eller andra data som är relevanta för konfigurationen.
