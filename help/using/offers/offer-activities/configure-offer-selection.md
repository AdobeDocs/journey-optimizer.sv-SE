---
title: Konfigurera urval av erbjudanden i beslut
description: Lär dig hur du hanterar urval av erbjudanden i beslut.
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 8c7135d7-bf5a-4671-afdf-afec60907a56
source-git-commit: 43fb98a08555e6b889ad537e79dba78286dafeb9
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 4%

---

# Konfigurera urval av erbjudanden i beslut {#offers-selection-in-activities}

Om flera erbjudanden är berättigade för en viss placering kan du välja den metod som ska användas för att välja det bästa erbjudandet för varje profil när du konfigurerar ett beslut (som tidigare kallades erbjudandeaktivitet). Du kan rangordna erbjudanden genom att:
* Prioritet
* Rankningsformel
* [AI-rankning](#use-ranking-strategy)  (endast för vissa användare i förtid)

![](../../assets/offer-rank-by.png)

## Prioritet {#about-offers-priority}

När flera erbjudanden är berättigade till en viss placering i ett beslut (tidigare kallat erbjudandeaktivitet) levereras erbjudandena med den högsta **prioriteten** till kunderna först.

![](../../assets/offer-priority.png)

Prioritetspoäng tilldelas när ett erbjudande skapas. Lär dig hur du skapar ett personaliserat erbjudande i [det här avsnittet](../offer-library/creating-personalized-offers.md).

## Rankningsformel {#assign-ranking-formula}

Förutom att erbjuda prioritet kan du med Journey Optimizer skapa **rankningsformler**. Detta är formler som avgör vilket erbjudande som ska presenteras först för en viss placering, i stället för att beakta offertens prioritetspoäng.

Du kan till exempel öka prioriteten för alla erbjudanden där slutdatumet är mindre än 24 timmar från och med nu, eller öka erbjudandena från kategorin&quot;löpande&quot; om profilens intressepunkt är&quot;igång&quot;.

Lär dig hur du skapar en rankningsformel i [det här avsnittet](../offer-library/create-ranking-formulas.md).

När en rankningsformel har skapats kan du tilldela den till en placering i ett beslut (som tidigare kallades erbjudandeaktivitet). Följ stegen nedan för att göra detta:

1. Skapa ett beslut eller redigera ett befintligt. Se [Skapa beslut](../offer-activities/create-offer-activities.md).

1. Lägg till de placeringar som kommer att innehålla dina erbjudanden. Se [Skapa placeringar](../offer-library/creating-placements.md).

1. Lägg till en samling för varje placering. Se [Skapa samlingar](../offer-library/creating-collections.md).

1. Välj om du vill rangordna erbjudanden med **[!UICONTROL Ranking]** i listrutan och klicka sedan på **[!UICONTROL Add ranking]**.

   ![](../../assets/offer-activity-ranking.png)

1. Välj önskad rankningsformel och klicka sedan på **[!UICONTROL Select]**.

   ![](../../assets/ranking-selection.png)

Rankningsformeln är nu kopplad till placeringen.

Om flera erbjudanden kan presenteras i denna placering, kommer beslutet att använda rangordningsformelns formel för att beräkna vilket erbjudande som ska levereras först.

## AI-rankning {#use-ranking-strategy}

<!--If you are an [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html){target="_blank"} user leveraging the **Offer Decisioning** application service,-->You can also use an trained model system that automatically ranks offers to display for a given profile by selecting a ranking strategy. Learn how to create a ranking strategy in [this section](../offer-library/create-ranking-strategies.md).

>[!CAUTION]
>
>AI-rankningen är för närvarande tillgänglig i förtid och endast för vissa användare.

När en rankningsstrategi har skapats kan du tilldela den till en placering i ett beslut (tidigare kallat erbjudandeaktivitet). Gör så här:

1. Skapa ett beslut eller redigera ett befintligt. Se [Skapa beslut](../offer-activities/create-offer-activities.md).

1. Lägg till de placeringar som kommer att innehålla dina erbjudanden. Se [Skapa placeringar](../offer-library/creating-placements.md).

1. Lägg till en samling för varje placering. Se [Skapa samlingar](../offer-library/creating-collections.md).

1. Välj om du vill rangordna erbjudanden med **[!UICONTROL AI ranking]** i listrutan.

   ![](../../assets/ranking-selection-ai-ranking.png)

1. Klicka på **[!UICONTROL Add ranking]**.

   ![](../../assets/ranking-selection-ai-ranking-add.png)

1. Välj den rankningsstrategi som du skapade. Alla detaljer om rankningsstrategin visas.

   ![](../../assets/ranking-selection-ai-ranking-selected.png)

1. Klicka på **[!UICONTROL Select]**.

Rankningsstrategin är nu kopplad till placeringen.

Om flera erbjudanden är giltiga, avgör det tränade modellsystemet vilket erbjudande som ska presenteras först för en viss placering.

<!--Result? Describe the impact for the user, i.e. what's the effect of selecting this ranking strategy for this collection/placement.-->

<!--Click **[!UICONTROL Next]** to confirm and save your decision.-->
