---
title: Konfigurera urval av erbjudanden i beslut
description: Lär dig hur du hanterar urval av erbjudanden i beslut.
feature: Erbjudanden
topic: Integreringar
role: User
level: Intermediate
source-git-commit: a25264cb43f77671c29f18522110fd85d0155697
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 7%

---

# Konfigurera urval av erbjudanden i beslut {#offers-selection-in-activities}

## Prioritet för erbjudanden {#about-offers-priority}

När flera erbjudanden är berättigade till en viss placering i ett beslut (tidigare kallat erbjudandeaktivitet) levereras erbjudandena med den högsta **prioriteten** till kunderna först. Prioritetspoäng för erbjudanden tilldelas när du skapar ett erbjudande (se [Skapa ett personaliserat erbjudande](../offer-library/creating-personalized-offers.md)).

![](../../assets/offer-priority.png)

I Journey Optimizer kan du dessutom skapa **rankningsformler**. Detta är formler som avgör vilket erbjudande som ska presenteras först för en viss placering, i stället för att beakta offertens prioritetspoäng.

Du kan till exempel öka prioriteten för alla erbjudanden där slutdatumet är mindre än 24 timmar från och med nu, eller öka erbjudandena från kategorin&quot;löpande&quot; om profilens intressepunkt är&quot;igång&quot;.

Mer information om hur du skapar en rankningsformel finns i [det här avsnittet](../offer-library/create-ranking-formulas.md).

## Tilldela en rankningsformel till en placering {#assign-ranking-formula}

När en rankningsformel har skapats kan du tilldela den till en placering i ett beslut. Följ stegen nedan för att göra detta:

1. Skapa ett beslut eller redigera ett befintligt, och skapa sedan de ersättningar som innehåller dina erbjudanden (se [Skapa beslut](../offer-activities/create-offer-activities.md)).

1. För varje placering väljer du **[!UICONTROL Ranking]** i listrutan.

1. Klicka på **[!UICONTROL Add ranking]**.

   ![](../../assets/offer-activity-ranking.png)

1. Välj önskad rankningsformel och klicka sedan på **[!UICONTROL Select]**.

   ![](../../assets/ranking-selection.png)

Rankningsformeln är nu kopplad till placeringen.

Om flera erbjudanden kan presenteras i denna placering, kommer beslutet att använda rangordningsformelns formel för att beräkna vilket erbjudande som ska levereras först.
