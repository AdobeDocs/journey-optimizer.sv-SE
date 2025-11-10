---
title: Lägg till representationer i ett erbjudande
description: Lär dig hur du lägger till representationer i dina erbjudanden
badge: label="Äldre" type="Informative"
feature: Decision Management
topic: Integrations
role: User
level: Intermediate
exl-id: 718af505-7b7c-495e-8974-bd9c35d796bb
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 0%

---

# Lägg till representationer i ett erbjudande {#add-representations}

>[!CONTEXTUALHELP]
>id="ajo_decisioning_representation"
>title="Representationer"
>abstract="Lägg till representationer för att definiera var ditt erbjudande ska visas i meddelandet. Ju fler representationer ett erbjudande har, desto fler möjligheter finns det att använda erbjudandet i olika placeringssammanhang."

Ett erbjudande kan visas på olika platser i ett meddelande: i en översta banderoll med en bild, som text i ett stycke, som ett HTML-block osv. Ju fler representationer ett erbjudande har, desto fler möjligheter finns det att använda erbjudandet i olika placeringssammanhang.

## Konfigurera offertens representationer {#representations}

Följ stegen nedan om du vill lägga till en eller flera representationer i ditt erbjudande och konfigurera dem.

1. För den första representationen börjar du med att välja **[!UICONTROL Channel]** som ska användas.

   ![](../assets/channel-placement.png)

   >[!NOTE]
   >
   >Endast de tillgängliga placeringarna för den valda kanalen visas i listrutan **[!UICONTROL Placement]**.

1. Välj en placering i listan.

   Du kan också använda knappen bredvid listrutan **[!UICONTROL Placement]** för att bläddra bland alla placeringar.

   ![](../assets/browse-button-placements.png)

   Där kan du fortfarande filtrera placeringarna efter kanal- och/eller innehållstyp. Välj en placering och klicka på **[!UICONTROL Select]**.

   ![](../assets/browse-placements.png)

1. Lägg till innehåll i din representation. Lär dig hur i [det här avsnittet](#content).

1. När du lägger till innehåll som en bild eller URL kan du ange **[!UICONTROL Destination link]**: de användare som klickar på erbjudandet dirigeras till motsvarande sida.

   ![](../assets/offer-destination-link.png)

1. Välj slutligen det språk du vill använda för att identifiera och hantera vad som ska visas för användarna.

1. Om du vill lägga till ytterligare en representation använder du knappen **[!UICONTROL Add representation]** och lägger till så många representationer som behövs.

   ![](../assets/offer-add-representation.png)

1. När du har lagt till alla dina representationer väljer du **[!UICONTROL Next]**.

## Definiera innehåll för dina representationer {#content}

Du kan lägga till olika typer av innehåll i en representation.

>[!NOTE]
>
>Endast innehåll som motsvarar placeringens innehållstyp är tillgängligt för användning.

### Lägg till bilder {#images}

Om den valda placeringen är av bildtyp kan du lägga till innehåll från **Adobe Experience Cloud Asset** -biblioteket, en centraliserad databas med resurser från [!DNL Adobe Experience Manager Assets].

>[!NOTE]
>
> Om du vill arbeta med [Adobe Experience Manager Assets Essentials](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/introduction.html?lang=sv-SE){target="_blank"} måste du distribuera [!DNL Assets Essentials] för din organisation och se till att användarna tillhör produktprofilerna **Assets Essentials Consumer Users** eller **Assets Essentials Users**. Läs mer om [den här sidan](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/get-started-admins/deploy-administer.html?lang=sv-SE){target="_blank"}.

1. Välj alternativet **[!UICONTROL Asset library]**.

1. Välj **[!UICONTROL Browse]**.

   ![](../assets/offer-browse-asset-library.png)

1. Bläddra bland resurserna och välj den bild du vill använda

1. Klicka på **[!UICONTROL Select]**.

   ![](../assets/offer-select-asset.png)

### Lägga till HTML- eller JSON-filer {#html-json}

Om den valda placeringen är av HTML-typ kan du även lägga till HTML- eller JSON-innehåll från [Adobe Experience Cloud-resursbiblioteket](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/introduction.html?lang=sv-SE){target="_blank"}).

Du har t.ex. skapat en e-postmall från HTML i [Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager.html?lang=sv-SE){target="_blank"} och vill använda den filen för ditt erbjudandeinnehåll. I stället för att skapa en ny fil kan du överföra mallen till **resursbiblioteket** för att kunna återanvända den i offertens representationer.

Om du vill återanvända ditt innehåll i en representation bläddrar du till **resursbiblioteket** enligt beskrivningen i [det här avsnittet](#images) och väljer den HTML- eller JSON-fil du vill använda.

![](../assets/offer-browse-asset-library-json.png)

### Lägg till URL:er {#urls}

Om du vill lägga till innehåll från en extern offentlig plats väljer du **[!UICONTROL URL]** och anger sedan URL-adressen för innehållet som ska läggas till.

Du kan anpassa URL-adresser med personaliseringsredigeraren. Läs mer om [personalisering](../../personalization/personalize.md#use-expression-editor).

![](../assets/offer-content-url.png)

Du vill till exempel anpassa bilden som visas som ett erbjudande. Man vill att användare som föredrar semestrar ska se NYC-skylten och användare som föredrar strandsemestrar ska se Hawaii i i nordkusten.

Använd personaliseringsredigeraren för att hämta profilattribut som lagras i Adobe Experience Platform med fackscheman. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schemas-overview.html?lang=sv-SE){target="_blank"}

![](../assets/offer-content-url-personalization.png)

Om du anger **[!UICONTROL Destination link]** kan du även anpassa URL:en som användarna som klickar på erbjudandet dirigeras till.

### Lägga till egen text {#custom-text}

Du kan också infoga text när du väljer en kompatibel placering.

1. Välj alternativet **[!UICONTROL Custom]** och klicka på **[!UICONTROL Add content]**.

   ![](../assets/offer-add-content.png)

   >[!NOTE]
   >
   >Det här alternativet är inte tillgängligt för bildtypsplaceringar.

1. Skriv den text som ska visas i erbjudandet.

   ![](../assets/offer-text-content.png)

   Ni kan personalisera ert innehåll med personaliseringsredigeraren. Läs mer om [personalisering](../../personalization/personalize.md#use-expression-editor).

   ![](../assets/offer-personalization.png)

   >[!NOTE]
   >
   >Endast källorna **[!UICONTROL Profile attributes]**, **[!UICONTROL Audiences]** och **[!UICONTROL Helper functions]** är tillgängliga för beslutshantering.

## Anpassa representationer baserat på kontextdata{#context-data}

När kontextdata skickas i [Edge-beslutsanropet](../api-reference/offer-delivery-api/edge-decisioning-api.md) kan du använda dessa data för att anpassa representationer dynamiskt. Du kan till exempel anpassa representationen av ett erbjudande baserat på realtidsfaktorer som aktuella väderförhållanden när beslutet fattas.

Om du vill använda kontextdata i offertrepresentationer lägger du till kontextdatavariabeln direkt i representationsinnehållet med hjälp av namnutrymmet `profile.timeSeriesEvents.`.

Här följer ett syntaxexempel som används för att anpassa en offerts representation baserat på användarnas operativsystem:

```
 {%#if profile.timeSeriesEvents.device.model = "Apple"%}ios{%else%}android{%/if%} 
```

Motsvarande Edge-beslutsbegäran med kontextdata är följande:

```
{
    "body": {
        "xdm": {
            "identityMap": {
                "Email": [
                    {
                        "id": "xyz@abc.com"
                    }
                ]
            },
            "device": {
                "model": "Apple"
            }
        },
        "extra": {
            "query": {
                "decisionScopes": [
                    "eyJ4ZG06..."
                ]
            }
        }
    }
}
```
