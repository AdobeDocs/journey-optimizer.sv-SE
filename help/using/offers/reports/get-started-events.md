---
title: Arbeta med beslutsledningshändelser
description: Lär dig skapa beslutsrapporter i Adobe Experience Platform.
feature: Offers
topic: Integrations
role: User
level: Beginner
exl-id: 51830c63-fa88-47e7-8605-192297fcf6b8
source-git-commit: a6a892ec20dfeb6879bef2f4c2eb4a0f8f54885f
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 48%

---

# Kom igång med beslutsledningshändelser {#monitor-offer-events}

Varje gång en beslutshantering fattar ett beslut om en viss profil, skickas information om dessa händelser automatiskt till Adobe Experience Platform.

På så sätt kan ni få insikter om era beslut, till exempel för att veta vilket erbjudande som presenterades för en viss profil. Du kan exportera dessa data för att analysera dem i ditt eget rapporteringssystem eller använda Adobe Experience Platform [Frågetjänst](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=sv) i kombination med andra verktyg för bättre analys och rapportering.

## Nyckelinformation finns i datauppsättningar {#key-information}

Varje händelse som skickas när ett beslut fattas innehåller fyra viktiga datapunkter som du kan använda för analys- och rapporteringsändamål:

![](../assets/events-dataset-preview.png)

* **[!UICONTROL Fallback]**: Namn och ID för det sekundära erbjudandet, om inget personaliserat erbjudande har valts,
* **[!UICONTROL Placement]**: Namn, ID och kanal för placeringen som användes för att leverera erbjudandet.
* **[!UICONTROL Selections]**: Namn och ID för erbjudandet som har valts för profilen.
* **[!UICONTROL Activity]**: Namn och ID för beslutet.

Dessutom kan du använda fälten **[!UICONTROL identityMap]** och **[!UICONTROL Timestamp]** för att hämta information om profilen och den tidpunkt då erbjudandet levererades.

Mer information om alla XDM-fält som skickas med varje beslut finns i [det här avsnittet](xdm-fields.md).

## Åtkomst till datauppsättningar {#access-datasets}

Datauppsättningar som innehåller beslutshanteringshändelser är tillgängliga från Adobe Experience Platform **[!UICONTROL Datasets]** -menyn. En datauppsättning skapas automatiskt vid etablering för var och en av dina instanser.

![](../assets/events-datasets-list.png)

Dessa datauppsättningar är baserade på **[!UICONTROL ODE DecisionEvents]** schema, som innehåller alla XDM-fält som krävs för att skicka information från Beslutshantering till Adobe Experience Platform.

>[!NOTE]
>
>Observera att datauppsättningarna ODE DecisionEvents är **icke-profildatauppsättningar**, vilket innebär att de inte kan importeras till Experience Platform för användning av realtidskundprofilen.
