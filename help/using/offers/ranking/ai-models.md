---
product: experience platform
solution: Experience Platform
title: Kom igång med AI-modeller
description: Lär dig mer om AI-modeller som gör det möjligt att rangordna erbjudanden
feature: Ranking, Decision Management
role: User
level: Intermediate
exl-id: 4f7f7d1d-a12a-4ff6-b0ff-1a1c3d305a9d
source-git-commit: 12f6c41252809bcc85bc076902f9a831a6c6e7d9
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 3%

---

# Kom igång med AI-modeller {#ai-models}

[!DNL Journey Optimizer] gör att du kan använda ett tränat modellsystem som rangordnar erbjudanden för en viss profil.

Med den här funktionen kan du skapa olika **AI-modeller** baserat på era affärsmål. Genom att använda dessa olika målbaserade strategier i ett beslut kommer det tränade modellsystemet att hjälpa dig att förstå hur de olika AI-modellerna påverkar era mål.

Du kan till exempel välja en AI-modell för e-postkanalen och en annan för push-kanalen. För varje kanal utnyttjar det tränade modellsystemet flera datapunkter för att avgöra vilket erbjudande som ska presenteras först för en viss placering, i stället för att beakta offertens prioritetspoäng eller en [rankningsformel](create-ranking-formulas.md).

>[!IMPORTANT]
>
>För närvarande stöds inte rankningsmodeller i kanaler som skapats av Journey Optimizer.

## AI-modelltyper {#ai-model-types}

>[!CONTEXTUALHELP]
>id="ajo_decisioning_ai_model_type"
>title="Välj modelltyp"
>abstract="Välj den typ av AI-modell som du vill skapa: **Automatisk optimering** optimerar erbjudanden baserat på tidigare erbjudanden, medan **Anpassad optimering** optimerar och personaliserar erbjudanden baserat på målgrupper och erbjuder resultat."
>additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/offer-decisioning/rankings/ai-models/create-ranking-strategies#create-ranking-strategy" text="Skapa en AI-modell"

Det finns två typer av AI-modeller i [!DNL Journey Optimizer]:

* **Automatiskt optimerade modeller** sträva efter att leverera erbjudanden som maximerar den avkastning (KPI) som affärsklienterna sätter. Dessa nyckeltal kan vara i form av konverteringsgrader, intäkter osv. I nuläget fokuserar automatisk optimering på att optimera erbjudandeklick med erbjudandekonvertering som mål. Automatisk optimering är icke-personaliserat och optimerar baserat på erbjudandets&quot;globala&quot; prestanda. [Läs mer](auto-optimization-model.md)

* **Personaliserade optimeringsmodeller** kan ni definiera affärsmål och använda kunddata för att utbilda affärsinriktade modeller för att leverera personaliserade erbjudanden och maximera nyckeltal. [Läs mer](personalized-optimization-model.md)

## Skapa en AI-modell {#create-ai-model}

De viktigaste stegen för att skapa och använda AI-modeller är följande:

1. Skapa en datauppsättning där konverterings- och inställningshändelser samlas in. [Läs mer](../data-collection/create-dataset.md)

1. Skapa en AI-modell som utnyttjar händelser från datauppsättningen för att rangordna erbjudanden. [Läs mer](create-ranking-strategies.md)

1. Konfigurera ditt erbjudandeschema för att automatiskt samla in händelser. [Läs mer](../data-collection/schema-requirement.md)

   >[!IMPORTANT]
   >
   >Rankningsmodeller kräver att feedback-händelser skickas in som upplevelsehändelser för att samlas in. [Läs mer om datainsamling för beslutshantering](../data-collection/data-collection.md)

1. Tilldela AI-modellen till en placering i ett beslut om att rangordna kvalificerade erbjudanden. [Läs mer](../offer-activities/configure-offer-selection.md)
