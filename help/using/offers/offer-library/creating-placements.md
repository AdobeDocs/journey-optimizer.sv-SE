---
title: Skapa placeringar
description: Lär dig hur du skapar ersättningar för dina erbjudanden
feature: Decision Management
topic: Integrations
role: User
level: Intermediate
exl-id: dfaf887e-d4b3-45b0-8297-bffdb0abff4d
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 1%

---

# Skapa placeringar {#create-placements}

>[!CONTEXTUALHELP]
>id="ajo_decisioning_placement"
>title="Placement"
>abstract="En placering är en behållare som används för att visa erbjudanden. Det hjälper er att se till att rätt erbjudandeinnehåll visas på rätt plats i ert budskap. Placeringar skapas från menyn Komponenter."

En placering säkerställer att rätt erbjudandeinnehåll visas på rätt plats i ert meddelande. När du lägger till innehåll i ett erbjudande blir du ombedd att välja en placering där innehållet kan visas.

➡️ [Lär dig hur du skapar placeringar i den här videon](#video)

I exemplet nedan finns det tre placeringar som motsvarar olika typer av innehåll (bild, text, HTML).

![](../assets/offers_placement_schema.png)

Listan över placeringar finns i **[!UICONTROL Components]** -menyn. Det finns filter som hjälper dig att hämta placeringar utifrån en viss kanal eller ett visst innehåll.

![](../assets/placements_filter.png)

Så här skapar du en placering:

1. Klicka på **[!UICONTROL Create placement]**.

   ![](../assets/offers_placement_creation.png)

1. Definiera placeringens egenskaper:

   * **[!UICONTROL Name]**: Placeringens namn. Se till att definiera ett beskrivande namn så att det blir enklare att hämta det.
   * **[!UICONTROL Channel type]**: Den kanal som placeringen ska användas för.
   * **[!UICONTROL Content type]**: Den typ av innehåll som placeringen kan visa: Text, HTML, Bildlänk eller JSON.
   * **[!UICONTROL Description]**: En beskrivning av placeringen (valfritt).

   ![](../assets/offers_placement_creation_properties.png)


1. The **[!UICONTROL Request settings]** och **[!UICONTROL Response format]** -avsnitten innehåller ytterligare parametrar:

   * **[!UICONTROL Allow Duplicates across placements]**: Bestäm om samma erbjudande kan erbjudas flera gånger på olika platser. Om det är aktiverat kommer systemet att överväga samma erbjudande för flera praktik. Som standard är parametern inställd på false.

     Om det här alternativet är inställt på false för alla placeringar i en beslutsbegäran, ärver alla placeringar i begäran inställningen &quot;false&quot;.

   * **[!UICONTROL Request offer]**: Som standard returneras ett erbjudande om beslutsomfånget för varje profil. Du kan justera antalet returnerade erbjudanden med det här alternativet. Om du till exempel väljer 2 visas de två bästa erbjudandena för det valda beslutsområdet.

   * **[!UICONTROL Include content]** / **[!UICONTROL Include metadata]**: ange om erbjudandets innehåll och metadata ska returneras i API-svaret. Du kan endast inkludera alla metadata eller specifika fält. Som standard är Inkludera metadata inställt på true.

   Dessa parametrar kan även anges direkt i din API-begäran om du arbetar med [Besluts-API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/offer-delivery-api/decisioning-api.html). Om du konfigurerar dem i användargränssnittet kan du spara tid eftersom du inte behöver skicka dem i varje API-begäran. Observera, att om du konfigurerar parametrarna både i användargränssnittet och i API-begäran, gäller värdena från API-begäran framför dem i gränssnittet.

   >[!NOTE]
   >
   >Om du arbetar med [API för Edge Decisioning](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/offer-delivery-api/edge-decisioning-api.html?)kan du inte ange de här parametrarna i din begäran. Du måste definiera dem på den här skärmen.
   >
   >Om du arbetar med [API för gruppbeslut](../api-reference/offer-delivery-api/batch-decisioning-api.md)kan du ange de här parametrarna antingen på den här skärmen eller i din API-begäran. Om parametervärdena inte överensstämmer mellan skärmen och APi-begäran används värdena för begäran.

1. Klicka på **[!UICONTROL Save]** för att bekräfta.

1. När placeringen har skapats visas den i placeringslistan. Du kan markera den för att visa dess egenskaper och redigera den.

   ![](../assets/placement_created.png)

## Instruktionsvideo{#video}

Lär dig hur du skapar praktik i beslutshantering.

>[!VIDEO](https://video.tv.adobe.com/v/329372?quality=12)

