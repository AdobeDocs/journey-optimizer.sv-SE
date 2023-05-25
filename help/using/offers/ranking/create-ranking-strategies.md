---
product: experience platform
solution: Experience Platform
title: Skapa AI-modeller
description: Lär dig hur du skapar AI-modeller för att rangordna erbjudanden
feature: Ranking Formulas
role: User
level: Intermediate
exl-id: 81d07ec8-e808-4bc6-97b1-b9f7db2aec22
source-git-commit: 4f331eff73991c32682ba2c1ca5f6b7341a561e1
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 2%

---

# Skapa AI-modeller {#ai-rankings}

[!DNL Journey Optimizer] kan du skapa **AI-modeller** att rangordna erbjudanden baserat på era affärsmål.

>[!CAUTION]
>
>Om du vill skapa, redigera eller ta bort AI-modeller måste du ha **Hantera rankningsstrategier** behörighet. [Läs mer](../../administration/high-low-permissions.md#manage-ranking-strategies)

## Skapa en AI-modell {#create-ranking-strategy}

Så här skapar du en AI-modell:

1. Skapa en datauppsättning där konverteringshändelser samlas in. [Lär dig mer](../data-collection/create-dataset.md)

1. I **[!UICONTROL Components]** -menyn, gå till **[!UICONTROL Ranking]** tabbtangenten och sedan **[!UICONTROL AI models]**.

   ![](../assets/ai-ranking-list.png)

   Alla AI-modeller som har skapats hittills visas.

1. Klicka på knappen **[!UICONTROL Create AI model]**.

1. Ange ett unikt namn och en beskrivning för AI-modellen och välj sedan den typ av AI-modell som du vill skapa:

   * **[!UICONTROL Auto-optimization]** optimerar erbjudanden baserat på tidigare erbjudanden. [Läs mer](auto-optimization-model.md)
   * **[!UICONTROL Personalized optimization]** optimerar och personaliserar erbjudanden baserat på segment och erbjudanden. [Läs mer](personalized-optimization-model.md)

   ![](../assets/ai-ranking-fields.png)

   >[!NOTE]
   >
   >The **[!UICONTROL Optimization metric]** innehåller information om den konverteringshändelse som används av AI-modellen för att beräkna offerternas rankning.
   >
   >[!DNL Journey Optimizer] Rangordna erbjudanden baserat på **konverteringsgrad** (Konverteringstakt = Totalt antal konverteringshändelser / Totalt antal tryckningshändelser). Konverteringsgraden beräknas med hjälp av två typer av mätvärden:
   >* **Impression-händelser** (erbjudanden som visas)
   >* **Konverteringshändelser** (erbjudanden som leder till klickningar via e-post eller webben).

   >
   >Dessa händelser hämtas automatiskt med Web SDK eller Mobile SDK som har angetts. Läs mer om detta i [Adobe Experience Platform Web SDK - översikt](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html).

1. Välj den eller de datauppsättningar där konverterings- och inställningshändelser samlas in. Lär dig hur du skapar en sådan datauppsättning i [det här avsnittet](../data-collection/create-dataset.md). <!--This dataset needs to be associated with a schema that must have the **[!UICONTROL Proposition Interactions]** field group (previously known as mixin) associated with it.-->

   ![](../assets/ai-ranking-dataset-id.png)

   >[!CAUTION]
   >
   >Endast datauppsättningar som skapats från scheman som är kopplade till **[!UICONTROL Experience Event - Proposition Interactions]** fältgruppen (som tidigare kallades mixin) visas i listrutan.

1. Om du skapar en **[!UICONTROL Personalized optimization]** AI-modellen väljer du de segment som ska användas för att utbilda AI-modellen.

   ![](../assets/ai-ranking-segments.png)

   >[!NOTE]
   >
   >Du kan markera upp till 5 segment.

1. Spara och aktivera AI-modellen.

   ![](../assets/ai-ranking-save-activate.png)

<!--At this point, you must have:

* created the AI model,
* defined which type of event you want to capture - offer displayed (impression) and/or offer clicked (conversion),
* and in which dataset you want to collect the event data.-->

Varje gång ett erbjudande visas och/eller klickas vill du att motsvarande händelse ska spelas in automatiskt av **[!UICONTROL Experience Event - Proposition Interactions]** fältgrupp med [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/web-sdk-faq.html#what-is-adobe-experience-platform-web-sdk%3F){target="_blank"} eller Mobile SDK.

För att kunna skicka i händelsetyper (erbjudandet visas eller erbjudandet klickas) måste du ange rätt värde för varje händelsetyp i en upplevelsehändelse som skickas till Adobe Experience Platform. [Lär dig mer](../data-collection/schema-requirement.md)