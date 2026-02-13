---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
role: User
level: Beginner, Intermediate
description: Versionsinformation om Adobe Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: b53c28405e453be3767f05e2c7a7a1b2e69d0416
workflow-type: tm+mt
source-wordcount: '1537'
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

## Versionsinformation 26 februari {#feb-26-01-rn}

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
<li>Bättre <strong>slutbarhet</strong> - Spridet skickar över tid för att bevara ett starkt <strong>avsändarrykte</strong> och minska risken för att flaggas som skräppost.</li>
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
<p>Nu kan du använda <strong>formler</strong> och <strong>AI-modeller</strong> för att automatiskt öka prioritetspoängen för <strong>resor</strong> baserat på kundprofilattribut och sammanhangsberoende faktorer, så att kunderna kommer in på de mest relevanta resorna.</p>
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
<p><strong>Adobe Experience Platform Agent Orchestrator</strong>, <strong>Journey Agent</strong> är tillgängligt i Journey Optimizer och gör att du kan analysera resor via ett <strong>naturligt språkgränssnitt</strong>. Nu kan du även generera och hantera kanalspecifikt innehåll direkt i Journey Agent, skapa innehåll för kanaler som e-post och push, tillämpa och förhandsgranska mallar, förfina ton och stil genom uppmaningar och öppna innehåll i <strong>Content Designer</strong> för kontextredigering.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Mobile Live-aktiviteter</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>Live Activity</strong> innehåller <strong>realtidsuppdateringar</strong> och interaktiva upplevelser i mobilappar, vilket gör att användare kan hålla sig informerade om pågående händelser eller uppgifter direkt på enhetens skärm. Den här funktionen förbättrar engagemanget genom att leverera live-information, som förloppsspårning, händelseuppdateringar eller interaktivt innehåll, utan att användarna behöver öppna appen.</p>
<p>Den här funktionen släpptes tidigare i betaversionen och är nu tillgänglig i alla miljöer (<strong>Allmän tillgänglighet</strong>).</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Verksamhet under resor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer har stöd för en ny generisk <strong>åtgärdsaktivitet</strong> som gör att du kan konfigurera både enskilda åtgärder och <strong>flera inkommande åtgärdsgrupper</strong>, vilket möjliggör en smidig åtgärdskonfiguration på <strong>arbetsytan </strong>. Den här nya funktionen gör det möjligt att:</p>
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
<p>Adobe Journey Optimizer har nu stöd för <strong>Web Push-meddelanden</strong>, vilket gör att push-kanalen kan användas även utanför mobila enheter. Ni kan smidigt leverera meddelanden till både webbläsare för mobiler och datorer, så att ni kan nå kunder direkt på deras enheter utan att behöva använda en app. Den här förbättringen gör att du kan engagera användare med rätt, personaliserade meddelanden i realtid och utnyttja samma <strong>redigeringsarbetsflöden</strong> och <strong>målinriktningsfunktioner</strong> som redan finns för mobilpush.</p>
<p>Den här funktionen släpptes tidigare i betaversionen och är nu tillgänglig i alla miljöer (<strong>Allmän tillgänglighet</strong>).</p>
<p>Tillgänglighetsdatum: 13 februari 2026</p>
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
<p>En ny <strong>aktivitet för innehållsbeslut</strong> finns nu tillgänglig på <strong>arbetsytan </strong> för att integrera <strong>personaliserade erbjudanden</strong> direkt i kundresorna. Med den här aktiviteten kan ni leverera beslutsbaserat innehåll och hänvisa till dessa erbjudanden under hela kundresan, under villkor för att skapa kvalificeringsbaserade förgreningar, i anpassade åtgärder för att skicka erbjudandedata till externa system och i andra aktiviteter för att skapa helt personaliserade kundupplevelser.</p>
<p>Den här funktionen släpptes tidigare i Begränsad tillgänglighet och är nu tillgänglig i alla miljöer (<strong>Allmän tillgänglighet</strong>).</p>
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
<p>Den här funktionen släpptes tidigare i Begränsad tillgänglighet och är nu tillgänglig i alla miljöer (<strong>Allmän tillgänglighet</strong>).</p>
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


* **Metoden för delegering av underdomäner** - Nu kan du växla från en <strong>delegeringsmetod för underdomäner</strong> till en annan. Detta gör att du kan migrera domäner med läget <strong>CNAME-delegering</strong> till metoden <strong>anpassad delegering</strong> för att följa företagets säkerhetsprofiler.

  **Obs!**: Den här funktionen är bara tillgänglig för en uppsättning organisationer (<strong>Begränsad tillgänglighet</strong>). Kontakta din Adobe-representant för att få åtkomst.


#### E-postdesigner

* **Använd ett varumärkestema för att konvertera en bild till en e-postmall** - När du konverterar en bild till en e-postmall i Journey Optimizer kan du nu använda ett <strong>tema</strong> som indata så att den genererade HTML följer dina <strong>varumärkesparametrar</strong>. Formatering som bakgrundsfärg, knappfärg, teckensnitt, radavstånd, marginaler och utfyllnad tillämpas automatiskt, vilket minskar det manuella arbetet och ger en mall som är klar att användas med minimala redigeringar.


* **Uppdatera varumärken med nya färgflikar** - <strong>Varumärkesriktlinjer</strong> hjälper till att säkerställa att ert varumärke presenteras på ett enhetligt sätt i alla kontaktytor. I det nya avsnittet <strong>Färger</strong> definieras standarderna för ditt varumärkes färgsystem, som visar hur färger väljs, ordnas och används i olika upplevelser. Det säkerställer konsekvent användning av primära, sekundära, dekorativa och neutrala färger för att stödja en sammanhängande, tillgänglig och identifierbar varumärkesidentitet.


#### AI

* **Integrering av anpassade Firefly-modeller och tredjepartsmodeller för bildgenerering** - Aktivera sömlös integrering av standardmodeller och anpassade <strong>Firefly-modeller</strong>, tillsammans med godkända <strong>tredjepartsmodeller</strong> (t.ex. NanoBanana), för att ge större flexibilitet, kontroll och varumärkesjustering när bilder genereras. På så sätt kan du välja den bästa modellen för varje användningsfall: standardmodell för Firefly för allmänna behov, anpassad Firefly för varumärkesgenerering eller godkända tredjepartsmodeller för specialiserade eller experimentella scenarier.


#### Experience Decision

* **Edge inkommande stöd för användning av Adobe Experience Platform-data i beslut** - Beslutsstöd för <strong>Experience Platform-datasökning</strong> inkluderar nu <strong>edge inkommande</strong> kanalanvändning. Funktionen är fortfarande begränsad. Allmän tillgänglighet för den underliggande datasökningsfunktionen är ännu inte annonserad (AEP/produktberoende).

  **Obs!**: Den här funktionen är bara tillgänglig för en uppsättning organisationer (<strong>Begränsad tillgänglighet</strong>). Kontakta din Adobe-representant för att få åtkomst.


* **Förhandsgranskning av Experience Decisioning i den kodbaserade upplevelsekanalen** - Du kan nu förhandsgranska <strong>beslutsobjekt</strong> när du konfigurerar <strong>Experience Decisioning</strong> med den <strong>kodbaserade upplevelsen</strong> . Förhandsgranskningen är tillgänglig direkt i redigeringsgränssnittet innan den publiceras.


* **Erbjud prioriterad AI-modellövervakning** - Med Journey Optimizer kan du nu övervaka <strong>hälsa</strong>, <strong>utbildningsstatus</strong> och <strong>prestanda</strong> i dina <strong>AI-modeller</strong> i ditt beslut, så att du kan kontrollera om kursen lyckades, felsöka och förstå hur resultatet blir. Den här funktionen är endast tillgänglig för personaliserade optimeringsmodeller (inte automatisk optimering).


* **Koppla fragment till beslutsobjekt** - Journey Optimizer kan nu koppla <strong>fragment</strong> till <strong>beslutsobjekt</strong> som kan utnyttjas i kodbaserade upplevelsekampanjer via <strong>beslutspolicyer</strong>.

  **Obs!**: Den här funktionen har tidigare släppts i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).

  Tillgänglighetsdatum: 12 februari 2026.


#### Resor

* **Flera inkommande åtgärder på resor** - För att förenkla din resesamordning kan du nu definiera flera <strong>inkommande åtgärder</strong> under en enskild resa. Den här funktionen, som tidigare fanns i kampanjer, gör att du kan leverera flera <strong>kodbaserade upplevelser</strong>, <strong> meddelanden i appen</strong>, <strong>innehållskort</strong> eller <strong>webbåtgärder</strong> till olika platser samtidigt, och varje åtgärd innehåller specifikt innehåll.

  **Obs!**: Den här funktionen har tidigare släppts i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).


* **SMS-webbhooks** - <strong>Webbhooks</strong> stöds nu av alla SMS-providers. Du kan konfigurera varje webkrok baserat på dess avsedda syfte: <strong>Inkommande webhooks</strong> för att hämta inkommande meddelanden och <strong>Feedback-webhooks</strong> för att ta emot leveranskvitton, statusuppdateringar och andra meddelanderelaterade händelser. [Läs mer](../sms/sms-webhook.md)

  Tillgänglighetsdatum: 2 februari 2026.