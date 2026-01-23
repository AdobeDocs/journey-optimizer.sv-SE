---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
topic: Content Management
description: Versionsinformation om Adobe Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 789bae8373dda34cd132ea7abffea37f002dbc50
workflow-type: tm+mt
source-wordcount: '2051'
ht-degree: 2%

---

# Versionsinformation {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="Nyheter?"
>abstract="**Adobe Journey Optimizer** levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen."

[!DNL Adobe Journey Optimizer] följer en kontinuerlig leveransmodell som gör att Adobe kan leverera nya funktioner, förbättringar och korrigeringar kontinuerligt. Detta tillvägagångssätt möjliggör en skalbar, fasad driftsättning av funktioner för att säkerställa prestanda och stabilitet i alla miljöer.

På grund av den här modellen uppdateras versionsinformationen mellan månadsversionerna. Fullständig information om frisläppningscykeln och tillgänglighetsfaserna finns i [Journey Optimizer versionscykel](releases.md).

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver från de senaste innovationerna och förbättringarna. Läs mer om de här ändringarna i [Adobe Experience Platform versionsinformation](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=sv-SE){target="_blank"}.

## Versionsinformation januari 26 {#latest-rn}

**Releasedatum**: 27 januari 2026

Versionsinformationen är förhandsversion och kan ändras fram till releasedatum. Länkar, skärmar och uppdaterad dokumentation publiceras i versionsinformationen på releasedatum.

### Nya funktioner {#jan-26-01-features}

<table>
<thead>
<tr>
<th><strong>Verksamhet under resor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer har stöd för en ny generisk <strong>åtgärdsaktivitet</strong> som gör att du kan konfigurera både enskilda åtgärder och <strong>flera inkommande åtgärdsgrupper</strong>, vilket ger en smidig åtgärdskonfiguration på arbetsytan. Den här nya funktionen gör det möjligt att:</p>
<ul>
<li>En förenklad inbyggd åtgärdskonfiguration på arbetsytan för resan.</li>
<li>Kapaciteten för att skapa inkommande åtgärdsgrupper med flera åtgärder.</li>
<li>Möjlighet att lägga till optimering till alla inbyggda kanalåtgärder.</li>
<li>Möjlighet att lägga till både experimentella och flerspråkiga alternativ i alla funktionsmakron.</li>
</ul>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
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
<p>Få djupare insikter i hälsa och prestanda för dina anpassade åtgärdsslutpunkter med en ny <strong>kontrollpanel</strong> och förbättrade händelsedata för kundsteg. Spåra lyckade samtal, fel, dataflöde, svarstider och väntetider för kön för att snabbt förstå när, var och varför avvikelser inträffar.</p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Tysta timmar/tidsbaserade undantag</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med tysta timmar kan du definiera <strong>tidsbaserade undantag</strong> för kanalerna Email, SMS, Push och WhatsApp. De ser till att inga meddelanden skickas under särskilda tidsperioder och hjälper er att följa kundönskemål och krav på regelefterlevnad. Du kan använda tysta timmar genom <strong>regeluppsättningar</strong>, som kan tilldelas enskilda åtgärder i kampanjer eller resor för exakt kontroll.</p>
<p><strong>Obs!</strong>: Tysta timmar stöds inte för Orchestrated-kampanjer.</p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer. I den här allmänna tillgänglighetsversionen inkluderar funktionen nu möjligheten för kunden att ställa en kampanjåtgärd i kö tills tysta timmar har slutförts och möjligheten att förhandsgranska den aktiverade regeln Tysta timmar.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Direktreklam, kanal på resor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Tidigare begränsad till Campaigns är nu <strong>Direct Mail-kanalen</strong> tillgänglig på <strong>arbetsytan för resan</strong>, vilket gör att du kan infoga Direct Mail i dina resor. Direktreklam kan nu användas i både batch- och 1:1-resscenarier, med stöd för filextraheringskonfiguration och tidsbaserade frekvensinställningar.</p>
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
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Beslutsstöd i Push- och SMS-kanaler</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Du kan nu lägga till <strong>beslutsprinciper</strong> i push- och SMS-resor och -kampanjer. Beslutspolicyer är behållare för era erbjudanden som utnyttjar beslutsmotorn för att dynamiskt returnera det bästa innehållet för varje målgruppsmedlem.</p>
<p>Den här funktionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Direktreklamkanal i samordnade kampanjer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Direktreklamkanalen finns nu tillgänglig i samordnade kampanjer. <strong>Direkte-postaktiviteten</strong> gör det lättare att skicka direktreklam i din samordnade kampanj, både för engångs- och återkommande meddelanden. Den används för att automatisera processen att generera den <strong>extraheringsfil</strong> som krävs av direktmeddelandeleverantörer. Ni kan kombinera kanalaktiviteter i den orkestrerade kampanjarbetsytan för att skapa flerkanalskampanjer som kan utlösa åtgärder baserat på kundbeteende och data.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Nya källkopplingar för lojalitetsappar</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nya <strong>källanslutningar</strong> är nu tillgängliga i Adobe Experience Platform för lojalitetsapparna Talon.One, Capillary och Kobie. Med dessa kopplingar kan ni smidigt strömma lojalitetsdata till Adobe Experience Platform och utnyttja dessa data i Journey Optimizer.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Meddelandeexport</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>En ny <strong>meddelandeexportfunktion</strong> är nu tillgänglig för e-post- och SMS-kanaler. Med den här funktionen kan du automatiskt exportera skickat meddelandeinnehåll till en dedikerad Experience Platform-datauppsättning, vilket gör att du kan:</p>
<ul>
<li>Uppfyll formella krav (t.ex. HIPAA)</li>
<li>Arkivera meddelanden om juridiska anspråk och kundvårdsfrågor</li>
<li>Bevara kopior av personaliserat innehåll som skickas till enskilda personer</li>
</ul>
<p>Poster sparas i datauppsättningen för export av AJO-meddelanden i <strong>7 kalenderdagar från att användaren har fått det </strong>. Under den här kvarhållningsperioden kan du exportera data till din egen lagring via Experience Platform destinationer. Funktionen är aktiverad på kanalkonfigurationsnivå, vilket ger dig detaljkontroll över vilka meddelanden som exporteras.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Journey Agent - Skapa en resa</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med Journey Create Agent kan Journey Optimizer-användare skapa och konfigurera marknadsföringsresor med ett naturligt språkgränssnitt. Med Journey Create Agent kan man snabbt skapa resor genom att beskriva kraven i samtal. Agenten effektiviserar framtagningen av resor så att marknadsförarna kan fokusera på strategi istället för teknisk konfiguration.</p>
<p><a href="https://experienceleague.adobe.com/sv/docs/experience-cloud-ai/experience-cloud-ai/agents/ajo-agent#journey-create-agent-skill-overview-and-user-guide" target="_blank">Läs mer</a></p>
<p>Tillgänglighetsdatum: 12 januari 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Nytt API för att hämta åtgärdskampanjer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Det finns nu ett nytt <strong>Journey Optimizer API</strong> som gör att du kan hämta och inspektera kampanjrelaterade data programmatiskt, till exempel information, versioner och konfigurationer.</p>
<p>Mer information finns i den <a href="https://developer.adobe.com/journey-optimizer-apis/references/campaigns-retrieve/">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 24 november 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Nya resevarningar</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Det finns nu tre nya <strong>resevarningar</strong> som hjälper dig att övervaka och spåra händelser i reselivscykler och anpassade åtgärder:</p>
<ul>
<li><strong>Resa publicerad</strong>: Få meddelanden när en resa publiceras av en behandlare på arbetsytan.</li>
<li><strong>Resan har slutförts</strong>: Få aviseringar när en resa har slutförts, med specifika definitioner baserade på resetyp (läsning eller händelseutlösta).</li>
<li><strong>Anpassad åtgärdsbegränsning utlöstes</strong>: meddelas när appning aktiveras för en anpassad åtgärdsslutpunkt.</li>
</ul>
<p>Dessa registreringar kan prenumereras på på organisationsnivå eller för specifika resor.</p>
<p>Mer information finns i den <a href="../reports/alerts.md#journey-alerts">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 5 november 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Teman i e-post-Designer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du snabbt tillämpa <strong>förgodkända teman</strong> för att säkerställa att alla e-postmeddelanden är enhetliga, snabba upp kampanjprocessen och oberoende producera högkvalitativa e-postmeddelanden samtidigt som du minskar beroendet av designteam.</p>
<p>Tidigare släppt i betaversion är den här funktionen nu tillgänglig för ett antal organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
<img src="assets/do-not-localize/themes.gif">
<p>Mer information finns i den <a href="../email/apply-email-themes.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 5 november 2025</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar {#jan-26-01-improv}

Förbättringar i den här versionen visas nedan.

#### AI

* **Kvalitetskontroller för AI-assistentinnehåll** - Förutom varumärkesjustering kan du nu utvärdera den övergripande <strong>innehållskvaliteten</strong> för att identifiera potentiella problem med läsbarhet, kohesivitet och effektivitet, oberoende av varumärkesriktlinjerna. Dessa automatiska kontroller hjälper till att identifiera otydliga meddelanden, inkonsekventa toner och strukturella luckor.

* **Uppdatera varumärken med nya färgflikar** - Riktlinjer för varumärken hjälper dig att se till att ert varumärke presenteras på ett enhetligt sätt över alla kontaktytor. I det nya avsnittet <strong>Färger</strong> definieras standarderna för ditt varumärkes färgsystem, som visar hur färger väljs, ordnas och används i olika upplevelser. Det säkerställer konsekvent användning av primära, sekundära, dekorativa och neutrala färger för att stödja en sammanhängande, tillgänglig och identifierbar varumärkesidentitet.

#### Kampanjer

* **Schemalägg kampanj med profiltidszon** - Kampanjplanering kan nu använda varje profils <strong>tidszon</strong> för att leverera meddelanden vid den avsedda lokala tidpunkten.

  **Obs!**: Den här förbättringen är bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet).

#### Kanaler

* **SMS-webbhooks: Fas II** - Beskrivning ska anges.

#### E-postdesigner

* **Korrigeringar på plats i e-postdesignern** - När du hanterar innehåll med din varumärkesriktlinje är <strong>AI-baserade automatiska innehållsförslag</strong> nu tillgängliga när fel upptäcks under innehållsvalideringen. Om innehållet markeras som felanpassat med riktlinjer för varumärket eller inte uppfyller kvalitetskriterierna genererar systemet proaktivt korrigerade alternativ som kan granskas och tillämpas internt, vilket förbättrar regelefterlevnaden och snabbar upp produktionen.

#### Experience Decision

* **Självbetjäningsverktyg för migrering av verktyg-API:er** - En ny uppsättning <strong>migreringsverktyg-API:er</strong> finns tillgängliga för att migrera Offer Management-entiteter till Experience Decision. Verktyget möjliggör sömlös migrering mellan sandlådor med beroendeupplösning och återställningsfunktioner.

* **Koppla fragment till beslutsobjekt** - Journey Optimizer kan nu koppla <strong>fragment</strong> till beslutsobjekt som kan utnyttjas i kodbaserade upplevelsekampanjer via beslutsprinciper.

  **Obs!**: Den här förbättringen har tidigare släppts i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).

#### Resor

* **Utnyttja nyttolasten för felsvar i kundresan med anpassade åtgärder** - Du kan nu definiera en valfri <strong>felsvarsnyttolast</strong> för anpassade åtgärder. När ett anrop misslyckas visas felnyttolasten i resekontexten och är tillgänglig i timeout/error-grenen för att stödja mer omfattande reservlogik och felsökning.

* **Kombinera inbyggda meddelandeåtgärder och Adobe Campaign-meddelandeåtgärder** - Med Journey Optimizer kan du nu kombinera Adobe Campaign v7/v8-meddelandeåtgärder med inbyggda kanalåtgärder på samma resa.

* **Verifiering av nyttolastens storlek på resan** - Journey Optimizer tillhandahåller nu validering av <strong>nyttolastens storlek</strong> för att säkerställa optimala prestanda och systemstabilitet. När du bygger eller publicerar resor får du tydliga varningar och fel om nyttolasterna närmar sig eller överskrider de rekommenderade gränserna, tillsammans med användbar vägledning för att optimera kundresans konfiguration. Denna proaktiva validering hjälper er att identifiera potentiella problem tidigt och att upprätthålla kundresan.

* **Flera inkommande åtgärder på resor** - För att förenkla kundresan kan du nu definiera <strong>flera inkommande åtgärder</strong> på en enskild resa. Den här funktionen, som tidigare fanns i kampanjer, gör att ni kan leverera flera kodbaserade upplevelser, meddelanden i appen, innehållskort eller webbåtgärder till olika platser samtidigt, och varje åtgärd innehåller ett visst innehåll.

  **Obs!**: Den här förbättringen har tidigare släppts i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).

#### Samordnade kampanjer

* **Välj attribut och kopiera distributionsvärden** - Nu kan du välja eller kopiera värden direkt från värdedistributionen i samordnade kampanjer.

* **Etikettarv för dataanvändning för målgrupper** - <strong>Etiketter för dataanvändning</strong> som används i Adobe Experience Platform överförs nu automatiskt när målgrupper sparas i orkestrerade kampanjer, vilket minskar den manuella DULE-taggningen.

* **Fördefinierade återmarknadsföringsfilter** - Den här versionen innehåller nya <strong>återmarknadsföringsfilter</strong> som stöd för enklare återmarknadsföring för samordnade kampanjanvändningsfall. Med dessa filter kan ni rikta in er direkt på målgrupper baserat på meddelandeengagemang, som t.ex. skickat, öppnat, klickat eller öppnat och klickat, och välja den kampanj eller kampanj i övergången som du vill rikta om.

* **Fördefinierade filter med parametrar** - Nu kan du skapa <strong>filter med parametrar</strong> i samordnade kampanjer för återanvändbara, redigerbara regler.

* **Meddelandebekräftelse före sändning** - Ett <strong>bekräftelsesteg</strong> är nu aktiverat som standard innan orkestrerade kampanjer skickas för att minska antalet oavsiktliga sändningar.

* **Användargenererat metadatastöd** - Hjälpfunktionen <strong>executionMetadata</strong> är nu tillgänglig i personaliseringsredigeraren för Orchestrated Campaigns, så att du kan bifoga kontextinformation till alla interna åtgärder och lagra den i en datauppsättning för export till externa system.

* **Starta om-knapp** - Orchestrerade-kampanjer innehåller nu en <strong>omstartsknapp</strong> så att du snabbt kan starta om kampanjer när det behövs innan kampanjen publiceras.

* **Stöd för hastighetskontroll** - Orchestrerade kampanjer har nu stöd för <strong>hastighetskontroll</strong> som hjälper dig att jämna ut leveranser och anpassa dig till volymbegränsningar.

#### Behörigheter

* **Förhindra självgodkännande för resor och kampanjer** - Nu kan du kräva att skapare inte kan godkänna sina egna resor eller kampanjer, vilket förbättrar <strong>ansvarsfördelningen</strong> i arbetsflöden för godkännande.

## Kommer snart {#jan-26-01-coming-soon}

Följande funktioner och förbättringar planeras släppas under de närmaste dagarna. **Informationen kan komma att ändras**. Uppdaterade länkar, skärmar och dokumentation delas när uppdateringarna är klara.

<table>
<thead>
<tr>
<th><strong>Generering av innehåll i Journey Agent</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>Journey Agent</strong>, som drivs av Adobe Experience Platform Agent Orchestrator, finns i Journey Optimizer och gör att du kan analysera resor via ett naturligt språkgränssnitt. Nu kan du även generera och hantera kanalspecifikt innehåll direkt i Journey Agent, skapa innehåll för kanaler som e-post och push, tillämpa och förhandsgranska mallar, förfina ton och stil genom uppmaningar och öppna innehåll i Content Designer för kontextredigering.</p>
<p>Tillgänglighetsdatum: 2 februari 2026</p>
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
<p>Du kan nu inkludera <strong>personaliserade erbjudanden</strong> på dina resor via en dedikerad innehållsbeslutsaktivitet på arbetsytan och använda dem i reseaktiviteter, inklusive villkor och anpassade åtgärder.</p>
<p>Tillgänglighetsdatum: 3 februari 2026</p>
</td>
</tr>
</tbody>
</table>
