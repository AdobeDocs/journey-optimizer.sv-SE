---
title: Lägg till representationer i ett erbjudande
description: Lär dig hur du lägger till representationer i dina erbjudanden
feature: Offers
topic: Integrations
role: User
level: Intermediate
source-git-commit: 0fa8ba1dc16062ea1553f9978752f3c018cec4c6
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 1%

---

# Lägg till representationer i ett erbjudande {#add-representations}

Ett erbjudande kan visas på olika platser i ett meddelande: i en övre banderoll med en bild, som text i ett stycke, som ett HTML-block osv. Ju fler representationer ett erbjudande har, desto fler möjligheter finns det att använda erbjudandet i olika placeringssammanhang.

## Konfigurera offertens representationer {#representations}

Följ stegen nedan om du vill lägga till en eller flera representationer i ditt erbjudande och konfigurera dem.

1. För den första representationen börjar du med att välja **[!UICONTROL Channel]** som kommer att användas.

   ![](../assets/channel-placement.png)

   >[!NOTE]
   >
   >Endast de tillgängliga placeringarna för den valda kanalen visas i **[!UICONTROL Placement]** nedrullningsbar lista.

1. Välj en placering i listan.

   Du kan också använda knappen bredvid knappen **[!UICONTROL Placement]** om du vill bläddra bland alla placeringar.

   ![](../assets/browse-button-placements.png)

   Där kan du fortfarande filtrera placeringarna efter kanal- och/eller innehållstyp. Välj en placering och klicka på **[!UICONTROL Select]**.

   ![](../assets/browse-placements.png)

1. Lägg till innehåll i din representation. Läs mer i [det här avsnittet](#content).

1. När du lägger till innehåll som en bild eller URL kan du ange en **[!UICONTROL Destination link]**: de användare som klickar på erbjudandet dirigeras till motsvarande sida.

   ![](../assets/offer-destination-link.png)

1. Välj slutligen det språk du vill använda för att identifiera och hantera vad som ska visas för användarna.

1. Om du vill lägga till en annan representation använder du **[!UICONTROL Add representation]** och lägg till så många representationer som behövs.

   ![](../assets/offer-add-representation.png)

1. När du har lagt till alla representationer väljer du **[!UICONTROL Next]**.

## Definiera innehåll för dina representationer {#content}

Du kan lägga till olika typer av innehåll i en representation.

>[!NOTE]
>
>Endast innehåll som motsvarar placeringens innehållstyp är tillgängligt för användning.

### Lägg till bilder {#images}

Om den valda placeringen är av bildtyp kan du lägga till innehåll från **Adobe Experience Cloud Asset** bibliotek, ett centraliserat arkiv med resurser från [!DNL Adobe Experience Manager Assets Essentials].

>[!NOTE]
>
> Arbeta med [Adobe Experience Manager Assets Essentials](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/introduction.html?lang=en){target=&quot;_blank&quot;}, du måste distribuera [!DNL Assets Essentials] för din organisation och se till att användarna är en del av **Assets Essentials hemanvändare** eller/och **Assets Essentials-användare** Produktprofiler. Läs mer på [den här sidan](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/deploy-administer.html){target=&quot;_blank&quot;}.

1. Välj alternativet **[!UICONTROL Asset library]**.

1. Välj **[!UICONTROL Browse]**.

   ![](../assets/offer-browse-asset-library.png)

1. Bläddra bland resurserna och välj den bild du vill använda

1. Klicka på **[!UICONTROL Select]**.

   ![](../assets/offer-select-asset.png)

### Lägg till URL:er {#urls}

Om du vill lägga till innehåll från en extern offentlig plats väljer du **[!UICONTROL URL]** anger du sedan URL-adressen till det innehåll som ska läggas till.

![](../assets/offer-content-url.png)

### Lägg till egen text {#custom-text}

Du kan också infoga text när du väljer en kompatibel placering.

1. Välj **[!UICONTROL Custom]** och klicka **[!UICONTROL Add content]**.

   ![](../assets/offer-add-content.png)

   >[!NOTE]
   >
   >Det här alternativet är inte tillgängligt för bildtypsplaceringar.

1. Skriv den text som ska visas i erbjudandet.

   ![](../assets/offer-text-content.png)

   Du kan anpassa ditt innehåll med uttrycksredigeraren. Läs mer på [personalisering](../../personalization/personalize.md#use-expression-editor).

   ![](../assets/offer-personalization.png)

   >[!NOTE]
   >
   >Endast **[!UICONTROL Profile attributes]**, **[!UICONTROL Segment memberships]** och **[!UICONTROL Helper functions]** Det finns källor för beslutsförvaltning.
