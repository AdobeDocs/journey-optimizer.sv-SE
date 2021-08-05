---
title: Tillåtelselista
description: Lär dig hur du använder tillåtelselista.
feature: levererbarhet
topic: Innehållshantering
role: User
level: Intermediate
source-git-commit: 288c27d4fc64a6d0a6f07b634ed044a6e858d0c1
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 1%

---

# Tillåtelselista {#allow-list}

Det är nu möjligt att definiera en specifik sändningssäker lista på [sandbox](administration/sandboxes.md)-nivå för att ha en säker miljö för testningsändamål. I icke-produktionssituationer, där misstag kan inträffa, ser tillåtelselista till att du inte löper någon risk att skicka ut oönskade meddelanden till dina kunder.

>[!CAUTION]
>
>Den här funktionen är inte tillgänglig i produktionssandlådor.

Med tillåtelselista kan du ange enskilda e-postadresser eller domäner som ska vara de enda mottagarna eller domänerna som ska ha behörighet att ta emot e-postmeddelanden som du skickar från en viss sandlåda. Detta kan förhindra att du av misstag skickar e-post till verkliga kundadresser när du befinner dig i en testmiljö.

>[!NOTE]
>
>Den här funktionen gäller endast för e-postkanalen.

## Aktivera tillåtelselista {#enable-allow-list}

Om du vill aktivera tillåtelselista i en icke-produktionssandlåda måste du göra ett Adobe API-anrop.

* Med detta API kan du när som helst inaktivera funktionen.

* Du kan uppdatera tillåtelselista innan eller efter att du har aktiverat funktionen.

* Logiken i tillåtelselista gäller när funktionen är aktiverad och om tillåtelselista inte är tom. Läs mer i [det här avsnittet](#logic).

>[!NOTE]
>
>När det här alternativet är aktiverat respekteras funktionen tillåtelselista vid körning av resor, men också när du testar meddelanden med [korrektur](preview.md#send-proofs) och testar resor med [testläge](building-journeys/testing-the-journey.md).

## Lägg till enheter i tillåtelselista {#add-entities}

>[!CAUTION]
>
>Den här funktionen är **inte** tillgänglig i produktionssandlådor. Det gäller endast för e-postkanaler.

Om du vill lägga till nya e-postadresser eller domäner i tillåtelselista för en viss sandlåda måste du anropa API:t för inaktivering med `ALLOWED`-värdet för attributet `listType`. Exempel:

![](assets/allow-list-api.png)

Du kan utföra åtgärderna **Lägg till**, **Ta bort** och **Hämta**.

>[!NOTE]
>
>Tillåtelselista kan innehålla upp till 1 000 poster.

Läs mer om hur du anropar Adobe API i [dokumentationen för Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-guide.html?lang=en).

## Tillåtelselista logik {#logic}

<!-- When the allowed list is \[enabled\]\(\add link here\) at the sandbox level using the API call above, the following applies.-->

1. När tillåtelselista är **tom** används inte logiken för tillåtelselista. Det innebär att du kan skicka e-postmeddelanden till alla profiler, förutsatt att de inte finns med i [listan](suppression-list.md).

1. När tillåtelselista är **inte tom** används tillåtelselista-logiken:

   * Om en entitet är **inte på tillåtelselista**, och inte på listan över inaktiveringar, kommer motsvarande mottagare inte att få e-postmeddelandet. Orsaken är **[!UICONTROL Not allowed]**.

   * Om en entitet är **på tillåtelselista**, och inte på listan över inaktiveringar, kan e-postmeddelandet skickas till motsvarande mottagare. Om entiteten också finns med i [listan](suppression-list.md) kommer den motsvarande mottagaren inte att få e-postmeddelandet. Orsaken är **[!UICONTROL Suppressed]**.




