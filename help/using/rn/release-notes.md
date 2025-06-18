---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
topic: Content Management
description: Versionsinformation om Adobe Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 25b1e6050e0cec3ae166532f47626d99ed68fe80
workflow-type: tm+mt
source-wordcount: '2050'
ht-degree: 7%

---

# Versionsinformation {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="Nyheter?"
>abstract="**Adobe Journey Optimizer** levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen."

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen. [!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver från de senaste innovationerna och förbättringarna. Läs mer om de här ändringarna i [Adobe Experience Platform versionsinformation](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=sv-SE){target="_blank"}.


## Versionsinformation 25 juni {#25-6-rn}

<!--
**Early release notes below are subject to change without prior notice until the release availability date**. Links, screens and updated documentation are published at the release date.-->

**Releasedatum**: 18 juni 2025

<!--See also [Adobe Experience Platform Pre Release Notes](https://experienceleague.adobe.com/sv/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.-->

### Nya funktioner {#25-06-features}

De nya funktionerna i den här versionen beskrivs nedan.


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
<!--p>For more information, refer to the <a href="../sms/sms-configuration.md">detailed documentation</a>.</p-->
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
<p>Nu kan ni inkludera personaliserade erbjudanden på era resor med en dedikerad Content Decisioning-aktivitet på arbetsytan och använda dem i reseaktiviteter, inklusive villkor och anpassade åtgärder.</p>
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

<!--* **Channel rule sets**

  * **Custom duration window** for capping -  A new **Repeat Count** field is now available in the channel rule sets configuration screen, allowing you to apply frequency capping rules over multiple days, weeks, or months, depending on the specified duration.

  * **Hourly duration** - You can now apply capping on an hourly basis for channel rule sets.    -->

* **Kodbaserade upplevelser**

   * Det finns nu en beslutsprofil i mallar för kodbaserat upplevelseinnehåll, där den kan användas för att utnyttja erbjudanden i redigerbara formulärfält. [Läs mer](../code-based/code-based-form-fields.md)

   * Från den kodbaserade upplevelseresan eller kampanjutgåvan kan ni nu lägga till en beslutspolicy direkt, utan att behöva öppna personaliseringsredigeraren. [Läs mer](../code-based/create-code-based.md#edit-code)

* **Anpassat CSS-stöd i Designer för e-post**

  Med Journey Optimizer kan du nu lägga till anpassad CSS i e-postinnehåll direkt i e-post-Designer. [Läs mer](../email/custom-css.md)

* **Ny fliknavigering för kampanjer**

  Ett nytt navigeringsmönster ger snabbare åtkomst till innehållsutveckling och stöd för ytterligare expansion av inställningar mellan kampanjer. [Läs mer](../campaigns/create-campaign.md)

* **Beslut** - Tillgänglighetsdatum: 3 juni 2025

  Beslutsobjekt kan nu kopieras mellan sandlådor, vilket effektiviserar arbetsflödena för testning och distribution. [Läs mer](../configuration/copy-objects-to-sandbox.md#decisioning)

* **Stöd för beslutsobjektattribut för beslutsregler** - Tillgänglighetsdatum: 4 juni 2025

  Nu kan du använda attribut för beslutsobjekt för att skapa beslutsregler. [Läs mer](../experience-decisioning/rules.md#create)

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
<p>Mer information finns i den <a href="../experience-decisioning/exd-ranking-formulas.md">detaljerade dokumentationen</a>.</p>
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

