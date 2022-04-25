---
title: API:er för beslutsfattande och Edge Decisioning
description: Beslutshantering är en samling tjänster och gränssnittsprogram som gör det möjligt för marknadsförare att skapa och leverera personaliserade erbjudanden för slutanvändare i alla kanaler och i alla tillämpningar med hjälp av logiska funktioner och beslutsregler.
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
source-git-commit: d3a22f223353dfa5d43acab400cea3d5c314662f
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 1%

---

# API:er för beslutsfattande och Edge Decisioning {#about-decisioning-apis}

Du kan leverera erbjudanden med **Beslut** eller **Edge Decisionering** API.

På den här sidan hittar du information om specifika funktioner som är tillgängliga för varje API. Vi rekommenderar att du använder **Edge Decisionering** API när det är möjligt för inkommande användning och för att säkerställa bättre latens och genomströmning på din plattform.

|  | Begäranden/sek | Latens |
|---|---|---|
| Besluts-API | 2000 | &lt;500ms |
| API för Edge Decisioning | 5000 | &lt;250 ms |

Mer information om hur du arbetar med API:erna finns i följande avsnitt:
* [Besluts-API](decisioning-api.md)
* [API för Edge Decisioning](edge-decisioning-api.md)

## API-funktioner för Edge Decisioning {#edge}

**Unik begäran om upplevelsehändelser och beslutsbegäranden**

Med Edge Decisioning API kan du i en enda begäran skicka upplevelsehändelsen tillsammans med beslutsbegäran, i stället för att ha två olika förfrågningar.

Om en kund t.ex. besöker din webbplats kommer förfrågan att innehålla upplevelsehändelsen (kundens besök på sidan) och ett erbjudande skickas tillbaka för att fylla i den besökta sidan.

**Lagring av kontextdata i Adobe Experience Platform**

Kontextdata avser data som du bara känner till när du vill ha tillbaka ett erbjudande. Till exempel färgen på den köpta artikeln, vädret vid tidpunkten för köpet osv.

När kontextdata skickas med en begäran från Edge Decisioning API, lagras data i Adobe Experience Platform-profilen, vilket möjliggör framtida återanvändning.

>[!NOTE]
>
>För att kontextdata ska kunna lagras måste du ha ett dedikerat XDM-schema konfigurerat. (+ länk till XDM-dokument)

## API-funktioner för beslut {#decisioning}

De funktioner som anges nedan är endast tillgängliga med besluts-API:t. Om du behöver utnyttja någon av dem för att uppfylla dina krav använder du API:t för beslut. I annat fall rekommenderar vi att du använder API:erna för Edge Decision.

* **Experience events**: utnyttja upplevelsehändelser för att bygga upp era beslutsregler.
* **Erbjud innehåll och egenskaper**: du kan välja att inte returnera innehållet och egenskaperna för ett erbjudande med ett dedikerat alternativ.
* **Erbjud metadata**: aktivera ett alternativ för att returnera metadata för ett erbjudande.
* **Kopplingsprincip**: i din begäran använda en annan sammanfogningsprincip än den som är kopplad till din sandlåda.
* **Beslutshändelser och frekvensbegränsning**: blockbeslutshändelser räknas inte av någon frekvensbegränsning som inträffar.
* **Duplicera förslag**: aktivera ett alternativ för att inte deduplicera förslag.
