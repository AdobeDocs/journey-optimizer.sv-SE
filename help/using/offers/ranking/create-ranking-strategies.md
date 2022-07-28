---
product: experience platform
solution: Experience Platform
title: Skapa AI-modeller
description: Lär dig hur du skapar AI-modeller för att rangordna erbjudanden
feature: Ranking Formulas
role: User
level: Intermediate
exl-id: 81d07ec8-e808-4bc6-97b1-b9f7db2aec22
source-git-commit: 3188bc97b8103d2a01101a23d8c242a3e2924f76
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 3%

---

# Skapa AI-modeller {#ai-rankings}

[!DNL Journey Optimizer] kan du skapa **AI-modeller** att rangordna erbjudanden baserat på era affärsmål.

>[!CAUTION]
>
>Om du vill skapa, redigera eller ta bort AI-modeller måste du ha **Hantera rankningsstrategier** behörighet. [Läs mer](../../administration/high-low-permissions.md#manage-ranking-strategies)

## Skapa en AI-modell {#create-ranking-strategy}

Så här skapar du en AI-modell:

1. I **[!UICONTROL Components]** -menyn, gå till **[!UICONTROL Ranking]** tabbtangenten och sedan **[!UICONTROL AI models]**.

   ![](../assets/ai-ranking-list.png)

   Alla AI-modeller som har skapats hittills visas.

1. Klicka på knappen **[!UICONTROL Create AI model]**.

1. Ange ett unikt namn och en beskrivning för AI-modellen och välj sedan den typ av AI-modell som du vill skapa:

   * **[!UICONTROL Auto-optimization]** optimerar erbjudanden baserat på tidigare erbjudanden. [Läs mer](auto-optimization-model.md)
   * **[!UICONTROL Personalized]** optimerar och personaliserar erbjudanden baserat på segment och erbjudanden. [Läs mer](personalized-optimization-model.md)

   ![](../assets/ai-ranking-fields.png)

   >[!NOTE]
   >
   >The **[!UICONTROL Optimization metric]** innehåller information om den konverteringshändelse som används av AI-modellen för att beräkna offerternas rankning.
   >
   >[!DNL Journey Optimizer] Rangordna erbjudanden baserat på **konverteringsgrad** (Konverteringstakt = Totalt antal konverteringshändelser / Totalt antal tryckningshändelser). Konverteringsgraden beräknas med hjälp av två typer av mätvärden:
   >* **Impression-händelser** (erbjudanden som visas)
   >* **Konverteringshändelser** (erbjudanden som leder till klickningar via e-post eller webben).

   >
   >Dessa händelser hämtas automatiskt med Web SDK eller Mobile SDK som har angetts. Läs mer om detta i [Adobe Experience Platform Web SDK - översikt](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en).

1. Välj den eller de datauppsättningar där konverterings- och inställningshändelser samlas in. Lär dig hur du skapar en sådan datauppsättning i [det här avsnittet](#create-dataset). <!--This dataset needs to be associated with a schema that must have the **[!UICONTROL Proposition Interactions]** field group (previously known as mixin) associated with it.-->

   ![](../assets/ai-ranking-dataset-id.png)

   >[!CAUTION]
   >
   >Endast datauppsättningar som skapats från scheman som är kopplade till **[!UICONTROL Experience Event - Proposition Interactions]** fältgruppen (som tidigare kallades mixin) visas i listrutan.

1. Om du skapar en **[!UICONTROL Personalization]** AI-modellen väljer du de segment som ska användas för att utbilda AI-modellen.

   ![](../assets/ai-ranking-segments.png)

   >[!NOTE]
   >
   >Du kan markera upp till 5 segment.

1. Spara och aktivera AI-modellen.

   ![](../assets/ai-ranking-save-activate.png)
