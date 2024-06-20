---
solution: Journey Optimizer
product: journey optimizer
title: Integrera Journey Optimizer med externa system
description: Lär dig de bästa sätten att integrera Journey Optimizer med externa system
feature: Integrations
role: User
level: Beginner
keywords: extern, API, optimerare, capping
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: fec6b15db9f8e6b2a07b55bc9e8fc4d9cb0d73d7
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 26%

---

# Integrera med externa system {#external-systems}

På den här sidan visas de olika säkerhetsutkast som Journey Optimizer ger när ett externt system integreras, liksom de bästa sätten: hur man optimerar skyddet för det externa systemet med API:t för appning, hur man konfigurerar tidsgränsen för resan och hur försök fungerar igen.

Med Journey Optimizer kan du konfigurera anslutningar till externa system via anpassade datakällor och anpassade åtgärder. På så sätt kan du t.ex. berika dina resor med data från ett externt bokningssystem eller skicka meddelanden med ett tredjepartssystem som Epsilon eller Facebook.

När du integrerar ett externt system kan du stöta på flera problem, systemet kan vara långsamt, det kan sluta svara eller så kanske det inte kan hantera en stor volym. Journey Optimizer erbjuder flera skyddsräcken för att skydda datorn mot överbelastning.

Alla externa system har olika prestanda. Du måste anpassa konfigurationen efter dina användningsfall.

När Journey Optimizer gör ett anrop till ett externt API körs de tekniska garantierna enligt följande:

1. Reglerna för begränsning eller begränsning tillämpas: om den maximala hastigheten uppnås tas återstående anrop bort eller köas.

2. Timeout och försök igen: om begränsnings- eller begränsningsregeln är uppfylld försöker Journey Optimizer genomföra anropet tills tidsgränsen har nåtts.

## API:er för begränsning och begränsning {#capping}

### Om API:er för begränsning och begränsning

När du konfigurerar en datakälla eller en åtgärd upprättar du en anslutning till ett system för att antingen hämta ytterligare information som ska användas under dina resor eller skicka meddelanden eller API-anrop.

API:er för resor har stöd för upp till 5 000 händelser per sekund, men vissa externa system eller API:er har kanske inte samma genomströmning. Du kan förhindra att dessa system överbelastas med **Takning** och **Begränsning** API:er som begränsar antalet händelser som skickas per sekund.

Varje gång ett API-anrop utförs via resor skickas det via API-motorn. Om gränsvärdet i API:t nås, avvisas anropet antingen om du använder API:t för begränsning, eller köas i upp till 6 timmar och behandlas så snart som möjligt i den ordning som de togs emot om du använder API:t för begränsning.

Anta till exempel att du har definierat en begränsning på 200 anrop per sekund för det externa systemet. Ditt system anropas av en anpassad åtgärd på tio olika resor. Om en resa tar emot 300 anrop per sekund används de 200 tillgängliga facken och de 100 återstående facken tas bort eller köas. Eftersom den högsta nivån har överskridits har de övriga nio resorna inte några fack kvar. Denna precision hjälper till att skydda det externa systemet från överbelastning och krascher.

>[!IMPORTANT]
>
>**Begränsningsregler** är konfigurerade på sandlådenivå, för en specifik slutpunkt (den anropade URL:en), men globala till alla resor i den sandlådan. Det finns ett tak för både datakällor och anpassade åtgärder.
>
>**Begränsningsregler** konfigureras endast för produktionssandlådor, för en specifik slutpunkt, men är globala för alla resor över alla sandlådor. Du kan bara ha en begränsningskonfiguration per organisation. Begränsning är bara tillgängligt för anpassade åtgärder.
>
>The **maxCallCount** värdet måste vara större än 1.

Mer information om hur du arbetar med API:erna finns i följande avsnitt:

* [API för reglering](capping.md)
* [API för begränsning](throttling.md)

En detaljerad beskrivning av API:erna finns i [Dokumentation för Adobe Journey Optimizer API:er](https://developer.adobe.com/journey-optimizer-apis/references/journeys/)

### Datakällor och kapacitet för anpassade åtgärder {#capacity}

För **externa datakällor** är det maximala antalet anrop per sekund begränsat till femton. Om den här gränsen överskrids, ignoreras eller köas eventuella ytterligare anrop beroende på vilket API som används. Det är möjligt att öka denna gräns för privata externa datakällor genom att kontakta Adobe för att inkludera slutpunkten i tillåtelselistan, men detta är inte ett alternativ för offentliga externa datakällor. * [Läs mer om hur du konfigurerar datakällor](../datasource/about-data-sources.md).

>[!NOTE]
>
>Om en datakälla använder en anpassad autentisering med en annan slutpunkt än den som används för datakällan måste du kontakta Adobe för att även inkludera den slutpunkten i tillåtelselistan.

För **anpassade åtgärder** måste du utvärdera kapaciteten för ditt externa API. Om Journey Optimizer t.ex. skickar 1 000 anrop per sekund och systemet bara har stöd för 200 anrop per sekund, måste du definiera en konfiguration för reglering eller begränsning så att systemet inte blir mättat. [Läs mer om hur du konfigurerar åtgärder](../action/action.md)

## Timeout och försök igen{#timeout}

Om begränsnings- eller begränsningsregeln är uppfylld tillämpas timeout-regeln.

Under varje resa kan du definiera en tidsgräns. Detta gör att du kan ange en maximal varaktighet när du anropar ett externt system. Tidsgränsen har konfigurerats i egenskaperna för en resa. Se [den här sidan](../building-journeys/journey-properties.md#timeout_and_error).

Den här tidsgränsen är global för alla externa anrop (externa API-anrop i anpassade åtgärder och anpassade datakällor). Som standard är den inställd på 30 sekunder.

Under den angivna tidsgränsen försöker Journey Optimizer anropa det externa systemet. Efter det första anropet kan högst tre försök utföras tills tidsgränsen för timeout har nåtts. Antalet försök kan inte ändras.

Varje nytt försök använder en kortplats. Om du har ett tak på 100 samtal per sekund och vart och ett av dina samtal kräver två försök, kommer hastigheten att sänkas till 30 samtal per sekund (varje samtal använder 3 platser: det första samtalet och två försök).

Tidsgränsvärdet beror på användningsfallet. Om du snabbt vill skicka ditt meddelande, till exempel när klienten kommer in i butiken, vill du inte ange en lång tidsgräns. Ju längre tidsgränsen är, desto fler objekt placeras i kö. Detta kan påverka prestandan avsevärt. Om Journey Optimizer utför 1 000 anrop per sekund, kan det vara bra att lagra 5 eller 15 sekunder med data.

Låt oss ta ett exempel i 5 sekunder.

* Det första anropet varar mindre än 5 sekunder: anropet lyckades, inget nytt försök utförs.
* Det första samtalet varar längre än 5 sekunder: samtalet avbryts och det görs inget nytt försök. Den räknas som ett timeout-fel vid rapportering.
* Det första anropet misslyckas efter 2 sekunder (det externa systemet returnerar ett fel): 3 sekunder återstår för nya försök, om det finns lediga fack.
   * Om ett av de tre försöken lyckas före slutet av de fem sekunderna utförs anropet och det finns inget fel.
   * Om tidsgränsen nås under återförsöken avbryts anropet och räknas som ett timeout-fel i rapporteringen.

## Vanliga frågor och svar{#faq}

**Hur konfigurerar jag en begränsning eller begränsning? Finns det en standardregel?**

Som standard finns det ingen begränsning eller begränsning. Regler definieras på sandlådenivå för en specifik slutpunkt (den URL som anropas) med API:t för begränsning eller begränsning. Se [det här avsnittet](../configuration/external-systems.md#capping).

**Hur många återförsök görs? Kan jag ändra antalet återförsök eller definiera en minsta vänteperiod mellan återförsök?**

För ett visst anrop kan högst tre försök utföras efter det första anropet, tills tidsgränsen för anropet har nåtts. Antalet försök och tiden mellan varje nytt försök kan inte ändras. Se [det här avsnittet](../configuration/external-systems.md#timeout).

**Var kan jag konfigurera tidsgränsen? Finns det ett maxvärde?**

Under varje resa kan du definiera en tidsgräns. Tidsgränsen har konfigurerats i egenskaperna för en resa. Tidsgränsen måste vara mellan 1 och 30 sekunder. Se [det här avsnittet](../configuration/external-systems.md#timeout) och [den här sidan](../building-journeys/journey-properties.md#timeout_and_error).