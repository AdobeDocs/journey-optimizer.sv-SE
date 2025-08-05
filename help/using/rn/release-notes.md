---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
topic: Content Management
description: Versionsinformation om Adobe Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 3a44111345c1627610a6b026d7b19b281c4538d3
workflow-type: tm+mt
source-wordcount: '1361'
ht-degree: 3%

---

# Versionsinformation {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="Nyheter?"
>abstract="**Adobe Journey Optimizer** levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen."

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen. [!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver från de senaste innovationerna och förbättringarna. Läs mer om de här ändringarna i [Adobe Experience Platform versionsinformation](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=sv-SE){target="_blank"}.


## Kampanjsamordning

**Tillgänglighetsdatum**: 4 augusti 2025

Journey Optimizer innehåller nu **Kampanjsamordning**, en ny funktion som är avsedd för varumärkesinitierade gruppkampanjer. I den här versionen introduceras en kampanjsamordningsyta och förbättrad datamodellering, som fungerar tillsammans för att marknadsförarna ska kunna planera, målinrikta och leverera personaliserade flerkanalskampanjer.

![Kampanjsamordning GIF](assets/do-not-localize/release.gif)

Den innehåller [Relationsscheman och datauppsättningar](#oc-relational) och [Kampanjarbetsyta](#oc-canvas). Tillsammans sätter dessa två innovationer en ny standard för att samordna batchkampanjer i Journey Optimizer. Viktiga funktioner listas nedan.

### Nyckelfunktioner {#oc-capabilities}

* **Flerstegsarbetsflöden**

  Skapa sofistikerade gruppkampanjer i flera kanaler med den nya, specialbyggda arbetsytan för kampanjhantering.

* **On demand-målgrupper**

  Segmentera målgrupper på begäran för omedelbar aktivering.

* **Segmentering för flera enheter**

  Bygg målgrupper med hjälp av företagskontext (icke-personella dimensioner) som produkt, butiker, förnyelser, reservationer med mera.

* **Synlighet före sändning**

  Granska, förfina och optimera målgrupper och kampanjer före lansering och medan kampanjer körs

### Kampanjarbetsyta {#oc-canvas}

Ett helt nytt gränssnitt för visuell samordning som är konstruerat för gruppkampanjer. På arbetsytan kan du

* Visuell planering av flerstegskampanjer för flera kanaler

* Stöd för on demand-målgrupper som bygger på relationsfrågor

* Avancerad målgruppsdelning, väntetider och villkorslogik

* Exakt antal före sändning när affärsregler och filter har tillämpats

### Relationsscheman och datauppsättningar {#oc-relational}

Adobe Experience Platform har nu stöd för relationsenheter (t.ex. produkter, butiker, bokningar, kontrakt) som är kopplade till personbaserade profiler. Detta möjliggör segmentering och personalisering över flerdimensionella datastrukturer, vilket möjliggör exempelvis följande:

* Ett meddelande per bokning, prenumeration eller kontrakt

* Segmentering baserad på relaterade entitetsattribut (t.ex. produktkategori eller butiksplats)

* Förbättrad adressering (t.ex. skicka till alla kända kontakter som är kopplade till en enhet)

### Varför det spelar någon roll

Den här versionen ger marknadsförarna full kontroll över varumärkesinitierad, målgruppsbaserad batchmarknadsföring, vilket kombinerar flexibel datamodellering med en specialbyggd orkestreringsupplevelse. Den är särskilt utformad för gruppkampanjsamordning från realtidsresor, samtidigt som den erbjuder avancerad personalisering och skalbarhet.

### Läs mer

Läs mer i [dokumentationen för kampanjsamordning](../orchestrated/gs-orchestrated-campaigns.md).

<!--
## August '25 pre release notes {#25-7-rn}

**Pre release notes below are subject to change without prior notice until the release availability date**. Links, screens and updated documentation are published at the release date.

See also [Adobe Experience Platform Pre-release notes](https://experienceleague.adobe.com/sv/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.

**Release date**: August 19, 2025


### New capabilities {#Aug-25-8-features}

New capabilities coming with this release are detailed below.

### Improvements {#Aug-25-8-improv}

Improvements coming with this release are listed below.
-->


## Versionsinformation juli 25 {#25-7-rn}

**Releasedatum**: 29 juli 2025

### Nya funktioner {#features-25-7}

De nya funktionerna i den här versionen beskrivs nedan.

#### Funktioner

<table>
<thead>
<tr>
<th><strong>WhatsApp Channel</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer har nu stöd för meddelanden direkt i WhatsApp, vilket möjliggör smidig integrering på era resor och kampanjer för förbättrad mottagarkommunikation och -engagemang. Den här inbyggda kanalen levereras direkt ur kartongen med whatsApp-mallintegrering, förhandsgranskning av meddelanden, personalisering, leveransrapportering, webbhooks, hantering av deltagande och avanmälan med mera.</p>
<p>Den här funktionen lanserades tidigare i Beta och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p><img src="../whatsapp/assets/do-not-localize/WA-Animation.gif"/><p>
<p>Mer information finns i den <a href="../whatsapp/get-started-whatsapp.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Varumärken</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan ni skapa och anpassa era egna varumärken för att tydligt definiera er visuella och verbala identitet i alla slags kommunikation. Med varumärkesjusteringspoängen kan ni få feedback i realtid om hur väl ert innehåll speglar ert varumärkes ton, stil och riktlinjer, så att ni kan hålla er enhetliga med varje budskap ni skickar.</p>
<p>Den här funktionen lanserades tidigare i Beta och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p><img src="assets/do-not-localize/brand-score.gif"/></p>
<p>Mer information finns i den <a href="../content-management/brands.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Använd beslut i e-postkanal</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan ni lägga till beslutsprinciper i e-postresor och -kampanjer. Beslutspolicyer är behållare för era erbjudanden som utnyttjar beslutsmotorn för att dynamiskt returnera det bästa innehållet för varje målgruppsmedlem.</p>
<p>Den här funktionen är tillgänglig med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.</p>
Mer information finns i <a href="../experience-decisioning/create-decision.md">detaljerad dokumentation</a></p>
</td>
</tr>
</tbody>
</table>

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
<p>LINE-kanalen är nu tillgänglig för alla användare (General Availability), som tidigare endast var tillgänglig för begäran.</p>
<p>Mer information finns i den <a href="../line/get-started-line.md">detaljerade dokumentationen</a>.</p></td>
</tr>
</tbody>
</table>

<!--
<table>
<thead>
<tr>
<th><strong>Optimization in campaigns</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer now empowers you with the tools to deliver personalized and optimized content to your campaigns' audience, allowing you to run content experiments, create rule-based targeting, and use advanced combinations of both, to maximize the effectiveness of your campaigns.</p>
<p>With Optimization, you can:</p>
<ul>
<li>Test multiple content variations to identify the most effective messaging.</li>
<li>Deliver personalized content based on user attributes and contextual data.</li>
<li>Combine targeting and experimentation for advanced campaign strategies.</li>
<li>Filter out users that do not match variant criteria.</li>
<li>Ensure fallback mechanisms to maintain user engagement.</li>
</ul>
<P>Once the campaign is live, profiles are evaluated against the defined criteria, and based on matching criteria, they are delivered with the appropriate experience or content from the campaign.</p>
<p><img src="assets/do-not-localize/campaign-optimization.gif"/></p>
<p>For more information, refer to the <a href="../FILE.md">detailed documentation</a></p>
</td>
</tr>
</tbody>
</table>
-->



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
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p>Mer information finns i <a href="../building-journeys/journey-dry-run.md">detaljerad dokumentation</a></p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Kompletterande ID för resor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du utlösa resor med ett profil-ID tillsammans med en annan identifierare, till exempel ett order-ID, ett prenumerations-ID eller ett förskrivnings-ID, vilket gör att samma profil kan finnas på samma resa flera gånger samtidigt. Detta möjliggör scenarier som att hantera flera order eller prenumerationer parallellt, där varje instans följer sin egen väg genom resan.</p>
<p>Tidigare släppt i Begränsad tillgänglighet är användningen av extra ID:n på resor nu tillgänglig för alla miljöer. I den här allmänna tillgänglighetsversionen har funktionen nu stöd för målgruppsresor för läsning.</p>
<p><img src="assets/do-not-localize/gif-supplemental.gif"/></p>
<p>Mer information finns i <a href="../building-journeys/supplemental-identifier.md">detaljerad dokumentation</a></p>
</td>
</tr>
</tbody>
</table>

### Varningar i produkten

Du kan nu prenumerera på **e-postmeddelanden och produktmeddelanden** för Journey Optimizer produktreleaser.

Så här prenumererar du:

* Navigera till **Adobe Experience Cloud-inställningar**
* Under **Notifications**, sök efter **Journey Optimizer New Relases**
* Aktivera meddelanden i programmet och e-postmeddelanden

![](assets/do-not-localize/pulse-notif.png){width="70%" align="left"}


### Förändringar i resevillkor {#ee-change@}

Från och med den 8 juli stöds inte längre skapande av uttryck med upplevelsehändelser i den uttrycksredigerare som används i resevillkor i nya kundorganisationer. Därför kan upplevelsehändelser i [Experience Platform-datakällan](../datasource/adobe-experience-platform-data-source.md) inte användas för att skapa uttryck. Alternativa metoder och bästa praxis för att skapa uttryck/logik med upplevelsehändelser refereras [här](../building-journeys/exp-event-lookup.md).

Det finns ingen förändring i hur händelsedata om resans kontext nås på enstaka resor. I redigeringsprogram för uttryck och personalisering kan användarna fortsätta att komma åt data som skickas in vid den första resehändelsen.

Läs mer [i de här vanliga frågorna](../building-journeys/exp-event-lookup.md#faq-ee).

### Förbättringar {#25-7-improv}

Förbättringar i den här versionen visas nedan.

* **Kampanjer**

   * **Flera inkommande åtgärder i kampanjer** - För att förenkla kampanjhanteringen kan du nu definiera flera inkommande åtgärder i en enda kampanj. Med den här funktionen kan ni leverera flera kodbaserade upplevelser, meddelanden i appen, innehållskort eller webbåtgärder till olika platser samtidigt, och varje åtgärd innehåller ett visst innehåll.
  <!-- [Read more](../FILE.md) -->

   * **Omorganisation av kampanjinventering** - Schemalagda och API-utlösta kampanjer delas nu upp på separata flikar i kampanjlagret för enklare navigering och hantering.

[Läs mer](../campaigns/modify-stop-campaign.md)

* **Datahantering**
   * **Datauppsättningar för beslutshanteringssystem** - De borttagna personliga erbjudandena och reserverbjudandena har nu markerats som arkiverade i datamängderna &quot;Decision_object_database_personalized_offers&quot; och &quot;Decision_object_database_fallback_offers&quot;. Befintliga poster i datauppsättningen ändras inte.

[Läs mer](../offers/export-catalog/access-dataset.md)

* **Resor**
   * **Förbättringar av verktygslådan Resesandlåda** - När du kopierar resor över flera sandlådor med hjälp av funktionerna för paketexport och import är nu även följande funktioner tillgängliga:
      * Välja en befintlig händelse på målet
      * Kopiera över en händelse oberoende av en resa
      * Identifiera fältgrupps-/datakällrelationer, länka till dem vid målet om de finns, och skapa dem om de inte gör det.

[Läs mer](../configuration/copy-objects-to-sandbox.md)

* **Kanal - i appen**
   * **Nyckel-/värdepar i appen** - Med meddelanden i appen kan du definiera nyckel- och värdepar som ska innehålla anpassade variabler i meddelandets nyttolast. Dessa nyckelvärdepar gör att du kan skicka ytterligare data baserat på din specifika konfiguration och användningsfall. [Läs mer](../in-app/design-in-app.md)

* **Kanal - Innehållskort**

   * **Regelbaserad kampanjavvikelse** - Vid redigering av ytterligare leveransregler har det tidigare alternativet Leveransregler ersatts med tre olika regeltyper för bättre kontroll av meddelandetiming och synlighet:
      * Visa meddelande om: Villkor som bestämmer när innehållskortet visas.
      * Stäng meddelandet om: Villkor som tillfälligt döljer innehållskortet. Den kan visas igen om visningsvillkoren uppfylls igen.
      * Diskvalificera meddelandet om: Villkor som permanent förhindrar att innehållskortet visas igen.

[Läs mer](../content-card/design-content-card.md)

* **Beslut**
   * **API:er för migreringsverktyg** - Journey Optimizer-teamet arbetar för närvarande med migreringsverktygs-API:er för att migrera beslutshanteringsenheter till beslut. Detta verktyg möjliggör sömlös migrering mellan sandlådor med beroendeupplösning och återställningsfunktioner. Kontakta Adobe om du är intresserad.

* **Personalization**
   * En ny hjälpfunktion, &quot;SHA256&quot;, har lagts till i personaliseringsredigeraren. Den här funktionen används för att beräkna och returnera sha256-hash för en sträng.

[Läs mer](../personalization/functions/string.md#sha256)
