---
product: experience platform
solution: Experience Platform
title: Kom igång med AI-modeller
description: Lär dig mer om AI-modeller som gör det möjligt att rangordna erbjudanden
feature: Ranking, Decision Management
role: User
level: Intermediate
exl-id: 07679823-2288-4528-b09a-12fd76a69482
source-git-commit: 18a1020971dc6a1101e4e35c1523d004f3fd4188
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 3%

---

# Kom igång med AI-modeller {#ai-models}

[!DNL Journey Optimizer] låter dig använda ett tränat modellsystem som rangordnar erbjudanden för en viss profil.

Med den här funktionen kan du skapa olika **AI-modeller** utifrån dina affärsmål. Genom att använda dessa olika målbaserade strategier i ett beslut kommer det tränade modellsystemet att hjälpa dig att förstå hur de olika AI-modellerna påverkar era mål.

<!--For example, you can select an AI model for the email channel and another one for the push channel. For each channel, the trained model system will leverage multiple data points to determine which offer should be presented first for a given decision policy?, rather than taking into account the offers' priority scores or a [ranking formula](create-ranking-formulas.md).

>[!IMPORTANT]
>
>For now, ranking models are not supported in Journey Optimizer authored channels.-->

## AI-modelltyper {#ai-model-types}

>[!CONTEXTUALHELP]
>id="ajo_exd_ai_model_type"
>title="Välj modelltyp"
>abstract="Välj den typ av AI-modell som du vill skapa: **Automatisk optimering** optimerar erbjudanden baserat på tidigare erbjudanden, medan **Anpassad optimering** optimerar och personaliserar erbjudanden baserat på målgrupper och erbjudandeprestanda."
>additional-url="https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/decisioning/offer-decisioning/rankings/ai-models/create-ranking-strategies#create-ranking-strategy" text="Skapa en AI-modell"

Det finns två typer av AI-modeller i [!DNL Journey Optimizer]:

* **Automatiska optimeringsmodeller** syftar till att leverera erbjudanden som maximerar den avkastning (KPI) som anges av affärsklienter. Dessa nyckeltal kan vara i form av konverteringsgrader, intäkter osv. I nuläget fokuserar automatisk optimering på att optimera erbjudandeklick med erbjudandekonvertering som mål. Automatisk optimering är icke-personaliserat och optimerar baserat på erbjudandets&quot;globala&quot; prestanda. [Läs mer](auto-optimization-model.md)

* Med **personaliserade optimeringsmodeller** kan du definiera affärsmål och använda kunddata för att utbilda affärsorienterade modeller för att leverera personaliserade erbjudanden och maximera nyckeltal. [Läs mer](personalized-optimization-model.md)

## Bygg en AI-modell {#create-ai-model}

De viktigaste stegen för att skapa och använda AI-modeller är följande:

1. Skapa en datauppsättning där konverterings- och inställningshändelser samlas in. [Läs mer](../data-collection/create-dataset.md)

1. Skapa en AI-modell som utnyttjar händelser från datauppsättningen för att rangordna erbjudanden. [Läs mer](create-ai-models.md)

1. Konfigurera ditt erbjudandeschema för att automatiskt samla in händelser. [Läs mer](../data-collection/schema-requirement.md)

   >[!IMPORTANT]
   >
   >Rankningsmodeller kräver att feedback-händelser skickas in som upplevelsehändelser för att samlas in. [Läs mer om att bestämma datainsamling](../data-collection/data-collection.md)

1. Tilldela AI-modellen till en urvalsstrategi för att rangordna kvalificerade erbjudanden. [Läs mer](../selection-strategies.md#select-ranking-method)
