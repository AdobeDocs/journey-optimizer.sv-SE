---
title: Kom igång med erbjudandeleverans-API:er
description: Läs mer om de API:er som finns för att leverera personaliserade erbjudanden.
feature: Decision Management, API
topic: Integrations
role: Developer
level: Experienced
exl-id: 7bc1a4ec-113c-4af7-b549-ee17b843b818
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# Kom igång med erbjudandeleverans-API:er {#about-decisioning-apis}

Du kan leverera erbjudanden med API:t **Decisioning** eller **Edge Decisioning** . Med API:t **Batch Decisioning** kan du dessutom leverera erbjudanden till alla profiler i en viss målgrupp i ett enda anrop. Erbjudandeinnehållet för varje profil i målgruppen placeras i en Adobe Experience Platform-datauppsättning där det är tillgängligt för anpassade grupparbetsflöden.

På den här sidan hittar du information om specifika funktioner som är tillgängliga med API:erna **Decisioning** och **Edge Decisioning** . Även om båda tillåter dig att leverera erbjudanden till dina kunder rekommenderar vi att du använder API:t för **Edge Decisioning** när det är möjligt för inkommande bruk och för att säkerställa bättre latens och genomströmning på din plattform.

Mer information om hur du arbetar med API:erna finns i följande avsnitt:

* [Besluts-API](decisioning-api.md)
* [Edge Decisioning API](edge-decisioning-api.md)
* [API för gruppbeslut](batch-decisioning-api.md)

## API-funktioner för Edge Decision {#edge}

**Unik begäran för upplevelsehändelser och beslutsbegäranden**

Med Edge Decisioning API kan du i en enda begäran skicka upplevelsehändelsen tillsammans med beslutsbegäran, i stället för att ha två olika förfrågningar.

Om en kund t.ex. besöker din webbplats kommer förfrågan att innehålla upplevelsehändelsen (kundens besök på sidan) och ett erbjudande skickas tillbaka för att fylla i den besökta sidan.

**Kontextdatalagring i Adobe Experience Platform**

Kontextdata avser data som du bara känner till när du vill ha tillbaka ett erbjudande. Till exempel färgen på den köpta artikeln, vädret vid köptillfället osv.

När kontextdata skickas med en Edge Decisioning API-begäran lagras data i Adobe Experience Platform-profilen, vilket möjliggör framtida återanvändning.

>[!NOTE]
>
>För att kontextdata ska kunna lagras måste du ha ett dedikerat XDM-schema konfigurerat.

**Räknaruppdatering för frekvensbegränsning**

Om frekvensbegränsning har aktiverats för vissa av dina erbjudanden för att definiera hur ofta deras antalet capping återställs, uppdateras räknaren och är tillgänglig i ett beslut av Edge Decisioning API på mindre än 3 sekunder. [Lär dig lägga till begränsningar i ett erbjudande](../../offer-library/add-constraints.md)

## API-funktioner för beslut {#decisioning}

De funktioner som anges nedan är endast tillgängliga med besluts-API:t. Om du behöver utnyttja någon av dem för att uppfylla dina krav använder du API:t för beslut. I annat fall rekommenderar vi att du använder API:erna för Edge-beslut.

* **Erbjud innehåll och egenskaper**: du kan välja att inte returnera innehåll och egenskaper för ett erbjudande med ett dedikerat alternativ.
* **Erbjud metadata**: aktivera ett alternativ för att returnera metadata för ett erbjudande.
* **Sammanslagningsprincip**: använd i din begäran en annan sammanfogningsprincip än den som är kopplad till din sandlåda.
* **Avgörande händelser och frekvensbegränsning**: blockbeslutshändelser räknas inte av någon frekvensbegränsning som inträffar.
* **Duplicera förslag**: aktivera ett alternativ för att inte deduplicera förslag.
