---
title: Viktig information om beslutshändelser
description: Läs mer om den viktiga information som skickas vid varje beslutshanteringshändelse.
feature: Erbjudanden
topic: Integreringar
role: User
level: Intermediate
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 82%

---

# Viktig information om beslutshanteringshändelser {#events-key-information}

Varje händelse som skickas när ett beslut fattas innehåller fyra viktiga datapunkter som du kan använda för analys- och rapporteringsändamål.

![](../../assets/events-dataset-preview.png)

* **[!UICONTROL Fallback]**: Namn och ID för det sekundära erbjudandet, om inget personaliserat erbjudande har valts,
* **[!UICONTROL Placement]**: Namn, ID och kanal för placeringen som användes för att leverera erbjudandet.
* **[!UICONTROL Selections]**: Namn och ID för erbjudandet som har valts för profilen.
* **[!UICONTROL Activity]**: namn och ID för beslutet (tidigare kallat erbjudandeaktivitet).

Dessutom kan du använda fälten **[!UICONTROL identityMap]** och **[!UICONTROL Timestamp]** för att hämta information om profilen och den tidpunkt då erbjudandet levererades.

Mer information om alla XDM-fält som skickas med varje beslut finns i [det här avsnittet](xdm-fields.md).
