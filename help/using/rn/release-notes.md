---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
role: User
level: Beginner, Intermediate
description: Versionsinformation om Adobe Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: d65590d3fdcec91470d93d385c6a706e17a0d561
workflow-type: tm+mt
source-wordcount: '1551'
ht-degree: 7%

---

# Versionsinformation {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="Nyheter?"
>abstract="**Adobe Journey Optimizer** levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen."

[!DNL Adobe Journey Optimizer] följer en kontinuerlig leveransmodell som gör att Adobe kan leverera nya funktioner, förbättringar och korrigeringar kontinuerligt. Detta tillvägagångssätt möjliggör en skalbar, fasad driftsättning av funktioner för att säkerställa prestanda och stabilitet i alla miljöer.

På grund av den här modellen uppdateras versionsinformationen mellan månadsversionerna. Fullständig information om frisläppningscykeln och tillgänglighetsfaserna finns i [Journey Optimizer versionscykel](releases.md).

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver från de senaste innovationerna och förbättringarna. Läs mer om de här ändringarna i [Adobe Experience Platform versionsinformation](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=sv-SE){target="_blank"}.

## Versionsinformation 26 mars {#march-26-rn}

Avsnitten [Nya funktioner](#march-26-features) och [Förbättringar](#march-26-improv) omfattar funktioner som redan är tillgängliga. Avsnittet [Kommer snart](#coming-soon) innehåller funktioner och förbättringar som är planerade att släppas senare i mars.

<!--
**The pre-release notes below are subject to change without prior notice until the release availability date**. Links, screens and updated documentation are published in the release notes, at the release date.

See also [Adobe Experience Platform pre-release notes](https://experienceleague.adobe.com/sv/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.-->

**Releasedatum**: 24-25 mars 2026

### Nya funktioner {#march-26-features}

<table>
<thead>
<tr>
<th><strong>Testaktivitet i samordnade kampanjer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>En ny <strong>Test</strong>-aktivitet är nu tillgänglig i Orchestrated Campaigns. Den här aktiviteten dirigerar arbetsflödeskörningen till olika grenar baserat på definierade villkor, vilket gör att du kan validera kampanjlogik och konfigurationer innan du aktiverar liveleveranser.</p>
<p><img src="../orchestrated/assets/test-1.png"></p>
<p>Mer information finns i den <a href="../orchestrated/activities/test.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Stöd för datauppslagssökning på resor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med en ny aktivitet på resorna, Dataset Lookup, kan du dynamiskt hämta data från Adobe Experience Platform postdatauppsättningar under körning. Genom att utnyttja den här funktionen kan ni få tillgång till data som kanske inte finns i profilen eller händelsens nyttolast, vilket säkerställer att era kundinteraktioner är både relevanta och aktuella. Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet). </p>
<p><img src="../building-journeys/assets/aep-data-activity.png"></p>
<p>Mer information finns i den <a href="../building-journeys/dataset-lookup.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Åtgärdsaktiviteter för inbyggda kanaler har tagits bort</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Efter den allmänna tillgängligheten för aktiviteten <strong>Åtgärd</strong> i februari 2026 har tidigare inbyggda kanalaktiviteter (e-post, push, SMS, in-app, webb, kodbaserad upplevelse och innehållskort) på arbetsytan nu tagits bort.</p>
<p>Du använder nu en enda <strong>åtgärdsaktivitet</strong> för att konfigurera alla kanalåtgärder och ersätta behovet av separata kanalspecifika noder.
Befintliga resor som använder äldre kanalaktiviteter fortsätter att fungera utan några ändringar eller migrering.</p>
<p><img src="assets/do-not-localize/action-activity.gif"></p>
<p>Mer information finns i den <a href="../building-journeys/journey-action.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<!--<table>
<thead>
<tr>
<th><strong>Decisioning support in email channel</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now use <strong>Decisioning</strong> to personalize and optimize the content of your email messages. Leverage Priority Scores, Formulas, or AI Models to display the most relevant offers and content to each recipient.</p>
<p>Previously released in Limited Availability, this capability is now available to all environments (General Availability). With this General Availability release, mirror pages are now supported.</p>
<p><img src="assets/do-not-localize/exd-email.gif"></p>
<p>For more information, refer to the <a href="../experience-decisioning/create-decision-policy.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>-->



<table>
<thead>
<tr>
<th><strong>Avancerad HTML-editor för e-postmallar</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med det avancerade HTML-läget för mallar för e-postinnehåll kan du redigera HTML-källan för ditt innehåll i e-postprogrammet Designer, lägga till avancerade uttryck (t.ex. villkor) i källan och växla mellan HTML-vyn och skrivbordsvyn utan att ändringarna går förlorade.</p>
<p>Den här funktionen är endast tillgänglig i innehållsmallar för e-postkanalen. Det finns för närvarande i begränsad tillgänglighet - kontakta din Adobe-representant för att få åtkomst.</p>
<p><img src="assets/do-not-localize/expert-mode.gif"/></p>
<p>Mer information finns i den <a href="../content-management/email-template-expert-mode.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 10 mars 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Integrering av anpassade Firefly-modeller och tredjepartsmodeller för bildgenerering</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Möjliggör smidig integrering av standardmodeller och anpassade Firefly-modeller, tillsammans med godkända bildmodeller från tredje part, för att ge större flexibilitet, kontroll och varumärkesanpassning vid generering av bilder.</p>
<p>Välj rätt modell för dina behov:</p>
<ul><li> <strong>Adobe-modell</strong> (från Firefly Image Model 4) för omedelbar bildgenerering utan ytterligare konfiguration</li><li> <strong>Partnermodell</strong> (från Gemini 2.5 Flash) för specialfunktioner</li><li><strong>Anpassade modeller</strong> (varumärkesspecifika modeller som utbildats utifrån dina egna resurser) för varumärkesgenerering som exakt överensstämmer med din varumärkesidentitet, stil och visuella riktlinjer.</li></ul>
<p>Mer information finns i den <a href="../content-management/generative-models.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 2 mars 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Live Activity for iOS</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Ge realtidsupplevelserna direkt till kundens Lock Screens och Dynamic Island med iOS Live Activity i Adobe Journey Optimizer. Leverera live-uppdateringar, från orderspårning och flygstatus till händelseräkningar, livepoäng och leveransförlopp, utan att användarna behöver öppna er app. Håll er målgrupp informerad och engagerad i precis rätt ögonblick, precis där de är.</p>
<p>Den här funktionen lanserades tidigare i betaversionen och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p>Mer information finns i den <a href="../mobile-live/get-started-mobile-live.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 3 mars 2026</p>
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
<p>Den här funktionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
<p>Mer information finns i den <a href="https://experienceleague.adobe.com/docs/experience-cloud-ai/experience-cloud-ai/agents/ajo-agent.html?lang=sv-SE">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 4 mars 2026</p>
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
<p><img src="assets/do-not-localize/ai-model-observability.gif"/></p>
<p>Mer information finns i den <a href="../experience-decisioning/ranking/ai-model-observability.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 9 mars 2026</p>
</td>
</tr>
</tbody>
</table>


### Förbättringar {#march-26-improv}

Förbättringar i den här versionen visas nedan.

<!--
#### Reporting

* **Send-Time Optimization: updated controls location and new lift report** - Send-Time Optimization (STO) controls have been relocated to the Action configuration menu. Additionally, a new lift report is now available in Journeys reports to measure the impact of STO on your campaign performance metrics.


* **Exclude bot clicks for email and SMS reporting** - Email and SMS reporting now automatically filters out bot clicks from click metrics, providing more accurate engagement data and preventing automated traffic from inflating your performance figures.

#### Email Designer

* **Email Designer displayed in Unified Shell** - The Email Designer is now displayed within the Unified Shell experience, providing a consistent navigation and header experience that aligns with other Adobe applications.

* **Text mode support in fragments** - To support text-based email workflows, you can now create and manage text versions of your visual fragments for optimal use in the plain text version of emails that include that fragment.

  **Caution:** When using a fragment that was created before the current release, the fragment text version may be incorrectly rendered—both in the Email Designer and in the final email delivered to your recipients. For best results with older fragments, edit, save and republish each fragment.-->
<!--
#### Decisioning

* **Optional fragments in decision items** - When using fragments in decision items, you can now make a fragment optional so that if it is temporarily unavailable on Edge, it is skipped and the journey or campaign continues rendering instead of failing.
-->

#### Konfiguration

<!--* **Folders for journeys and campaigns** - You can now organize your journeys and campaigns into folders, enabling structured navigation and easier management for teams working with large volumes of content. This capability is only available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.-->

* **Datauppsättningen för den sekundära mottagarfeedbacken för AJO byter namn** - datauppsättningen `AJO Email BCC Feedback Event` har bytt namn till datauppsättningen `AJO Secondary Recipient Feedback Event`. Effekten varierar beroende på din situation:

   * **Befintliga användare**: Endast visningsnamnet uppdateras. Det underliggande tabellnamnet ändras inte.
   * **Nya användare och sandlådor**: Både visningsnamnet och tabellnamnet återspeglar det nya namnet.
   * **Befintliga användare med nya sandlådor**: Både visningsnamnet och tabellnamnet uppdateras till det nya namnet.

  Tillgänglighetsdatum: 2 mars 2026


#### Resor

* **Åtgärden Uppdatera profil: stöd för flera profilattribut** - Åtgärdsaktiviteten **Uppdatera profil** stöder nu uppdatering av upp till fem profilattribut i en enda nod. Tidigare kunde varje åtgärd bara uppdatera ett attribut i taget, vilket innebar att flera noder måste uppdatera flera attribut. Använd den nya knappen **Uppdatera ett annat fält** om du vill lägga till fler fält-/värdepar, vilket minskar arbetsytans komplexitet och förbättrar prestandan. [Läs mer](../building-journeys/update-profiles.md)

* **Påfyllnadssändning av utgående meddelanden på resor** - Du kan nu schemalägga att meddelanden från Journey Optimizer-resor levereras i kontrollerade batchar över tid. [Läs mer](../building-journeys/send-using-waves.md)

  Tidigare släppt i Begränsad tillgänglighet för användning under resor är den här funktionen nu tillgänglig i alla miljöer (allmän tillgänglighet).

  Tillgänglighetsdatum: 16 mars 2026

* **Pausa och återuppta detaljer i färdens tekniska detaljer** - Resan **teknisk information** innehåller nu ytterligare information om paus och återupptagning: datum och tid för senaste paus och återupptagning, visningsnamnet och den interna identifieraren för den användare som utförde varje åtgärd samt en fullständig uppsättning pausade reseinställningar som pausbeteende, maximal paustid och automatiskt återupptagningstillstånd. [Läs mer](../building-journeys/journey-properties.md)

  Tillgänglighetsdatum: 2 mars 2026


## Kommer snart {#coming-soon}

Funktionerna och förbättringarna nedan planeras släppas senare i mars/början av april. Releasedatum och omfång kan ändras utan föregående meddelande.

<table>
<thead>
<tr>
<th><strong>Utlös samordnade kampanjer med en signal</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du utlösa en orkestrerad kampanj via en signal som skickas via API:er. Konfigurera målkampanjen som"utlöst av en signal" och publicera den. Använd sedan ett API-anrop för att starta kampanjen. API-anropet kan innehålla parametrar som ska vara tillgängliga som variabler i den utlösta kampanjen. Obs! En orkestrerad kampanj som startats av en signal är fortfarande en **batch**-kampanj och är inte detsamma som API-utlösta kampanjer.</p>
<p><img src="assets/do-not-localize/oc-triggered.gif"></p>
<p>Tillgänglighetsdatum: 1 april 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Konvertera bilder till e-postmallar</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du konvertera bilder till e-postmallar direkt i Journey Optimizer. Använd AI-baserad analys för att automatiskt generera strukturerade HTML-mallar från visuella referenser, vilket avsevärt minskar tiden för e-postdesign.</p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet). <a href="../content-management/image-to-html.md">Läs mer</a></p>
<p>Tillgänglighetsdatum: 26 mars 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>URL-parameterkryptering</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>URL-parametrar för spårning av länkar och landningssidor kan nu krypteras, vilket ger ett extra säkerhetslager för känsliga parameterdata.</p>
<ul>
<li>Registrera och hantera krypteringsnycklar i ett dedikerat <strong>Administration</strong> -register.</li>
<li>Använd den nya krypteringshjälpen i uttryck för att kryptera känsliga data i spårningslänkar och URL:er för landningssidor för de frågeparametrar som du vill skydda vid återgivningen.</li>
</ul>
<p>Den här funktionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
<p>Tillgänglighetsdatum: 31 mars 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Transaktionskategori i orkestrerade kampanjer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>I samordnade kampanjer kan du nu ange en kanalaktivitet till kategorin <strong>Transactional</strong>. Detta tillämpar transaktionskanalskonfigurationer för den aktiviteten och är användbart när affärsregler inte ska gälla eller när kundernas deltagande inte krävs.</p>
<p><img src="assets/do-not-localize/oc-transactional.gif"></p>
<p>Tillgänglighetsdatum: 26 mars 2026 - Den här funktionen kommer gradvis att lanseras för alla regioner under de närmaste dagarna.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Inkorg</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>Inkorgen</strong> är en mobilfunktion, tillgänglig med innehållskort, som gör det möjligt för kunder att skapa en central plats i appen eller på webbplatsen för att visa meddelanden som skickas till användarna. Detta förlänger marknadsföringskommunikationernas livstid genom att säkerställa att de förblir tillgängliga även efter att de har avvisats.</p>
<p>Tillgänglighetsdatum: 31 mars 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Optimering av resväg</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Använd den nya Optimera-noden för att rikta in er på specifika målgrupper eller kör A/B-tester för att fastställa den bästa vägen för att uppfylla era affärsinriktade nyckeltal.
Med det här verktyget kan du testa och ändra, och anpassa kommunikation, sekvensering och timing för att nå dina kunder på bästa sätt.
</p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet). <a href="../building-journeys/optimize.md">Läs mer</a></p>
<p>Tillgänglighetsdatum: 3 april 2026</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar

* **Globala variabler i samordnade kampanjer** - Orchestrated Campaigns har nu stöd för globala variabler som kan definieras en gång och återanvändas för alla aktiviteter i ett arbetsflöde, vilket förenklar konfigurationen och säkerställer konsekvens i dynamiska värden och uttryck. <br/>Tillgänglighetsdatum: 1 april 2026

<!--WAITING RELEASE DATE CONFIRMATION * **Target dimension simplification in Orchestrated Campaigns** - The active targeting dimension is now shown on the workflow canvas, so you can see which dimension is used by a channel activity. The multi-entity segmentation flow is simpler as you no longer need a separate "Change dimension" activity. Moreover, you can now choose explicitly whether messages are sent at the profile level or at a secondary dimension level.-->
