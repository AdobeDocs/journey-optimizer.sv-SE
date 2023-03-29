---
title: Konfigurera urval av erbjudanden i beslut
description: Lär dig hur du hanterar urval av erbjudanden i beslut
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 8c7135d7-bf5a-4671-afdf-afec60907a56
source-git-commit: 4f3d22c9ce3a5b77969a2a04dafbc28b53f95507
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 5%

---

# Konfigurera urval av erbjudanden i beslut {#offers-selection-in-decisions}

Om flera erbjudanden är berättigade till en viss placering kan du välja den metod som ska användas för att välja det bästa erbjudandet för varje profil när du konfigurerar ett beslut. Du kan rangordna erbjudanden genom att:
* Prioritet
* Rankningsformel
* [AI-rankning](#use-ranking-strategy)

![](../assets/offer-rank-by.png)

## Prioritet {#offer-priority}

När flera erbjudanden kan komma i fråga för en viss placering i ett beslut är de som har högst **prioritet** kommer att levereras till kunderna först.

![](../assets/offer-priority.png)

Prioritetspoäng tilldelas när ett erbjudande skapas. Lär dig hur du skapar ett personaliserat erbjudande i [det här avsnittet](../offer-library/creating-personalized-offers.md).

## Rankningsformel {#assign-ranking-formula}

Förutom att ge prioritet kan du med Journey Optimizer skapa **rankningsformler**. Detta är formler som avgör vilket erbjudande som ska presenteras först för en viss placering, i stället för att beakta offertens prioritetspoäng.

Du kan till exempel öka prioriteten för alla erbjudanden där slutdatumet är mindre än 24 timmar från och med nu, eller öka erbjudandena från kategorin&quot;löpande&quot; om profilens intressepunkt är&quot;igång&quot;.

Lär dig hur du skapar en rankningsformel i [det här avsnittet](../ranking/create-ranking-formulas.md).

När du har skapat en formel kan du tilldela den till en placering i ett beslut. Följ stegen nedan för att göra detta:

1. Skapa ett beslut eller redigera ett befintligt. Se [Skapa beslut](../offer-activities/create-offer-activities.md).

1. Lägg till de placeringar som kommer att innehålla dina erbjudanden. Se [Skapa placeringar](../offer-library/creating-placements.md).

1. Lägg till en samling för varje placering. Se [Skapa samlingar](../offer-library/creating-collections.md).

1. Välj **[!UICONTROL Formula]** som rangordningsmetod och klicka sedan på **[!UICONTROL Add ranking]**.

   ![](../assets/offer-activity-ranking.png)

1. Välj önskad formel och klicka sedan på **[!UICONTROL Select]**.

   ![](../assets/ranking-selection.png)

Rankningsformeln är nu kopplad till placeringen.

Om flera erbjudanden kan presenteras på den här platsen, kommer beslutet att använda den valda formeln för att beräkna vilket erbjudande som ska levereras först.

## AI-rankning {#use-ranking-strategy}

<!--If you are an [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html){target="_blank"} user leveraging the **Offer Decisioning** application service,-->

Du kan också använda ett utbildat modellsystem som automatiskt rangordnar erbjudanden för en viss profil genom att välja en rangordningsstrategi. Lär dig hur du skapar en rankningsstrategi i [det här avsnittet](../ranking/create-ranking-strategies.md).

När en rankningsstrategi har skapats kan du tilldela den till en placering i ett beslut. Gör så här:

1. Skapa ett beslut eller redigera ett befintligt. Se [Skapa beslut](../offer-activities/create-offer-activities.md).

1. Lägg till de placeringar som kommer att innehålla dina erbjudanden. Se [Skapa placeringar](../offer-library/creating-placements.md).

1. Lägg till en samling för varje placering. Se [Skapa samlingar](../offer-library/creating-collections.md).

1. Välj om du vill rangordna erbjudanden efter **[!UICONTROL AI ranking]** i listrutan och klicka på **[!UICONTROL Add ranking]**.

   ![](../assets/ranking-selection-ai-ranking.png)

1. Välj den rankningsstrategi som du skapade. Alla detaljer om rankningsstrategin visas.

   ![](../assets/ranking-selection-ai-ranking-selected.png)

1. Klicka på **[!UICONTROL Select]**. Rankningsstrategin är nu kopplad till placeringen.

Om flera erbjudanden är giltiga, avgör det tränade modellsystemet vilket erbjudande som ska presenteras först för en viss placering.

