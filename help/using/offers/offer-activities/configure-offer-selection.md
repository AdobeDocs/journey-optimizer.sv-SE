---
title: Konfigurera urval av erbjudanden i beslut
description: Lär dig hur du hanterar urval av erbjudanden i beslut.
feature: Erbjudanden
topic: Integreringar
role: User
level: Intermediate
source-git-commit: 807157d4d6fc1dba018bbe796c8bd213504589dc
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 5%

---

# Konfigurera urval av erbjudanden i beslut {#offers-selection-in-activities}

Om flera erbjudanden är berättigade för en viss placering kan du välja den metod som ska användas för att välja det bästa erbjudandet för varje profil när du konfigurerar ett beslut (som tidigare kallades erbjudandeaktivitet). Du kan rangordna erbjudanden genom att:
* Prioritet
* Rankningsformel

## Prioritet {#about-offers-priority}

När flera erbjudanden är berättigade till en viss placering i ett beslut (tidigare kallat erbjudandeaktivitet) levereras erbjudandena med den högsta **prioriteten** till kunderna först.

![](../../assets/offer-priority.png)

Prioritetspoäng tilldelas när ett erbjudande skapas. Lär dig hur du skapar ett personaliserat erbjudande i [det här avsnittet](../offer-library/creating-personalized-offers.md)).

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
