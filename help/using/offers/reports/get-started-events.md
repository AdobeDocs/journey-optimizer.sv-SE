---
title: Kom igång med beslutsledningshändelser
description: Lär dig hur du skapar beslutsrapporter i Adobe Experience Platform.
feature: Offers
topic: Integrations
role: User
level: Beginner
exl-id: 51830c63-fa88-47e7-8605-192297fcf6b8
source-git-commit: 51254efaab08a572def118d475dc18f74c9d29b7
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 47%

---

# Kom igång med beslutsledningshändelser {#monitor-offer-events}

Varje gång beslutshanteringen fattar ett beslut om en viss profil skickas information om dessa händelser automatiskt till Adobe Experience Platform.

På så sätt kan du exportera dessa data för att analysera dem i ditt eget rapporteringssystem. Du kan också använda [frågetjänsten](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=sv) i Adobe Experience Platform i kombination med andra verktyg för förbättrade analys- och rapporteringsändamål.

Datauppsättningar som innehåller beslutshanteringshändelser är tillgängliga från Adobe Experience Platform **[!UICONTROL Datasets]** -menyn. En datauppsättning skapas automatiskt vid etablering för var och en av dina instanser.

![](../../assets/events-datasets-list.png)

Dessa datauppsättningar är baserade på **[!UICONTROL ODE DecisionEvents]** schema, som innehåller alla XDM-fält som krävs för att skicka information från Beslutshantering till Adobe Experience Platform.

>[!NOTE]
>
>Observera att datauppsättningarna ODE DecisionEvents är **icke-profildatauppsättningar**, vilket innebär att de inte kan importeras till Experience Platform för användning av realtidskundprofilen.

**Relaterade ämnen:**

* [Viktig information om beslutshändelser](../reports/key-information.md)
* [Åtkomst till XDM-fält för händelser](../reports/xdm-fields.md)
