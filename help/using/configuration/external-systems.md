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
source-git-commit: 0b0badfa09a24d451671f5bae9ddc437c6db2911
workflow-type: tm+mt
source-wordcount: '1805'
ht-degree: 16%

---

# Integrera med externa system {#external-systems}

På den här sidan visas de olika säkerhetsutkast som Journey Optimizer ger när ett externt system integreras, liksom de bästa sätten: hur man optimerar skyddet för det externa systemet med API:t för appning, hur man konfigurerar tidsgränsen för resan och hur försök fungerar igen.

Med Journey Optimizer kan du konfigurera anslutningar till externa system via anpassade datakällor och anpassade åtgärder. På så sätt kan du till exempel berika dina resor med data från ett externt bokningssystem eller skicka meddelanden med ett tredjepartssystem som Epsilon eller Facebook.

När du integrerar ett externt system kan du stöta på flera problem, systemet kan vara långsamt, det kan sluta svara eller så kanske det inte kan hantera en stor volym. Journey Optimizer erbjuder flera skyddsräcken för att skydda datorn mot överbelastning.

Alla externa system har olika prestanda. Du måste anpassa konfigurationen efter dina användningsfall.

När Journey Optimizer gör ett anrop till ett externt API körs de tekniska garantierna enligt följande:

1. Reglerna för begränsning eller begränsning tillämpas: om den maximala hastigheten uppnås tas återstående anrop bort eller köas.

1. Timeout och försök igen: om begränsnings- eller begränsningsregeln är uppfylld försöker Journey Optimizer genomföra anropet tills tidsgränsen har nåtts.

>[!TIP]
>
>Vi rekommenderar att du lämnar minst en buffert på en minut mellan det externa API:ts giltighetsperiod för token och din Journey Optimizer [`cacheDuration`-inställning &#x200B;](../datasource/external-data-sources.md#custom-authentication-access-token), särskilt under stora arbetsbelastningar, för att undvika avvikelser vid förfallodatum och 401 fel.

## API:er för begränsning och begränsning {#capping}

### Om API:er för begränsning och begränsning

När du konfigurerar en datakälla eller en åtgärd upprättar du en anslutning till ett system för att antingen hämta ytterligare information som ska användas under dina resor eller skicka meddelanden eller API-anrop.

API:er för resor har stöd för upp till 5 000 händelser per sekund, men vissa externa system eller API:er har kanske inte samma genomströmning. Om du vill förhindra att dessa system överbelastas kan du använda API:erna **Capping** och **Throttling** för att begränsa antalet händelser som skickas per sekund.

Varje gång ett API-anrop utförs via resor skickas det via API-motorn. Om gränsvärdet i API:t nås, avvisas anropet antingen om du använder API:t för begränsning, eller köas i upp till 6 timmar och behandlas så snart som möjligt i den ordning som de togs emot om du använder API:t för begränsning.

Anta till exempel att du har definierat en begränsning på 200 anrop per sekund för det externa systemet. Ditt system anropas av en anpassad åtgärd på tio olika resor. Om en resa tar emot 300 anrop per sekund används de 200 tillgängliga facken och de 100 återstående facken tas bort eller köas. Eftersom den högsta nivån har överskridits har de övriga nio resorna inte några fack kvar. Denna precision hjälper till att skydda det externa systemet från överbelastning och krascher.

>[!IMPORTANT]
>
>**Takregler** är konfigurerade på sandlådenivå för en specifik slutpunkt (den anropade URL:en), men globala för alla resor i den sandlådan. Det finns ett tak för både datakällor och anpassade åtgärder.
>
>**Begränsningsregler** konfigureras endast för produktionssandlådor, för en specifik slutpunkt, men är globala för alla resor över alla sandlådor. Du kan bara ha en begränsningskonfiguration per organisation. Begränsning är bara tillgängligt för anpassade åtgärder.
>
>Värdet **maxCallCount** måste vara större än 1.

Mer information om hur du arbetar med API:erna finns i följande avsnitt:

* [API för reglering](capping.md)
* [API för begränsning](throttling.md)

En detaljerad beskrivning av API:erna finns i [dokumentationen för Adobe Journey Optimizer API:er](https://developer.adobe.com/journey-optimizer-apis/references/journeys-throttling/)

### Datakällor och kapacitet för anpassade åtgärder {#capacity}

För **externa datakällor** är det maximala antalet anrop per sekund begränsat till femton. Om den här gränsen överskrids, ignoreras eller köas eventuella ytterligare anrop beroende på vilket API som används. Det är möjligt att öka denna gräns för privata externa datakällor genom att kontakta Adobe för att inkludera slutpunkten i tillåtelselistan, men detta är inte ett alternativ för offentliga externa datakällor. * [Läs mer om hur du konfigurerar datakällor](../datasource/about-data-sources.md).

>[!NOTE]
>
>Om en datakälla använder en anpassad autentisering med en annan slutpunkt än den som används för datakällan måste du kontakta Adobe för att även inkludera den slutpunkten i tillåtelselistan.

För **anpassade åtgärder** måste du utvärdera kapaciteten för ditt externa API. Om Journey Optimizer till exempel skickar 1 000 samtal per sekund och ditt system bara kan hantera 200 samtal per sekund, måste du definiera en begränsning eller begränsning så att systemet inte blir mättat. [Läs mer om hur du konfigurerar åtgärder](../action/action.md)

>[!NOTE]
>
>Eftersom svaren nu stöds bör du använda anpassade åtgärder i stället för datakällor för externa datakällor som användningsfall. Mer information om svar finns i [avsnittet](../action/action-response.md)

## Slutpunkter med långsam svarstid {#response-time}

När en slutpunkt har en svarstid på mer än 0,75 sekunder dirigeras dess anpassade åtgärdsanrop via en dedikerad **långsam anpassad åtgärdstjänst** i stället för standardtjänsten.

Den här tjänsten för långsam anpassad åtgärd tillämpar en begränsning på 150 000 anrop var 30:e sekund. Gränsen används med ett skjutfönster som kan börja när som helst under en 30-sekundersperiod. När fönstret är fullt avvisas ytterligare anrop med spärrfel. Systemet väntar inte på nästa fasta intervall, men börjar kryssa omedelbart efter att tröskelvärdet på 30 sekunder har uppnåtts.

Eftersom långsamma slutpunkter kan orsaka fördröjningar för alla åtgärder i kön i pipeline, bör du inte konfigurera anpassade åtgärder med slutpunkter som har långsamma svarstider. Vidarebefordra sådana åtgärder till den långsamma tjänsten för att skydda den övergripande systemprestandan och förhindra ytterligare latens för andra anpassade åtgärder.

## Timeout och försök igen {#timeout}

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

## Vanliga frågor {#faq}

Nedan finns Frågor och svar om hur du integrerar Journey Optimizer med externa system.

Behöver du mer information? Använd alternativen för feedback längst ned på den här sidan för att ställa din fråga eller kontakta [Adobe Journey Optimizer Community](https://experienceleaguecommunities.adobe.com/t5/adobe-journey-optimizer/ct-p/journey-optimizer?profile.language=en){target="_blank"}.

+++ Hur konfigurerar jag en begränsning eller begränsning? Finns det en standardregel?

Se [det här avsnittet](../configuration/external-systems.md#capping) om du vill skapa regler för begränsning och begränsning. Som standard finns det ingen begränsning, men en begränsning på 300 000 anrop över en minut som definierats för alla anpassade åtgärder, per värd och per sandlåda. Gränsvärdet per värd gäller på domännivå (t.ex. example.com). Den här gränsen har fastställts baserat på kundanvändning för att skydda externa slutpunkter som har anpassats efter anpassade åtgärder. Om det behövs kan du åsidosätta den här inställningen genom att definiera en större begränsning för begränsning eller begränsning via våra API:er för begränsning/begränsning. Se [den här sidan](../action/about-custom-action-configuration.md) om du vill ha mer information om hur du begär höjda capping.

+++

+++ Hur många återförsök görs? Kan jag ändra antalet återförsök eller definiera en minsta vänteperiod mellan återförsök?

För ett visst anrop kan högst tre försök utföras efter det första anropet, tills tidsgränsen för anropet har nåtts. Antalet försök och tiden mellan varje nytt försök kan inte ändras. Se [det här avsnittet](../configuration/external-systems.md#timeout).

+++

+++ Var kan jag konfigurera tidsgränsen? Finns det ett maxvärde?

Under varje resa kan du definiera en tidsgräns. Tidsgränsen har konfigurerats i egenskaperna för en resa. Tidsgränsen måste vara mellan 1 och 30 sekunder. Se [det här avsnittet](../configuration/external-systems.md#timeout) och [sidan](../building-journeys/journey-properties.md#timeout_and_error).

+++

+++ Vad är egresutkastet och när ska jag använda det?

Gresproxyn tillhandahåller en **statisk IP-adress** för utgående samtal från Journey Optimizer till dina externa system. Använd det när slutpunkterna från tredje part kräver IP-tillåtelselistning.

**Viktigt!** Gressproxyn kontrollerar INTE genomströmning, hastighetsbegränsningar eller antalet samtidiga anslutningar. Om du vill hantera samtalsvolym och anslutningsgränser använder du [API:t för begränsning](capping.md) eller [API:t för begränsning](throttling.md).

**Använd egresproxy för:**
* Tillåtslista en statisk IP-adress på en brandvägg eller slutpunkt från tredje part

**Använd API:er för begränsning/begränsning för:**
* Begränsa antalet API-anrop per sekund
* Styra samtidiga anslutningar till slutpunkten
* Skydda det externa systemet mot överbelastning

Kontakta Adobe för att aktivera offresproxy för din organisation om du behöver en statisk IP för tillåtelselistning.

+++

+++ Vilket är det högsta antalet anslutningar som öppnas av Journey Optimizer när anpassade åtgärder används?

När IP-proxyn är aktiverad och en begränsningskonfiguration har definierats för målslutpunkten, baseras antalet anslutningar på hastigheten (dessa är uppskattningar, inte garanterade siffror):

* mellan 200 och 2000 c/s: 50 anslutningar
* mellan 2000 och 3000: 75 anslutningar
* mellan 3 000 och 4 000: 100 anslutningar
* mellan 4 000 och 5 000: 125 anslutningar

Om ingen begränsningskonfiguration har definierats för en slutpunkt är Journey Optimizer-motorn utformad för att skalas upp och kan få ett stort antal anslutningar (fler än 2 000). För att få ett begränsat antal anslutningar måste kunderna använda en begränsningskonfiguration.

+++
