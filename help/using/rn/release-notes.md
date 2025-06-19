---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
topic: Content Management
description: Versionsinformation om Adobe Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 5e7aad25fa08994f6cbce9adfce4a3dc94fe3e47
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 8%

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

* **Beslut** - Tillgänglighetsdatum: 3 juni 2025

  Beslutsobjekt kan nu kopieras mellan sandlådor, vilket effektiviserar arbetsflödena för testning och distribution. [Läs mer](../configuration/copy-objects-to-sandbox.md#decisioning)

* **Stöd för beslutsobjektattribut för beslutsregler** - Tillgänglighetsdatum: 4 juni 2025

  Nu kan du använda attribut för beslutsobjekt för att skapa beslutsregler. [Läs mer](../experience-decisioning/rules.md#create)

* **API-uppdatering för interaktiv meddelandekörning** - tillgänglighetsdatum: 6 juni 2025

  Med API:t för interaktiv meddelandekörning kan du nu ta bort schemat för kommande kampanjkörningar. [Läs mer](https://developer.adobe.com/journey-optimizer-apis/references/messaging/){target="_blank"}
