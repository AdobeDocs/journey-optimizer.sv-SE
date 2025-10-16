---
solution: Journey Optimizer
product: journey optimizer
title: Schemalägg en API-utlöst kampanj
description: Lär dig hur du schemalägger en API-utlöst kampanj.
feature: Campaigns, API
topic: Content Management
role: Developer
level: Experienced
keywords: kampanjer, API-utlösta, REST, optimering, meddelanden
exl-id: e04b0d38-6b3d-4086-a0f0-c1b8f6d9634f
source-git-commit: 93698c93f3750b4d7feff18509f8144a7c79f156
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# Schemalägg den API-utlösta kampanjen {#api-schedule}

Använd fliken **[!UICONTROL Schedule]** för att definiera kampanjschemat.

## Ange start- och slutdatum

API-utlösta kampanjer startar som standard när de utlöses och avslutas så snart meddelandet har skickats en gång. Om du inte vill köra kampanjen direkt efter att den har utlösts, kan du ange ett datum och en tidpunkt då meddelandet ska skickas med alternativet **[!UICONTROL Campaign start]**.

Med alternativet **[!UICONTROL Campaign end]** kan du ange när en kampanj ska sluta köras. Utanför de angivna datumen kommer kampanjen inte att köras.

![](assets/api-triggered-schedule.png)

>[!NOTE]
>
>När du schemalägger kampanjer i [!DNL Adobe Journey Optimizer] måste du se till att startdatumet/starttiden är i linje med den önskade första leveransen.

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

## Nästa steg {#next}

När kampanjens konfiguration och innehåll är klart kan du granska och aktivera det. [Läs mer](../campaigns/review-activate-api-triggered-campaign.md)
