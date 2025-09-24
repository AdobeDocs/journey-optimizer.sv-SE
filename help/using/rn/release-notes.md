---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
topic: Content Management
description: Versionsinformation om Adobe Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 1969a6bcea8627ea48c304f632b21bc41278b1bd
workflow-type: tm+mt
source-wordcount: '1803'
ht-degree: 1%

---

# Versionsinformation {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="Nyheter?"
>abstract="**Adobe Journey Optimizer** levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen."

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen. [!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver från de senaste innovationerna och förbättringarna. Läs mer om de här ändringarna i [Adobe Experience Platform versionsinformation](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=sv-SE){target="_blank"}.


## Versionsinformation 25 september {#25-9-rn}

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
<p>Mer information finns i <a href="https://experienceleague.adobe.com/sv/docs/experience-cloud-ai/experience-cloud-ai/agents/ajo-agent-analyze" target="_blank">detaljerad dokumentation</a></p>
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
<p>Den här funktionen lanserades tidigare som betaversion och är nu tillgänglig för alla miljöer med begränsad tillgänglighet. I den här versionen har följande förbättringar införts:</p>
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

* **Behörigheter för godkännandeprincip**
Ett alternativ lades till när en godkännandeprincip skapades eller ställdes in för att förhindra att de som skapar en resa/kampanj godkänner sina egna objekt. [Läs mer](../test-approve/approval-policies.md)

* **Kapslade JSON-body-parametrar stöds nu i anpassad autentisering**\
  När anpassad autentisering konfigureras för en anpassad åtgärd stöds nu kapslade JSON-objekt (t.ex. underobjekt inom `bodyParams`). [Läs mer](../datasource/external-data-sources.md#custom-authentication-mode)


* **mTLS-stöd för SMS-kanal**
När du konfigurerar en anpassad SMS-leverantör har du nu möjlighet att aktivera gemensam TLS-autentisering (mTLS), vilket kräver att både klienten och servern bekräftar varandras identiteter innan en säker anslutning upprättas. [Läs mer](../sms/sms-configuration-custom.md)

* **Modellbaserade scheman**\
  Modellbaserade scheman kan nu användas av för att stödja dina relationsmodelleringsbehov i samordnade kampanjer. [Läs mer](../orchestrated/gs-schemas.md)

* **Stöd för datauppsättningssökning på resor**\
  En ny aktivitet på resorna, **Datauppsättningssökning**, gör att du kan hämta data dynamiskt från Adobe Experience Platform postdatamängder under körning. Genom att utnyttja den här funktionen kan ni få tillgång till data som kanske inte finns i profilen eller händelsens nyttolast, vilket säkerställer att era kundinteraktioner är både relevanta och aktuella. [Läs mer](../building-journeys/dataset-lookup.md)

  Den här aktiviteten är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.

* **Simulera innehållsvariationer för alla inkommande kanaler**\
  Tidigare var det bara tillgängligt för meddelandekanalerna för e-post, SMS och push. Nu gäller även simulering av innehållsvarianter för alla inkommande kanaler. [Läs mer](../test-approve/simulate-sample-input.md)

* **Omdirigeringsstöd i anpassade åtgärder för resor**\
  Omdirigeringar (302) stöds nu i Anpassade åtgärder för resan.

* **Begäranden om att avbryta prenumerationen med ett klick** - Vi har förbättrat hanteringen av begäranden om att avbryta prenumerationen som konfigurerats under Adobe Managed, vilket ger tillförlitlig och konsekvent behandling.

* **Återställa begränsningsfrekvens per timme** - Du kan nu tillämpa begränsning per timme för kanalregeluppsättningar. Den här funktionen fanns tidigare i Begränsad tillgänglighet och är nu tillgänglig i alla miljöer. Du kan välja en timme (tidigare 3 timmar). [Läs mer](../conflict-prioritization/channel-capping.md) - Tillgänglighetsdatum: 17 september

* **Stöd för dynamiska domäner** - Journey Optimizer har nu stöd för fullständig URL-anpassning/basanpassning för fördefinierade domäner som accepteras av Adobe. [Läs mer](../personalization/personalization-build-expressions.md#where) - Tillgänglighetsdatum: 12 september

  Den här funktionen är tillgänglig i begränsad tillgänglighet för en uppsättning kunder.

* **Uttryck för regler för beslutsavgränsning** - Du kan nu skapa egna uttryck för att definiera tröskelvärdet för en begränsningsregel för ett beslutsobjekt. [Läs mer](../experience-decisioning/items.md#capping)

  Den här funktionen är för närvarande tillgänglig som begränsad tillgänglighet för alla användare.

* **Varningar för kanalkonfigurationsövervakning** - Du kan nu prenumerera på systemvarningar, antingen via e-post eller i Journey Optimizer meddelandecenter, om ett konfigurationsfel för e-postkanal som använder den anpassade delegeringstypen inträffar. [Läs mer](../reports/alerts.md#alert-dns-record-missing)



### Kommer snart {#sept-25-9-soon}

Följande funktioner och förbättringar planeras släppas under de närmaste dagarna. **Informationen kan komma att ändras**. Uppdaterade länkar, skärmar och dokumentation delas när uppdateringarna är klara.

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
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Ny meddelandekanal för Web Push</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer har nu stöd för Web Push-meddelanden, vilket gör att den här pushkanalen kan användas även utanför mobila enheter. Ni kan smidigt leverera meddelanden till både webbläsare för mobiler och datorer, så att ni kan nå kunder direkt på deras enheter utan att behöva använda en app.</p>
<p>Den här förbättringen gör att ni kan engagera användarna med rätt, personaliserade meddelanden i realtid, och utnyttja samma arbetsflöden och målgruppsfunktioner som redan finns för mobilpush.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Övervakning och rapportering av anpassade åtgärder</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Övervakning och rapportering av anpassade åtgärder är nu tillgängligt. Den här funktionen ger bättre synlighet när det gäller hälsa och utförande av resan, inklusive livscykelstatus och prestandavarningar. Nu kan ni snabbt förstå när, var och varför en onormal situation inträffar i en anpassad åtgärd.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Nya källkopplingar för lojalitetsappar</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu finns nya källanslutningar i Adobe Experience Platform för lojalitetsapparna Talon.One, Capillary och Kobie. Med dessa kopplingar kan ni smidigt strömma lojalitetsdata till Adobe Experience Platform och utnyttja dessa data i Journey Optimizer.</p>
</td>
</tr>
</tbody>
</table>


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
<p>Den här funktionen är tillgänglig med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.</p>
<p><img src="assets/do-not-localize/forms.gif"/></p>
<!--p>For more information, refer to the <a href="../landing-pages/lp-forms.md">detailed documentation</a></p-->
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
<!--p>For more information, refer to the <a href="../email/pdf-attachments.md">detailed documentation</a></p-->
</td>
</tr>
</tbody>
</table>



* **Nya reseaviseringar**\
  Det finns nya förkonfigurerade aviseringar för resor:

   * Frekvensen för ignorerade profiler överskreds: Profilförhållandet mellan ignorerade profiler och angivna profiler under de senaste 5 minuterna överskred tröskelvärdet.
   * Felfrekvens för anpassad åtgärd överskreds: Förhållandet mellan anpassade åtgärdsfel och lyckade HTTP-anrop under de senaste 5 minuterna överskred tröskelvärdet.
   * Profilfelsfrekvensen har överskridits: Profilernas felförhållande till de angivna profilerna under de senaste 5 minuterna överskred tröskelvärdet.
<!--
  * [Profile Discard Rate Exceeded](../reports/alerts.md#profile-discard-rate-exceeded): Ratio of profile discards to entered profiles over the last 5 mins exceeded threshold.  
  * [Custom Action Error Rate Exceeded](../reports/alerts.md#custom-action-error-rate-exceeded): Ratio of custom action errors to successful HTTP calls over the last 5 mins exceeded threshold.  
  * [Profile Error Rate Exceeded](../reports/alerts.md#profile-error-rate-exceeded): Ratio of profiles-in-error to entered profiles over the last 5 mins exceeded threshold.-->

Du kan ändra tröskelvärden och prenumerera på enskilda varningar på resenivå jämfört med globalt.


* **Stöd för anpassade attribut med en klickning för att avbryta prenumeration på URL**\
  Med Journey Optimizer kan du, om du hanterar samtycke utanför Adobe, ange en extern anpassad slutpunkt genom att definiera en egen länk för att avbryta prenumerationen i e-postkonfigurationen. När mottagarna klickar på länken för att avbryta prenumerationen lägger Journey Optimizer till vissa standardprofilspecifika parametrar i händelsen för att skicka medgivandeuppdatering.

  Om du vill anpassa e-postadressen för att avbryta prenumerationen ytterligare kan du nu definiera anpassade attribut som läggs till i medgivandehändelsen. Den här funktionen har redan varit tillgänglig för den anpassade länken för att avbryta prenumerationen med ett enda klick sedan den 25 augusti.

* **Högt genomströmningsläge för API-utlösta e-postkampanjer**\
  Nu finns det ett nytt högfrekvensläge tillgängligt i API-utlösta kampanjer. Det här läget är utformat för storskaliga meddelanden i realtid (upp till 5 000 transaktioner per sekund) och ger högre tillgänglighet med lägre latens.\
  Den här funktionen är endast tillgänglig för e-postkanalen, för organisationer som har köpt tillägget Adobe High-through transactional messaging. Kontakta Adobe om du vill ha mer information.

* **Webkrok-stöd för API-utlösta kampanjer**\
  API-utlösta kampanjer har nu stöd för webhooks. Konfigurera en webkros-URL för att få statusuppdateringar i realtid för varje meddelande, vilket förbättrar observerbarheten och möjliggör smidig övervakning och automatisering.
