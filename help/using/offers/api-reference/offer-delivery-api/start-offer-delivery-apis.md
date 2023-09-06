---
title: Kom igång med erbjudandeleverans-API:er
description: Läs mer om de API:er som finns för att leverera personaliserade erbjudanden.
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 7bc1a4ec-113c-4af7-b549-ee17b843b818
source-git-commit: ccc3ad2b186a64b9859a5cc529fe0aefa736fc00
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 0%

---

# Kom igång med erbjudandeleverans-API:er {#about-decisioning-apis}

Du kan leverera erbjudanden med **Beslut** eller **Edge Decisionering** API. Dessutom kan du **Gruppbeslut** Med API kan ni leverera erbjudanden till alla profiler i en viss målgrupp i ett enda samtal. Erbjudandeinnehållet för varje profil i målgruppen placeras i en Adobe Experience Platform-datauppsättning där det är tillgängligt för anpassade grupparbetsflöden.

På den här sidan hittar du information om specifika funktioner som är tillgängliga med **Beslut** och **Edge Decisionering** API. Vi rekommenderar att du använder **Edge Decisionering** API när det är möjligt för inkommande användning och för att säkerställa bättre latens och genomströmning på din plattform.


Mer information om hur du arbetar med API:erna finns i följande avsnitt:
* [Besluts-API](decisioning-api.md)
* [API för Edge Decisioning](edge-decisioning-api.md)
* [API för gruppbeslut](batch-decisioning-api.md)

## API-funktioner för Edge Decision {#edge}

**Unik begäran om upplevelsehändelser och beslutsbegäranden**

Med Edge Decisioning API kan du i en enda begäran skicka upplevelsehändelsen tillsammans med beslutsbegäran, i stället för att ha två olika förfrågningar.

Om en kund t.ex. besöker din webbplats kommer förfrågan att innehålla upplevelsehändelsen (kundens besök på sidan) och ett erbjudande skickas tillbaka för att fylla i den besökta sidan.

**Lagring av kontextdata i Adobe Experience Platform**

Kontextdata avser data som du bara känner till när du vill ha tillbaka ett erbjudande. Till exempel färgen på den köpta artikeln, vädret vid köptillfället osv.

När kontextdata skickas med en begäran från Edge Decisioning API, lagras data i Adobe Experience Platform-profilen så att de kan återanvändas i framtiden.

>[!NOTE]
>
>För att kontextdata ska kunna lagras måste du ha ett dedikerat XDM-schema konfigurerat.

## API-funktioner för beslut {#decisioning}

De funktioner som anges nedan är endast tillgängliga med besluts-API:t. Om du behöver utnyttja någon av dem för att uppfylla dina krav använder du API:t för beslut. I annat fall rekommenderar vi att du använder API:erna för Edge Decision.

* **Experience events**: utnyttja upplevelsehändelser för att bygga upp era beslutsregler.
* **Erbjud innehåll och egenskaper**: du kan välja att inte returnera innehållet och egenskaperna för ett erbjudande med ett dedikerat alternativ.
* **Erbjud metadata**: aktivera ett alternativ för att returnera metadata för ett erbjudande.
* **Kopplingsprincip**: använd i din begäran en annan sammanfogningsprincip än den som är kopplad till din sandlåda.
* **Beslutshändelser och frekvensbegränsning**: blockbeslutshändelser räknas inte av någon frekvensbegränsning som inträffar.
* **Duplicera förslag**: aktivera ett alternativ för att inte deduplicera anbud.
