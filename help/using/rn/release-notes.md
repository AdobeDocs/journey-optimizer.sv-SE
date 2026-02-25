---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
role: User
level: Beginner, Intermediate
description: Versionsinformation om Adobe Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: f1c324ec00aaa077c924635558170e2c352cbb41
workflow-type: tm+mt
source-wordcount: '1562'
ht-degree: 6%

---

# Versionsinformation {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="Nyheter?"
>abstract="**Adobe Journey Optimizer** levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen."

[!DNL Adobe Journey Optimizer] följer en kontinuerlig leveransmodell som gör att Adobe kan leverera nya funktioner, förbättringar och korrigeringar kontinuerligt. Detta tillvägagångssätt möjliggör en skalbar, fasad driftsättning av funktioner för att säkerställa prestanda och stabilitet i alla miljöer.

På grund av den här modellen uppdateras versionsinformationen mellan månadsversionerna. Fullständig information om frisläppningscykeln och tillgänglighetsfaserna finns i [Journey Optimizer versionscykel](releases.md).

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver från de senaste innovationerna och förbättringarna. Läs mer om de här ändringarna i [Adobe Experience Platform versionsinformation](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target="_blank"}.

## Versionsinformation 26 februari {#feb-26-01-rn}

Avsnitten [Nya funktioner](#feb-26-01-features) och [Förbättringar](#feb-26-01-improv) omfattar funktioner som redan är tillgängliga. Avsnittet [Kommer snart](#coming-soon) innehåller funktioner och förbättringar som är planerade att släppas senare i februari.

<!--**The pre-release notes below are subject to change without prior notice until the release availability date**. Links, screens and updated documentation are published in the release notes, at the release date.

See also [Adobe Experience Platform Pre-release notes](https://experienceleague.adobe.com/en/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.-->

<!--**Release date**: February 17-18, 2026-->

### Nya funktioner {#feb-26-01-features}


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

#### Experience Decision

* **Stöd för inkommande trafik från Edge för användning av Adobe Experience Platform-data i beslut** - Om du använder Adobe Experience Platform-data i beslut stöds nu även kantinkommande användningsfall, förutom e-post och anpassade åtgärder på resor. [Läs mer](../experience-decisioning/aep-data-exd.md)

  Den här funktionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.


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

## Kommer snart {#coming-soon}

Funktionerna och förbättringarna nedan är planerade att släppas senare i februari. Releasedatum och omfång kan ändras utan föregående meddelande.

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
<!--p><img src="assets/do-not-localize/journey-arbitration-formulas.gif"/></p-->
<p>Den här funktionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
<p>Tillgänglighetsdatum: 25 februari 2026</p>
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
<p>Tillgänglighetsdatum: tidig mars 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>AI-modellövervakning</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du övervaka hälsa, utbildningsstatus och prestanda för dina AI-modeller för beslut. På så sätt kan ni verifiera att kursen har lyckats, felsöka och förstå hur resultatet blir för att kunna välja de bästa erbjudandena för varje kund med hjälp av AI. Observera att den här funktionen endast är tillgänglig för <strong>Decision</strong> (inte för äldre beslutsmodeller).</p>
<p>Den här funktionen är för närvarande endast tillgänglig för <strong>personaliserade optimeringsmodeller</strong> (inte automatisk optimering).</p>
<p>Tillgänglighetsdatum: tidig mars 2026</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar {#coming-soon-improv}

<!--* **Experience Decisioning preview in Code-based Experience channel** - You can now preview decision items when configuring Experience Decisioning with the Code-based Experience channel. Preview is available directly in the authoring interface before going live.

  Availability date: early March, 2026.-->

* **Integrering av anpassade Firefly-modeller och tredjepartsmodeller för bildgenerering** - Möjliggör smidig integrering av Firefly-modeller och egna, tillsammans med godkända tredjepartsmodeller (t.ex. NanoBanana), för att ge större flexibilitet, kontroll och varumärkesjustering när bilder genereras. På så sätt kan du välja den bästa modellen för varje användningsfall: standardmodell för Firefly för allmänna behov, anpassad Firefly för varumärkesgenerering eller godkända tredjepartsmodeller för specialiserade eller experimentella scenarier.

  Tillgänglighetsdatum: tidig mars 2026.

