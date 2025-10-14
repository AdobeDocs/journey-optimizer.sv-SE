---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
topic: Content Management
description: Versionsinformation om Adobe Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 0a014d90c8a6654afcbfbd115db9a805c793cef5
workflow-type: tm+mt
source-wordcount: '1768'
ht-degree: 1%

---

# Versionsinformation {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="Nyheter?"
>abstract="**Adobe Journey Optimizer** levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen."

[!DNL Adobe Journey Optimizer] följer en kontinuerlig leveransmodell som gör att Adobe kan leverera nya funktioner, förbättringar och korrigeringar kontinuerligt. Detta tillvägagångssätt möjliggör en skalbar, fasad driftsättning av funktioner för att säkerställa prestanda och stabilitet i alla miljöer.

På grund av den här modellen uppdateras versionsinformationen mellan månadsversionerna.  Ett dedikerat avsnitt om [de senaste uppdateringarna](#updates-rn) visar på nya funktioner och förbättringar när de distribueras till produktionen, så att du alltid informeras om alla ändringar i realtid. <!--For full details about the release cycle and availability phases, see [Journey Optimizer release cycle](#releases.md).-->

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver från de senaste innovationerna och förbättringarna. Läs mer om de här ändringarna i [Adobe Experience Platform versionsinformation](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target="_blank"}.

## Senaste uppdateringar {#updates-rn}

Nya funktioner och förbättringar som släppts under de senaste veckorna listas nedan med deras tillgänglighetsdatum. De grupperas med nästa versionsinformation i slutet av månaden. Se även den senaste [versionsinformationen nedan](#latest-rn).

### Nya funktioner {#updates-features}

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
<p>Mer information finns i <a href="../personalization/functions/helpers.md#execution-metadata">detaljerad dokumentation</a></p>
<p>Tillgänglighetsdatum: 13 oktober 2025</p>
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
<p>Mer information finns i <a href="../email/pdf-attachments.md">detaljerad dokumentation</a></p>
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

### Förbättringar {#updates-improvements}

**Stöd för anpassade attribut för adressen Mailto (unsubscribe)**

Med Journey Optimizer kan du, om du hanterar samtycke utanför Adobe, ange externa anpassade slutpunkter genom att definiera en egen länk för att avbryta prenumerationen och en anpassad e-postadress för att avbryta prenumerationen i e-postkonfigurationen. När mottagarna klickar på länken för att avbryta prenumerationen lägger Journey Optimizer till vissa standardprofilspecifika parametrar i händelsen för att skicka medgivandeuppdatering.

Om du vill anpassa dina anpassade slutpunkter ytterligare kan du nu definiera anpassade attribut som också läggs till i medgivandehändelsen. [Läs mer](../email/list-unsubscribe.md#custom-attributes)

>[!AVAILABILITY]
>
>Den här funktionen har redan varit tillgänglig för den anpassade **[!UICONTROL One-click Unsubscribe URL]** sedan 25 augusti och har nu släppts för alternativet **[!UICONTROL Mailto (unsubscribe)]** med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.

Tillgänglighetsdatum: 6 oktober 2025

## Versionsinformation 25 september {#latest-rn}

**Releasedatum**: 23-24 september 2025

### Nya funktioner {#sept-25-9-features}

<table>
<thead>
<tr>
<th><strong>Journey Optimizer Experimentation Accelerator</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer Experimentation Accelerator är en AI-förstahandsprodukt som utformats för att ta dina experiment till nästa nivå. Det är byggt för användare av Adobe Journey Optimizer och Adobe Target och ger en enhetlig experimenthantering, AI-baserade insikter och möjligheter samt introducerar en ny experimentagent.</p>
<p>Du kan se fram emot att:</p>
<ul>
<li><strong>Enhetlig experimentinventering:</strong> Visa, filtrera och hantera snabbt alla experiment från Adobe Journey Optimizer och Adobe Target på en central arbetsyta.</li>
<li><strong>AI Experimentera med insikter och möjligheter:</strong> Gå bortom statistiska avläsningar med GenAI-baserade insikter och rekommendationer. Varje experiment visar nu möjligheter att agera, med stöd för logiska funktioner, så att teamen kan bestämma vad som ska testas härnäst.</li>
<li><strong>Stöd för MAB (Multi-Armed Bandit) i Journey Optimizer:</strong> Maximera påverkan samtidigt som du minskar bortslösad trafik med Multi-Armed Bandit-experiment. I stället för att dela målgrupper jämnt tilldelar MAB automatiskt fler besökare till de mest effektiva variationerna i realtid så att ni kan leverera bättre upplevelser till fler kunder samtidigt som ni lär er vad som fungerar.</li></ul>
<p><img src="assets/do-not-localize/experimentation-accelerator.gif"/></p>
<p>Mer information finns i <a href="../content-management/experiment-accelerator.md">detaljerad dokumentation</a></p>
<p>Tillgänglighetsdatum: 3 okt 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Journey Agent är här!</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Agent tillhandahålls av <a href="https://experienceleague.adobe.com/sv/docs/experience-cloud-ai/experience-cloud-ai/agents/agent-orchestrator" target="_blank">Adobe Experience Platform Agent Orchestrator</a> och finns i Journey Optimizer. Det gör att ni kan analysera resor via ett naturligt språkgränssnitt. Agenten kommer att upptäcka målgrupper eller schemalägga konflikter och bortfall av profiler under en resa för att hjälpa er att vidta åtgärder för att lösa dem. Snart kan du skapa resor med äkta stöd.</p>
<p>Mer information finns i <a href="https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/ajo-agent-analyze" target="_blank">detaljerad dokumentation</a></p>
<p>Tillgänglighetsdatum: 24 september 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Mörkt läge i e-post-Designer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer Email Designer erbjuder nu möjlighet att växla till vyn för mörkt läge, där du kan definiera ytterligare anpassade inställningar som bara ska visas för mottagare som läser deras e-post i mörkt läge.</p>
<p>Observera följande:</p>
<ul>
<li>Den slutliga återgivningen i mörkt läge kan variera och beror på mottagarens e-postklient.</li>
<li>Alla e-postklienter stöder inte anpassat mörkt läge. Vissa e-postklienter använder dessutom bara sitt eget mörka standardläge för alla e-postmeddelanden som tas emot. I båda fallen går det inte att återge de anpassade inställningarna som du har definierat i e-post-Designer.</li>
</ul>
<p><img src="assets/do-not-localize/dark-mode.gif"/></p>
<p>Mer information finns i <a href="../email/dark-mode.md">detaljerad dokumentation</a></p>
 <p>Tillgänglighetsdatum: 16 september 2025</p>
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
<p>Använd den nya Optimera-noden för att rikta in er på specifika målgrupper eller kör A/B-tester för att fastställa den bästa vägen för att uppfylla era affärsinriktade nyckeltal.</p>
<p>Med det här verktyget kan du testa och ändra, och anpassa kommunikation, sekvensering och timing för att nå dina kunder på bästa sätt.</p>
<p>Den här funktionen är tillgänglig med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.</p>
<p><img src="assets/do-not-localize/optimize.gif"/></p>
<p>Mer information finns i <a href="../building-journeys/optimize.md">detaljerad dokumentation</a></p>
<p>Tillgänglighetsdatum: 4 september 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Anpassad delegeringsmetod för underdomäner</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Utöver den fullständiga delegeringen och CNAME-metoden finns nu en ny konfigurationsmetod för underdomäner: metoden för anpassad delegering, som gör att du kan ha fullständig kontroll över och underhålla alla aspekter av DNS som krävs för att leverera, återge och spåra meddelanden.</p>
<p>Den här funktionen är tillgänglig med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.</p>
<p><img src="assets/do-not-localize/custom-delegation.gif"/></p>
<p>Mer information finns i <a href="../configuration/delegate-custom-subdomain.md">detaljerad dokumentation</a></p>
<p>Tillgänglighetsdatum: 4 september 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Använd Adobe Experience Platform-data för personalisering och beslutsfattande</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Den här funktionen finns nu tillgänglig i alla miljöer, som tidigare lanserats i betaversioner. I den här versionen har följande förbättringar införts:</p>
<ul><li>Stöd för personalisering av datasetsökningar i inkommande kanaler.</li>
<li>Hjälpfunktionen"datasetLookup" kan nu användas i uttrycksfragment. För närvarande är den här funktionen tillgänglig för ett begränsat antal kunder. Kontakta din Adobe-representant för att få åtkomst.</li>
<li>Med ett alternativ i datauppsättningsgränssnittet kan du nu aktivera postbaserade datauppsättningar för sökpersonalisering, utan att behöva utföra ett API-anrop.</li>
<li>Förbättrad övervakning för att spåra dataöverföringshastighet och veta när datauppsättningar är klara för sökning.</li>
<li>Uppdaterade riktlinjer och säkerhetsregler för optimala prestanda och tillförlitlighet.</li>
<li>Adobe Experience Platform-datauppsättningar kan nu utnyttjas i regler för beslutsplatsappning.</li></ul></p>
<p>Mer information finns i <a href="../data/lookup-aep-data.md">detaljerad dokumentation</a></p>
<p>Tillgänglighetsdatum: 1 september 2025</p>
</td>
</tr>
</tbody>
</table>


### Förbättringar {#sept-25-9-improvements}

* **Webkrok-stöd för API-utlösta kampanjer**\
  API-utlösta kampanjer har nu stöd för webhooks. Konfigurera en webkros-URL för att få statusuppdateringar i realtid för varje meddelande, vilket förbättrar observerbarheten och möjliggör smidig övervakning och automatisering. [Läs mer](../configuration/feedback-webhooks.md)

  Tillgänglighetsdatum: 29 september 2025

* **mTLS-stöd för SMS-kanal**
När du konfigurerar en anpassad SMS-leverantör har du nu möjlighet att aktivera gemensam TLS-autentisering (mTLS), vilket kräver att både klienten och servern bekräftar varandras identiteter innan en säker anslutning upprättas. [Läs mer](../sms/sms-configuration-custom.md) - Tillgänglighetsdatum: 23 september 2025

* **Modellbaserade scheman**\
  Modellbaserade scheman kan nu användas av för att stödja dina relationsmodelleringsbehov i samordnade kampanjer. [Läs mer](../orchestrated/gs-schemas.md) - Tillgänglighetsdatum: 23 september 2025

* **Stöd för datauppsättningssökning på resor**\
  En ny aktivitet på resorna, **Datauppsättningssökning**, gör att du kan hämta data dynamiskt från Adobe Experience Platform postdatamängder under körning. Genom att utnyttja den här funktionen kan ni få tillgång till data som kanske inte finns i profilen eller händelsens nyttolast, vilket säkerställer att era kundinteraktioner är både relevanta och aktuella. [Läs mer](../building-journeys/dataset-lookup.md) - Tillgänglighetsdatum: 23 september 2025

  Den här aktiviteten är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.

* **Omdirigeringsstöd i anpassade åtgärder för resor**\
  Omdirigeringar (302) stöds nu i Anpassade åtgärder för resan. - Tillgänglighetsdatum: 23 september 2025

* **Varningar för kanalkonfigurationsövervakning** - Du kan nu prenumerera på systemvarningar, antingen via e-post eller i Journey Optimizer meddelandecenter, om ett konfigurationsfel för e-postkanal som använder den anpassade delegeringstypen inträffar. [Läs mer](../reports/alerts.md#alert-channel-config-failure) - Tillgänglighetsdatum: 23 september 2025

* **Begäranden om att avbryta prenumerationen med ett klick** - Vi har förbättrat hanteringen av begäranden om att avbryta prenumerationen som konfigurerats under Adobe Managed, vilket ger tillförlitlig och konsekvent behandling. - Tillgänglighetsdatum: 23 september 2025

* **Kapslade JSON-body-parametrar stöds nu i anpassad autentisering**\
  När anpassad autentisering konfigureras för en anpassad åtgärd stöds nu kapslade JSON-objekt (t.ex. underobjekt inom `bodyParams`). [Läs mer](../datasource/external-data-sources.md#custom-authentication-mode) - Tillgänglighetsdatum: 18 september 2025

* **Återställa begränsningsfrekvens per timme** - Du kan nu tillämpa begränsning per timme för kanalregeluppsättningar. Den här funktionen fanns tidigare i Begränsad tillgänglighet och är nu tillgänglig i alla miljöer. Du kan välja en timme (tidigare 3 timmar). [Läs mer](../conflict-prioritization/channel-capping.md) - Tillgänglighetsdatum: 17 september 2025

* **Simulera innehållsvariationer för alla inkommande kanaler**\
  Tidigare var det bara tillgängligt för meddelandekanalerna för e-post, SMS och push. Nu gäller även simulering av innehållsvarianter för alla inkommande kanaler. [Läs mer](../test-approve/simulate-sample-input.md) - Tillgänglighetsdatum: 17 september 2025

* **Uttryck för regler för beslutsavgränsning** - Du kan nu skapa egna uttryck för att definiera tröskelvärdet för en begränsningsregel för ett beslutsobjekt. [Läs mer](../experience-decisioning/items.md#capping) - Tillgänglighetsdatum: 16 september 2025

* **Stöd för dynamiska domäner** - Journey Optimizer har nu stöd för fullständig URL-anpassning/basanpassning för fördefinierade domäner som accepteras av Adobe. [Läs mer](../personalization/personalization-build-expressions.md#where) - Tillgänglighetsdatum: 12 september 2025

  Den här funktionen är tillgänglig i begränsad tillgänglighet för en uppsättning kunder.

* **Webhooks** - I den här versionen presenteras följande förbättringar för Webhooks när en anpassad SMS-provider konfigureras:

   * Du kan nu definiera webbhogens syfte, antingen inkommande eller feedback, beroende på vilken typ av data du vill hämta. [Läs mer](../sms/sms-configuration-custom.md#webhook) - Tillgänglighetsdatum: 23 september 2025

   * Gränssnittet för att konfigurera nyckelord har förbättrats för enklare konfiguration. [Läs mer](../sms/sms-configuration-custom.md#webhook) - Tillgänglighetsdatum: 23 september 2025

* **SMS**

   * När du konfigurerar en anpassad SMS-provider kan du nu definiera nyckelordet **Default** som används när ett inkommande SMS innehåller ett okänt nyckelord. Du kan också skapa **anpassade**-nyckelord för specifika åtgärder. [Läs mer](../sms/sms-configuration-custom.md) - Tillgänglighetsdatum: 23 september 2025

   * Du kan nu komma åt odefinierade inkommande nyckelordssvar som skickas via ett SMS-meddelande, inklusive typos, ord eller meningar som inte uttryckligen definieras i konfigurationen. De lagras i datamängden **AJO Email Tracking Experience Event** under **InboundMessage** i 13 månader. Endast tillgängligt med Sinch, Infobip och anpassad SMS-leverantör. - Tillgänglighetsdatum: 23 september 2025

<!--
* **Approval policy permissions**
  Added an option when creating or setting Approval Policy to prevent Journey/Campaign creators from approving their own objects. [Read more](../test-approve/approval-policies.md) - Availability date: Sept 23, 2025-->

<!--
### Coming soon {#sept-25-9-soon}

In the next few days, the following capabilities and enhancements are scheduled for release. **Information is subject to change**. Updated links, screens, and documentation will be shared once these updates are live in production.

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


<table>
<thead>
<tr>
<th><strong>Landing page custom forms</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>With [!DNL Journey Optimizer], you can now capture profile attributes though your landing pages.</p>
<p>Create, design and manage custom forms tailored to your needs based on a specific dataset. You can then leverage these forms in landing pages to add the profile attributes of your choice into the dataset defined for each form.</p>
<p>This capability is available in Limited Availability. Contact your Adobe representative to gain access.</p>
<p><img src="assets/do-not-localize/forms.gif"/></p>
<p>For more information, refer to the <a href="../landing-pages/lp-forms.md">detailed documentation</a></p>
<p>Availability date: Sept XX, 2025</p>
</td>
</tr>
</tbody>
</table>


* **New Journey Alerts**  
  New pre-configured alerts are available for journeys:

  * Profile Discard Rate Exceeded: Ratio of profile discards to entered profiles over the last 5 mins exceeded threshold.  
  * Custom Action Error Rate Exceeded: Ratio of custom action errors to successful HTTP calls over the last 5 mins exceeded threshold.  
  * Profile Error Rate Exceeded: Ratio of profiles-in-error to entered profiles over the last 5 mins exceeded threshold.


  * [Profile Discard Rate Exceeded](../reports/alerts.md#profile-discard-rate-exceeded): Ratio of profile discards to entered profiles over the last 5 mins exceeded threshold.  
  * [Custom Action Error Rate Exceeded](../reports/alerts.md#custom-action-error-rate-exceeded): Ratio of custom action errors to successful HTTP calls over the last 5 mins exceeded threshold.  
  * [Profile Error Rate Exceeded](../reports/alerts.md#profile-error-rate-exceeded): Ratio of profiles-in-error to entered profiles over the last 5 mins exceeded threshold.

  You can modify threshold values and subscribe to individual journey-level alerts vs globally.

  Availability date: Sept XX, 2025

-->
