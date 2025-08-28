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
exl-id: b183eeb8-606f-444d-9302-274f159c3847
source-git-commit: eeacfacf3068f831afb7b7ad78214941a9259c93
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---

# Schemalägg åtgärdskampanjen {#action-campaign-schedule}

Använd fliken **[!UICONTROL Schedule]** för att definiera kampanjschemat.

## Ange start- och slutdatum

Åtgärdskampanjer startar som standard när de aktiveras manuellt och avslutas så snart meddelandet har skickats en gång. Om du inte vill köra kampanjen direkt efter aktiveringen kan du ange ett datum och en tidpunkt då meddelandet ska skickas med alternativet **[!UICONTROL Campaign start]**.

Med alternativet **[!UICONTROL Campaign end]** kan du ange när en kampanj ska sluta köras. Utanför de angivna datumen kommer kampanjen inte att köras.

![](assets/create-campaign-schedule.png)

>[!NOTE]
>
>När du schemalägger kampanjer i [!DNL Adobe Journey Optimizer] måste du se till att startdatumet/starttiden är i linje med den önskade första leveransen. Om den initiala schemalagda tiden redan har passerat för återkommande kampanjer kommer kampanjerna att föras över till nästa tillgängliga tidsrymd enligt reglerna för återkommande kampanjer.

## Ange hastighetskontroll

Med [!DNL Journey Optimizer] kan du aktivera hastighetskontroll för utgående åtgärder (e-post, SMS, push-meddelanden).

Den här funktionen är särskilt användbar för att förhindra överbelastning i system längre fram i kedjan, som landningssidor eller kundtjänstplattformar. Du kan till exempel ange en hastighetsgräns på 165 meddelanden per sekund för att säkerställa stabil leverans utan överväldigande system i efterföljande led.

Om du vill ange hastighetskontroll aktiverar du alternativet **[!UICONTROL Throttle delivery]** i avsnittet **[!UICONTROL Delivery settings]** och anger önskad **[!UICONTROL Delivery rate]** per sekund.

* Lägsta tillåtna leveransfrekvens: 1 per sekund.
* Högsta leveransfrekvens som stöds: 2 000 per sekund när alternativet Begränsad leverans är aktiverat.

![](assets/throttling-rate-control.png)

>[!IMPORTANT]
>
>När du anger en leveransfrekvens är den maximala tidsram som kampanjens målgrupp kan genomföra 12 timmar. Om leveransfrekvensen är inställd på ett värde som inte tillåter att alla målgrupper får meddelandet inom 12-timmars tidsram, kommer de återstående profilerna att uteslutas från kampanjen. Du kan se antalet uteslutna profiler i kampanjrapporten.

## Ange en körningsfrekvens

För e-post-, SMS- och push-meddelandeåtgärder kan du definiera en frekvens som kampanjens meddelande ska skickas med. Det gör du genom att använda alternativen **[!UICONTROL Action triggers]** på skärmen för att skapa kampanjer för att ange om kampanjen ska köras varje dag, varje vecka eller varje månad.

![](assets/action-triggers.png)

## Ställ in IP-värmningsplaner

För e-poståtgärder kan ni skapa specifika aktiveringskampanjer för IP-warmup-plan. Kampanjschemat styrs av IP-värmeringsplanen som det är kopplat till, vilket innebär att schemat inte längre definieras i själva kampanjen. [Lär dig hur du skapar IP-värmeringskampanjer](../configuration/ip-warmup-campaign.md).

## Nästa steg {#next}

När kampanjschemat är klart kan ni granska och aktivera kampanjen. [Läs mer](review-activate-campaign.md)
