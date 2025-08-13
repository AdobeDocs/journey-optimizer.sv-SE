---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation 2025
description: Versionsinformation om Journey Optimizer 2025
feature: Release Notes
topic: Content Management
role: User
level: Beginner, Intermediate
exl-id: aa8c74de-748b-4947-a972-14703f6ab4a7
source-git-commit: 4d7ad2c3ed71801298f1afe31d0e29d7bb1d5c7f
workflow-type: tm+mt
source-wordcount: '4197'
ht-degree: 7%

---

# Versionsinformation för 2025 {#release-notes-2025}

På den här sidan visas alla funktioner och förbättringar för [!DNL Journey Optimizer] som släpptes 2025.


## Versionsinformation 25 juni {#25-6-rn}

**Releasedatum**: 18 juni 2025

### Nya funktioner {#25-06-features}

De nya funktionerna i den här versionen beskrivs nedan.

<table>
<thead>
<tr>
<th><strong>Adobe Experience Platform datasets in decisioning (beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform datamängder fanns tidigare för personalisering och kan nu utnyttjas för beslut. Detta gör att du kan utöka definitionen av dina beslutsattribut till ytterligare data i datauppsättningar för bulkuppdateringar som ändras regelbundet utan att du behöver uppdatera attributen manuellt en i taget. Till exempel tillgänglighet, väntetider osv.</p>
<p>Den här funktionen är för närvarande tillgänglig för alla kunder som en betaversion. Kontakta din kontorepresentant om du vill ha tillgång till tjänsten.</p>
<p>Mer information finns i den <a href="../experience-decisioning/aep-data-exd.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 20 juni 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>RCS-meddelanden</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>RCS-meddelanden (Rich Communication Services) stöds nu i Journey Optimizer, vilket möjliggör följande förbättrade meddelandefunktioner under förutsättning att leverantörer och operatörer stöds:</p>
<ul>
<li>Stöd för varumärken och verifierade avsändare: Skicka meddelanden med verifierade affärsprofiler med varumärkeselement (logotyp, avsändarnamn osv.).</li>
<li>Information om meddelandeleverans: Ta emot detaljerade leveransrapporter inklusive meddelandestatusuppdateringar (t.ex. skickade, levererade, lästa).</li>
<li>Länkspårning: Bädda in och spåra URL:er i RCS-meddelanden för engagemangsanalys.</li>
<li>Återställning till SMS: Automatisk återgång till SMS när profilens enhet inte stöder RCS eller är tillfälligt oåtkomlig via RCS.</li>
<li>Grundläggande meddelandekomposition: Skicka textbaserade RCS-meddelanden med valfria medier och multimedieelement beroende på leverantörens support.</li>
</ul>
<p>Mer information finns i den <a href="../sms/sms-configuration.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Formulärfält i kodbaserat upplevelseinnehåll</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du definiera specifika redigerbara fält i JSON- eller HTML-innehållsmallar, som gör det möjligt för icke-tekniska användare att enkelt redigera innehåll i en formulärvy i den kodbaserade upplevelsekanalutvecklingen, utan att behöva ändra någon kod.<br />Mer än så när du definierar kodbaserade innehållsmallar för upplevelser kan du nu infoga beslutsprinciper i mallen, vilket ökar återanvändbarheten och användarvänligheten.</p>
<img src="assets/do-not-localize/form-fields.gif">
<p>Mer information finns i den <a href="../code-based/code-based-form-fields.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<!--
<table>
<thead>
<tr>
<th><strong>Custom delegation method for subdomains</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>In addition to the full delegation and the CNAME method, a new subdomain configuration method is now available: the Custom delegation method, which enables you to fully own controlling and maintaining all aspects of DNS that are required for delivering, rendering and tracking messages.</p>
</td>
</tr>
</tbody>
</table>
-->

<table>
<thead>
<tr>
<th><strong>Innehållsbeslutsaktivitet på resor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan ni inkludera personaliserade erbjudanden på era resor genom en särskild innehållsbeslutsaktivitet på arbetsytan och använda dem i reseaktiviteter, inklusive villkor och anpassade åtgärder.</p>
<img src="assets/do-not-localize/content-decision.gif">
<p>Den här funktionen är bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet) och kommer att lanseras globalt i en framtida version.</p>
<p>Mer information finns i den <a href="../building-journeys/content-decision.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Körning av resetorr</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Körning på resa Dry är ett särskilt publiceringsläge för resor i Adobe Journey Optimizer som gör det möjligt för resenärer att testa en resa med hjälp av verkliga produktionsdata utan att behöva kontakta riktiga kunder eller uppdatera profilinformation. Den här funktionen hjälper resenärer att få förtroende för sin resedesign och målgruppsanpassning innan de publicerar den live.</p>
<img src="assets/do-not-localize/DryRun.gif">
<p>Den här funktionen är bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet) och kommer att lanseras globalt i en framtida version.</p>
<p>Mer information finns i den <a href="../building-journeys/journey-dry-run.md">detaljerade dokumentationen</a>.</p>

</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Pausa och återuppta resor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du pausa och återuppta dina resor. Denna förmåga ger resenärerna större kontroll och flexibilitet genom att göra det möjligt att tillfälligt avbryta pågående resor utan att störa kundupplevelsen. När det är pausat skickas ingen kommunikation och profilerna förblir i ett uppehåll tills resan återupptas.</p>
<p>Du kan bara pausa och återuppta en resa, eller utföra grupppausningar och återuppta åtgärder på en grupp resor.</p>
<p>Dessutom kan du använda globala filter på pausade resor för att exkludera profiler baserat på deras attribut.</p>
<img src="assets/do-not-localize/PauseResume.gif">
<p>Den här funktionen är bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet) och kommer att lanseras globalt i en framtida version.</p>
<p>Mer information finns i den <a href="../building-journeys/journey-pause.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Skala din vinnare av experiment</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Skala din vinnare av experiment så att du automatiskt eller manuellt kan lansera den vinnande varianten av ett experiment till din fulla publik. Den här funktionen ser till att du när en topprestanda har identifierats kan maximera dess räckvidd och effektivitet utan ständig manuell tillsyn.</p>
<p>Mer information finns i den <a href="../content-management/content-experiment.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 2 juni 2025</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Konflikt och prioritering</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>I Journey Optimizer är det viktigt att hantera kampanjernas och resornas volym och tidpunkter för att undvika överväldigande kunder med alltför många interaktioner. Journey Optimizer har nu flera verktyg för konflikthantering och -prioritering - som tidigare bara fanns för LA-organisationer (limited-access) - som nu är allmänt tillgängliga (GA).</p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer. I den här allmänna tillgänglighetsversionen har följande förbättringar införts:</p>
<ul>
<li>Utökat stöd: Konflikthanteringsverktygen har nu stöd för både Unitary Journeys och Audience Qualification Journeys, utöver Läs målgruppsresor.</li>
<li>Förbättrad felsökning: Det finns nu två nya händelsefält tillgängliga i frågetjänsten, så att du kan analysera varför en profil avvisades från en resa eller kampanj.</li>
<li>Förbättrad rapportering: Rapporterna visar nu vilken specifik regel som uteslöt en profil från en resa eller kampanj, vilket ger större transparens och åtgärdbara insikter.</li></ul>
<img src="assets/do-not-localize/gif-conflict.gif">
<p>Mer information finns i den <a href="../conflict-prioritization/gs-conflict-prioritization.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 3 juni 2025</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar {#25-06-improv}

Förbättringar i den här versionen visas nedan.

* **Kanalregeluppsättningar**

   * **Anpassat varaktighetsfönster** för capping - Ett nytt **Varje**-fält är nu tillgängligt i konfigurationsskärmen för kanalregeluppsättningar, så att du kan tillämpa regler för frekvensbegränsning över flera dagar, veckor eller månader, beroende på den angivna varaktigheten.

   * **Återställa begränsningsfrekvens per timme** - Du kan nu tillämpa begränsning per timme för kanalregeluppsättningar. Den här funktionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta kundtjänst för att aktivera det.

   * **Daglig varaktighet** - Tidigare i begränsad tillgänglighet är frekvensbegränsningen &quot;Dagligen&quot; i kanalregeluppsättningar nu tillgänglig för alla kunder.

  Mer information finns i den [detaljerade dokumentationen](../conflict-prioritization/channel-capping.md).

* **Kodbaserade upplevelser**

   * Det finns nu en beslutsprofil i mallar för kodbaserat upplevelseinnehåll, där den kan användas för att utnyttja erbjudanden i redigerbara formulärfält. [Läs mer](../code-based/code-based-form-fields.md)

   * Från den kodbaserade upplevelseresan eller kampanjutgåvan kan ni nu lägga till en beslutspolicy direkt, utan att behöva öppna personaliseringsredigeraren. [Läs mer](../code-based/create-code-based.md#edit-code)

* **Anpassat CSS-stöd i Designer för e-post**

  Med Journey Optimizer kan du nu lägga till anpassad CSS i e-postinnehåll direkt i e-post-Designer. [Läs mer](../email/custom-css.md)

* **Ny fliknavigering för kampanjer**

  Ett nytt navigeringsmönster ger snabbare åtkomst till innehållsutveckling och stöd för ytterligare expansion av inställningar mellan kampanjer. [Läs mer](../campaigns/create-campaign.md)

* **Beslut**

   * **Sandbox copy &amp; Decisioning** (tillgänglighetsdatum: 3 juni 2025) - Beslutsobjekt kan nu kopieras mellan sandlådor, vilket effektiviserar arbetsflödena för testning och distribution. [Läs mer](../configuration/copy-objects-to-sandbox.md#decisioning)

   * **Stöd för beslutsobjektattribut för beslutsregler** (tillgänglighetsdatum: 4 juni 2025) * Du kan nu använda beslutsobjektattribut för att skapa beslutsregler. [Läs mer](../experience-decisioning/rules.md#create)

* **API-uppdatering för interaktiv meddelandekörning** - tillgänglighetsdatum: 6 juni 2025

  Med API:t för interaktiv meddelandekörning kan du nu ta bort schemat för kommande kampanjkörningar. [Läs mer](https://developer.adobe.com/journey-optimizer-apis/references/messaging/){target="_blank"}


## Versionsinformation 25 maj {#25-5-rn}

<!--**Release date**: May 20-21, 2025-->

### Nya funktioner {#25-05-features}

De nya funktionerna i den här versionen beskrivs nedan.

<table>
<thead>
<tr>
<th><strong>Kalendervy för Kampanj- och Resurslager</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu finns en kalendervy tillgänglig i rese- och kampanjlistorna. Ni kan visualisera alla resor och kampanjaktiveringar i respektive lista.</p>
<p>Den här ändringen är för närvarande bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Använd <a href="https://forms.cloud.microsoft/r/FC49afuJVi" target="_blank">det här formuläret</a> om du vill begära åtkomst.</p>
<img src="assets/do-not-localize/calendar.gif">
<p>Mer information finns i följande avsnitt: <a href="../building-journeys/journey-ui.md">Bläddra och filtrera dina resor</a>, <a href="../campaigns/modify-stop-campaign.md">Åtkomstkampanjer</a>.</p>
<p>Tillgänglighetsdatum: 28 maj 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Integrering av Adobe Experience Manager Content fragment</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Tack vare integreringen av Adobe Experience Manager och Adobe Journey Optimizer kan du nu enkelt använda Adobe Experience Manager Content Fragments i ditt Journey Optimizer-innehåll. Denna smidiga anslutning gör det enklare att komma åt och använda AEM-material direkt i Journey Optimizer.</p>
<p>Den här funktionen, som tidigare fanns för en begränsad uppsättning organisationer (LA), är nu GA med följande förbättring: du kan nu definiera platshållare och mappa personaliseringsvärden inom fragmentsignaturen i redigeringsläget.</p>
<ul>
<!--li>Create offers by directly selecting an AEM Content Fragment.</li>
<li>Define placeholders and map personalization values within the fragment signature using the Editor mode.</li-->
</ul>
</br>
<img src="assets/do-not-localize/content-fragment.gif">
<p>Mer information finns i den <a href="../integrations/aem-fragments.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 23 maj 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Adobe Experience Manager Dynamic Media-integrering</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Dynamiska medieresurser är nu tillgängliga direkt i Journey Optimizer. Integreringen gör att du kan:</p>
<ul>
<li>Hantera resurser centralt med uppdateringar i realtid.</li>
<li>Ändra inställningar för resurser som bredd och höjd direkt.</li>
<li>Anpassa dynamiska mediamallar genom att uppdatera innehållet och lägga till anpassningsfält.</li>
</ul>
</br>
<img src="assets/do-not-localize/dynamic_media_template_html.gif">
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p>Mer information finns i den <a href="../integrations/aem-dynamic.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 23 maj 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Kompletterande ID för händelseutlösta resor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du utlösa resor med ett profil-ID tillsammans med en annan identifierare, till exempel ett order-ID, ett prenumerations-ID eller ett förskrivnings-ID, vilket gör att samma profil kan finnas på samma resa flera gånger samtidigt. Detta möjliggör scenarier som att hantera flera order eller prenumerationer parallellt, där varje instans följer sin egen väg genom resan.</p>
<p>Mer information finns i den <a href="../building-journeys/supplemental-identifier.md">detaljerade dokumentationen</a>.</p>
<p>Den här funktionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
<p>Tillgänglighetsdatum: 23 maj 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Simulera innehållsvariationer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<!--p>Previously available in beta, content variations simulation is now generally available (GA). It allows you to preview different variations of your content using sample input data uploaded from a CSV or JSON file or added manually. All the attributes used in your content for personalization are automatically detected by the system and can be used for your tests to create multiple variants.</p-->
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer. I den här allmänna tillgänglighetsversionen har funktionen nu stöd för flerspråkigt innehåll och innehållsexperiment, vilket gör att du kan testa variationer mellan olika språk och behandlingar. Dessutom har det nu stöd för sammanhangsbaserade attribut (utöver profilattribut), vilket möjliggör ännu mer dynamisk och situationsstyrd innehållstestning.</p>
<img src="assets/do-not-localize/variants.gif">
<p>Mer information finns i den <a href="../test-approve/simulate-sample-input.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 23 maj 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Synkronisera läsmålgruppsschema med batchsegmenteringsjobb</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du utlösa dagliga körningar efter gruppsegmentering. Det här alternativet är nu tillgängligt i dagliga schemalagda resor till alla kunder. Med den kan ni definiera för en tidsperiod på upp till 6 timmar för att vänta på målgruppsdata från batchsegmenteringsjobb, vilket säkerställer att resorna körs med de senaste data eller hoppas över om de inte är klara.</p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<img src="assets/do-not-localize/trigger-journeys.gif">
<p>Mer information finns i den <a href="../building-journeys/read-audience.md#schedule">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 20 maj 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Anpassad SMS-provider</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du konfigurera fler SMS-leverantörer än standardalternativen i Journey Optimizer: Sinch, Infobip och Twilio. Med anpassad SMS-providerkonfiguration kan du integrera tredjepartsleverantörer direkt, utnyttja avancerad anpassning av nyttolasten för dynamiska meddelanden och hantera medgivandeinställningar (anmälan/avanmälan) för att säkerställa regelefterlevnad.</p>
<p>Mer information finns i den <a href="../sms/sms-configuration-custom.md">detaljerade dokumentationen</a>.</p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p>Tillgänglighetsdatum: 20 maj 2025</p>
</td>
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
<p>Nu kan ni snabbt tillämpa förgodkända teman för att säkerställa ett enhetligt varumärke i alla e-postmeddelanden, snabba upp kampanjprocessen och oberoende producera högkvalitativa e-postmeddelanden samtidigt som ni minskar beroendet av designteam.</p>
<p>Funktionen finns för närvarande i betaversion och är endast tillgänglig för betatestare. Kontakta din Adobe-representant om du vill delta i betaprogrammet.</p>
<img src="assets/do-not-localize/themes.gif">
<p>Mer information finns i den <a href="../email/apply-email-themes.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 14 maj 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Beslut - ny AI-formelbyggare</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du skapa särskilda bedömningsformler genom att definiera och kombinera villkor från ett nytt förbättrat gränssnitt. I stället för att bara förlita dig på en statisk erbjudandeprioritet kan du definiera anpassade rankningsformler som kombinerar AI-modellpoäng, erbjudandeprioriteringar, profilattribut, erbjudandeattribut och sammanhangsbaserade signaler via ett guidat gränssnitt.</p>
<img src="assets/do-not-localize/formula-builder.gif">
<p>Mer information finns i den <a href="../experience-decisioning/ranking/ranking-formulas.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 14 maj 2025</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar {#25-05-improv}

Förbättringar i den här versionen visas nedan.


* **Nytt kampanjobjekt har stöd för sandlådekopia** - Tillgänglighetsdatum: 15 maj 2025

  När du kopierar kampanjer i flera sandlådor med hjälp av funktionerna för paketexport och -import kopieras nu även följande beroenden: kanalkonfigurationer, experimentera med varianter och inställningar, beslutsprinciper och objekt. [Läs mer](../configuration/copy-objects-to-sandbox.md)

* **Mappar för landningssidor** - Tillgänglighetsdatum: 9 maj 2025

  För att enkelt hantera dina landningssidor kan du nu använda mappar för att ordna dem mer effektivt i en strukturerad hierarki. [Läs mer](../landing-pages/manage-lp.md)

* **Direktreklam: Stöd för SSH-nyckel för SFTP-anslutningar** - Tillgänglighetsdatum: 5 maj 2025

  Förutom den befintliga SFTP-servern med lösenordsautentiseringstypen kan du nu exportera din direktmeddelandefil till en SFTP-server med SSH-nyckelautentisering i konfigurationen för filroutning för direkt e-post. [Läs mer](../direct-mail/direct-mail-configuration.md)

* **Fyller i aktivering för personalisering** - Tillgänglighetsdatum: 5 maj 2025

  En ny Pills-knapp har lagts till i personaliseringsredigeraren. När det här alternativet är aktiverat visas profil- och kontextuella attribut som tabletter, vilket förbättrar läsbarheten för koden. [Läs mer](../personalization/personalization-build-expressions.md#options)

  >[!AVAILABILITY]
  >
  >Denna kapacitet kommer gradvis att byggas ut till alla miljöer under de kommande 30 dagarna.

* **&#39;Stöd för omdirigering till URL&#39; i webbkanal** - Tillgänglighetsdatum: 20 maj 2025

  Journey Optimizer webbkanal ger dig nu möjlighet att dirigera om besökare till en annan befintlig URL i stället för att skapa en ny variant i den visuella redigeraren. Den här funktionen kan användas för att experimentera med två helt olika sidor i stället för att bara ändra ett fåtal element på en sida. [Läs mer](../web/create-web.md#web-redirect-to-url)

* **Mappar för mallar och fragment** - Tillgänglighetsdatum: 20 maj 2025

  Med mappar kan du ordna dina objekt enklare och effektivare i en strukturerad hierarki. Tidigare var mappar tillgängliga för en uppsättning organisationer (LA), och nu är de tillgängliga för alla användare (GA) att hantera sina innehållsmallar och fragment. Läs mer i avsnitten [Innehållsmallar](../content-management/access-content-templates.md#folders) och [Fragment](../content-management/manage-fragments.md#folders) .

* **Klickspårning i e-postmallar** - Tillgänglighetsdatum: 20 maj 2025

  Klickspårning på `<area>` element i bildscheman i e-postinnehåll stöds nu internt i [!DNL Journey Optimizer]. Detta är för att säkerställa att bildschemaområden får samma spårningsomslutning, spårningsdata och tillagda parametrar som standardhyperlänkar. [Läs mer om meddelandespårning](../email/message-tracking.md#manage-tracking)

<!--
* **Decisioning - Leverage Adobe Experience Platform datasets** 
  
  Journey Optimizer now allows you to leverage Adobe Experience Platform datasets in the following Decisioning objects: eligibility rules, ranking formulas, and capping rules.-->

* **Högerspåret i kampanjlistan** - Tillgänglighetsdatum: 20 maj 2025

  Om du väljer en kampanj i kampanjlistan öppnas nu en ruta med information om kampanjen.

<!--* **Form fields in code-based experience content**

  In content templates, you can now define specific JSON or HTML fields which enable non-technical users to easily edit content in code-based experiences without the need to manipulate code.-->

<!--* **Subdomains - 'Custom delegation' method**  
  In addition to the full delegation and the CNAME method, a new subdomain configuration method is now available: the Custom delegation method, which enables you to fully own controlling and maintaining all aspects of DNS that are required for delivering, rendering, and tracking messages.
  -->



## Versionsinformation 25 april {#25-4-rn}

**Releasedatum**: 29-30 april 2025

### Nya funktioner {#25-04-features}

Nya funktioner i den här versionen visas nedan.

<table>
<thead>
<tr>
<th><strong>Personalization Editor - Learn by Doing</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu finns det en personaliseringsmiljö där du kan experimentera med personaliseringsuttryck. Du kan utforska exempelmallar och nyttolaster för att komma igång och testa dina egna personaliseringsuttryck.</p>
<p>Mer information finns i den <a href="../personalization/personalize.md#playground">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 24 april 2025</p>
<img src="assets/do-not-localize/templating-playground.gif"/>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Adobe Experience Manager as a Cloud Service integration</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The integration between Adobe Journey Optimizer and Adobe Experience Manager as a Cloud Service is now released in General Availability (GA). This integration enables seamless content sourcing and management for personalized customer journeys.</p>
<p>For more information, refer to the <a href="../integrations/aem-templates.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table-->

<!--<table>
<thead>
<tr>
<th><strong>Simulate content variations (General Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Previously available in beta, content variations simulation is now generally available (GA). It allows you to preview different variations of your content using sample input data uploaded from a CSV or JSON file or added manually. All the attributes used in your content for personalization are automatically detected by the system and can be used for your tests to create multiple variants.</p>
<p>With the General Availability release, the feature now includes support for multilingual content and content experiments, enabling you to test variations across different languages and treatments. Additionally, it now supports contextual attributes (in addition to profile attributes), allowing for even more dynamic and situational content testing.</p>
<img src="assets/do-not-localize/variants.gif">
</td>
</tr>
</tbody>
</table>-->

<table>
<thead>
<tr>
<th><strong>LINE-kanal</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer har utökat sina flerkanalsfunktioner så att de har stöd för LINE-kanalen. Den här förbättringen gör att du kan skapa, redigera och förhandsgranska LINE-upplevelser, vilket möjliggör mer personaliserade och engagerande interaktioner. Med LINE kan ni få kontakt med fler kunder, skicka relevant innehåll och förbättra engagemanget.</p>
<p>LINE-kanalen aktiveras på begäran av Adobe Journey Optimizer-kunder. Kontakta Adobe kundtjänst eller en Adobe-representant för att aktivera funktionen för din organisation.</p>
<p>Mer information finns i den <a href="../../rp_landing_pages/line-landing-page.md">detaljerade dokumentationen</a>.</p></td>
</tr>
</tbody>
</table>


<!--table>
<thead>
<tr>
<th><strong>Custom SMS provider (General Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer now supports custom SMS providers, allowing you to integrate your preferred SMS services for enhanced communication flexibility.</p>
<p>For more information, refer to the <a href="../sms/sms-configuration-custom.md">detailed documentation</a>.</p></td>
</tr>
</tbody>
</table-->


<table>
<thead>
<tr>
<th><strong>Resemått</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu finns det resestatistik som gör det möjligt att mäta effekten av dina aktiviteter över nyckeltalen i ditt företag och att ge tydligare insikter i hur det fungerar.</p>
</br>
<img src="assets/do-not-localize/success-metric.gif"/>
<p>Mer information finns i den <a href="../building-journeys/success-metrics.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 9 april 2025</p>
</td>
</tr>
</tbody>
</table>



<!--<table>
<thead>
<tr>
<th><strong>Calendar view for campaign and journey inventory (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>A new calendar view is now available for campaigns and journey activations. This feature provides a visual representation of scheduled activities, allowing you to view and manage your campaigns and journeys more effectively. Selecting a calendar item opens a right rail with detailed information. This feature is currently in Limited Availability.</p>
<img src="assets/do-not-localize/calendar.gif">
</td>
</tr>
</tbody>
</table>-->

<table>
<thead>
<tr>
<th><strong>Adobe Express-integrering (begränsad tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer kan nu integreras med Adobe Express så att ni smidigt kan koppla samman ert kreativa material med resesamordning. Den här integreringen förenklar processen att utforma och distribuera personaliserat innehåll mellan kampanjer. </p>
<p>Denna integrering är för närvarande inte tillgänglig för användning med hälso- och sjukvårdsskölden eller skölden för skydd av privatlivet och säkerheten.</p>
<img src="assets/do-not-localize/express_resize.gif">
<p>Mer information finns i den <a href="../integrations/express.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Utlös den dagliga resan efter gruppsegmentering (begränsad tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>För dagliga schemalagda resor kan du med ett nytt alternativ definiera ett tidsintervall på upp till 6 timmar för att vänta på målgruppsdata från batchsegmenteringsjobb, vilket säkerställer att resorna körs med de senaste data eller hoppas över om de inte är klara. Utlösaren efter grupputvärdering är bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
<p>Mer information finns i den <a href="../building-journeys/read-audience.md#schedule">detaljerade dokumentationen</a>.</p>
<img src="assets/do-not-localize/trigger-journeys.gif">
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Themes in the Email Designer (Beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now quickly apply pre-approved styling themes to your email content to ensure brand consistency across all emails, speed up your campaign creation process and independently produce hight-quality emails while reducing dependency on design teams.</p>
<p>This capability is currently in beta version and only available to beta customers. To join the beta program, contact your Adobe representative.</p>
<p>For more information, refer to the <a href="../content-management/brands-score.md">detailed documentation</a>.</p>
<img src="assets/do-not-localize/themes.gif">
<p>Availability date: May 5, 2025</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>Poäng för varumärkesjustering (Beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med funktionen för varumärkesjustering får du tydlig feedback direkt i e-postprogrammet Designer, som hjälper dig att se om ditt innehåll överensstämmer med varumärkets ton, stil och riktlinjer. Den här funktionen är tillgänglig i Beta.</p>
<p>Mer information finns i den <a href="../content-management/brands-score.md">detaljerade dokumentationen</a>.</p>
<img src="assets/do-not-localize/brand-score.gif">
</td>
</tr>
</tbody>
</table>

<!--
<table>
<thead>
<tr>
<th><strong>Decisioning - New AI formula builder</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now create specific Decisioning ranking formulas by defining and combining criteria from a new improved interface. Ranking formulas allow you to define rules that will determine which decision items should be presented first, rather than taking into account the priority scores.</p>
<p>For more information, refer to the <a href="../content-management/brands-score.md">detailed documentation</a>.</p>
<img src="assets/do-not-localize/formula-builder.gif">
<p>Availability date: May 5, 2025</p>
</td>
</tr>
</tbody>
</table>
-->

### Förbättringar {#25-04-improv}

**API för förhandsgranskning av kampanjer**

Det finns nya API:er för att förhandsgranska kampanjer, utöver befintliga funktioner för att skicka korrektur. [Läs mer](https://developer.adobe.com/journey-optimizer-apis/references/simulations/#operation/createCampaignPreview){target="_blank"}.

**Verktyg för sandlåda**

* **Verktyg i sandlådan för anpassade åtgärder**

  Anpassade åtgärder ingår nu i listan över Adobe Journey Optimizer-objekt som kan kopieras med sandlådeverktygen, vilket effektiviserar testning och driftsättning. [Läs mer](../configuration/copy-objects-to-sandbox.md)

* **Sandlådeverktyg för kampanjer** - Tillgänglighetsdatum: 3 april 2025

  Nu kan ni kopiera kampanjer över flera sandlådor med hjälp av funktioner för paketexport och -import. Kampanjer kopieras tillsammans med alla objekt som hör till profilen, målgruppen, schemat, textbundna meddelanden och beroende objekt. Vissa objekt kopieras inte, t.ex. beslutsobjekt, dataanvändningsetiketter och språkinställningar. [Läs mer](../configuration/copy-objects-to-sandbox.md#custom-actions)

**Personalization**

* **Nytt sammanhangsberoende attribut**

  Ett nytt sammanhangsberoende attribut, **Profil-ID**, är nu tillgängligt att välja i personaliseringsredigeraren. Det här är ett meddelandeorienterat attribut som unikt identifierar varje meddelande som skickas till varje målprofil i en leverans. Den här unika identifieraren kan till exempel användas som en URL-spårningsparameter för att särskilja varje länk som öppnats eller klickats av mottagarna.

* **Fyllda attribut i attributrutan** - Tillgänglighetsdatum: 2 april 2025

  Attributrutan i anpassningsredigeraren visar nu endast ifyllda attribut som standard. Om du vill visa alla attribut använder du inställningsknappen för att inaktivera alternativet **[!UICONTROL Show only populated attributes]**. [Läs mer](../personalization/personalization-build-expressions.md)

**E-postkanal**

* **Anpassad URL-spårning** - Tillgänglighetsdatum: 30 april 2025

  För ökad flexibilitet och kontroll över e-postinställningarna kan du nu anpassa alla URL-spårningsparametrar samtidigt på e-postkanalens konfigurationsnivå, i stället för att göra det i e-post-Designer för varje länk i ditt innehåll. [Läs mer](../email/surface-personalization.md#personalize-url-tracking)

* **E-posta Designer** - Tillgänglighetsdatum: 1 april 2025

  För att förbättra tillgängligheten i Journey Optimizer finns nu två nya fält tillgängliga i e-post-Designer: de motsvarar elementet `<title>` och attributet `lang` i elementet `<html>` i ditt e-postinnehåll. Du kan definiera dessa inställningar utöver fältet **[!UICONTROL Preheader]** i e-postavsnittet **[!UICONTROL Body]**. [Läs mer](../email/email-metadata.md)

**Använd fallspelningsböcker**

* **Skapa och dela spelböcker (privat beta)** - Nu kan du skapa, hantera och dela egna fallspelningsböcker. Den här funktionen är för närvarande bara tillgänglig för en uppsättning organisationer som en privat betaversion. Kontakta din Adobe-representant för att få åtkomst. [Läs mer](../start/playbooks.md)

**Navigering**

* **Innehållshantering** - Tillgänglighetsdatum: 2 april 2025

  För att enkelt hantera dina innehållsmallar och fragment kan du nu använda mappar för att ordna dem mer effektivt i en strukturerad hierarki. Läs mer i avsnitten [Innehållsmallar](../content-management/access-content-templates.md#folders) och [Fragment](../content-management/manage-fragments.md#folders).

  >[!AVAILABILITY]
  >
  >Den här förbättringen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet).

<!--- **Folders for content templates and fragments** - Availability date: May 5, 2025

  Previously available for a set of organizations (LA), folders are now available to all users (GA) to manage their content templates and fragments. Folders let you organize your content templates and fragments more easily and effectively into a structured hierarchy.



<!--- **Right rail in campaigns list**  

  A right rail has been added to the campaigns list, providing detailed information when a campaign is selected.-->

<!--**Playbooks**

- **Create your own playbooks (Beta)**
  
  You can now create your own playbooks in Adobe Journey Optimizer, enabling greater customization and flexibility in journey planning.-->



## Versionsinformation 25 mars {#25-3-rn}

### Nya funktioner {#25-03-features}

De nya funktionerna i den här versionen beskrivs nedan.

<!--table>
<thead>
<tr>
<th><strong>Integration with Adobe Express (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The Adobe Express integration in Adobe Journey Optimizer lets you use Adobe Express's editing tools directly during content creation, enabling you to resize, remove backgrounds, crop, and convert assets to JPEG or PNG.<p>
<p>Adobe Express integration in Adobe Journey Optimizer is currently only available for a set of organizations (Limited Availability). It cannot be deployed for use with Healthcare Shield or Privacy and Security Shield.</p>
<p>For more information, refer to the <a href="../integrations/express.md">detailed documentation</a>.</p>
</br>
<img src="assets/do-not-localize/express_resize.gif"/>
</td>
</tr>
</tbody>
</table-->


<!--table>
<thead>
<tr>
<th><strong>Journey metrics</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey metrics are now available, allowing you to measure the impact of your activities across the key metrics of your business and to provide clearer insights into your performance.</p>
<p>For more information, refer to the <a href="../building-journeys/success-metrics.md">detailed documentation</a>.</p>
<img src="assets/do-not-localize/success-metric.gif"/>
</td>
</tr>
</tbody>
</table-->

<!-- table>
<thead>
<tr>
<th><strong>Calendar view for journeys (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>A calendar view is now available in Journey Optimizer to visualize all journeys activations. From this view, you can browse your journeys and check details and properties.<p>
<p>This change is only available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.</p>
<p>For more information, refer to the <a href="../conflict-prioritization/rule-sets.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>Integrering med Dynamic Media (begränsad tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Dynamiska medieresurser är nu tillgängliga direkt i Journey Optimizer. Integreringen gör att du kan:
<ul>
<li>Hantera resurser centralt med uppdateringar i realtid</li>
<li>Ändra inställningar för resurser som bredd och höjd direkt</li>
<li>Anpassa dynamiska mediamallar genom att uppdatera innehållet och lägga till anpassningsfält</li>
</ul>
<p>
<p>Den här integreringen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
<p>Mer information finns i den <a href="../integrations/aem-dynamic.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>



<table>
<thead>
<tr>
<th><strong>Integrering med Adobe GenStudio (begränsad tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>För att effektivisera marknadsföringen och bibehålla varumärkets enhetlighet kan ni nu smidigt integrera GenStudio for Performance Marketing-upplevelser med Journey Optimizer. På så sätt kan du utnyttja GenStudio AI-kraftfulla funktioner för att skapa innehåll tillsammans med Journey Optimizer avancerade orkestreringsfunktioner.<p>
<p>Användningen av GenStudio integrering i Journey Optimizer är för närvarande inte tillgänglig för användning med hälso- och sjukvårdsskölden eller skölden för skydd av privatlivet och säkerheten (begränsad tillgänglighet).</p>
<p>Mer information finns i den <a href="../integrations/genstudio.md">detaljerade dokumentationen</a>.</p>
<img src="assets/do-not-localize/genstudio.gif"/>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Flexibel målgruppsutvärdering (GA)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Tidigare fanns en uppsättning organisationer (LA), och nu är alla användare (GA) tillgängliga för att utvärdera den flexibla målgruppen. Med den här funktionen kan ni köra ett segmenteringsjobb på begäran för utvalda målgrupper, vilket säkerställer att ni alltid har de senaste målgruppsdata innan ni kan inrikta er på dem på Journey Optimizer resor och kampanjer.</p>
<img src="assets/do-not-localize/flexible-audience.gif">
<p>Mer information finns i den <a href="../audience/creating-a-segment-definition.md#flexible">detaljerade dokumentationen</a>.</p>
</tr>
</tbody>
</table>
</table>

<!--table>
<thead>
<tr>
<th><strong>LINE channel (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer has expanded its cross-channel capabilities to include support for the LINE channel. This enhancement allows you to create, edit, and preview LINE experiences enabling more personalized and engaging interactions. With LINE, you can connect with more customers, send relevant content, and improve your engagement.<p>
<p>This capability is only available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.</p>
<p>For more information, refer to the <a href="../conflict-prioritization/rule-sets.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table-->


### Förbättringar {#25-03-improv}

**Personalization-redigerare** (tillgänglighetsdatum: 12 mars)

Journey Optimizer personaliseringsredigerare har uppdaterats med nya funktioner:
* **Uppdaterad design för kodredigeraren** - ett renare och modernt gränssnitt för förbättrad användbarhet och fokus.
* **Sök och ersätt** - Funktioner har lagts till för att snabbt hitta och ersätta innehåll i redigeraren.
* **Stöd för Ångra och Gör om** - Gör det enkelt att ångra eller göra om ändringar.
* **Anpassningsbar teckensnittsstorlek** - Aktiverar justering av redigerarens teckensnittsstorlek för bättre läsbarhet.
* **Inline JSON-validering** - Tillhandahåller realtidsvalidering på klientsidan för JSON-innehåll för att påskynda felidentifieringen.
* **Komplettera automatiskt för profil- och kontextattribut** - erbjuder smarta förslag för att effektivisera skapandet av innehåll.
* **Förbättrad syntaxmarkering** - Förbättrar läsbarheten genom att göra kodstrukturen mer visuellt tydlig.

![Video med den nya funktionen i Personalization Editor](assets/do-not-localize/personalization-editor.gif)

Mer information finns i den [detaljerade dokumentationen](../personalization/personalization-build-expressions.md).

**Godkännanden**

När du definierar villkoren för en godkännandeprincip kan du nu välja att filtrera efter tagg och/eller objektkategori.

Mer information finns i den [detaljerade dokumentationen](../test-approve/approval-policies.md).

**Konfiguration**

* Nu kan du tilldela enhetliga Adobe Experience Platform-taggar till kanalkonfigurationer. På så sätt kan du enkelt klassificera dem och förbättra sökning och navigering i alla listor. [Läs mer](../configuration/channel-surfaces.md#channel-config-tags)

* När du konfigurerar eller redigerar en e-postunderdomän i Journey Optimizer kan du nu välja att hantera den associerade DMARC-posten på egen hand, om den är tillgänglig på den överordnade domänen. [Läs mer](../configuration/dmarc-record.md#set-up-dmarc)

**Affärsregler**

Nu kan ni använda daglig frekvensbegränsning i resor och kampanjer med batchsegmentering. Se till att du väljer det namnutrymme som har högst prioritet när du skapar en kampanj eller resa, så att reglerna för den dagliga takten är korrekta. Läs mer om namnområdesprioritet i [Handboken för Platform Identity Service](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/namespace-priority){target="_blank"}

Som påminnelse är den dagliga frekvensbegränsningen i regeluppsättningar bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.

Mer information om affärsregler finns i [detaljerad dokumentation](../conflict-prioritization/rule-sets.md).

**Innehållsmallar**

HTML-mallar för typograferat innehåll är nu föråldrade. Observera att du fortfarande kan använda befintliga HTML-innehållsmallar som tidigare skapats i [!DNL Journey Optimizer]. [Läs mer om innehållsmallar](../content-management/content-templates.md)


<!--**Deliverability**

You can now choose to have your emails relayed to your SMTP servers instead of being sent directly from Journey Optimizer to ISPs. This allows you to route final email deliveries through your own Mail Transfer Agents and IPs, or to perform final validations on the emails before sending them to your recipients. The SMTP relay capacity is available on demand - contact your Adobe representative.-->




## Versionsinformation 25 februari {#25-02-rn}

**Releasedatum**: 18-19 februari 2025


### Nya funktioner {#25-02-features}

De nya funktionerna i den här versionen beskrivs nedan.

<table>
<thead>
<tr>
<th><strong>Skapa och hantera affärsregler</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du skapa affärsregler med hjälp av regeluppsättningar. Regeluppsättningar är grupper av regler som hjälper er att begränsa skickade meddelanden inom kampanjer och reseåtgärder över flera kanaler, och att kontrollera profilinmatningar under resor.<p>
<p><ul><li>Skapa kanalregeluppsättningar för att begränsa antalet meddelanden som skickas över en eller flera kanaler. Använd dem på kampanjer eller reseåtgärder för att tillämpa de regler som definieras i regeluppsättningen. Med kanalregeluppsättningen kan du tillämpa regler för appning baserat på kommunikationstyper. Ange till exempel en regeluppsättning som begränsar"kampanjmeddelanden" och en annan för"nyhetsbrev". Använd rätt regeluppsättning i kampanjen eller reseåtgärden beroende på vilken typ av kommunikation du skickar.</li>
<li> Skapa uppsättningar av resegler för att styra profilposter till resor. Begränsa hur ofta en profil kan ta sig in på en resa inom en viss period eller hur många resor en profil kan registreras samtidigt. Använd dessa på resenivå för att säkerställa en korrekt hantering av inträde på arbetsmarknaden.</li></ul></p>
<p>Affärsreglerna fanns tidigare för en uppsättning organisationer (LA) och är nu tillgängliga för alla användare (GA). Affärsreglerna för resedomäner är fortfarande bara tillgängliga för ett begränsat antal organisationer (LA).</p>
<p>Mer information finns i den <a href="../conflict-prioritization/rule-sets.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Generera landningssidor med AI Assistant</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med hjälp av AI Assistant kan du nu skapa övertygande innehåll för landningssidor, inklusive helsidesdesign, skräddarsydd text och anpassade bilder.</p>
<img src="assets/do-not-localize/ai-lp.gif">
<p>Mer information finns i den <a href="../content-management/generative-lp.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Varumärken med AI Assistant (Beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan ni skapa egna varumärken för att definiera ert varumärkes visuella och verbala identitet. </p>
<p>Den här funktionen lanseras som en privat betaversion för en begränsad uppsättning kunder. Den kommer att finnas tillgänglig successivt för alla kunder i framtida versioner.</p>
<p>Mer information finns i den <a href="../content-management/brands.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Felsöka anpassade åtgärder</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du validera en anpassad åtgärdskonfiguration genom att göra riktiga API-anrop direkt från Adobe Journey Optimizer. Den här nya funktionen hjälper dig att felsöka anpassade åtgärder före eller efter det att du har använt dem under en resa. </p>
<p>Mer information finns i den <a href="../action/troubleshoot-custom-action.md">detaljerade dokumentationen</a>.</p>
<!--p> This capability is only available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.</p-->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Flexibel utvärdering av målgruppen (begränsad tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med flexibel målgruppsutvärdering kan ni köra ett segmenteringsjobb på begäran för utvalda målgrupper, vilket säkerställer att ni alltid har de senaste målgruppsdata innan ni inriktar dem på Journey Optimizer resor och kampanjer.</p>
<img src="assets/do-not-localize/flexible-audience.gif">
<p>Mer information finns i den <a href="../audience/creating-a-segment-definition.md#flexible">detaljerade dokumentationen</a>.</p>
<p>Den här funktionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
<p>Tillgänglighetsdatum: 28 januari 2025</p>
</tr>
</tbody>
</table>
</table>


### Förbättringar {#25-02-improvements}

Förbättringarna nedan följer med uppdateringen från februari.

* **Datauppsättning TTL (Time-to-live)** - Från och med den här månaden kommer ett TTL-skyddsprotokoll att introduceras i Journey Optimizer systemgenererade datauppsättningar i nya sandlådor och nya orgs enligt följande:

   * 90 dagar för data i profilarkivet
   * 13 månader för data i sjön

  Den här ändringen kommer att introduceras i befintliga kundsandlådor i en efterföljande fas.

  Läs mer om den här uppdateringen i [de dedikerade vanliga frågorna](../data/datasets-ttl.md#frequently-asked-questions).

<!--* **Playbooks** - You can now create and publish your own Use Case Playbooks in Journey Optimizer.-->

* **Direktutskick** - En ny servertyp, Datalandningszon, stöds nu för filroutning i konfigurationen för direktutskick. [Läs mer](../direct-mail/direct-mail-configuration.md#file-routing-configuration)

* **SMS** - Nu kan du hantera SMS-meddelandeleverans från flerregionala slutpunkter genom att åsidosätta URL:er för leverans, feedback, inkommande och återanrop. För att detta ska fungera har en ny åsidosättnings-URL lagts till i konfigurationen för API-autentiseringsuppgifter. Den här ändringen är endast tillgänglig för SINK-providern. [Läs mer](../sms/sms-configuration-sinch.md)

* **Personalization** (Tillgänglighetsdatum: 29 januari 2025) - Det finns nya hjälpfunktioner för datum/tid som kan användas i personaliseringsredigeraren. [Läs mer](../personalization/functions/dates.md)


<!--
* The personalization editor has been enhanced with new capabilities such as Auto-complete, Search, and filtering options. You can also show or hide deprecated attributes.-->


* **E-postkonfiguration** - Om du hanterar samtycke utanför Adobe kan du nu ange en anpassad e-postadress för att avbryta prenumerationen och en anpassad URL för att avbryta prenumerationen som en del av konfigurationsinställningarna för e-postkanalen. [Läs mer](../email/list-unsubscribe.md#custom-managed)

  ![](../email/assets/surface-list-unsubscribe-custom.png){width="80%"}

* **Beslut** (Tillgänglighetsdatum: 28 januari 2025) - Beslut stöder nu objekttyper när objektkatalogens schema redigeras. [Läs mer](../experience-decisioning/catalogs.md)
