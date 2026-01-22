---
solution: Journey Optimizer
product: journey optimizer
title: Förhandsanteckningar för Journey Optimizer
description: Adobe Journey Optimizer förhandsanteckningar
feature: Release Notes
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 86bd616a9331c5225c78ccf52c5d26a063fa8654
workflow-type: tm+mt
source-wordcount: '2080'
ht-degree: 1%

---

# Anteckningar före lanseringen {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och buggfixar. Alla ändringar konsolideras i slutet av varje månad i [releasenoterna](release-notes.md).


## Förhandsanteckningar för januari &#39;26 {#jan-26-01-rn}

**Förhandsanteckningarna nedan kan ändras utan föregående meddelande fram till releasedatumet**. Länkar, skärmar och uppdaterad dokumentation publiceras i versionsanteckningarna vid releasedatumet.

Se även [Adobe Experience Platform Pre-release anteckningar](https://experienceleague.adobe.com/sv/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.

**Releasedatum**: 26 januari 2026

### Nya möjligheter {#jan-26-01-features}

<table>
<thead>
<tr>
<th><strong>Handlingsaktivitet i resor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer stödjer en ny generisk <strong>Handlingsaktivitet</strong> som gör det möjligt att konfigurera både enskilda åtgärder och <strong>flerhandlingsgrupper för inkommande handlingar</strong>, vilket möjliggör en smidig åtgärdskonfiguration inom resduken. I synnerhet möjliggör denna nya funktion:</p>
<ul>
<li>En förenklad inhemsk handlingskonfiguration inom resduken.</li>
<li>Kapaciteten att skapa multiaktionsgrupper för inkommande insatser.</li>
<li>Möjligheten att lägga till optimering i vilken inbyggd kanalåtgärd som helst.</li>
<li>Möjligheten att lägga till både experimenterande och flerspråkiga alternativ till vilken handling som helst.</li>
</ul>
<p>Tidigare släppt i begränsad tillgänglighet, är denna funktion nu tillgänglig för alla miljöer (allmän tillgänglighet).</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Anpassad åtgärdsövervakning</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Få djupare insikt i hälsan och prestandan hos dina anpassade åtgärdsendpoints med en ny <strong>övervakningsdashboard</strong> och berikade händelsedata för journey step. Följ framgångsrika samtal, fel, genomströmning, svarstider och köväntetider för att snabbt förstå när, var och varför avvikelser uppstår.</p>
<p>Tidigare släppt i begränsad tillgänglighet, är denna funktion nu tillgänglig för alla miljöer (allmän tillgänglighet).</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Tysta tider / tidsbaserade undantag</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Tysta timmar låter dig definiera <strong>tidsbaserade undantag</strong> för e-post, SMS, Push och WhatsApp-kanaler. De säkerställer att inga meddelanden skickas under specifika tidsperioder, vilket hjälper dig att respektera kundpreferenser och efterlevnadskrav. Du kan tillämpa tysta timmar genom <strong>regeluppsättningar</strong>, som kan tilldelas individuella handlingar i kampanjer eller resor för exakt kontroll.</p>
<p>Tidigare släppt i begränsad tillgänglighet, är denna funktion nu tillgänglig i alla miljöer. Med denna General Availability-version inkluderar funktionen nu möjligheten för kunden att köa en kampanjåtgärd tills Quiet Hours är klara, samt möjligheten att förhandsgranska den aktiverade Quiet Hours-regeln.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Direktpostkanal i resor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Tidigare begränsad till kampanjer <strong>finns Direct Mail-kanalen</strong> nu tillgänglig på reseskärmen<strong></strong>, vilket gör det möjligt för dig att integrera Direct Mail i dina resor. Direktreklam kan nu användas både i batch- och 1:1-ressituationer, med stöd för filutvinningskonfiguration och tidsbaserade frekvensinställningar.</p>
<p>Tidigare släppt i begränsad tillgänglighet, är denna funktion nu tillgänglig för alla miljöer (allmän tillgänglighet).</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Webb push-notifikationskanal</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer stöder <strong>nu Web Push-notiser</strong> och utvidgar pushkanalen bortom mobil. Du kan sömlöst leverera notiser till både mobil- och desktopwebbläsare, vilket gör att du kan nå kunder direkt på deras enheter utan att behöva en app. Den här förbättringen gör att ni kan engagera användarna med rätt, personaliserade meddelanden i realtid, och utnyttja samma arbetsflöden och målgruppsfunktioner som redan finns för mobilpush.</p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Grundläggande RCS-meddelanden</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med det nya erbjudandet <strong>RCS Basic Basic-tillägg</strong> kan du nu leverera grundläggande RTCS-meddelanden (Rich Communication Services) i Journey Optimizer, vilket aktiverar följande förbättrade meddelandefunktioner beroende på leverantör och operatörssupport:</p>
<ul>
<li>Stöd för varumärken och verifierade avsändare: Skicka meddelanden med verifierade affärsprofiler med varumärkeselement (logotyp, avsändarnamn osv.).</li>
<li>Insikter om meddelandeleverans: Ta emot detaljerade leveransrapporter inklusive uppdateringar av meddelandestatus (t.ex. skickat, levererat, läst).</li>
<li>Länkspårning: Bädda in och spåra URL:er i RCS-meddelanden för engagemangsanalys.</li>
<li>Tillbakagång till SMS: Automatisk tillbakagång till SMS när profilens enhet inte stöder RCS eller tillfälligt är otillgänglig via RCS.</li>
<li>Grundläggande meddelandesammansättning: Skicka enkla textbaserade RCS-meddelanden.</li>
</ul>
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
<p>Denna funktion är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). För att få tillgång, kontakta din Adobe-representant.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Direktreklamkanal i orkestrerade kampanjer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Direktreklamkanalen finns nu tillgänglig i orkestrerade kampanjer. Direktmail-aktiviteten <strong></strong> underlättar direktutskick inom din orkestrerade kampanj, både för engångs- och återkommande meddelanden. Den fungerar för att automatisera processen att generera extraktionsfilen <strong></strong> som krävs av direktreklamleverantörer. Du kan kombinera kanalaktiviteter i den orkestrerade kampanjcanvasen för att skapa cross-channel-kampanjer som kan trigga åtgärder baserat på kundbeteende och data.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Anpassade formulär på landningssidan</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med Journey Optimizer kan du nu hämta <strong>profilattribut</strong> via dina landningssidor. Skapa, designa och hantera <strong>anpassade formulär</strong> som är anpassade efter dina behov utifrån en specifik datamängd. Du kan sedan använda dessa formulär på landningssidor för att lägga till de profilattribut du väljer i datauppsättningen som definieras för varje formulär.</p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
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
<p>Nya <strong>källanslutningar</strong> är nu tillgängliga i Adobe Experience Platform för lojalitetsapparna Talon.One, Capillary och Kobie. Dessa kopplingar låter dig sömlöst strömma lojalitetsdata till Adobe Experience Platform och utnyttja denna data i Journey Optimizer.</p>
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
<p>Det är nu möjligt att <strong>exportera skickade leveranser</strong> till en specifik datamängd för arkivering och efterlevnad. Denna kapacitet är tillgänglig inte bara för e-post, utan även andra kanaler som SMS. Datalagringen för meddelandeexportdataset är nu <strong>7 dagar</strong>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Nytt API för att hämta Action Campaigns</strong><br/></th>
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
<p>Tre nya <strong>resevarningar finns nu tillgängliga för att hjälpa dig att övervaka och följa livscykelhändelser</strong> och anpassad åtgärdsprestanda:</p>
<ul>
<li><strong>Journey Published</strong>: Ta emot notiser när en resa publiceras av en utövare i journey-canvasen.</li>
<li><strong>Resa avslutad</strong>: Få aviseringar när en resa är avslutad, med specifika definitioner baserade på restyp (läs målgrupp eller händelseutlöst).</li>
<li><strong>Anpassad åtgärdsbegränsning utlöst</strong>: Bli meddelad när begränsning aktiveras på en anpassad åtgärdsändpunkt.</li>
</ul>
<p>Dessa aviseringar kan prenumereras på organisationsnivå eller för specifika resor.</p>
<p>Mer information finns i den <a href="../reports/alerts.md#journey-alerts">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 5 november 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Teman i e-postdesignern</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Du kan nu snabbt använda <strong>förgodkända teman</strong> för att säkerställa varumärkets konsekvens i alla e-postmeddelanden, snabba upp din kampanjskapande och självständigt producera högkvalitativa mejl samtidigt som du minskar beroendet av designteam.</p>
<p>Tidigare släppt i betaversion, är denna funktion nu tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). För att få tillgång, kontakta din Adobe-representant.</p>
<img src="assets/do-not-localize/themes.gif">
<p>Mer information finns i den <a href="../email/apply-email-themes.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 5 november 2025</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar {#jan-26-01-improv}

Förbättringar som kommer med denna utgåva listas nedan.

#### AI

* **AI-assistentens kvalitetskontroller** av innehåll – Utöver varumärkesanpassning kan du nu utvärdera den övergripande <strong>innehållskvaliteten</strong> för att upptäcka potentiella problem med läsbarhet, sammanhållning och effektivitet, oberoende av dina varumärkesriktlinjer. Dessa automatiserade kontroller hjälper till att identifiera otydliga meddelanden, inkonsekvent ton eller strukturella luckor.
* **Uppdatera varumärken med ny färgflik** – Varumärkesriktlinjer hjälper till att säkerställa att ditt varumärke presenteras konsekvent över alla kontaktpunkter. Den nya <strong>sektionen</strong> Färger definierar standarderna för ditt varumärkes färgsystem och beskriver hur färger väljs, organiseras och appliceras över upplevelser. Det säkerställer konsekvent användning av primära, sekundära, accent- och neutrala färger för att stödja en sammanhållen, tillgänglig och igenkännbar varumärkesidentitet.

#### Kampanjer

* **Schemalägg kampanj med hjälp av profilens tidszon** – Kampanjschemaläggning kan nu använda varje profils <strong>tidszon</strong> för att leverera meddelanden vid avsedd lokal tid.

  **Observera**: Denna förbättring är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet).

#### Kanaler

* **SMS-webbhookar: Fas II** - Beskrivning kommer att följa.

* **WhatsApp Vidareförsäljningserbjudande** – Beskrivning kommer att tillhandahållas.

#### E-postdesigner

* **Korrigeringar på plats i E-postdesignern** – <strong>AI-drivna automatiska innehållsförslag</strong> finns nu tillgängliga i E-postdesignern när överträdelser upptäcks under innehållsvalideringen. Om innehåll flaggas som felaktigt i linje med varumärkesriktlinjer eller inte uppfyller kvalitetskriterierna, genererar systemet proaktivt korrigerade alternativ som kan granskas och tillämpas indirekt, vilket förbättrar efterlevnaden och påskyndar produktionen.

#### Erfarenhetsbeslut

* **Reseskiljeförfarande** - Nu kan du använda <strong>formler och AI-modeller</strong> för att automatiskt öka prioritetspoängen för resan baserat på kundprofilattribut och sammanhangsberoende faktorer, så att kunderna kommer in på de mest relevanta resorna.

  **Obs!**: Den här förbättringen är bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet).

* **dokumentation för verktyg för utökad sandlåda - uppdatering** - Beskrivning ska anges.

* **Självbetjäningsverktyg för migrering av verktyg-API:er** - En ny uppsättning <strong>migreringsverktyg-API:er</strong> finns tillgängliga för att migrera Offer Management-entiteter till Experience Decision. Verktygen möjliggör sömlös migrering mellan sandlådor med beroendelösning och rollback-funktioner.

* **Fäst fragment till beslutsobjekt** – Journey Optimizer ger nu möjlighet att koppla <strong>fragment</strong> till beslutsobjekt som kan användas i kodbaserade upplevelsekampanjer via beslutspolicys.

  **Notera**: Tidigare släppt i begränsad tillgänglighet, är denna förbättring nu tillgänglig för alla miljöer (allmän tillgänglighet).

#### Resor

* **Utnyttja en felrespons-payload i journey Custom Actions** – Du kan nu definiera en valfri <strong>felresponspayload</strong> för anpassade åtgärder. När ett anrop misslyckas exponeras felpayloaden i reskontexten och finns tillgänglig i timeout/error-grenen för att stödja rikare fallback-logik och felsökning.

* **Kombinera native och Adobe Campaigns meddelandeåtgärder** – Journey Optimizer låter dig nu kombinera Adobe Campaign v7/v8 meddelandeåtgärder med native kanalåtgärder i samma resa.

* **Validering av** nyttolaststorlek i resor – Journey Optimizer erbjuder <strong>nu validering</strong> av nyttolaststorlek för att säkerställa optimal prestanda och systemstabilitet. När du bygger eller publicerar resor får du tydliga varningar och fel om nyttolaststorlekar närmar sig eller överskrider rekommenderade gränser, tillsammans med handlingsbar vägledning för att optimera din resekonfiguration. Denna proaktiva validering hjälper dig att identifiera potentiella problem tidigt och bibehålla resans prestation.

* **Flera inkommande handlingar i resor** – För att förenkla din reseorkestrering kan du nu definiera <strong>flera inkommande handlingar</strong> i en och samma resa. Tidigare tillgänglig i kampanjer gör denna funktion det möjligt att leverera flera kodbaserade upplevelser, meddelanden i appen, innehållskort eller webbhandlingar till olika platser samtidigt, där varje åtgärd innehåller ett specifikt innehåll.

  **Notera**: Tidigare släppt i begränsad tillgänglighet, är denna förbättring nu tillgänglig för alla miljöer (allmän tillgänglighet).

#### Orkestrerade kampanjer

* **Välj attribut och kopiera distributionsvärden** – Du kan nu välja eller kopiera värden direkt från fördelningsvyn i orkestrerade kampanjer.

* **Etikettarv för dataanvändning för målgrupper** - <strong>Etiketter för dataanvändning</strong> som används i Adobe Experience Platform överförs nu automatiskt när målgrupper sparas i orkestrerade kampanjer, vilket minskar den manuella DULE-taggningen.

* **Fördefinierade återmarknadsföringsfilter** - Den här versionen innehåller nya <strong>återmarknadsföringsfilter</strong> som stöd för enklare återmarknadsföring för samordnade kampanjanvändningsfall. Med dessa filter kan ni rikta in er direkt på målgrupper baserat på meddelandeengagemang, som t.ex. skickat, öppnat, klickat eller öppnat och klickat, och välja den kampanj eller kampanj i övergången som du vill rikta om.

* **Fördefinierade filter med parametrar** - Nu kan du skapa <strong>filter med parametrar</strong> i samordnade kampanjer för återanvändbara, redigerbara regler.

* **Meddelandebekräftelse före sändning** - Ett <strong>bekräftelsesteg</strong> är nu aktiverat som standard innan orkestrerade kampanjer skickas för att minska antalet oavsiktliga sändningar.

* **Användargenererat metadatastöd** - Hjälpfunktionen <strong>executionMetadata</strong> är nu tillgänglig i personaliseringsredigeraren för Orchestrated Campaigns, så att du kan bifoga kontextinformation till alla interna åtgärder och lagra den i en datauppsättning för export till externa system.

* **Starta om** knappen – Orkestrerade kampanjer inkluderar nu en <strong>omstart-knapp</strong> så att du snabbt kan starta om omgångar vid behov innan kampanjen publiceras.

* **Stöd** för priskontroll – Orkestrerade kampanjer stödjer <strong>nu priskontroll</strong> för att hjälpa dig att anpassa leveranserna och anpassa dem till volymbegränsningar.

#### Behörigheter

* **Förhindra självgodkännande för resor och kampanjer** – Du kan nu kräva att skapare inte får godkänna sina egna resor eller kampanjer, vilket förbättrar <strong>ansvarsfördelningen</strong> i godkännandeflödena.

## Kommer snart {#jan-26-01-coming-soon}

Följande funktioner och förbättringar planeras släppas under de närmaste dagarna. **Informationen kan komma att ändras**. Uppdaterade länkar, skärmar och dokumentation kommer att delas när dessa uppdateringar är i produktion.

<table>
<thead>
<tr>
<th><strong>Innehållsgenerering inom Journey Agent</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Drivet av Adobe Experience Platform Agent Orchestrator <strong>finns Journey Agent</strong> tillgängligt i Journey Optimizer och gör det möjligt för dig att analysera resor via ett naturligt språkgränssnitt. Du kan nu också generera och hantera kanalspecifikt innehåll direkt i Journey Agent, skapa innehåll för kanaler som e-post och push, tillämpa och förhandsgranska mallar, förfina ton och stil genom prompts samt öppna innehåll i Content Designer för redigering i kontext.</p>
<p>Tillgänglighetsdatum: 2 februari 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Innehållsbeslutsaktivitet</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Du kan nu inkludera <strong>personliga erbjudanden</strong> i dina resor genom en dedikerad innehållsbeslutsaktivitet i reseskärmen, och använda dem i resaktiviteter, inklusive villkor och anpassade åtgärder.</p>
<p>Tillgänglighetsdatum: 2 februari 2026</p>
</td>
</tr>
</tbody>
</table>
