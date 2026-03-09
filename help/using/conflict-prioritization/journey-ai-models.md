---
title: AI-modeller för medling i resebranschen
description: Lär dig hur du skapar och använder AI-modeller för att rangordna resor för medling, så att den bästa resan väljs per profil baserat på AI-styrda poäng.
feature: Journeys, Decisioning
role: User
level: Intermediate
version: Journey Orchestration
badge: label="Begränsad tillgänglighet" type="Informative"
hide: true
hidefromtoc: true
exl-id: 3e7c3069-b022-4709-936d-acaad56b5882
source-git-commit: afc09bbcb76d53404574bb53c0a896109cd7f1da
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 0%

---

# Använd AI-modeller för att rangordna resor {#journey-ai-models}

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande begränsad. Kontakta din Adobe-representant för att få åtkomst.

[!DNL Adobe Journey Optimizer] hjälper dig att kontrollera vilka resor en profil kan registrera när de kvalificerar sig för mer än vad systemet tillåter. Om du vill göra det kan du använda [regeluppsättningar](rule-sets.md) för att definiera ändpunkter för resepost eller samtidighet. När en profil är berättigad till fler resor än vad som är tillåtet enligt begränsningen, avgör prioriteringen för varje resa vilka resor som väljs.

I stället för att använda prioritet kan du använda **AI-modeller** i dina rankningsformler för att dynamiskt rangordna resor baserat på tränade modellpoäng.

## Skapa en AI-modell {#create-ai-model}

<!--Do you need specific permissions to create AI models?
>[!CAUTION]
>
>To create, edit, or delete AI models, you must have the **Manage Ranking Strategies** permission. [Learn more](../administration/high-low-permissions.md#manage-ranking-strategies)-->

Följ stegen nedan för att skapa en AI-modell för rankning av resor.

1. Skapa en datauppsättning där konverteringshändelser samlas in. [Lär dig hur](../experience-decisioning/data-collection/create-dataset.md)

1. Gå till avsnittet **[!UICONTROL Orchestration ranking]** och välj sedan fliken **[!UICONTROL AI models]**. Listan med tidigare skapade AI-modeller visas.

1. Klicka på **[!UICONTROL Create AI model]**.

1. Ange ett unikt namn och, om det behövs, en beskrivning av AI-modellen.

   ![Informationsfönster för AI-modell med namn- och beskrivningsfält](assets/journey-model-details.png){width="80%"}

   >[!NOTE]
   >
   >Rankningsobjektet är den enhet som rankningsformeln gäller för. Som standard är rankningsobjektet inställt på **[!UICONTROL Journey]**.

<!--
1. Select the type of AI model you want to create:

    * **[!UICONTROL Auto-optimization]** optimizes based on past performance. [Learn more](../experience-decisioning/ranking/auto-optimization-model.md)
    * **[!UICONTROL Personalized optimization]** optimizes and personalizes based on audiences and performance. [Learn more](../experience-decisioning/ranking/personalized-optimization-model.md)-->

1. I **[!UICONTROL Optimization metric]** visas alla mätvärden från din standarddatavy [!DNL Customer Journey Analytics] [&#128279;](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views){target="_blank"} i listan. Välj det mätvärde som du vill optimera modellen på.

   ![Informationsfönster för AI-modell med namn- och beskrivningsfält](assets/journey-model-metrics.png){width="80%"}

   [!DNL Journey Optimizer] rangordnas baserat på **konverteringsgrad** (konverteringsgrad = totalt antal konverteringshändelser/totalt antal inställningshändelser). Konverteringsgraden beräknas med hjälp av:

   * **Impression-händelser** (objekt som visas)
   * **Konverteringshändelser** (objekt som resulterar i klick eller konverteringar)

   Dessa händelser spelas in automatiskt med Web SDK eller Mobile SDK. Läs mer i översikten för [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html).

1. Välj den eller de datauppsättningar där konverterings- och inställningshändelser samlas in. Lär dig hur du skapar sådana datauppsättningar i [det här avsnittet](../experience-decisioning/data-collection/create-dataset.md).

   ![Val av datauppsättning för konverterings- och inställningshändelser](../experience-decisioning/assets/ai-model-datasets.png){width="85%"}

   >[!CAUTION]
   >
   >Endast datauppsättningar som skapats från scheman som är kopplade till fältgruppen **[!UICONTROL Experience Event - Proposition Interactions]** (som tidigare kallades mixin) visas i listrutan.

1. &#x200B;<!--If you are creating a **[!UICONTROL Personalized optimization]** AI model, -->Välj det eller de segment som ska användas för att utbilda AI-modellen.

   >[!NOTE]
   >
   >Du kan välja upp till 50 målgrupper.

1. Spara och aktivera AI-modellen.

AI-modellen kan nu väljas när du skapar en rankningsformel.

## Välj en AI-modell för en rankningsformel {#select-ai-model-for-ranking-formula}

Nu kan du ange AI-modellen som en referens för att skapa en rankningsformel. Följ stegen nedan.

1. Skapa en rankningsformel. [Lär dig hur](journey-ranking-formulas.md#create-journey-ranking-formula)

1. Använd knappen **[!UICONTROL Select AI model]** för att välja den AI-modell som du vill använda.

   ![Rankningsformelinformationsruta med val av AI-modell](assets/journey-formula-ai-model.png){width="80%"}

1. Definiera ett villkor i minst ett av **[!UICONTROL Criterion]**-avsnitten och välj **[!UICONTROL AI model score]** som rangordningsmetod. Om resan till exempel har taggen&quot;Promo&quot; är rankningspoängen AI-modellpoängen.

   ![Rankningsformel: Promo-taggen använder AI-modellpoäng](assets/journey-formula-ex-2.png){width="60%"}

1. Klicka på **[!UICONTROL Create]** för att slutföra din rankningsformel.

## Tilldela AI-modellen till en regeluppsättning {#assign-ai-model-to-ruleset}

Om du vill använda en AI-modell för att rangordna dina resor måste du tilldela formeln som refererar till den här AI-modellen till en regeluppsättning.

1. På menyn **[!UICONTROL Business rules]** skapar du en regeluppsättning som du vill använda för skiljeväggar för resan. [Lär dig hur](rule-sets.md#Create)

1. Se till att du väljer domänen **[!UICONTROL Journey]**.

1. I regeluppsättningsegenskaperna anger du **[!UICONTROL Ranking method]** till **[!UICONTROL Formula]** (i stället för **[!UICONTROL Priority]**).

1. Välj formeln som använder den AI-modell som du skapade i listrutan.

1. Skapa de regler för capping för resan som du vill lägga till i regeluppsättningen. [Lär dig hur](journey-capping.md#create-rule)

1. Spara regeluppsättningen.

Nu tilldelas formeln som använder AI-modellen till regeluppsättningen. Du kan sedan tillämpa den regeln på dina resor.

## Använd regeluppsättningen på en resa {#assign-rule-set-to-journey}

Följ stegen nedan för att tilldela regeluppsättningen till en resa.

1. Skapa eller öppna den resa som du vill tilldela regeluppsättningen till. [Lär dig skapa en resa](../building-journeys/journey-gs.md)

1. Välj regeluppsättningen i listrutan i reseegenskaperna. [Lär dig hur](journey-capping.md#apply-capping).

   >[!NOTE]
   >
   >Endast en regeluppsättning i taget kan användas på en resa.

1. Spara resan.

Alla resor som använder den här regeluppsättningen kommer att rangordnas med den valda formeln med hjälp av AI-modellen när taket tillämpas.
