---
solution: Journey Optimizer
product: journey optimizer
title: Schemalägg åtgärdskampanjen
description: Lär dig hur du schemalägger åtgärdskampanjen.
feature: Campaigns
topic: Content Management
role: User
level: Beginner
mini-toc-levels: 1
keywords: skapa, optimera, kampanj, yta, meddelanden
source-git-commit: 1bdba8c5c1a9238d351b159551f6d3924935b339
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 0%

---


# Schemalägg åtgärdskampanjen {#action-campaign-schedule}

Använd fliken **[!UICONTROL Schedule]** för att definiera kampanjschemat.

Åtgärdskampanjer startar som standard när de aktiveras manuellt och avslutas så snart meddelandet har skickats en gång. Om du inte vill köra kampanjen direkt efter aktiveringen kan du ange ett datum och en tidpunkt då meddelandet ska skickas med alternativet **[!UICONTROL Campaign start]**.

Med alternativet **[!UICONTROL Campaign end]** kan du ange när en kampanj ska sluta köras. Utanför de angivna datumen kommer kampanjen inte att köras.

![](assets/create-campaign-schedule.png)

>[!NOTE]
>
>När du schemalägger kampanjer i [!DNL Adobe Journey Optimizer] måste du se till att startdatumet/starttiden är i linje med den önskade första leveransen. Om den initiala schemalagda tiden redan har passerat för återkommande kampanjer kommer kampanjerna att föras över till nästa tillgängliga tidsrymd enligt reglerna för återkommande kampanjer.

Ytterligare schemaläggningsalternativ är tillgängliga baserat på kampanjkanalen:

* **Frekvens** (E-post, SMS, push-åtgärd)

  Du kan definiera hur ofta kampanjens meddelande ska skickas. Det gör du genom att använda alternativen **[!UICONTROL Action triggers]** på skärmen för att skapa kampanjer för att ange om kampanjen ska köras varje dag, varje vecka eller varje månad.

* **Aktivering av IP-värmeringsplan** (e-post)

  För e-postkampanjer kan ni skapa specifika aktiveringskampanjer för IP-warmup-plan. Kampanjschemat styrs av IP-värmeringsplanen som det är kopplat till, vilket innebär att schemat inte längre definieras i själva kampanjen. [Lär dig hur du skapar IP-värmeringskampanjer](../configuration/ip-warmup-campaign.md).

## Nästa steg {#next}

När kampanjschemat är klart kan ni granska och aktivera kampanjen. [Läs mer](review-activate-campaign.md)
