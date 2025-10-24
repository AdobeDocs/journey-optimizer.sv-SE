---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
topic: Content Management
description: Versionsinformation om Adobe Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 913104934e78b61b91ea3fca21ee80372050a1fb
workflow-type: tm+mt
source-wordcount: '1204'
ht-degree: 6%

---

# Versionsinformation {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="Nyheter?"
>abstract="**Adobe Journey Optimizer** levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen."

[!DNL Adobe Journey Optimizer] följer en kontinuerlig leveransmodell som gör att Adobe kan leverera nya funktioner, förbättringar och korrigeringar kontinuerligt. Detta tillvägagångssätt möjliggör en skalbar, fasad driftsättning av funktioner för att säkerställa prestanda och stabilitet i alla miljöer.

På grund av den här modellen uppdateras versionsinformationen mellan månadsversionerna.  Ett dedikerat avsnitt om [de senaste uppdateringarna](#updates-rn) visar på nya funktioner och förbättringar när de distribueras till produktionen, så att du alltid informeras om alla ändringar i realtid. <!--For full details about the release cycle and availability phases, see [Journey Optimizer release cycle](#releases.md).-->

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver från de senaste innovationerna och förbättringarna. Läs mer om de här ändringarna i [Adobe Experience Platform versionsinformation](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=sv-SE){target="_blank"}.

## Versionsinformation 25 oktober {#oct-25-10-rn}

**Releasedatum**: 22 oktober 2025

### Nya funktioner {#oct-25-10-features}

<table>
<thead>
<tr>
<th><strong>Anpassade formulär för landningssida</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med [!DNL Journey Optimizer] kan du nu hämta profilattribut via dina landningssidor.</p>
<p>Skapa, designa och hantera anpassade formulär som är skräddarsydda efter era behov utifrån en specifik datamängd. Du kan sedan använda dessa formulär på landningssidor för att lägga till de profilattribut du väljer i datauppsättningen som definieras för varje formulär.</p>
<p>Den här funktionen är för närvarande begränsad för kunder i USA och Australien. Kontakta din Adobe-representant för att få åtkomst.</p>
<p><img src="assets/do-not-localize/forms.gif"/></p>
<p>Mer information finns i den <a href="../landing-pages/lp-forms.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 23 oktober 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Tysta timmar/tidsbaserade undantag</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med tysta timmar kan du definiera tidsbaserade undantag för e-post-, SMS-, push- och whatsApp-kanaler. De ser till att inga meddelanden skickas under särskilda tidsperioder och hjälper er att följa kundönskemål och krav på regelefterlevnad.</p>
<p>Du kan lägga till tysta timmar genom regeluppsättningar, som kan tilldelas enskilda åtgärder i kampanjer eller resor för exakt kontroll.</p>
<p>Regler för tysta timmar är för närvarande bara tillgängliga för en uppsättning organisationer (begränsad tillgänglighet). Om du vill bli medlem i väntelistan kontaktar du Adobe.</p>
<img src="assets/do-not-localize/quiet-hour.gif">
<p>Mer information finns i den <a href="../conflict-prioritization/quiet-hours.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 22 oktober 2025</p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Custom action monitoring and reporting</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>This capability provides better visibility into journey health and execution, including lifecycle status and performance alerts. You can now quickly understand when, where, and why an anomalous situation is occurring in a custom action.</p>
<img src="assets/do-not-localize/FILE.gif">
<p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p>
<p>Availability date: October 22, 2025</p>
</td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>RCS Basic Messaging</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>With the new RCS Basic add-on offering, you can now deliver basic Rich Communication Services (RCS) messaging in Journey Optimizer, enabling the following enhanced messaging capabilities subject to provider and geographical support:</p>
<ul>
<li><strong>Branded and verified sender support:</strong> Send messages using verified business profiles with branding elements (logo, sender name, etc.).</li>
<li><strong>Message delivery insights:</strong> Receive detailed delivery reports including message status updates (e.g., sent, delivered, read).</li>
<li><strong>Link tracking:</strong> Embed and track URLs within RCS messages for engagement analytics.</li>
<li><strong>Fallback to SMS:</strong> Automatic fallback to SMS when the recipient's device does not support RCS or is temporarily unreachable via RCS.</li>
<li><strong>Basic message composition:</strong> Send basic text-based RCS messages.</li>
</ul>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
<!--/td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>Direct mail channel in Orchestrated campaigns</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Direct mail channel is now available in orchestrated campaigns. The Direct mail activity facilitates direct mail sending within your Orchestrated campaign, for both one-time and recurring messages. It serves to automate the process of generating the extraction file required by direct mail providers. You can combine channel activities into the Orchestrated campaign canvas to create cross-channel campaigns that can trigger actions based on customer behavior and data.</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
<!--/td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>Direct Mail channel in journeys</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Previously limited to Campaigns, Direct Mail channel is now available on the journey canvas, enabling you to incorporate Direct Mail into your journeys. Direct Mail can now be used in both batch and 1:1 journey scenarios, with support for file extraction configuration and time-based frequency settings.</p>
<p> Previously released in Limited Availability, this capability is now available to all environments (General Availability).</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
<!--/td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>New API to retrieve Action Campaigns</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>A new Journey Optimizer API is now available, enabling you to programmatically retrieve and inspect campaign-related data such as details, versions, and configurations.</p>
<p>For more information, refer to the <a href="https://developer.adobe.com/journey-optimizer-apis/references/campaigns-retrieve/">detailed documentation</a>.</p>
<p>Availability date: October 22, 2025</p>
</td>
</tr>
</tbody>
</table-->

<!--<table>
<thead>
<tr>
<th><strong>New source connectors for loyalty apps</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>New source connectors are now available in Adobe Experience Platform for the Talon.One, Capillary and Kobie loyalty Apps. These connectors let you seamlessly stream loyalty data into Adobe Experience Platform and leverage these data in Journey Optimizer.</p>
<p>For more information, refer to the <a href="../start/get-started-sources.md">detailed documentation</a>.</p>
<p>Availability date: October 22, 2025</p>
</td>
</tr>
</tbody>
</table>-->

<!--table>
<thead>
<tr>
<th><strong>Decisioning support in email channel</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now add Decision policies into email journeys and campaigns. Decision policies are containers for your offers that leverage the Decisioning engine to dynamically return the best content to deliver for each audience member.</p>
<p>Previously released in Limited Availability, this capability is now available to all environments (General Availability).</p>
<img src="assets/do-not-localize/FILE.gif">
<p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p>
<p>Availability date: October 22, 2025</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>Meddelanden med hög genomströmning för API-utlösta e-postkampanjer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Ett nytt transaktionsläge med hög genomströmning är tillgängligt i API-utlösta kampanjer. Det här läget är utformat för storskaliga transaktionsmeddelanden i realtid och stöder upp till 5 000 transaktioner per sekund med högre tillgänglighet. I det här läget kan du även hantera transaktionsmeddelanden utan att referera till eller skapa kundprofiler, till exempel gästutcheckning, orderbekräftelse, lösenordsåterställningar, säkerhetsmeddelanden och andra service-/driftsmeddelanden.</p>
<p>Den här funktionen är endast tillgänglig för e-postkanalen, för organisationer som har köpt tillägget Adobe High Throput Transactional Messaging. Kontakta Adobe om du vill ha mer information.</p>
<p>Mer information finns i den <a href="../campaigns/api-triggered-high-throughput.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 22 oktober 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Återanvändbara målinriktningsregler</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>För att spara tid och arbete kan du nu med Journey Optimizer skapa återanvändbara regler från en dedikerad användargränssnittsmeny och utnyttja dem när du skapar målinriktning, antingen som en del av optimeringen av innehåll i en kampanj eller en resa, antingen i Optimera kundresan.</p>
<p>Målreglerna är för närvarande begränsade. Kontakta din Adobe-representant för att få åtkomst. Observera att den här funktionen endast är tillgänglig för organisationer som har köpt tilläggserbjudandet för beslut. Den kommer att successivt lanseras för alla kunder.</p>
<img src="assets/do-not-localize/targeting-rules.gif">
<p>Mer information finns i den <a href="../experience-decisioning/rules.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 22 oktober 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Nya reseaviseringar</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Det finns nya förkonfigurerade aviseringar som kan övervaka din resa:</p>
<ul><li><a href="../reports/alerts.md#alert-discard-rate">Frekvensen för ignorerade profiler överskreds</a>: Profilförhållandet mellan ignorerade profiler och angivna profiler under de senaste 5 minuterna överskred tröskelvärdet</li>
<li><a href="../reports/alerts.md#alert-custom-action-error-rate">Felfrekvens för anpassad åtgärd överskreds</a>: Förhållandet mellan anpassade åtgärdsfel och lyckade HTTP-anrop under de senaste 5 minuterna överskred tröskelvärdet</li>
<li><a href="../reports/alerts.md#alert-profile-error-rate">Profilens felfrekvens har överskridits</a>: Profilernas felförhållande till de angivna profilerna under de senaste 5 minuterna överskred tröskelvärdet.</li></ul> <p>Du kan ändra tröskelvärden och prenumerera på enskilda varningar på resenivå jämfört med globalt.</p>
<p>Mer information finns i den <a href="../reports/alerts.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 14 oktober 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Hjälp för körningsmetadata</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>En ny hjälpfunktion, executeMetadata, är tillgänglig i personaliseringsredigeraren. Det gör att du kan lägga till sammanhangsbaserad information till alla inbyggda åtgärder och hämta den i en datauppsättning för export till externa system.</p>
<p>Den här funktionen är tillgänglig med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.</p>
<img src="assets/do-not-localize/execution-metadata.gif">
<p>Mer information finns i den <a href="../personalization/functions/helpers.md#execution-metadata">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 13 oktober 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Experimentation Accelerator med Experimentation Agent</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer Experimentation Accelerator innehåller nu Experimentation Agent, ett AI-drivet konversationsverktyg med vilket du kan interagera med dina experiment, insikter och möjligheter. Det förbättrar Journey Optimizer Experimentation Accelerator upplevelse och hjälper dig att köra experiment effektivare, upptäcka vad som fungerar och se var du kan optimera nästa steg.</p>
<p>Mer information finns i den <a href="https://experienceleague.adobe.com/docs/experience-cloud-ai/experience-cloud-ai/agents/agent-experiment.html?lang=sv-SE" target="_blank">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 10 oktober 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>PDF bilagor till e-postmeddelanden</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Du kan nu bifoga en statisk PDF-fil i ett e-postmeddelande som skickas med Journey Optimizer.</p>
<ul>
<li>Du kan skicka upp till 6 meddelanden med en PDF-bilaga per profil och år.</li>
<li>Den största tillåtna filstorleken för varje bifogad fil är 5 MB.</li>
<li>För ytterligare storlekar och volymer kan du köpa tillägget PDF-bilagor. Mer information får du av Adobe.</li>
</ul>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p><img src="assets/do-not-localize/pdf-attachments.gif"/></p>
<p>Mer information finns i den <a href="../email/pdf-attachments.md">detaljerade dokumentationen</a>.</p>
<p>Tillgänglighetsdatum: 30 september 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Offentligt API för att hämta resor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Det finns nu ett nytt Journey Optimizer-API för att hämta resor och tillhörande objekt som kampanjer och ytor.</p>
<p>Mer information finns i <a href="https://developer.adobe.com/journey-optimizer-apis/references/journeys-retrieve/">detaljerad dokumentation</a></p>
<p>Tillgänglighetsdatum: 25 september 2025</p>
</td>
</tr>
</tbody>
</table>

<!--
## Latest updates {#updates-rn}

New capabilities and improvements released in the past weeks are listed below, with their availability date. They will be grouped with the next release notes content at the end of the month. See also the latest [release notes below](#latest-rn).
-->

### Förbättringar {#updates-improvements}

<!--Availability date: October 22, 2025-->

**Körningsfält för WhatsApp-kanal**

Förutom E-post och SMS kan du även uppdatera standardkörningsfältet för dina WhatsApp-leveranser på sandlådenivå. Det går också att åsidosätta körningsfältet som angetts globalt genom att ändra det i de avancerade parametrarna för whatsApp-reseaktiviteten eller i konfigurationen för WhatsApp-kanalen. [Läs mer](../configuration/primary-email-addresses.md)

Tillgänglighetsdatum: 22 oktober 2025

**Stöd för anpassade attribut för adressen Mailto (unsubscribe)**

Med Journey Optimizer kan du, om du hanterar samtycke utanför Adobe, ange externa anpassade slutpunkter genom att definiera en egen länk för att avbryta prenumerationen och en anpassad e-postadress för att avbryta prenumerationen i e-postkonfigurationen. När mottagarna klickar på länken för att avbryta prenumerationen lägger Journey Optimizer till vissa standardprofilspecifika parametrar i händelsen för att skicka medgivandeuppdatering.

Om du vill anpassa dina anpassade slutpunkter ytterligare kan du nu definiera anpassade attribut som också läggs till i medgivandehändelsen. [Läs mer](../email/list-unsubscribe.md#custom-attributes)

>[!AVAILABILITY]
>
>Den här funktionen har redan varit tillgänglig för den anpassade **[!UICONTROL One-click Unsubscribe URL]** sedan 25 augusti och har nu släppts för alternativet **[!UICONTROL Mailto (unsubscribe)]** med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.

Tillgänglighetsdatum: 6 oktober 2025

### Kommer snart {#oct-25-10-soon}

Följande funktioner och förbättringar planeras släppas under de närmaste dagarna. **Informationen kan komma att ändras**. Uppdaterade länkar, skärmar och dokumentation delas när uppdateringarna är klara.

#### Nya funktioner {#oct-25-10-soon-features}

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
<p>Tidigare släppt i betaversion är den här funktionen nu tillgänglig för ett antal organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
<!--img src="assets/do-not-localize/themes.gif">
<p>For more information, refer to the <a href="../email/apply-email-themes.md">detailed documentation</a>.</p>
<p>Availability date: November 4, 2025</p-->
</td>
</tr>
</tbody>
</table>

#### Förbättringar {#oct-25-10-soon-improvements}

**Bestämning i e-postmeddelanden via AI-modeller**

Nu kan ni använda AI-modeller för att optimera det bästa innehållet i e-postmeddelandet med hjälp av Beslutsfattande. Den här funktionen gör att du till exempel kan erbjuda det bästa innehållet baserat på anpassade händelser som Inköp, Knapp-klick, Lägg till i kundvagnen osv.

<!--
<table>
<thead>
<tr>
<th><strong>New Web Push notifications channel</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer now supports Web Push notifications, expanding the push channel beyond mobile. You can seamlessly deliver notifications to both mobile and desktop browsers, enabling you to reach customers directly on their devices without requiring an app.</p>
<p>This enhancement allows you to engage users with timely, personalized messages in real time, leveraging the same authoring workflows and targeting capabilities already available for mobile push.</p>
<p>For more information, refer to the <a href="../FILE.md">detailed documentation</a></p>
<p>Availability date: Sept XX, 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Custom action monitoring and reporting</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Custom action monitoring and reporting is now available. This capability provides better visibility into journey health and execution, including lifecycle status and performance alerts. You can now quickly understand when, where, and why an anomalous situation is occurring in a custom action.</p>
<p>For more information, refer to the <a href="../FILE.md">detailed documentation</a></p>
<p>Availability date: Sept XX, 2025</p>
</td>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>New source connectors for loyalty apps</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>New source connectors are now available in Adobe Experience Platform for the Talon.One, Capillary, and Kobie loyalty apps. These connectors let you seamlessly stream loyalty data into Adobe Experience Platform and leverage these data in Journey Optimizer.</p>
</td>
</tr>
</tbody>
</table>

-->
