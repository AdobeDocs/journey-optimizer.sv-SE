---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
role: User
level: Beginner, Intermediate
description: Versionsinformation om Adobe Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: b414d330a25a98c11b7417beda4536c54c41fd83
workflow-type: tm+mt
source-wordcount: '1884'
ht-degree: 8%

---

# Versionsinformation {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="Nyheter?"
>abstract="**Adobe Journey Optimizer** levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen."

[!DNL Adobe Journey Optimizer] följer en kontinuerlig leveransmodell som gör att Adobe kan leverera nya funktioner, förbättringar och korrigeringar kontinuerligt. Detta tillvägagångssätt möjliggör en skalbar, fasad driftsättning av funktioner för att säkerställa prestanda och stabilitet i alla miljöer.

På grund av den här modellen uppdateras versionsinformationen mellan månadsversionerna. Fullständig information om frisläppningscykeln och tillgänglighetsfaserna finns i [Journey Optimizer versionscykel](releases.md).

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver från de senaste innovationerna och förbättringarna. Läs mer om de här ändringarna i [Adobe Experience Platform versionsinformation](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=sv-SE){target="_blank"}.

## 26 februari-uppdateringar {#feb-26-updates}

### Nya funktioner {#feb-26-01-updates-features}

<table>
<thead>
<tr>
<th><strong>Aktivitet för innehållsbeslut</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>En ny <strong>aktivitet för innehållsbeslut</strong> är nu tillgänglig på arbetsytan för att integrera <strong>personaliserade erbjudanden</strong> direkt på kundresorna. Med den här aktiviteten kan ni leverera beslutsbaserat innehåll och hänvisa till dessa erbjudanden under hela kundresan - under villkor för att skapa kvalificeringsbaserade förgreningar, i anpassade åtgärder för att skicka erbjudandedata till externa system och i andra aktiviteter för att skapa helt personaliserade kundupplevelser.</p>
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
<p><strong>Migreringsverktygs-API:er</strong> är nu tillgängliga för programmässig migrering av beslutshanteringsenheter till Beslutsfattare, med följande innehåll:</p>
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
<p>Få djupare insikter i hälsa och prestanda för dina <strong>anpassade åtgärdsslutpunkter</strong> med en ny kontrollpanel och förbättrade händelsedata för kundsteg. Spåra lyckade samtal, fel, dataflöde, svarstider och väntetider för kön för att snabbt förstå när, var och varför avvikelser inträffar.</p>
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
<p>Du kan nu anpassa och optimera innehållet i dina <strong>SMS-meddelanden</strong> med <strong>Beslutsfattande</strong>. Använd prioriteringspoäng, formler eller AI-modeller för att visa det bästa innehållet för era kunder.</p>
<p>Mer information finns i den <a href="../experience-decisioning/create-decision.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 2 februari 2026</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar {#feb-26-01-updates-improv}

* **Koppla fragment till beslutsobjekt** - Journey Optimizer kan nu koppla <strong>fragment</strong> till <strong>beslutsobjekt</strong> som kan utnyttjas i kodbaserade upplevelsekampanjer via beslutsprinciper. Den här förbättringen fanns tidigare i Begränsad tillgänglighet och är nu tillgänglig i alla miljöer (Allmän tillgänglighet). [Läs mer](../experience-decisioning/fragments-decision-policies.md)

  Tillgänglighetsdatum: 12 februari 2026.

* **JSON-typerad uttrycksfragmentvalidering** - JSON-typerade uttrycksfragment valideras nu syntaktiskt när de sparas. Valideringsfel behandlas som varningar och visas som varningar när de har sparats. [Läs mer](../content-management/create-fragments.md#content)

  Tillgänglighetsdatum: 12 februari 2026.

* **SMS-webbhooks** - Webbhooks stöds nu av alla SMS-leverantörer. Du kan konfigurera varje webkrok baserat på dess avsedda syfte, inkommande webbhooks för att hämta inkommande meddelanden och Feedback-webbhooks för att ta emot leveranskvitton, statusuppdateringar och andra meddelanderelaterade händelser. [Läs mer](../sms/sms-webhook.md)

  Tillgänglighetsdatum: 2 februari 2026.

## Versionsinformation januari 26 {#latest-rn}

<!--**Release date**: January 27-28, 2026-->

Avsnitten [Funktioner](#jan-26-01-features) och [Förbättringar](#jan-26-01-improv) omfattar funktioner som redan är tillgängliga, medan [Kommer snart](#jan-26-01-coming-soon) listar objekt som är schemalagda för ett senare tillgänglighetsdatum.

<!-- **The pre-release notes below are subject to change without prior notice until the release availability date**. Links, screens and updated documentation are published in the release notes, at the release date. 

See also [Adobe Experience Platform Pre-release notes](https://experienceleague.adobe.com/sv/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.-->

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

<!--
## Coming soon {#jan-26-01-coming-soon}

In the next few days, the following capabilities and enhancements are scheduled for release. **Information is subject to change**. Updated links, screens, and documentation will be shared once these updates are live in production.

### Features


<table>
<thead>
<tr>
<th><strong>Web Push notifications channel</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer now supports <strong>Web Push notifications</strong>, expanding the push channel beyond mobile. You can seamlessly deliver notifications to both <strong>mobile and desktop browsers</strong>, enabling you to reach customers directly on their devices without requiring an app. This enhancement allows you to engage users with timely, personalized messages in real time, leveraging the same authoring workflows and targeting capabilities already available for mobile push.</p>
<p><img src="assets/do-not-localize/web-push.gif"/></p>
<p>Previously released in Beta, this capability will be available to all environments (General Availability).</p>
<p>Availability date: February 11, 2026</p>
</td>
</tr>
</tbody>
</table>

### Improvements


-->