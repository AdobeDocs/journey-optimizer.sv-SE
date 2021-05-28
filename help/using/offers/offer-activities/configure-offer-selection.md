---
title: Konfigurera urval av erbjudanden i beslut
description: Lär dig hur du hanterar urval av erbjudanden i beslut.
source-git-commit: db7fd318b14d01a0369c934a3e01c6e368d7658d
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 2%

---

# Konfigurera val av erbjudanden i beslut {#offers-selection-in-activities}

## Om prioritet {#about-offers-priority} för erbjudanden

När flera erbjudanden är berättigade till en viss placering i ett beslut (tidigare kallat erbjudandeaktivitet) levereras erbjudandena med den högsta **prioriteten** till kunderna först. Prioritetspoäng för erbjudanden tilldelas när du skapar ett erbjudande (se [Skapa ett personaliserat erbjudande](../offer-library/creating-personalized-offers.md)).

![](../../assets/offer-priority.png)

I Journey Optimizer kan du dessutom skapa **rankningsformler**. Detta är formler som avgör vilket erbjudande som ska presenteras först för en viss placering, i stället för att beakta offertens prioritetspoäng. Du kan till exempel öka prioriteten för alla erbjudanden där slutdatumet är mindre än 24 timmar från och med nu, eller öka erbjudandena från kategorin&quot;löpande&quot; om profilens intressepunkt är&quot;igång&quot;.

Mer information om hur du skapar en rankningsformel finns i [det här avsnittet](../offer-library/create-ranking-formulas.md).

## Tilldela en rankningsformel till en placering {#assign-ranking-formula}

När en rankningsformel har skapats kan du tilldela den till en placering i ett beslut. Följ stegen nedan för att göra detta:

* Skapa ett beslut eller redigera ett befintligt, och skapa sedan de ersättningar som innehåller dina erbjudanden (se [Skapa beslut](../offer-activities/create-offer-activities.md)).

* För varje placering väljer du **[!UICONTROL Ranking]** i listrutan och klickar sedan på **[!UICONTROL Add ranking]**.

   ![](../../assets/offer-activity-ranking.png)

* Välj önskad rankningsformel och klicka sedan på **[!UICONTROL Select]**.

   ![](../../assets/ranking-selection.png)

Rankningsformeln är nu kopplad till placeringen. Om flera erbjudanden kan presenteras i denna placering, kommer beslutet att använda rangordningsformelns formel för att beräkna vilket erbjudande som ska levereras först.
