---
title: Utforma innehållskort
description: Lär dig designa innehåll för innehållskort
topic: Content Management
role: User
level: Beginner
badge: label="Begränsad tillgänglighet" type="Informative"
hide: true
hidefromtoc: true
source-git-commit: 8a902298bbbac5689b4f84266dd9c9027e45fad5
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 1%

---

# Utforma innehåll för innehållskort {#design-content-card}

>[!BEGINSHADEBOX]

**Innehållsförteckning**

* [Kom igång med innehållskort](get-started-content-card.md)
* [Krav för innehållskort](content-card-configuration-prereq.md)
* [Konfigurera innehållskortskanal i Journey Optimizer](content-card-configuration.md)
* [Skapa innehållskort](create-content-card.md)
* **Utforma innehållskort**
* [Rapport om innehållskort](content-card-report.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>Innehållskort är för närvarande bara tillgängliga för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.

Utvecklingskonstruktionen för kort är en formulärbaserad redigeringsupplevelse som ger marknadsförarna grundläggande indata som kan användas för att återges av utvecklaren.

När innehållet är definierat och personaliserat kan du granska och aktivera det. Din kampanj skickas enligt angivet schema. [Läs mer på den här sidan](../campaigns/review-activate-campaign.md).

## Fliken Innehåll {#content-tab}

På fliken **[!UICONTROL Content]** kan du anpassa dina innehållskort genom att definiera både deras innehåll och designen för knappen **[!UICONTROL Close]**. Dessutom kan du förbättra innehållet med media och lägga till åtgärdsknappar direkt från den här fliken.

### Knappen Stäng {#close-button}

![](assets/content-card-design-1.png)

Välj **[!UICONTROL Style]** för **[!UICONTROL Close button]** om du vill anpassa utseendet.

Du kan välja bland följande format:

* **[!UICONTROL None]**
* **[!UICONTROL Simple]**
* **[!UICONTROL Circle]**

### Innehåll {#title-body}

Skriv texten i fälten **[!UICONTROL Title]** och **[!UICONTROL Body]** för att skapa meddelandet.

![](assets/content-card-design-2.png)

+++Fler alternativ med avancerad formatering

Om **[!UICONTROL Advanced formatting mode]** är aktiverat kan du välja för **[!UICONTROL Header]** och **[!UICONTROL Body]**:

* **[!UICONTROL Font]**
* **[!UICONTROL Pt size]**
* **[!UICONTROL Font Color]**
* **[!UICONTROL Alignment]**
+++

Om du vill anpassa meddelandet ytterligare kan du använda ikonen **[!UICONTROL Personalization]** för att lägga till anpassade element. Detaljerade instruktioner om hur du använder personaliseringsfunktionerna finns i [det här avsnittet](../personalization/personalize.md).

### Media {#add-media}

I fältet **[!UICONTROL Media]** kan du förbättra dina innehållskort genom att lägga till media, vilket kan göra presentationen mer engagerande för slutanvändarna.

![](assets/content-card-design-3.png)

Om du vill ta med media skriver du antingen in URL-adressen för det medium som du vill använda eller klickar på ikonen **[!UICONTROL Select Assets]** för att välja bland resurser som lagras i ditt Assets-bibliotek. [Läs mer om resurshantering](../content-management/assets.md).

+++Fler alternativ med avancerad formatering

Om **[!UICONTROL Advanced formatting mode]** är aktiverat kan du lägga till en **[!UICONTROL Alternative text]** för skärmläsarprogram och en annan resurs i fältet **[!UICONTROL Dark Mode Media URL]**.

+++

### Knappar {#add-buttons}

Lägg till knappar så att användarna kan interagera med dina innehållskort.

![](assets/content-card-design-4.png)

1. Klicka på **[!UICONTROL Add button]** om du vill skapa en ny åtgärdsknapp.

1. Redigera knappfältet **[!UICONTROL Title]** för att ange etiketten som ska visas på knappen.

1. Välj en **[!UICONTROL Interact event]** för att definiera vilken åtgärd som ska utlösas när användarna klickar på eller interagerar med knappen.

1. I fältet **[!UICONTROL Target]** anger du webb-URL:en eller länken till den plats där användarna ska dirigeras efter att ha interagerat med knappen.

+++Fler alternativ med avancerad formatering

Om **[!UICONTROL Advanced formatting mode]** är aktiverat kan du välja för **[!UICONTROL Buttons]**:

* **[!UICONTROL Font]**
* **[!UICONTROL Pt size]**
* **[!UICONTROL Font Color]**
* **[!UICONTROL Alignment]**

+++

### Vid klickning, beteende

![](assets/content-card-design-5.png)

I fältet **[!UICONTROL Target URL]** anger du webb-URL:en eller dee-linken som dirigerar användarna till önskad destination efter att de interagerat med ditt innehållskort. Det kan vara en extern webbplats, en specifik sida i din app eller någon annan plats där du vill att användarna ska hamna baserat på deras interaktion.

## Fliken Data

## Anpassade data {#custom-data}

![](assets/content-card-design-6.png)

Klicka på **[!UICONTROL Add Key/Value pair]** i avsnittet **[!UICONTROL Custom data]** om du vill ta med anpassade variabler i nyttolasten. Med dessa nyckel-/värdepar kan du skicka ytterligare data beroende på din konfiguration. På så sätt kan ni lägga till personaliserat eller dynamiskt innehåll, spårningsinformation eller andra data som är relevanta för konfigurationen.
