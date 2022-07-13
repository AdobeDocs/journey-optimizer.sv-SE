---
title: Kom igång med API:er för erbjudanden
description: Läs mer om de API:er som finns för att leverera personaliserade erbjudanden.
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 7bc1a4ec-113c-4af7-b549-ee17b843b818
source-git-commit: bf738ebac09d5c852872a8ea85f6532ad9d4222d
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 1%

---

# Kom igång med API:er för erbjudanden {#about-decisioning-apis}

Du kan leverera erbjudanden med **Beslut** eller **Edge Decisionering** API. Dessutom finns **Gruppbeslut** Med API kan ni leverera erbjudanden till alla profiler i ett visst segment i ett enda anrop. Erbjudandeinnehållet för varje profil i segmentet placeras i en Adobe Experience Platform-datauppsättning där det är tillgängligt för anpassade grupparbetsflöden.

På den här sidan hittar du information om specifika funktioner som är tillgängliga med **Beslut** och **Edge Decisionering** API:er. Vi rekommenderar att du använder **Edge Decisionering** API när det är möjligt för inkommande användning och för att säkerställa bättre latens och genomströmning på din plattform.

|  | Begäranden/sek | Latens |
|---|---|---|
| Besluts-API | 2000 | &lt;500ms |
| API för Edge Decisioning | 5000 | &lt;250 ms |

Mer information om hur du arbetar med API:erna finns i följande avsnitt:
* [Besluts-API](decisioning-api.md)
* [API för Edge Decisioning](edge-decisioning-api.md)
* [API för gruppbeslut](batch-decisioning-api.md)

## API-funktioner för Edge Decisioning {#edge}

**Unik begäran om upplevelsehändelser och beslutsbegäranden**

Med Edge Decisioning API kan du i en enda begäran skicka upplevelsehändelsen tillsammans med beslutsbegäran, i stället för att ha två olika förfrågningar.

Om en kund t.ex. besöker din webbplats kommer förfrågan att innehålla upplevelsehändelsen (kundens besök på sidan) och ett erbjudande skickas tillbaka för att fylla i den besökta sidan.

**Lagring av kontextdata i Adobe Experience Platform**

Kontextdata avser data som du bara känner till när du vill ha tillbaka ett erbjudande. Till exempel färgen på den köpta artikeln, vädret vid tidpunkten för köpet osv.

När kontextdata skickas med en begäran från Edge Decisioning API, lagras data i Adobe Experience Platform-profilen, vilket möjliggör framtida återanvändning.

>[!NOTE]
>
>För att kontextdata ska kunna lagras måste du ha ett dedikerat XDM-schema konfigurerat.

## API-funktioner för beslut {#decisioning}

De funktioner som anges nedan är endast tillgängliga med besluts-API:t. Om du behöver utnyttja någon av dem för att uppfylla dina krav använder du API:t för beslut. I annat fall rekommenderar vi att du använder API:erna för Edge Decision.

* **Experience events**: utnyttja upplevelsehändelser för att bygga upp era beslutsregler.
* **Erbjud innehåll och egenskaper**: du kan välja att inte returnera innehållet och egenskaperna för ett erbjudande med ett dedikerat alternativ.
* **Erbjud metadata**: aktivera ett alternativ för att returnera metadata för ett erbjudande.
* **Kopplingsprincip**: i din begäran använda en annan sammanfogningsprincip än den som är kopplad till din sandlåda.
* **Beslutshändelser och frekvensbegränsning**: blockbeslutshändelser räknas inte av någon frekvensbegränsning som inträffar.
* **Duplicera förslag**: aktivera ett alternativ för att inte deduplicera förslag.
