---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
role: User
level: Beginner, Intermediate
description: Versionsinformation om Adobe Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: aa66cc14a9d10df066f91403ed072cb95eebaa8f
workflow-type: tm+mt
source-wordcount: '1863'
ht-degree: 4%

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

**Releasedatum**: 27-28 januari 2026

Avsnitten [Funktioner](#jan-26-01-features) och [Förbättringar](#jan-26-01-improv) omfattar funktioner som redan är tillgängliga, medan [Kommer snart](#jan-26-01-coming-soon) listar objekt som är schemalagda för ett senare tillgänglighetsdatum.

<!-- **The pre-release notes below are subject to change without prior notice until the release availability date**. Links, screens and updated documentation are published in the release notes, at the release date. 

See also [Adobe Experience Platform Pre-release notes](https://experienceleague.adobe.com/sv/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.-->

### Nya funktioner {#jan-26-01-features}

<table>
<thead>
<tr>
<th><strong>Journey Agent - Skapa en resa</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Agent har nu funktioner för att skapa, vilket gör det möjligt för Journey Optimizer-användare att skapa och konfigurera marknadsföringsresor via ett <strong>naturligt språkgränssnitt</strong>. Praktikanter kan snabbt skapa resor genom att beskriva sina krav på samtal. Detta effektiviserar processen att skapa kundresan, så att marknadsförarna kan fokusera på strategi snarare än teknisk konfiguration.</p>
<p>Mer information finns i den <a href="../start/ai-features.md#journey-agent">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 12 januari 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>API för hämtning av åtgärdskampanj</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med ett nytt API kan ni hämta åtgärdskampanjer och filtrera dem efter nyckelattribut för att stödja automatisering och rapporteringsarbetsflöden.</p>
<p>Mer information finns i den <a href="https://developer.adobe.com/journey-optimizer-apis/references/campaigns-retrieve/" target="_blank">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 24 november 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Resevarningar</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nya varningsmeddelanden om resan hjälper dig att övervaka viktiga hälsosignaler för resan. I den här versionen introduceras varningstyper för antal ignorerade profiler, felfrekvens för anpassade åtgärder och felfrekvens för profiler, tillsammans med konfigurerbara tröskelvärden och prenumerationer på varningar på resenivå från kundinventeringen.</p>
<p>Tröskelvärdena är globala över alla resor.</p>
<p>Mer information finns i den <a href="../reports/alerts.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 14 oktober 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Skicka e-post till Designer-teman</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Använd enhetlig formatering i e-post-Designer med återanvändbara teman när du skapar e-postinnehåll.</p>
<p><img src="assets/do-not-localize/themes.gif"/></p>
<p>Mer information finns i den <a href="../email/apply-email-themes.md">detaljerade dokumentationen</a>.</p>
<p>Den här funktionen är tillgänglig i begränsad tillgänglighet för en uppsättning organisationer. Kontakta Adobe.</p>
<p>Tillgänglighetsdatum: 5 november 2025</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar {#jan-26-01-improv}

#### Experience Decision

* **Koppla fragment till beslutsobjekt** - Journey Optimizer kan nu koppla <strong>fragment</strong> till beslutsobjekt, som kan utnyttjas i kodbaserade upplevelsekampanjer via beslutsprinciper. [Läs mer](../experience-decisioning/items.md)

  **Obs!**: Den här förbättringen har tidigare släppts i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).

#### Resor

* **Utnyttja nyttolasten för felsvar i kundresan med anpassade åtgärder** - Du kan nu definiera en valfri <strong>felsvarsnyttolast</strong> för anpassade åtgärder. När ett anrop misslyckas visas felnyttolasten i kundresans kontext och är tillgänglig i timeout/error-grenen, tillsammans med `jo_status_code`, som stöd för större reservlogik och felsökning. [Läs mer](../action/action-response.md)

* **Kombinera inbyggda meddelandeåtgärder och Adobe Campaign-meddelandeåtgärder** - Med Journey Optimizer kan du nu kombinera Adobe Campaign v7/v8-meddelandeåtgärder med inbyggda kanalåtgärder på samma resa. [Läs mer](../building-journeys/using-adobe-campaign-v7-v8.md)

* **Verifiering av nyttolastens storlek på resan** - Journey Optimizer validerar nu kundens nyttolaststorlekar för att säkerställa optimala prestanda och systemstabilitet. När du bygger eller publicerar resor får du tydliga varningar och fel om nyttolasterna närmar sig eller överskrider de rekommenderade gränserna, tillsammans med användbar vägledning för att optimera kundresans konfiguration. Denna proaktiva validering hjälper er att identifiera potentiella problem tidigt och att upprätthålla kundresan. [Läs mer](../start/guardrails.md#message-content-size)

#### Samordnade kampanjer

* **Välj attribut och kopiera distributionsvärden** - Nu kan du välja eller kopiera värden direkt från värdedistributionen i samordnade kampanjer. [Läs mer](../orchestrated/orchestrated-rule-builder.md)

* **Etikettarv för dataanvändning för målgrupper** - Etiketter som används i Adobe Experience Platform överförs nu automatiskt när målgrupper sparas i orkestrerade kampanjer, vilket minskar den manuella DULE-taggningen. [Läs mer](../orchestrated/activities/save-audience.md)

* **Fördefinierade återmarknadsföringsfilter** - Den här versionen innehåller nya <strong>filter för kampanjåterkoppling</strong> som stöd för enklare återmarknadsföring för samordnade kampanjanvändningsfall. Med dessa filter kan ni rikta in er direkt på målgrupper baserat på meddelandeengagemang, som t.ex. skickat, öppnat, klickat eller öppnat och klickat, och välja den kampanj eller kampanj i övergången som du vill rikta om. [Läs mer](../orchestrated/retarget.md)

* **Fördefinierade filter med parametrar** - Nu kan du skapa fördefinierade filter med <strong>parametrar</strong> i samordnade kampanjer för återanvändbara, redigerbara regler. [Läs mer](../orchestrated/predefined-filters.md)

* **Meddelandebekräftelse före sändning** - Ett <strong>bekräftelsesteg</strong> är nu aktiverat som standard innan orkestrerade kampanjer skickas för att minska antalet oavsiktliga sändningar. [Läs mer](../orchestrated/activities/channels.md#confirm-message-sending)

* **Användargenererat stöd för metadata** - Hjälpfunktionen <strong>executionMetadata</strong> är nu tillgänglig i personaliseringsredigeraren för orkestrerade kampanjer, vilket gör att du kan bifoga kontextinformation till alla interna åtgärder och lagra den i en datauppsättning för export till externa system. [Läs mer](../personalization/functions/helpers.md#execution-metadata)

* **Starta om-knapp** - Orchestrerade-kampanjer innehåller nu en <strong>omstartsknapp</strong> så att du snabbt kan starta om kampanjer när det behövs innan kampanjen publiceras. [Läs mer](../orchestrated/start-monitor-campaigns.md)

* **Stöd för hastighetskontroll** - Orchestrerade kampanjer har nu stöd för <strong>hastighetskontroll</strong> som hjälper dig att jämna ut leveranser och anpassa dig till volymbegränsningar. [Läs mer](../orchestrated/activities/channels.md#rate-control)

#### Behörigheter

* **Förhindra självgodkännande för resor och kampanjer** - Ett alternativ lades till när en godkännandeprincip skapades eller ställdes in för att förhindra att den som skapar kampanjen godkänner sina egna objekt. [Läs mer](../test-approve/approval-policies.md)

## Kommer snart {#jan-26-01-coming-soon}

Följande funktioner och förbättringar planeras släppas under de närmaste dagarna. **Informationen kan komma att ändras**. Uppdaterade länkar, skärmar och dokumentation delas när uppdateringarna är klara.

### Funktioner

<table>
<thead>
<tr>
<th><strong>Meddelandeexport</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>En ny <strong>meddelandeexportfunktion</strong> kommer att vara tillgänglig för e-post- och SMS-kanaler. Med den här funktionen kan du automatiskt exportera skickat meddelandeinnehåll till en dedikerad Experience Platform-datauppsättning, vilket gör att du kan:</p>
<ul>
<li>Uppfyll formella krav (t.ex. HIPAA)</li>
<li>Arkivera meddelanden om juridiska anspråk och kundvårdsfrågor</li>
<li>Bevara kopior av personaliserat innehåll som skickas till enskilda personer</li>
</ul>
<p>Poster sparas i datauppsättningen för export av AJO-meddelanden i 7 kalenderdagar från intag. Under den här kvarhållningsperioden kan du exportera data till din egen lagring via Experience Platform destinationer. Funktionen är aktiverad på kanalkonfigurationsnivå, vilket ger dig detaljkontroll över vilka meddelanden som exporteras.</p>
<p>Den här funktionen är bara tillgänglig för e-post- och SMS-kanalen, för organisationer som har köpt tillägget för meddelandeexport. Kontakta din Adobe-representant om du vill veta mer.</p>
<p>Tillgänglighetsdatum: 28 januari 2026</p>
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
<p>Adobe Journey Optimizer stöder <strong>Web Push-meddelanden</strong>, vilket utökar push-kanalen bortom mobilen. Ni kan leverera meddelanden till både webbläsare för mobiler och datorer, så att ni kan nå kunder direkt på deras enheter utan att behöva använda en app. Den här förbättringen hjälper er att engagera användarna med rätt, personaliserade meddelanden i realtid, och utnyttjar samma arbetsflöden och målgruppsfunktioner som redan finns för mobilpush.</p>
<p>Den här funktionen lanserades tidigare i Beta och är tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p>Tillgänglighetsdatum: 28 januari 2026</p>
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
<p><strong>API:er för migreringsverktyg</strong> kommer att vara tillgängliga för programmässig migrering av beslutshanteringsenheter till beslut, med följande innehåll:</p>
<ul>
<li>Flexibla migreringsomfång (sandlåda, erbjudande eller beslutsnivå)</li>
<li>Automatisk beroendeanalys och validering</li>
<li>Återställningsstöd för slutförda migreringar</li>
<li>Detaljerade migreringsrapporter med objektmappningar</li>
</ul>
<p>Tillgänglighetsdatum: 28 januari 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Tysta timmar (tidsbaserade undantag)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med tysta timmar kan du definiera <strong>tidsbaserade undantag</strong> för kanalerna Email, SMS, Push och WhatsApp. De ser till att inga meddelanden skickas under specifika perioder, vilket hjälper dig att uppfylla kundönskemål och krav på regelefterlevnad. Du kan använda tysta timmar genom <strong>regeluppsättningar</strong>, som kan tilldelas enskilda åtgärder i kampanjer eller resor för exakt kontroll.</p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är tillgänglig i alla miljöer (allmän tillgänglighet). I den här allmänna tillgänglighetsversionen inkluderar funktionen även möjligheten att placera en kampanjåtgärd i kö tills tysta timmar har slutförts och möjligheten att förhandsgranska den aktiverade regeln Tysta timmar.</p>
<p>Tillgänglighetsdatum: 28 januari 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Direktreklamkanal på resor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Tidigare begränsad till kampanjer kommer kanalen <strong>Direct Mail</strong> att vara tillgänglig på arbetsytan så att du kan lägga in Direct Mail på dina resor. Direktreklam stöds i både batch- och 1:1-kundresscenarier, med filextraheringskonfiguration och tidsbaserade frekvensinställningar.</p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p>Tillgänglighetsdatum: 28 januari 2026</p>
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
<p>Direktreklamkanalen kommer att vara tillgänglig i samordnade kampanjer. <strong>Direkte-postaktiviteten</strong> underlättar direktutskick inom din samordnade kampanj för både engångs- och återkommande meddelanden. Den automatiserar genereringen av den <strong>extraheringsfil</strong> som krävs av direktmeddelandeleverantörer. Ni kommer att kunna kombinera kanalaktiviteter i den samordnade kampanjarbetsytan för att skapa flerkanalskampanjer som triggar åtgärder baserat på kundbeteende och data.</p>
<p>Tillgänglighetsdatum: 28 januari 2026</p>
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
<p>Du kan få djupare insikter i hälsa och prestanda för dina anpassade åtgärdsslutpunkter med en ny <strong>kontrollpanel</strong> för övervakning och inbyggda händelsedata för kundsteg. Spåra lyckade samtal, fel, dataflöde, svarstider och väntetider för kön för att snabbt förstå när, var och varför avvikelser inträffar.</p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p>Tillgänglighetsdatum: 28 januari 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Generering av innehåll i Journey Agent</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>Journey Agent</strong> kommer att vara tillgänglig i Journey Optimizer med Adobe Experience Platform Agent Orchestrator och du kan analysera resor via ett naturligt språkgränssnitt. Du kan generera och hantera kanalspecifikt innehåll direkt i Journey Agent, skapa innehåll för kanaler som e-post och push, tillämpa och förhandsgranska mallar, förfina ton och stil genom uppmaningar och öppna innehåll i <strong>Content Designer</strong> för kontextredigering.</p>
<p>Tillgänglighetsdatum: 2 februari 2026</p>
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
<p>Du kan anpassa och optimera innehållet i dina push- och SMS-meddelanden med <strong>Beslutsfattning</strong>. Använd beslutsprinciper, <strong>prioriteringspolicyer</strong>, formler eller AI-modeller för att visa det bästa innehållet för dina kunder.</p>
<p>Tillgänglighetsdatum: 3 februari 2026</p>
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
<p>En ny <strong>aktivitet för innehållsbeslut</strong> kommer att vara tillgänglig på arbetsytan för att integrera personaliserade erbjudanden direkt på kundresorna. Med den här aktiviteten kan ni leverera beslutsbaserat innehåll och hänvisa till dessa erbjudanden under hela kundresan, skapa kvalificeringsbaserade förgreningar, i anpassade åtgärder för att skicka erbjudandedata till externa system och i andra aktiviteter för att skapa helt personaliserade kundupplevelser.</p>
<p>Den här funktionen är tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p>Tillgänglighetsdatum: 3 februari 2026</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar

* **Kvalitetskontroller för AI-assistentinnehåll** - Förutom varumärkesjustering kan du utvärdera den övergripande <strong>innehållskvaliteten</strong> för att identifiera potentiella problem med läsbarhet, kohesivitet och effektivitet, oberoende av varumärkesriktlinjerna. Dessa automatiska kontroller hjälper till att identifiera otydliga meddelanden, inkonsekventa toner eller strukturella luckor. Tillgänglighetsdatum: 28 januari 2026.

* **Uppdatera varumärken med nya färgflikar** - Riktlinjer för varumärket hjälper dig att se till att ert varumärke presenteras på ett enhetligt sätt över alla kontaktytor. Det nya avsnittet <strong>Färger</strong> definierar standarderna för ditt varumärkes färgsystem och visar hur färger väljs, ordnas och används i olika upplevelser. Det kommer att säkerställa en konsekvent användning av primära, sekundära, dekorativa och neutrala färger för att stödja en sammanhängande, tillgänglig och identifierbar varumärkesidentitet. Tillgänglighetsdatum: 28 januari 2026.

* **SMS-webbhooks** - <strong>Webbhooks</strong> stöds av alla SMS-providers. Du kan konfigurera varje webkrok baserat på dess avsedda syfte: inkommande webbhooks för att hämta inkommande meddelanden och Feedback-webbhooks för att ta emot leveranskvitton, statusuppdateringar och andra meddelanderelaterade händelser. Tillgänglighetsdatum: 28 januari 2026.

* **Schemalägg kampanj med profiltidszon** - Kampanjplaneringen kan använda varje profils <strong>tidszon</strong> för att leverera meddelanden vid den avsedda lokala tidpunkten. **Obs!**: Den här förbättringen är bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Tillgänglighetsdatum: 28 januari 2026.
