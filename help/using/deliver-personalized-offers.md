---
title: Lägg till personaliserade erbjudanden
description: Lär dig hur du lägger till personaliserade erbjudanden i dina meddelanden
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 0%

---

# Lägg till anpassade erbjudanden {#deliver-personalized-offers}

![](assets/do-not-localize/badge.png)

## Om beslutshantering {#about-offer-decisioning}

Med [!DNL Journey Optimizer] kan du i dina e-postmeddelanden infoga beslut (som tidigare kallats erbjudandeaktiviteter) som utnyttjar beslutsmotorn för erbjudanden för att välja det bästa erbjudandet som ska levereras till dina kunder.

Du kan t.ex. lägga till ett beslut som i ditt e-postmeddelande visas ett särskilt rabatterbjudande som varierar beroende på mottagarens lojalitetsnivå.

Mer information om hur du skapar och hanterar erbjudanden finns i [det här avsnittet](offers/get-started/starting-offer-decisioning.md).

## Infoga ett beslut i ett e-postmeddelande {#insert-offers}

Följ stegen nedan för att infoga ett beslut i ett e-postmeddelande:

1. Skapa e-postmeddelandet och öppna sedan e-postdesignern för att konfigurera innehållet.

1. Lägg till en **[!UICONTROL Offer decision]**-innehållskomponent (se [Använd innehållskomponenter](content-components.md)).

   ![](assets/deliver-offer-component.png)

1. En **[!UICONTROL Offer decision]**-flik läggs till i komponenten. Klicka på **[!UICONTROL Add personalization - Offer decision]** för att lägga till en erbjudandeaktivitet.

   ![](assets/deliver-offer-tab.png)

1. Välj den placering som motsvarar de erbjudanden du vill visa.

   Placeringar är behållare som används för att visa upp dina erbjudanden. I det här exemplet använder vi placeringen&quot;e-post top image&quot;. Den här placeringen har skapats i erbjudandebiblioteket för att visa erbjudanden av bildtyp som ligger överst i meddelandena.

1. Välj den erbjudandeaktivitet som ska användas i innehållskomponenten och klicka sedan på **[!UICONTROL Add]**.

   >[!NOTE]
   >
   >Observera att endast beslut som är kompatibla med den valda placeringen visas i listan. I det här exemplet matchar endast en erbjudandeaktivitet placeringen &quot;email top image&quot;.

   ![](assets/deliver-offer-placement.png)

1. Erbjudandeaktiviteten har nu lagts till i komponenten. Du kan förhandsgranska de olika erbjudanden som är en del av beslutet med hjälp av **[!UICONTROL Offers]**-avsnittet eller innehållskomponentpilarna.

   ![](assets/deliver-offer-preview.png)
