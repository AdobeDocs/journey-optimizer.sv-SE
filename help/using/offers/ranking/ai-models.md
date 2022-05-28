---
product: experience platform
solution: Experience Platform
title: Kom igång med AI-modeller
description: Lär dig mer om AI-modeller som gör det möjligt att rangordna erbjudanden
feature: Ranking Formulas
role: User
level: Intermediate
exl-id: 4f7f7d1d-a12a-4ff6-b0ff-1a1c3d305a9d
source-git-commit: 12b01cb9de84399e5ede987866609acc10b64c5f
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 3%

---

# Kom igång med AI-modeller {#ai-models}

[!DNL Journey Optimizer] gör att du kan använda ett tränat modellsystem som rangordnar erbjudanden för en viss profil.

Med den här funktionen kan du skapa olika **AI-modeller** baserat på era affärsmål. Genom att använda dessa olika målbaserade strategier i ett beslut kommer det tränade modellsystemet att hjälpa dig att förstå hur de olika AI-modellerna påverkar era mål.

Du kan till exempel välja en AI-modell för e-postkanalen och en annan för push-kanalen. För varje kanal utnyttjar det tränade modellsystemet flera datapunkter för att avgöra vilket erbjudande som ska presenteras först för en viss placering, i stället för att beakta offertens prioritetspoäng eller en [rankningsformel](create-ranking-formulas.md).

## AI-modelltyper {#ai-model-types}

För tillfället [!DNL Journey Optimizer]** har en AI-modell, **Automatisk optimering**, som optimerar erbjudanden baserat på tidigare erbjudanden. Detaljerad information om den här typen av AI-modell finns i [det här avsnittet](auto-optimization-model.md).

## Skapa en AI-modell {#create-ai-model}

De viktigaste stegen för att skapa och använda AI-modeller är följande:

1. Skapa en datauppsättning där konverterings- och inställningshändelser samlas in. [Läs mer](create-dataset.md)
1. Skapa en AI-modell som utnyttjar händelser från datauppsättningen för att rangordna erbjudanden. [Läs mer](create-ranking-strategies.md)
1. Konfigurera ditt erbjudandeschema för att automatiskt samla in händelser. [Läs mer](schema-requirement.md)
1. Tilldela AI-modellen till en placering i ett beslut om att rangordna kvalificerade erbjudanden. [Läs mer](../offer-activities/configure-offer-selection.md)
