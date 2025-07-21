---
solution: Journey Optimizer
product: journey optimizer
title: schemalägg en API-utlöst kampanj
description: Lär dig hur du schemalägger en API-utlöst kampanj.
feature: Campaigns, API
topic: Content Management
role: Developer
level: Experienced
keywords: kampanjer, API-utlösta, REST, optimering, meddelanden
source-git-commit: 1bdba8c5c1a9238d351b159551f6d3924935b339
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 1%

---


# Schemalägg den API-utlösta kampanjen {#api-schedule}

Använd fliken **[!UICONTROL Schedule]** för att definiera kampanjschemat.

API-utlösta kampanjer startar som standard när de utlöses och avslutas så snart meddelandet har skickats en gång. Om du inte vill köra kampanjen direkt efter att den har utlösts, kan du ange ett datum och en tidpunkt då meddelandet ska skickas med alternativet **[!UICONTROL Campaign start]**.

Med alternativet **[!UICONTROL Campaign end]** kan du ange när en kampanj ska sluta köras. Utanför de angivna datumen kommer kampanjen inte att köras.

![](assets/api-triggered-schedule.png)

>[!NOTE]
>
>När du schemalägger kampanjer i [!DNL Adobe Journey Optimizer] måste du se till att startdatumet/starttiden är i linje med den önskade första leveransen.

## Nästa steg {#next}

När kampanjens konfiguration och innehåll är klart kan du granska och aktivera det. [Läs mer](review-activate-campaign.md)
