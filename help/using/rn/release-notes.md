---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
role: User
level: Beginner, Intermediate
description: Versionsinformation om Adobe Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 279fd366b14520daec1df7f843ed337348e145a5
workflow-type: tm+mt
source-wordcount: '1551'
ht-degree: 3%

---

# Versionsinformation {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="Nyheter?"
>abstract="**Adobe Journey Optimizer** levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen."

[!DNL Adobe Journey Optimizer] följer en kontinuerlig leveransmodell som gör att Adobe kan leverera nya funktioner, förbättringar och korrigeringar kontinuerligt. Detta tillvägagångssätt möjliggör en skalbar, fasad driftsättning av funktioner för att säkerställa prestanda och stabilitet i alla miljöer.

På grund av den här modellen uppdateras versionsinformationen mellan månadsversionerna. Fullständig information om frisläppningscykeln och tillgänglighetsfaserna finns i [Journey Optimizer versionscykel](releases.md).

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver från de senaste innovationerna och förbättringarna. Läs mer om de här ändringarna i [Adobe Experience Platform versionsinformation](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=sv-SE){target="_blank"}.

## Februari 26 förhandsversionsinformation {#feb-26-01-rn}

**Förhandsversionsinformationen nedan kan komma att ändras utan föregående meddelande till releasedatumet**. Länkar, skärmar och uppdaterad dokumentation publiceras i versionsinformationen på releasedatum.

Se även [Förhandsversionsinformation för Adobe Experience Platform](https://experienceleague.adobe.com/sv/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.

**Releasedatum**: 17-18 februari 2026

### Nya funktioner {#feb-26-01-features}

<table>
<thead>
<tr>
<th><strong>Påfyllnadssändning av utgående meddelanden</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Du kan schemalägga utgående meddelanden från <strong>kampanjer</strong> eller <strong>resor</strong> som ska levereras i kontrollerade <strong>batchar</strong> över tid.</p>
<p>Wave-sändning ger följande fördelar:</p>
<ul>
<li>Bättre <strong>slutbarhet</strong> - Spridet skickar över tid för att bevara ett starkt avsändarrykte och minska risken för att flaggas som skräppost.</li>
<li><strong>Lastkontroll</strong> - Undvik överväldigande system längre fram i kedjan (t.ex. callcenters, landningssidor) genom att begränsa hur många meddelanden som skickas samtidigt.</li>
<li>Användningsfall med stor volym och tidskänslighet - Passar för stora målgrupper eller när du behöver styra timing (t.ex. callcenters kapacitet, uppfartsavtal eller tidsbundna erbjudanden).</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Skiljeförfarande på resan</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du använda <strong>formler</strong> och <strong>AI-modeller</strong> för att automatiskt öka prioritetspoängen för resan baserat på kundprofilattribut och sammanhangsberoende faktorer, så att kunderna kommer in på de mest relevanta resorna.</p>
<p>Den här funktionen är bara tillgänglig för en uppsättning organisationer (<strong>Begränsad tillgänglighet</strong>). Kontakta din Adobe-representant för att få åtkomst.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Journey Agent: Skapa kanalinnehåll</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>Adobe Experience Platform Agent Orchestrator</strong>, <strong>Journey Agent</strong> är tillgängligt i Journey Optimizer och gör att du kan analysera resor via ett naturligt språkgränssnitt. Nu kan du även generera och hantera kanalspecifikt innehåll direkt i Journey Agent, skapa innehåll för kanaler som e-post och push, tillämpa och förhandsgranska mallar, förfina ton och stil genom uppmaningar och öppna innehåll i <strong>Content Designer</strong> för kontextredigering.</p>
</td>
</tr>
</tbody>
</table>

<!--
<table>
<thead>
<tr>
<th><strong>Mobile Live Activities</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>Live Activities</strong> provide real-time updates and interactive experiences within mobile apps, allowing users to stay informed about ongoing events or tasks directly on their device's screen. This feature enhances engagement by delivering live information, such as progress tracking, event updates, or interactive content, without requiring users to open the app.</p>
<p>Previously released in beta, this capability is now available to all environments (General Availability).</p>
</td>
</tr>
</tbody>
</table>
-->

<table>
<thead>
<tr>
<th><strong>Verksamhet under resor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer har stöd för en ny generisk <strong>åtgärdsaktivitet</strong> som gör att du kan konfigurera både enskilda åtgärder och inkommande åtgärdsgrupper för flera åtgärder, vilket ger en smidig åtgärdskonfiguration på arbetsytan. Den här nya funktionen gör det möjligt att:</p>
<ul>
<li>En förenklad inbyggd åtgärdskonfiguration på arbetsytan för resan.</li>
<li>Kapaciteten för att skapa inkommande åtgärdsgrupper med flera åtgärder.</li>
<li>Möjlighet att lägga till <strong>optimering</strong> i inbyggda kanalåtgärder.</li>
<li>Möjlighet att lägga till alternativen <strong>experiment</strong> och <strong>flerspråkig</strong> i alla åtgärder.</li>
</ul>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Meddelandekanal för Web Push</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer har nu stöd för <strong>Web Push-meddelanden</strong>, vilket gör att push-kanalen kan användas även utanför mobila enheter. Ni kan smidigt leverera meddelanden till både webbläsare för mobiler och datorer, så att ni kan nå kunder direkt på deras enheter utan att behöva använda en app. Den här förbättringen gör att ni kan engagera användarna med rätt, personaliserade meddelanden i realtid, och utnyttja samma arbetsflöden och målgruppsfunktioner som redan finns för mobilpush.</p>
<p>Den här funktionen lanserades tidigare i betaversionen och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p>Tillgänglighetsdatum: 13 februari 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Meddelandekanal för Web Push</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer har nu stöd för <strong>Web Push-meddelanden</strong>, vilket gör att push-kanalen kan användas även utanför mobila enheter. Du kan enkelt leverera meddelanden till både <strong>mobilwebbläsare och datorwebbläsare</strong>, så att du kan nå kunder direkt på deras enheter utan att behöva använda en app. Den här förbättringen gör att ni kan engagera användarna med rätt, personaliserade meddelanden i realtid, och utnyttja samma arbetsflöden och målgruppsfunktioner som redan finns för mobilpush.</p>
<p><img src="assets/do-not-localize/web-push.gif"/></p>
<p>Den här funktionen lanserades tidigare i Beta och är tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p>Mer information finns i den <a href="../push/push-configuration-web.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 11 februari 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Aktivitet för innehållsbeslut</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>En ny <strong>aktivitet för innehållsbeslut</strong> är nu tillgänglig på arbetsytan för att integrera personaliserade erbjudanden direkt i kundresorna. Med den här aktiviteten kan ni leverera beslutsbaserat innehåll och hänvisa till dessa erbjudanden under hela kundresan, under villkor för att skapa kvalificeringsbaserade förgreningar, i anpassade åtgärder för att skicka erbjudandedata till externa system och i andra aktiviteter för att skapa helt personaliserade kundupplevelser.</p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p><img src="assets/do-not-localize/content-decision.gif"/></p>
<p>Mer information finns i den <a href="../building-journeys/content-decision.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 11 februari 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Verktyg-API:er för självbetjäningsmigrering</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>Migreringsverktygs-API:er</strong> är nu tillgängliga för programmässig migrering av entiteter för <strong>beslutshantering</strong> till <strong>beslutshantering</strong>, med:</p>
<ul>
<li>Flexibla migreringsomfång (<strong>sandbox</strong>, <strong>offer</strong> eller <strong>Decision</strong> -nivå)</li>
<li>Automatiserad <strong>beroendeanalys</strong> och validering</li>
<li><strong>Återställningsstöd</strong> för slutförda migreringar</li>
<li>Detaljerade migreringsrapporter med objektmappningar</li>
</ul>
<p>Mer information finns i den <a href="../experience-decisioning/decisioning-migration-api.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 3 februari 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Övervakning av anpassade åtgärder</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Få djupare insikter i hälsa och prestanda för dina <strong>anpassade åtgärdsslutpunkter</strong> med en ny <strong>övervakningsinstrumentpanel</strong> och förbättrade <strong>händelsedata för kundsteg</strong>. Spåra lyckade samtal, fel, dataflöde, svarstider och väntetider för kön för att snabbt förstå när, var och varför avvikelser inträffar.</p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p>Mer information finns i den <a href="../action/reporting.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 3 februari 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Beslutsstöd i SMS-kanal</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Du kan nu anpassa och optimera innehållet i dina <strong>SMS-meddelanden</strong> med <strong>Beslutsfattande</strong>. Använd <strong>Prioritetsresultat</strong>, <strong>Formler</strong> eller <strong>AI-modeller</strong> för att visa det bästa innehållet för dina kunder.</p>
<p>Mer information finns i den <a href="../experience-decisioning/create-decision.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 2 februari 2026</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar {#feb-26-01-improv}

Förbättringar i den här versionen visas nedan.

#### Konfiguration

* **Upplev händelseanvändning i reseuttryck** - Från och med 1 april 2026 stöds inte längre användningen av upplevelsehändelseattribut i reseuttryck för organisationer som inte har använt den här funktionen de senaste 90 dagarna. Den här funktionen har redan varit otillgänglig för nya kundorganisationer sedan 8 juli 2025. Mer information finns i [Upplevelsesökning under resor](../building-journeys/exp-event-lookup.md).


* **Metoden för delegering av underdomäner** - Du kan nu växla från en delegeringsmetod för underdomäner till en annan. Detta gör att du kan migrera domäner med CNAME-delegeringsläget till den anpassade delegeringsmetoden för att följa företagets säkerhetsprofiler.

  **Obs!**: Den här funktionen är bara tillgänglig för en uppsättning organisationer (<strong>Begränsad tillgänglighet</strong>). Kontakta din Adobe-representant för att få åtkomst.


#### E-postdesigner

* **Använd ett varumärkestema för att konvertera en bild till en e-postmall** - När du konverterar en bild till en e-postmall i Journey Optimizer kan du nu använda ett tema som indata så att den genererade HTML följer dina varumärkesparametrar. Formatering som bakgrundsfärg, knappfärg, teckensnitt, radavstånd, marginaler och utfyllnad tillämpas automatiskt, vilket minskar det manuella arbetet och ger en mall som är klar att användas med minimala redigeringar.


* **Uppdatera varumärken med nya färgflikar** - Riktlinjer för varumärken hjälper dig att se till att ert varumärke presenteras på ett enhetligt sätt över alla kontaktytor. I det nya avsnittet Färger definieras standarderna för ert varumärkes färgsystem och de visar hur färger väljs, ordnas och används i olika upplevelser. Det säkerställer konsekvent användning av primära, sekundära, dekorativa och neutrala färger för att stödja en sammanhängande, tillgänglig och identifierbar varumärkesidentitet.


#### AI

* **Integrering av anpassade Firefly-modeller och tredjepartsmodeller för bildgenerering** - Möjliggör smidig integrering av Firefly-modeller och egna, tillsammans med godkända tredjepartsmodeller (t.ex. NanoBanana), för att ge större flexibilitet, kontroll och varumärkesjustering när bilder genereras. På så sätt kan du välja den bästa modellen för varje användningsfall: standardmodell för Firefly för allmänna behov, anpassad Firefly för varumärkesgenerering eller godkända tredjepartsmodeller för specialiserade eller experimentella scenarier.


#### Experience Decision

* **Stöd för inkommande trafik från Edge för användning av Adobe Experience Platform-data i beslut** - Om du använder Adobe Experience Platform-data i beslut stöds nu även kantinkommande användningsfall, förutom e-post och anpassade åtgärder på resor.

  **Obs!**: Den här funktionen är bara tillgänglig för en uppsättning organisationer (<strong>Begränsad tillgänglighet</strong>). Kontakta din Adobe-representant för att få åtkomst.


* **Förhandsgranskning av Experience Decisioning i den kodbaserade Experience Channel** - Du kan nu förhandsgranska beslutsobjekt när du konfigurerar Experience Decision med den kodbaserade Experience Channel. Förhandsgranskningen är tillgänglig direkt i redigeringsgränssnittet innan den publiceras.


* **Erbjud prioriterad AI-modellövervakning** - Med Journey Optimizer kan du nu övervaka hälsa, utbildningsstatus och prestanda för dina AI-modeller i beslutet, så att du kan verifiera att kursen har lyckats, felsöka fel och förstå hur resultatet påverkas. Den här funktionen är endast tillgänglig för personaliserade optimeringsmodeller (inte automatisk optimering).


* **Koppla fragment till beslutsobjekt** - Journey Optimizer kan nu koppla fragment till beslutsobjekt som kan utnyttjas i kodbaserade upplevelsekampanjer via beslutspolicyer.

  **Obs!**: Den här funktionen har tidigare släppts i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).

  Tillgänglighetsdatum: 12 februari 2026.


#### Resor

* **Flera inkommande åtgärder under resor** - För att förenkla din resesamordning kan du nu definiera flera inkommande åtgärder under en enskild resa. Den här funktionen, som tidigare fanns i kampanjer, gör att ni kan leverera flera kodbaserade upplevelser, meddelanden i appen, innehållskort eller webbåtgärder till olika platser samtidigt, och varje åtgärd innehåller specifikt innehåll.

  **Obs!**: Den här funktionen har tidigare släppts i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).


* **SMS-webbhooks** - <strong>Webbhooks</strong> stöds nu av alla SMS-providers. Du kan konfigurera varje webkrok baserat på dess avsedda syfte: <strong>Inkommande webhooks</strong> för att hämta inkommande meddelanden och <strong>Feedback-webhooks</strong> för att ta emot leveranskvitton, statusuppdateringar och andra meddelanderelaterade händelser. [Läs mer](../sms/sms-webhook.md)

  Tillgänglighetsdatum: 2 februari 2026.