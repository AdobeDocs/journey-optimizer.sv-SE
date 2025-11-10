---
title: Konfigurera urval av erbjudanden i beslut
description: Lär dig hur du hanterar urval av erbjudanden i beslut
badge: label="Äldre" type="Informative"
feature: Decision Management
topic: Integrations
role: User
level: Intermediate
exl-id: 8c7135d7-bf5a-4671-afdf-afec60907a56
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 3%

---

# Konfigurera urval av erbjudanden i beslut {#offers-selection-in-decisions}

Om flera erbjudanden är berättigade till en viss placering kan du välja den metod som ska användas för att välja det bästa erbjudandet för varje profil när du konfigurerar ett beslut. Du kan rangordna erbjudanden genom att:

* Prioritet
* Rankningsformel
* [AI-rankning](#use-ranking-strategy)

![](../assets/offer-rank-by.png)

## Prioritet {#offer-priority}

När flera erbjudanden är berättigade till en viss placering i ett beslut levereras erbjudandena med den högsta **prioriteten** till kunderna först.

![](../assets/offer-priority.png)

Prioritetspoäng för erbjudanden tilldelas när ett erbjudande skapas. Lär dig hur du skapar ett personligt erbjudande i [det här avsnittet](../offer-library/creating-personalized-offers.md).

## Rankningsformel {#assign-ranking-formula}

Förutom att erbjuda prioritet kan du med Journey Optimizer skapa **rankningsformler**. Detta är formler som avgör vilket erbjudande som ska presenteras först för en viss placering, i stället för att beakta offertens prioritetspoäng.

Du kan till exempel öka prioriteten för alla erbjudanden där slutdatumet är mindre än 24 timmar från och med nu, eller öka erbjudandena från kategorin&quot;löpande&quot; om profilens intressepunkt är&quot;igång&quot;.

Lär dig hur du skapar en rankningsformel i [det här avsnittet](../ranking/create-ranking-formulas.md).

När du har skapat en formel kan du tilldela den till en placering i ett beslut. Gör så här:

1. Skapa ett beslut eller redigera ett befintligt. Se [Skapa beslut](../offer-activities/create-offer-activities.md).

1. Lägg till de placeringar som innehåller dina erbjudanden. Se [Skapa placeringar](../offer-library/creating-placements.md).

1. Lägg till en samling för varje placering. Se [Skapa samlingar](../offer-library/creating-collections.md).

1. Välj **[!UICONTROL Formula]** som rankningsmetod och klicka sedan på **[!UICONTROL Add ranking]**.

   ![](../assets/offer-activity-ranking.png)

1. Välj önskad formel och klicka sedan på **[!UICONTROL Select]**.

   ![](../assets/ranking-selection.png)

Rankningsformeln är nu kopplad till placeringen.

Om flera erbjudanden kan presenteras på den här platsen, kommer beslutet att använda den valda formeln för att beräkna vilket erbjudande som ska levereras först.

## AI-rankning {#use-ranking-strategy}

<!--If you are an [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html?lang=sv-SE){target="_blank"} user leveraging the **Offer Decisioning** application service,-->

Du kan också använda ett utbildat modellsystem som automatiskt rangordnar erbjudanden för en viss profil genom att välja en AI-modell. Lär dig hur du skapar en AI-modell i [det här avsnittet](../ranking/create-ranking-strategies.md).

När en AI-modell har skapats kan du tilldela den till en placering i ett beslut. Gör så här:

1. Skapa ett beslut eller redigera ett befintligt. Se [Skapa beslut](../offer-activities/create-offer-activities.md).

1. Lägg till de placeringar som innehåller dina erbjudanden. Se [Skapa placeringar](../offer-library/creating-placements.md).

1. Lägg till en samling för varje placering. Se [Skapa samlingar](../offer-library/creating-collections.md).

1. Välj att rangordna erbjudanden efter **[!UICONTROL AI ranking]** i listrutan och klicka på **[!UICONTROL Add ranking]**.

   ![](../assets/ranking-selection-ai-ranking.png)

1. Välj den AI-modell som du skapade. All information om modellen visas.

   ![](../assets/ranking-selection-ai-ranking-selected.png)

1. Klicka på **[!UICONTROL Select]**. AI-modellen är nu kopplad till placeringen.

Om flera erbjudanden är giltiga, avgör det tränade modellsystemet vilket erbjudande som ska presenteras först för en viss placering.

