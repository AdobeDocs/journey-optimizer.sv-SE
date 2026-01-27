---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
role: User
level: Beginner, Intermediate
description: Versionsinformation om Adobe Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: c0ed4d941863730e6bc8dbea771cba94b305dd5b
workflow-type: tm+mt
source-wordcount: '1699'
ht-degree: 1%

---

# Versionsinformation {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="Nyheter?"
>abstract="**Adobe Journey Optimizer** levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen."

[!DNL Adobe Journey Optimizer] följer en kontinuerlig leveransmodell som gör att Adobe kan leverera nya funktioner, förbättringar och korrigeringar kontinuerligt. Detta tillvägagångssätt möjliggör en skalbar, fasad driftsättning av funktioner för att säkerställa prestanda och stabilitet i alla miljöer.

På grund av den här modellen uppdateras versionsinformationen mellan månadsversionerna. Fullständig information om frisläppningscykeln och tillgänglighetsfaserna finns i [Journey Optimizer versionscykel](releases.md).

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver från de senaste innovationerna och förbättringarna. Läs mer om de här ändringarna i [Adobe Experience Platform versionsinformation](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target="_blank"}.

## 26 förhandsversionsinformation januari {#latest-rn}

**Releasedatum**: 27 januari 2026

**Förhandsversionsinformationen nedan kan komma att ändras utan föregående meddelande till releasedatumet**. Länkar, skärmar och uppdaterad dokumentation publiceras i versionsinformationen på releasedatum.

Se även [Förhandsversionsinformation för Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.

### Nya funktioner {#jan-26-01-features}

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
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet). I den här allmänna tillgänglighetsversionen inkluderar funktionen nu möjligheten för kunder att placera en kampanjåtgärd i kö tills tysta timmar har slutförts och möjligheten att förhandsgranska den aktiverade regeln Tysta timmar.</p>
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
<p>Adobe Journey Optimizer har nu stöd för <strong>Web Push-meddelanden</strong>, vilket gör att push-kanalen kan användas även utanför mobila enheter. Ni kan leverera meddelanden till både webbläsare för mobiler och datorer, så att ni kan nå kunder direkt på deras enheter utan att behöva använda en app. Den här förbättringen hjälper er att engagera användarna med rätt, personaliserade meddelanden i realtid, och utnyttjar samma arbetsflöden och målgruppsfunktioner som redan finns för mobilpush.</p>
<p>Den här funktionen lanserades tidigare i Beta och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
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
<p><strong>Direktreklam</strong> har tidigare begränsats till kampanjer och är nu tillgänglig på arbetsytan så att du kan lägga in direktreklam på dina resor. Direktreklam kan nu användas i både batch- och 1:1-resscenarier, med stöd för filextraheringskonfiguration och tidsbaserade frekvensinställningar.</p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
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
<p>Direktreklamkanalen finns nu tillgänglig i samordnade kampanjer. <strong>Direkte-postaktiviteten</strong> gör det lättare att skicka direktreklam i din samordnade kampanj för både engångs- och återkommande meddelanden. Den automatiserar genereringen av den <strong>extraheringsfil</strong> som krävs av direktmeddelandeleverantörer. Ni kan kombinera kanalaktiviteter i den samordnade kampanjarbetsytan för att skapa flerkanalskampanjer som triggar åtgärder baserat på kundbeteende och data.</p>
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
<p>Du kan nu lägga till <strong>beslutsprinciper</strong> i SMS-resor och -kampanjer. Beslutspolicyer är behållare för era erbjudanden som utnyttjar beslutsmotorn för att dynamiskt returnera det bästa innehållet för varje målgruppsmedlem.</p>
<p>Den här funktionen är tillgänglig i begränsad tillgänglighet för en uppsättning organisationer. Kontakta Adobe.</p>
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
<p>Poster sparas i datauppsättningen för export av AJO-meddelanden i 7 kalenderdagar från intag. Under den här kvarhållningsperioden kan du exportera data till din egen lagring via Experience Platform destinationer. Funktionen är aktiverad på kanalkonfigurationsnivå, vilket ger dig detaljkontroll över vilka meddelanden som exporteras.</p>
<p>Den här funktionen är bara tillgänglig för e-post- och SMS-kanalen, för organisationer som har köpt tillägget för meddelandeexport. Kontakta din Adobe-representant om du vill veta mer.</p>
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
<p><strong>Migreringsverktygs-API:er</strong> är nu tillgängliga för programmässig migrering av beslutshanteringsenheter till Beslutsfattare, med följande innehåll:</p>
<ul>
<li>Flexibla migreringsomfång (sandlåda, erbjudande eller beslutsnivå)</li>
<li>Automatisk beroendeanalys och validering</li>
<li>Återställningsstöd för slutförda migreringar</li>
<li>Detaljerade migreringsrapporter med objektmappningar</li>
</ul>
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
<th><strong>Journey Agent - Skapa en resa</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Create Agent gör det möjligt för Journey Optimizer-användare att skapa och konfigurera marknadsföringsresor med ett <strong>naturligt språkgränssnitt</strong>. Praktikanter kan snabbt skapa resor genom att beskriva sina behov på samtal, effektivisera framtagningen av resor och låta marknadsförarna fokusera på strategi i stället för teknisk konfiguration.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar {#jan-26-01-improv}

Förbättringar i den här versionen visas nedan.

#### AI

* **Kvalitetskontroller för AI-assistentinnehåll** - Förutom varumärkesjustering kan du nu utvärdera den övergripande <strong>innehållskvaliteten</strong> för att identifiera potentiella problem med läsbarhet, kohesivitet och effektivitet, oberoende av varumärkesriktlinjerna. Dessa automatiska kontroller hjälper till att identifiera otydliga meddelanden, inkonsekventa toner och strukturella luckor.

* **Uppdatera varumärken med nya färgflikar** - Riktlinjer för varumärken hjälper dig att se till att ditt varumärke visas på ett enhetligt sätt på alla kontaktytor. I det nya avsnittet <strong>Färger</strong> definieras standarderna för ditt varumärkes färgsystem, som visar hur färger väljs, ordnas och används i olika upplevelser. Det säkerställer konsekvent användning av primära, sekundära, dekorativa och neutrala färger för att stödja en sammanhängande, tillgänglig och identifierbar varumärkesidentitet.

#### Kanaler

* **SMS-webbhooks** - <strong>Webbhooks</strong> stöds nu för alla SMS-providers. Du kan konfigurera varje webkrok baserat på dess avsedda syfte: Inkommande webbhooks för att fånga inkommande meddelanden och Feedback-webbhooks för att ta emot leveranskvitton, statusuppdateringar och andra meddelanderelaterade händelser.

#### Kampanjer

* **Schemalägg kampanj med profiltidszon** - Kampanjplanering kan nu använda varje profils <strong>tidszon</strong> för att leverera meddelanden vid den avsedda lokala tidpunkten.

  **Obs!**: Den här förbättringen är bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet).


#### Experience Decision

* **Koppla fragment till beslutsobjekt** - Journey Optimizer kan nu koppla <strong>fragment</strong> till beslutsobjekt, som kan utnyttjas i kodbaserade upplevelsekampanjer via beslutsprinciper.

  **Obs!**: Den här förbättringen har tidigare släppts i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).

#### Resor

* **Utnyttja nyttolasten för felsvar i kundresan med anpassade åtgärder** - Du kan nu definiera en valfri <strong>felsvarsnyttolast</strong> för anpassade åtgärder. När ett anrop misslyckas visas felnyttolasten i kundresans kontext och är tillgänglig i timeout/error-grenen, tillsammans med `jo_status_code`, som stöd för större reservlogik och felsökning.

* **Kombinera inbyggda meddelandeåtgärder och Adobe Campaign-meddelandeåtgärder** - Med Journey Optimizer kan du nu kombinera Adobe Campaign v7/v8-meddelandeåtgärder med inbyggda kanalåtgärder på samma resa.

* **Verifiering av nyttolastens storlek på resan** - Journey Optimizer validerar nu kundens nyttolaststorlekar för att säkerställa optimala prestanda och systemstabilitet. När du bygger eller publicerar resor får du tydliga varningar och fel om nyttolasterna närmar sig eller överskrider de rekommenderade gränserna, tillsammans med användbar vägledning för att optimera kundresans konfiguration. Denna proaktiva validering hjälper er att identifiera potentiella problem tidigt och att upprätthålla kundresan.

#### Samordnade kampanjer

* **Välj attribut och kopiera distributionsvärden** - Nu kan du välja eller kopiera värden direkt från värdedistributionen i samordnade kampanjer.

* **Etikettarv för dataanvändning för målgrupper** - Etiketter som används i Adobe Experience Platform överförs nu automatiskt när målgrupper sparas i orkestrerade kampanjer, vilket minskar den manuella DULE-taggningen.

* **Fördefinierade återmarknadsföringsfilter** - Den här versionen innehåller nya <strong>filter för kampanjåterkoppling</strong> som stöd för enklare återmarknadsföring för samordnade kampanjanvändningsfall. Med dessa filter kan ni rikta in er direkt på målgrupper baserat på meddelandeengagemang, som t.ex. skickat, öppnat, klickat eller öppnat och klickat, och välja den kampanj eller kampanj i övergången som du vill rikta om.

* **Fördefinierade filter med parametrar** - Nu kan du skapa fördefinierade filter med <strong>parametrar</strong> i samordnade kampanjer för återanvändbara, redigerbara regler.

* **Meddelandebekräftelse före sändning** - Ett <strong>bekräftelsesteg</strong> är nu aktiverat som standard innan orkestrerade kampanjer skickas för att minska antalet oavsiktliga sändningar.

* **Användargenererat stöd för metadata** - Hjälpfunktionen <strong>executionMetadata</strong> är nu tillgänglig i personaliseringsredigeraren för orkestrerade kampanjer, vilket gör att du kan bifoga kontextinformation till alla interna åtgärder och lagra den i en datauppsättning för export till externa system.

* **Starta om-knapp** - Orchestrerade-kampanjer innehåller nu en <strong>omstartsknapp</strong> så att du snabbt kan starta om kampanjer när det behövs innan kampanjen publiceras.

* **Stöd för hastighetskontroll** - Orchestrerade kampanjer har nu stöd för <strong>hastighetskontroll</strong> som hjälper dig att jämna ut leveranser och anpassa dig till volymbegränsningar.

#### Behörigheter

* **Förhindra självgodkännande för resor och kampanjer** - Ett alternativ lades till när en godkännandeprincip skapades eller ställdes in för att förhindra att den som skapar kampanjen godkänner sina egna objekt.

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
<p><strong>Journey Agent</strong>, som drivs av Adobe Experience Platform Agent Orchestrator, finns i Journey Optimizer och gör att du kan analysera resor via ett naturligt språkgränssnitt. Nu kan du generera och hantera kanalspecifikt innehåll direkt i Journey Agent, skapa innehåll för kanaler som e-post och push, tillämpa och förhandsgranska mallar, förfina ton och stil genom uppmaningar och öppna innehåll i <strong>Content Designer</strong> för kontextredigering.</p>
<p>Tillgänglighetsdatum: 2 februari 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Beslutsstöd i push-kanal</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Du kan nu anpassa och optimera innehållet i dina push-meddelanden med <strong>beslutande</strong>. Använd <strong>Prioritetsresultat</strong>, formler eller AI-modeller för att visa det bästa innehållet för dina kunder.</p>
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
<p>En ny <strong>aktivitet för innehållsbeslut</strong> är nu tillgänglig på arbetsytan för att integrera personaliserade erbjudanden direkt i kundresorna. Med den här aktiviteten kan ni leverera beslutsbaserat innehåll och hänvisa till dessa erbjudanden under hela kundresan, skapa kvalificeringsbaserade förgreningar, i anpassade åtgärder för att skicka erbjudandedata till externa system och i andra aktiviteter för att skapa helt personaliserade kundupplevelser.</p>
<p>Den här funktionen är tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p>Tillgänglighetsdatum: 3 februari 2026</p>
</td>
</tr>
</tbody>
</table>
