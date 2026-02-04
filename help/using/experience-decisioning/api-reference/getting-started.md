---
title: Kom igång med besluts-API:er
description: Lär dig hur du börjar använda API:erna för beslutsfattande för att programmässigt hantera beslutsobjekt och leverera personaliserade erbjudanden.
feature: API, Decisioning
topic: Integrations
role: Developer
level: Experienced
exl-id: 7a4b5d4e-9c1d-4f3a-b8e9-1d5f6e7a8c3a
version: Journey Orchestration
source-git-commit: 9ac3eaba0b4c6536c1c447df825eb5f5c0afc900
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 0%

---

# Utvecklarhandbok för API för beslut {#decisioning-api-developer-guide}

Med API:er för beslutsfattande kan ni skapa och hantera de komponenter som används för att leverera personaliserade erbjudanden till era kunder via programmering. Dessa RESTful API:er tillhandahåller fullständiga CRUD-åtgärder (Skapa, Läs, Uppdatera, Ta bort) för beslutsobjekt, urvalsstrategier, regler för behörighet och andra beslutskomponenter.

## Autentisering {#authentication}

Innan du använder API:er för beslut måste du konfigurera autentisering för att komma åt API-slutpunkterna. I [Journey Optimizer-autentiseringsguiden](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"} finns stegvisa instruktioner.

## Tillgängliga API-åtgärder {#available-operations}

Besluts-API:erna innehåller omfattande hanteringsfunktioner för beslutskomponenter. Följande kategorier av åtgärder är tillgängliga:

* **Beslutsobjekt** - Skapa, läsa, uppdatera, ta bort och lista beslutsobjekt som representerar erbjudanden eller innehåll som du vill leverera till kunder.

  ➡️ [Lär dig hantera beslutsobjekt](decisions-items/create.md)

* **Objektsamlingar** - Ordna beslutsobjekt i samlingar för enklare hantering och målgruppsanpassning med hjälp av regler för behörighet.

  ➡️ [Lär dig hantera objektsamlingar](items-collections/create.md)

* **Urvalsstrategier** - Definiera hur beslutsartiklar väljs och rangordnas när flera artiklar kvalificerar sig för leverans.

  ➡️ [Lär dig hantera markeringsstrategier](selection-strategies/create.md)

* **Kvalifikationsregler** - Ange villkor som avgör vilka profiler som är berättigade att ta emot specifika beslutsartiklar.

  ➡️ [Lär dig hur du hanterar berättiganderegler](eligibility-rules/create.md)

* **Rankningsformler** - Skapa anpassad rankningslogik för att avgöra i vilken ordning beslutsobjekten presenteras.

  ➡️ [Lär dig hantera rankningsformler](ranking-formulas/create.md)

* **Placeringar** - Definiera platser eller sammanhang där beslutsobjekt kan visas i dina upplevelser.

  ➡️ [Lär dig hantera placeringar](exd-placements/create.md)

## Nästa steg {#next-steps}

Nu när du förstår grunderna i API:erna för beslut kan du fortsätta med de specifika åtgärderna:

* [Skapa beslutsobjekt](decisions-items/create.md)
* [Lista beslutsobjekt](decisions-items/decision-items-list.md)
* [Skapa urvalsstrategier](selection-strategies/create.md)
* [Skapa berättiganderegler](eligibility-rules/create.md)

Mer information om hur du använder beslut i kampanjer och resor finns i [beslutsdokumentationen](../gs-experience-decisioning.md).

>[!NOTE]
>
>Om du behöver migrera befintliga beslutshanteringsobjekt till Beslutsfattandet använder du det dedikerade [API:t för beslutsmigrering](../decisioning-migration-api.md). Detta specialiserade API har automatiserade beroendeupplösningar och återställningsfunktioner som är särskilt utformade för att migrera beslutsenheter över sandlådor.
