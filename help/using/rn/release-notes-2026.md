---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation 2026
description: Versionsinformation om Journey Optimizer 2026
feature: Release Notes
topic: Content Management
role: User
level: Beginner, Intermediate
exl-id: 65ca94cf-8e17-4a25-90f3-238083f81477
source-git-commit: b6b74e357029f4924f9699c05af3a0fcd7fcefd6
workflow-type: tm+mt
source-wordcount: '2573'
ht-degree: 9%

---

# Versionsinformation för 2026 {#release-notes-2026}

På den här sidan visas alla funktioner och förbättringar för [!DNL Journey Optimizer] som släpptes 2026.



## Versionsinformation 26 februari {#feb-26-01-rn}

### Nya funktioner {#feb-26-01-features}


<table>
<thead>
<tr>
<th><strong>Skiljeförfarande på resan</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Du kan nu använda <strong>rankningsformler</strong> för att automatiskt öka prioritetspoängen för resan baserat på kundprofilattribut och sammanhangsberoende faktorer, så att kunderna kan komma in på de mest relevanta resorna.</p>
<p><img src="assets/do-not-localize/journey-arbitration-formulas.gif"/></p>
<p>Den här funktionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
<p>Mer information finns i den <a href="../conflict-prioritization/journey-ranking-formulas.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 24 februari 2026</p>
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
<p>Journey Optimizer har stöd för en ny generisk <strong>åtgärdsaktivitet</strong> som gör att du kan konfigurera både enskilda åtgärder och inkommande åtgärdsgrupper för flera åtgärder, vilket ger en smidig åtgärdskonfiguration på arbetsytan. Den här nya funktionen gör det möjligt att:</p>
<ul>
<li>En förenklad inbyggd åtgärdskonfiguration på arbetsytan för resan.</li>
<li>Kapaciteten för att skapa inkommande åtgärdsgrupper med flera åtgärder.</li>
<li>Möjlighet att lägga till optimering till alla inbyggda kanalåtgärder.</li>
<li>Möjlighet att lägga till både experimentella och flerspråkiga alternativ i alla funktionsmakron.</li>
</ul>
<p><img src="assets/do-not-localize/action-activity.gif"/></p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p>Mer information finns i den <a href="../building-journeys/journey-action.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 20 februari 2026</p>
<p><strong>Obs!</strong> Alla inbyggda kanaler är nu tillgängliga via åtgärdsreseaktiviteten. Gamla inbyggda kanalaktiviteter kommer att bli inaktuella i mars-versionen. Befintliga resor med äldre åtgärder kommer att fortsätta att fungera som de är - ingen migrering krävs.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Påfyllnadssändning av utgående meddelanden</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan ni schemalägga meddelanden från Journey Optimizer kampanjer eller resor som ska levereras i kontrollerade omgångar över tid.</p>
<p>Wave-sändning ger följande fördelar:</p>
<ul>
<li>Bättre leveransförmåga - Spridning skickar över tid för att bevara ett starkt avsändarrykte och minska risken för att flaggas som skräppost.</li>
<li>Belastningskontroll - Undvik överväldigande system längre fram i kedjan (t.ex. callcenters, landningssidor) genom att begränsa hur många meddelanden som skickas samtidigt.</li>
<li>Användningsfall med stor volym och tidskänslighet - Passar för stora målgrupper eller när du behöver styra timing (t.ex. callcenters kapacitet, uppfartsavtal eller tidsbundna erbjudanden).</li>
</ul>
<p><img src="assets/do-not-localize/waves.gif"/></p>
<p>I <strong>kampanjer</strong> är den här funktionen tillgänglig för alla miljöer (allmän tillgänglighet). Mer information finns i den <a href="../campaigns/send-using-waves.md">detaljerade dokumentationen</a>.</p>

<p>På <strong>resor</strong> är den här funktionen bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet) - Kontakta din Adobe-representant för att få åtkomst. Mer information finns i den <a href="../building-journeys/send-using-waves.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 19 februari 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Migrera underdomäner till anpassad delegering</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du migrera underdomäner med CNAME-delegeringsläget till anpassad delegering direkt från gränssnittet, så att du kan följa striktare säkerhetsregler i enlighet med företagets riktlinjer utan att behöva skapa kanalkonfigurationer på nytt.</p>
<p><img src="assets/do-not-localize/subdomain-migration.gif"/></p>
<p>Den här funktionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
<p>Mer information finns i den <a href="../configuration/custom-subdomain-migration.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 19 februari 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Webbpush-meddelandekanal</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer har nu stöd för <strong>webb-push-meddelanden</strong>, vilket utökar push-kanalen bortom mobilen. Du kan enkelt leverera meddelanden till både <strong>mobilwebbläsare och datorwebbläsare</strong>, så att du kan nå kunder direkt på deras enheter utan att behöva använda en app. Den här förbättringen gör att ni kan engagera användarna med rätt, personaliserade meddelanden i realtid, och utnyttja samma arbetsflöden och målgruppsfunktioner som redan finns för mobilpush.</p>
<p><img src="assets/do-not-localize/web-push.gif"/></p>
<p>Den här funktionen lanserades tidigare i Beta och är tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p>Mer information finns i den <a href="../push/push-configuration-web.md">detaljerade dokumentationen</a>.</p>
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
<p>En ny <strong>aktivitet för innehållsbeslut</strong> är nu tillgänglig på arbetsytan för att integrera personaliserade erbjudanden direkt i kundresorna. Med den här aktiviteten kan ni leverera beslutsbaserat innehåll och hänvisa till dessa erbjudanden under hela kundresan, under villkor för att skapa kvalificeringsbaserade förgreningar, i anpassade åtgärder för att skicka erbjudandedata till externa system och i andra aktiviteter för att skapa helt personaliserade kundupplevelser.</p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p><img src="assets/do-not-localize/content-decision.gif"/></p>
<p>Mer information finns i den <a href="../building-journeys/content-decision.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 10 februari 2026</p>
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
<p>Migreringsverktygs-API:er är nu tillgängliga för programmatisk migrering av <strong>beslutshantering</strong>-entiteter till <strong>beslutshantering</strong>, med:</p>
<ul>
<li>Flexibla migreringsomfång (sandlåda, erbjudande eller beslutsnivå)</li>
<li>Automatisk beroendeanalys och validering</li>
<li>Återställningsstöd för slutförda migreringar</li>
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
<p>Få djupare insikter i hälsa och prestanda för era anpassade åtgärdsslutpunkter med en ny kontrollpanel och förbättrade händelsedata för kundsteg. Spåra lyckade samtal, fel, dataflöde, svarstider och väntetider för kön för att snabbt förstå när, var och varför avvikelser inträffar.</p>
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
<p>Ni kan nu personalisera och optimera innehållet i era SMS-meddelanden med Beslutsfattning. Använd prioriteringspoäng, formler eller AI-modeller för att visa det bästa innehållet för era kunder.</p>
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

#### Innehållshantering

<!--
* **Update brands with new color tab** - Brand guidelines help ensure your brand is presented consistently across all touchpoints. The new <strong>Colors</strong> section defines the standards for your brand's color system, outlining how colors are selected, organized, and applied across experiences. It ensures consistent use of primary, secondary, accent, and neutral colors to support a cohesive, accessible, and recognizable brand identity. [Read more](../content-management/brands.md)
-->

* **Använd teman för att konvertera bilder till e-postmallar** - När du konverterar en bild till en e-postmall i Journey Optimizer kan du nu använda ett tema som indata så att den genererade HTML följer varumärkesparametrarna. Formatering som bakgrundsfärg, knappfärg, teckensnitt, radavstånd, marginaler och utfyllnad tillämpas automatiskt, vilket minskar det manuella arbetet och ger en mall som är klar att användas med minimala redigeringar. [Läs mer](../content-management/image-to-html.md)

  Tillgänglighetsdatum: 17 februari 2026.

<!--* **Text mode for fragments** - You can now create and manage text versions of your fragments, supporting workflows that rely on plain text content and providing the same flexibility as in email content. [Read more](../content-management/create-fragments.md)-->

#### E-postdesigner

* **Textindrag** - Du kan nu använda anpassningsbara vänsterindrag på den första raden med stycken i textkomponenter direkt från egenskapspanelen. <!--The new **Indentation** control lets you define indentation in pixels or percentage via a numeric input or slider, with live preview on the canvas. -->Detta förbättrar läsbarheten för innehåll i lång form, t.ex. redigeringar och artiklar. [Läs mer](../email/get-started-email-style.md)

  Tillgänglighetsdatum: 18 februari 2026.

#### Beslut

* **Stöd för inkommande trafik från Edge för användning av Adobe Experience Platform-data i beslut** - Om du använder Adobe Experience Platform-data i beslut stöds nu även kantinkommande användningsfall, förutom e-post och anpassade åtgärder på resor. [Läs mer](../experience-decisioning/aep-data-exd.md)

  Den här funktionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.

* **Förhandsgranskning av beslut i den kodbaserade upplevelsekanalen** - Du kan nu förhandsgranska beslutsobjekt när du konfigurerar beslut med den kodbaserade upplevelsekanalen. Förhandsgranskningen är tillgänglig direkt i redigeringsgränssnittet innan den publiceras. [Läs mer](../code-based/test-code-based.md#preview-code-based)

  Tillgänglighetsdatum: 18 februari 2026

* **Koppla fragment till beslutsobjekt** - Journey Optimizer kan nu koppla fragment till beslutsobjekt som kan utnyttjas i kodbaserade upplevelsekampanjer via beslutspolicyer. [Läs mer](../experience-decisioning/fragments-decision-policies.md)

  Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).

  Tillgänglighetsdatum: 12 februari 2026.

#### Personalisering

* **Hjälp för körningsmetadata** - Hjälpfunktionen `executionMetadata` är nu tillgänglig för alla Journey Optimizer-kunder. Använd den för att dynamiskt lägga till sammanhangsbaserad information till alla interna åtgärder och hämta in den i en datauppsättning för export till externa system. [Läs mer](../personalization/functions/helpers.md#execution-metadata)

  Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).

  Tillgänglighetsdatum: 20 februari 2026.

#### SMS

* **SMS-webbhooks** - Webbhooks stöds nu av alla SMS-leverantörer. Du kan konfigurera varje webkrok baserat på dess avsedda syfte: inkommande webbhooks för att fånga inkommande meddelanden och Feedback-webbhooks för att ta emot leveranskvitton, statusuppdateringar och andra meddelanderelaterade händelser. [Läs mer](../sms/sms-webhook.md)

  Tillgänglighetsdatum: 2 februari 2026.



## Versionsinformation januari 26 {#jan-26-rn}

<!--**Release date**: January 27-28, 2026-->

### Nya funktioner {#jan-26-01-features}


<table>
<thead>
<tr>
<th><strong>Beslutsstöd i push-kanal</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Du kan nu anpassa och optimera innehållet i dina <strong>push-meddelanden</strong> med <strong>beslut</strong>. Använd prioriteringspoäng, formler eller AI-modeller för att visa det bästa innehållet för era kunder.</p>
<p>Experience Decision med push-meddelanden kräver en specifik version av Mobile SDK. Innan du implementerar den här funktionen bör du kontrollera <a href="https://developer.adobe.com/client-sdks/home/release-notes" target="_blank">versionsinformationen</a> för att identifiera den version som krävs och kontrollera att du har uppgraderat därefter. Du kan även visa alla tillgängliga SDK-versioner för din plattform i <a href="https://developer.adobe.com/client-sdks/home/current-sdk-versions/" target="_blank">det här avsnittet</a>.</p>
<p>Mer information finns i den <a href="../experience-decisioning/create-decision.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 30 januari 2026</p>
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
<p>Kanalen <strong>Direktreklam</strong> har tidigare begränsats till kampanjer och är nu tillgänglig på arbetsytan så att du kan lägga in direktreklam på dina resor. Direktreklam kan nu användas i både <strong>batch- och 1:1-resescenarier</strong>, med stöd för filextraheringskonfiguration och tidsbaserade frekvensinställningar.</p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p><img src="assets/do-not-localize/dm-journey.gif"/></p>
<p>Mer information finns i den <a href="../direct-mail/get-started-direct-mail.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 29 januari 2026</p>
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
<p>Med <strong>tysta timmar</strong> kan du definiera tidsbaserade undantag för e-post-, SMS-, push- och whatsApp-kanaler. De ser till att inga meddelanden skickas under särskilda tidsperioder och hjälper er att följa kundönskemål och krav på regelefterlevnad. Du kan använda tysta timmar genom <strong>regeluppsättningar</strong>, som kan tilldelas enskilda åtgärder i kampanjer eller resor för exakt kontroll.</p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer. I den här allmänna tillgänglighetsversionen inkluderar funktionen nu möjligheten för kunden att ställa en kampanjåtgärd i kö tills tysta timmar har slutförts och möjligheten att förhandsgranska den aktiverade regeln Tysta timmar.</p>
<p><img src="assets/do-not-localize/quiet-hour-ga.gif"/></p>
<p>Mer information finns i den <a href="../conflict-prioritization/quiet-hours.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 29 januari 2026</p>
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
<p>Poster sparas i datauppsättningen för export av AJO-meddelanden i 7 kalenderdagar från intag. Under den här kvarhållningsperioden kan du exportera dem till din egen lagringsplats via Experience Platform-destinationer. Funktionen är aktiverad på kanalkonfigurationsnivå, vilket ger dig <strong>detaljkontroll</strong> över vilka meddelanden som exporteras.</p>
<p>Den här funktionen är bara tillgänglig för e-post- och SMS-kanalen, för organisationer som har köpt tillägget för meddelandeexport. Kontakta din Adobe-representant om du vill veta mer.</p>
<p><img src="assets/do-not-localize/message-export.gif"/></p>
<p>Mer information finns i den <a href="../configuration/message-export.md#message-export">detaljerade dokumentationen</a>.</p>
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
<p>Direktreklamkanalen finns nu tillgänglig i samordnade kampanjer. <strong>Direkte-postaktiviteten</strong> gör det lättare att skicka direktreklam i din samordnade kampanj, både för engångs- och återkommande meddelanden. Den används för att automatisera processen att generera den <strong>extraheringsfil</strong> som krävs av direktmeddelandeleverantörer. Ni kan kombinera kanalaktiviteter i den orkestrerade kampanjarbetsytan för att skapa flerkanalskampanjer som kan utlösa åtgärder baserat på kundbeteende och data.</p>
<p><img src="assets/do-not-localize/dm-oc.gif"/></p>
<p>Mer information finns i den <a href="../orchestrated/activities/channels.md#channel">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 28 januari 2026</p>
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
<p>Journey Agent har nu funktioner för att skapa, vilket gör det möjligt för Journey Optimizer-användare att skapa och konfigurera marknadsföringsresor via ett <strong>naturligt språkgränssnitt</strong>. Med dessa nya kunskaper kan yrkesverksamma snabbt skapa resor genom att helt enkelt beskriva sina krav i <strong>konversationsprompter</strong>. Denna innovation effektiviserar processen att skapa kundresor så att marknadsförarna kan fokusera på strategi istället för teknisk konfiguration.</p>
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
<p>Det finns nu ett nytt Journey Optimizer-API, som gör att du kan hämta och inspektera <strong>kampanjrelaterade data</strong> automatiskt, till exempel information, versioner och konfigurationer.</p>
<p>Mer information finns i den <a href="https://developer.adobe.com/journey-optimizer-apis/references/campaigns-retrieve/" target="_blank">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 24 november 2025</p>
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
<p>Nu kan du snabbt tillämpa <strong>förgodkända teman</strong> för att säkerställa <strong>varumärkets enhetlighet</strong> i alla e-postmeddelanden, snabba upp kampanjprocessen och oberoende producera högkvalitativa e-postmeddelanden samtidigt som du minskar beroendet av designteam.</p>
<p><img src="assets/do-not-localize/themes.gif"/></p>
<p>Tidigare släppt i betaversion är den här funktionen nu tillgänglig för ett antal organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
<p>Mer information finns i den <a href="../email/apply-email-themes.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 5 november 2025</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar {#jan-26-01-improv}

#### AI

* **Kvalitetskontroller för AI-assistentinnehåll** - Förutom varumärkesjustering kan du nu utvärdera den övergripande <strong>innehållskvaliteten</strong> för att upptäcka potentiella problem med <strong>läsbarhet</strong>, kohesivitet och effektivitet, oberoende av varumärkesriktlinjerna. Dessa automatiska kontroller hjälper till att identifiera otydliga meddelanden, inkonsekventa toner och strukturella luckor. [Läs mer](../content-management/brands-score.md#validate-quality).

  [Upptäck den här funktionen i videon](https://video.tv.adobe.com/v/3470550/?captions=swe&learn=on).

#### Resor

* **Kombinera inbyggda meddelandeåtgärder och Adobe Campaign-meddelandeåtgärder** - Med Journey Optimizer kan du nu kombinera <strong>Adobe Campaign v7/v8</strong>-meddelandeåtgärder med <strong>inbyggda kanalåtgärder</strong> under samma resa. [Läs mer](../building-journeys/using-adobe-campaign-v7-v8.md)

  Tillgänglighetsdatum: 27 januari 2026.

* **Nyttolast för anpassat åtgärdsfelsvar** - Du kan nu definiera en valfri <strong>felsvarsnyttolast</strong> för anpassade åtgärder. När ett anrop misslyckas visas felnyttolasten i kundresans kontext (under åtgärdens errorResponse-nod) och är tillgänglig i <strong>timeout/error-grenen</strong>, tillsammans med `jo_status_code`, som stöd för större reservlogik och felsökning. [Läs mer](../action/about-custom-action-configuration.md#define-the-message-parameters)

  Tillgänglighetsdatum: 27 januari 2026.

* **Verifiering av nyttolastens storlek på resan** - Journey Optimizer validerar nu <strong>nyttolaststorlekarna</strong> för att säkerställa optimala prestanda och systemstabilitet. När du skapar eller publicerar resor får du tydliga <strong>varningar och fel</strong> om nyttolaststorlekarna närmar sig eller överskrider de rekommenderade gränserna, tillsammans med användbar vägledning för att optimera konfigurationen av din resa. Denna proaktiva validering hjälper er att identifiera potentiella problem tidigt och att upprätthålla kundresan. [Läs mer](../start/guardrails.md#journey-payload-size)

  Tillgänglighetsdatum: 27 januari 2026.


* **Resensaviseringar** - Nya <strong>förkonfigurerade aviseringar</strong> är tillgängliga för resor.
   * <strong>Frekvensen för ignorerade profiler har överskridits</strong> - Profilförhållandet ignoreras för angivna profiler under de senaste 5 minuterna
   * <strong>Felfrekvens för anpassad åtgärd överskreds</strong> - Förhållandet mellan anpassade åtgärdsfel och lyckade HTTP-anrop under de senaste 5 minuterna överskred tröskelvärdet
   * <strong>Profilens felfrekvens har överskridits</strong> - Profilernas felförhållande till de angivna profilerna under de senaste 5 minuterna har överskridit tröskelvärdet

  Mer information finns i den [detaljerade dokumentationen](../reports/alerts.md).

  Tillgänglighetsdatum: 14 oktober 2025.

#### Samordnade kampanjer

* **Etikettarv för dataanvändning för målgrupper** - Etiketter som används i Adobe Experience Platform överförs nu automatiskt när <strong>målgrupper</strong> sparas i samordnade kampanjer, vilket minskar den manuella <strong>DULE-taggningen</strong>. [Läs mer](../orchestrated/activities/save-audience.md)

* **Fördefinierade filter med parametrar** - Nu kan du skapa <strong>fördefinierade filter</strong> med <strong>parametrar</strong> i samordnade kampanjer för återanvändbara, redigerbara regler. [Läs mer](../orchestrated/predefined-filters.md)

* **Välj attribut och kopiera distributionsvärden** - Nu kan du <strong>välja eller kopiera värden</strong> direkt från vyn <strong>Värdefördelning</strong> i samordnade kampanjer. [Läs mer](../orchestrated/build-query.md)

* **Meddelandebekräftelse före sändning** - Ett <strong>bekräftelsesteg</strong> är nu aktiverat som standard innan orkestrerade kampanjer skickas för att minska antalet oavsiktliga sändningar. [Läs mer](../orchestrated/activities/channels.md#confirm-message-sending)

* **Fördefinierade återmarknadsföringsfilter** - Den här versionen innehåller nya <strong>filter för kampanjåterkoppling</strong> som stöd för enklare återmarknadsföring för samordnade kampanjanvändningsfall. Med de här filtren kan du rikta in dig direkt på målgrupper baserat på <strong>meddelandeinteraktion</strong>, till exempel skickad, öppnad, klickad eller öppnad och klickad, och välja den kampanj eller kampanj i övergången som du vill rikta om. [Läs mer](../orchestrated/retarget.md)

* **Stöd för hastighetskontroll** - Orchestrerade kampanjer har nu stöd för <strong>hastighetskontroll</strong> som hjälper dig att jämna ut leveranser och anpassa dig till <strong>volymbegränsningar</strong>. [Läs mer](../orchestrated/activities/channels.md#rate-control)

* **Starta om-knapp** - Orchestrerade-kampanjer innehåller nu en <strong>omstartsknapp</strong> så att du snabbt kan <strong>starta om körningar</strong> innan kampanjen publiceras. [Läs mer](../orchestrated/start-monitor-campaigns.md)

* **Användargenererat stöd för metadata** - Hjälpfunktionen <strong>executionMetadata</strong> är nu tillgänglig i personaliseringsredigeraren för Orchestrated-kampanjer, vilket gör att du kan bifoga kontextinformation till alla interna åtgärder och lagra den i en datauppsättning för export till externa system. [Läs mer](../personalization/functions/helpers.md#execution-metadata)

  Tillgänglighetsdatum: 27 januari 2026.

* **Återgå livekampanjer till utkaststatus** - Nu kan du återställa direktsända eller iscensatta kampanjer till utkaststatus när de stöter på körningsfel eller när du måste ändra schemalagda kampanjer innan de börjar köras. Det här alternativet är tillgängligt tills det första meddelandet skickas. [Läs mer](../orchestrated/start-monitor-campaigns.md#back-to-draft)

#### Kampanjer

* **Schemalägg kampanj med profiltidszon** - Kampanjplanering kan nu använda varje profils <strong>tidszon</strong> för att leverera meddelanden vid den avsedda lokala tidpunkten. [Läs mer](../campaigns/campaign-schedule.md)

  **Obs!**: Den här förbättringen är bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet).

  Tillgänglighetsdatum: 27 januari 2026.

#### Behörigheter

* **Förhindra självgodkännande för resor och kampanjer** - Ett alternativ lades till när <strong>Godkännandeprincip</strong> skapades eller ställdes in för att förhindra att den som skapar kampanjer eller reser <strong>godkänner sina egna objekt</strong>. [Läs mer](../test-approve/approval-policies.md)

  Tillgänglighetsdatum: 27 januari 2026.
