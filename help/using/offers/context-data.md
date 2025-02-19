---
product: experience platform
solution: Experience Platform
title: Kom igång med kontextdata
description: Lär dig utnyttja kontextdata i beslutsprocessen.
feature: Decision Management
role: Developer, Data Engineer
level: Experienced
source-git-commit: 9b66f4871d8b539bf0201b2974590672205a3243
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---


# Kom igång med kontextdata {#context-data}

Data som skickas som en del av beslutsbegäran betraktas som kontextdata. Du kan utnyttja kontextdata i beslutsmotorn, t.ex. för att utforma en beslutsregel som kräver att det aktuella vädret är ≥80 grader vid tidpunkten då beslutsbegäran görs.

Kontextdata definieras annorlunda mellan API-begäranden för **beslutande** och **Edge-beslut**. För båda typerna av förfrågningar kan kontextdata användas i regler för behörighet eller i rankningsformler, men endast Edge Decisioning API-förfrågningar kan använda kontextdata för att personalisera innehåll.

Innan du startar bör du kontrollera följande skyddsräcken och begränsningar:

* På grund av olika sätt att skicka in kontext mellan ansökningsomgångar för beslut och Edge-beslut är kontextbaserade regler för behörighet och rankningsformler inte utbytbara mellan beslut och Edge-beslut.
* Det går bara att testa med parametern `dryrun` med API:t för beslut. Det är inte tillgängligt med Edge Decisioning API. Observera att om den här parametern anges till `true` med API:t för beslut påverkas inte ändpunkter och antalet utkast.

Detaljerad information om hur du använder kontextdata i varje API finns i följande avsnitt:

* [Använd kontextdata i Edge Decisioning-begäranden](context-data-edge.md)
* [Använd kontextdata i beslutsbegäranden](context-data-decisioning.md)

