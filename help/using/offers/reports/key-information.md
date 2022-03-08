---
title: Viktig information om beslutshändelser
description: Läs mer om den viktiga information som skickas vid varje beslutshanteringshändelse.
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 07be59e8-e994-4854-8089-25614d005dbe
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 78%

---

# Viktig information om beslutshändelser {#events-key-information}

Varje händelse som skickas när ett beslut fattas innehåller fyra viktiga datapunkter som du kan använda för analys- och rapporteringsändamål.

![](../assets/events-dataset-preview.png)

* **[!UICONTROL Fallback]**: Namn och ID för det sekundära erbjudandet, om inget personaliserat erbjudande har valts,
* **[!UICONTROL Placement]**: Namn, ID och kanal för placeringen som användes för att leverera erbjudandet.
* **[!UICONTROL Selections]**: Namn och ID för erbjudandet som har valts för profilen.
* **[!UICONTROL Activity]**: Namn och ID för beslutet.

Dessutom kan du använda fälten **[!UICONTROL identityMap]** och **[!UICONTROL Timestamp]** för att hämta information om profilen och den tidpunkt då erbjudandet levererades.

Mer information om alla XDM-fält som skickas med varje beslut finns i [det här avsnittet](xdm-fields.md).
