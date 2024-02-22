---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
topic: Content Management
description: Versionsinformation om Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: d3f0adab52ed8e44a6097c5079396d1e9c06e0a7
workflow-type: tm+mt
source-wordcount: '1140'
ht-degree: 7%

---

# Versionsinformation {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="Nyheter?"
>abstract="**Adobe Journey Optimizer** levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen."

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen.

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver av sina senaste innovationer och förbättringar. Läs mer om de här ändringarna i [Versionsinformation för Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target="_blank"}.

![Nyhetsbrev](../assets/do-not-localize/nl-icon.png) Registrera dig för [Adobe Journey Optimizer kvartalsvis nyhetsbrev](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"} idag och få de senaste produktuppdateringarna, spännande historier, användningsexempel, tips och mycket annat levererat direkt till din inkorg varje kvartal.

## Versionsinformation februari 2024 {#feb-2024}

**Releasedatum**: 21-22 feb 2024

### Nya funktioner{#feb-features}

Den här versionen innehåller de nya funktionerna som listas nedan.


<table>
<thead>
<tr>
<th><strong>Webb-meddelanden i appen</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du använda den nya meddelandefunktionen i Web In-App för att visa personaliserat innehåll direkt på webbplatser, via modala överläggsmeddelanden. Med den här funktionen kan ni interagera effektivt med webbbesökare och förbättra användarinteraktionen, kundlojaliteten och konverteringsgraden.<br/><br/></p>
<p>Mer information finns i den <a href="../in-app/create-in-app-web.md">detaljerade dokumentationen</a>.<br></br></p>
<img src="assets/do-not-localize/web_inapp.gif">
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Mallar för flerkanalsinnehåll</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Förutom e-post finns nu innehållsmallar för följande kanaler: push, in-app, SMS och Direct mail, där varje kanal har dedikerade malltyper. För E-post kan du nu välja innehållstypen, som gör att du kan spara ämnesraden som en del av din e-postmall. <br/><br/></p>
<p>Mer information finns i den <a href="../content-management/content-templates.md">detaljerade dokumentationen</a>.<br></br></p>
<img src="assets/do-not-localize/multi-chan-templates.gif">
</tr>
</tbody>
</table>


### Förbättringar {#feb-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**Publiker**

* **Utsändningslistor** - Varianter stöds nu när de använder **listor med startsidor**. Startadresserna får en kopia av alla varianter av samma budskap (t.ex. olika behandlingar av ett innehållsexperiment). [Läs mer](../configuration/seed-lists.md)

Tidigare som betaversion är följande förbättringar nu tillgängliga för alla användare:

* Nu kan du ange mål **målgrupper skapade genom målgruppssammansättning** och utnyttja anrikningsattributen i Journeys. [Läs mer](../building-journeys/read-audience.md)

* Nu kan du ange mål **målgrupper som överförts från en CSV-fil** på resor och kampanjer. [Läs mer](../audience/about-audiences.md#segments-in-journey-optimizer)

  >[!AVAILABILITY]
  >
  >* Användningen av målgrupper och attribut från målgruppssammansättning och anpassad uppladdning (CSV-fil) är för närvarande inte tillgänglig för användning med hälso- och sjukvårdsskölden eller skölden för skydd av privatlivet och säkerheten.
  >* The **målgruppsuppladdning från en CSV-fil** förbättring introduceras gradvis under flera dagar efter den första releasen. Vissa användare har omedelbar åtkomst, men andra kan uppleva en fördröjning innan den blir tillgänglig i sin miljö.

**Resor**

* **Filtrera dina resor** - Nu kan du använda **anpassade datum för att filtrera resorna** lager, utöver befintliga fördefinierade datumfilter. På så sätt kan du förfina listan genom att visa resor som skapats eller publicerats på ett visst datum, inom en viss månad, under ett helt år eller inom angivna tidsintervall. [Läs mer](../building-journeys/journey-gs.md#filter)
* **Anpassade åtgärder** - Du kan nu uppdatera **content-type** header. Den här nya **content-type** ska referera till JSON-innehåll. [Läs mer](../action/about-custom-action-configuration.md#url-configuration)
* **Konfiguration** - Attributet identityMap i stepEvents är nu förfyllt. Den primära identiteten definieras som &quot;primär = true&quot;. [Läs mer](../reports/sharing-field-list.md)
* **Användargränssnitt** - Den övre ribban på skärmar har omstrukturerats för en förbättrad upplevelse. Bland de olika uppdateringarna kan du lägga märke till att pennikonen som gör att du kan komma åt färgegenskaperna nu visas till vänster om det övre fältet, bredvid resans namn. [Läs mer](../building-journeys/journey-gs.md#change-properties)

**SMS-kanal**

* **Nyckelord för anmälan/avanmälan** - När du konfigurerar din SMS-kanal kan du nu anpassa **Nyckelord för deltagande och avanmälan** enligt dina önskemål. Journey Optimizer utlöser svaret baserat på dessa angivna nyckelord. [Läs mer](../sms/sms-configuration.md#create-api)

**Kampanjer**

* **API-utlösta kampanjer** - Den cURL-kod som genereras efter aktivering av en API-utlöst kampanj har förbättrats. Det innehåller nu alla personaliseringsvariabler (profil och kontext) som används i meddelandet. [Läs mer](../campaigns/api-triggered-campaigns.md#execute)

**Frekvensregler**

* Utöver E-post och push-meddelanden kan du nu skapa frekvensregler för SMS- och Direct Mail-kanaler. Frekvensreglerna exkluderar automatiskt överbegärda profiler från meddelanden och åtgärder när frekvensgränsen nås. [Läs mer](../configuration/frequency-rules.md)

<!--**Decision management**

* **Capping rules** - You can now add **multiple capping rules** for one offer. This allows you to increase the level of control over the way offers are sent.-->

<!--
**Content templates**

* **Thumbnails** - A **Grid view** is now available for content templates for improved visual access.

   >[!AVAILABILITY]
   >
   >This capability is released in Limited Availability (LA) for a small set of customers.
-->


## Versionsinformation januari 2024 {#jan-2024}

**Releasedatum**: 30-31 januari 2024

### Nya funktioner{#jan24-features}

Den här versionen innehåller de nya funktionerna som listas nedan.

<table>
<thead>
<tr>
<th><strong>Uppdateringar om leveransbarhet</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer stöder nu tekniken för DMARC-autentisering.</p>
<p>Från 1 februari 2024, Google och Yahoo! kräver att du har en DMARC-post för alla domäner som du använder för att skicka e-post till dem. Se till att du har ställt in DMARC-posten för alla underdomäner som du har delegerat eller delegerat till Adobe i Journey Optimizer.</p>
<p>Mer information finns i den <a href="../configuration/dmarc-record-update.md">detaljerade dokumentationen</a>.</p>
<br/><img src="assets/do-not-localize/dmarc.gif"/>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Spelböcker med användningsexempel</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Använd en katalog med branschspecifika fallspelningsböcker i Real-Time CDP och Journey Optimizer för att hantera vanliga användningsområden som du kan använda Adobe Experience Platform och Adobe Journey Optimiser.</p><p>När du har valt den spelbok som bäst passar dina behov kan du aktivera den för att generera de resurser som behövs för att stödja ditt användningssätt, som resor, meddelanden, scheman eller segment, och anpassa dem till ditt schema för snabbare time-to-value.</p>
<p>Mer information finns i den <a href="../start/playbooks.md">detaljerade dokumentationen</a>.</p>
<br/><img src="assets/do-not-localize/playbooks.gif"/>
</tr>
</tbody>
</table>

### Förbättringar {#jan24-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**Rapporter**

* **Nya domänbaserade uppdelningswidgetar** - Nya widgetar har lagts till för att förbättra kampanjrapporten och reserapporten. The **Studsa orsaker efter domän**, **Skickat och levererat av domäner**, **Öppnar och klickar per domän** och **Studsa och fel efter domän** widgetar ger en detaljerad beskrivning på domännivå för viktiga e-postleveranser och spårningsvärden. [Läs mer](../reports/channel-report.md)

**SMS-kanal**

* **Dubbel anmälan** - Arbetsflödet för dubbel anmälan för SMS garanterar att användare uttryckligen väljer att ta emot meddelanden när begäran initieras från sin enhet. Användarna initierar godkännandeprocessen genom att skicka ett inkommande SMS-meddelande. När de har bekräftat sitt samtycke skickas ett uppföljningsmeddelande med en begäran om slutlig verifiering. Om en användarprofil inte finns skapas den när den har bekräftats. [Läs mer](../sms/sms-configuration.md#create-api)

  Observera att den här funktionen är tillgänglig med SMS-leverantörer för Sinch och Infobip.

**Resor**

* **Varaktighet för reaktionshändelser** - Den maximala varaktighet som du kan definiera i **Reaktionshändelser** är nu 29 dagar i stället för 30. [Läs mer](../building-journeys/reaction-events.md)

<!--* **Date filters** - You can now use custom dates to filter the journeys inventory, in addition to the existing predefined date filters. This allows you to refine the list by displaying journeys published on a specific date, within a particular month, throughout an entire year, or within specified time ranges. [Learn more](../building-journeys/journey-gs.md#filter)-->

* **Läsa målgrupper**  - **Läs målgrupp** aktiviteten bygger nu på data för profilögonblicksbilder för batchsegment, som bara genereras en gång om dagen efter att det schemalagda dagliga batchjobbet har körts, och därför kommer data att uppdateras till det senaste dagliga batchjobbet. [Läs mer](../building-journeys/read-audience.md)

* **Fältgrupper** - Den här versionen åtgärdar ett problem som hindrade fältgrupper från att sparas i vissa fall.

* Stöd för `<listObject>` har ändrats i flera funktioner.

**Frekvensregler**

* **Frekvensbegränsning varje vecka och dag** - Du kan nu ange maximalt antal meddelanden som skickas till en kundprofil under en vecka eller en dag, utöver månaden. Frekvensbegränsningen baseras på den valda kalenderperioden och återställs i början av motsvarande tidsram. [Läs mer](../configuration/frequency-rules.md#create-new-rule)


**Beslutsledning**

* **Frekvensbegränsning på Edge** - Räknaren för frekvensbegränsning har nu uppdaterats och är tillgänglig i ett beslut av Edge Decisioning API på mindre än 3 sekunder. [Läs mer](../offers/api-reference/offer-delivery-api/start-offer-delivery-apis.md)
