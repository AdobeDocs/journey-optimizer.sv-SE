---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation 2022
description: Versionsinformation om Journey Optimizer 2022
exl-id: 0997a640-3f89-4460-ba93-ea21a9d4efc5
source-git-commit: 2160d52f24af50417cdcf8c6ec553b746a544c2f
workflow-type: tm+mt
source-wordcount: '2519'
ht-degree: 9%

---

# Versionsinformation för 2022 {#release-notes-2022}

På den här sidan visas alla funktioner och förbättringar för [!DNL Journey Optimizer] släppt 2022.

## Version från augusti 2022 {#aug-2022-release}

### Nya funktioner

<table>
<thead>
<tr>
<th><strong>Skapa och hantera kampanjer i Journey Optimizer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Använd Journey Optimizer kampanjer för att leverera engångsinnehåll till ett visst segment via olika kanaler. När du använder resor är åtgärderna utformade för att utföras i sekvens. Med kampanjer utförs åtgärder samtidigt, antingen omedelbart eller baserat på ett angivet schema. </p>
<img src="assets/do-not-localize/campaigns.gif"/>
<p>Lär dig hur du skapar en kampanj i <a href="../campaigns/get-started-with-campaigns.md">detaljerad dokumentation</a> och <a href="https://video.tv.adobe.com/v/346680">funktionsvideo</a>.
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Skicka SMS till användarna (allmän tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du skapa, anpassa och skicka SMS i Journey Optimizer via en integrering med <b>Sinch</b> eller <b>Twilio</b>.</p>
<img src="assets/do-not-localize/SMS.gif"/>
<p>Lär dig hur du skapar och skickar ett SMS i det här <a href="../messages/create-sms.md">detaljerad dokumentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>New Dynamic Expression Builder</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now create conditional content blocks across different authoring services to personalize your content.</p>
<p>In addition to the Personalization Expression Library, the Expression Editor provides a new Conditional Rule Builder to help you design and save your content blocks.</p>
<p>For more information, refer to the <a href="../building-journeys/read-segment.md#configuring-segment-trigger-activity">detailed documentation</a>.
</td>
</tr>
</tbody>
</table-->


### Förbättringar

**Rapportering**

* Policytabell och diagram för samtycke finns nu tillgängliga i globala rapporter om resor. Med dessa widgetar kan du spåra de uteslutna profilerna från profilerna i dina anpassade åtgärder. [Läs mer](../reports/journey-global-report.md#journey-global)

   Observera att du måste återställa de olika rapportinstrumentpanelerna för att få tillgång till de senaste widgetarna. Mer information om anpassning av kontrollpanelen finns i [detaljerad dokumentation](../reports/global-report.md).

**Administrering**

* Det går nu att uppdatera det primära telefonnumret som ska användas för SMS-kanalen. [Läs mer](../configuration/primary-email-addresses.md)


## Version från juli 2022 {#july-2022-release}

### Nya funktioner

<table>
<thead>
<tr>
<th><strong>Nytt textbundet meddelandeflöde</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer har ett nytt flöde för att skapa meddelanden i Journeys. Med textbundna meddelanden sparar man mycket tid och effektiviserar arbetsflödet för att skapa och leverera e-post, push-meddelanden eller SMS i Journey Optimizer. Genom att ta bort meddelanden som ett separat steg och i stället göra dem redigerbara online som en del av en åtgärd på arbetsytan på resan, måste användarna klicka på färre knappar och navigera bland färre skärmar för att utforma och redigera innehållet.</p>
<img src="assets/do-not-localize/inline.gif"/>
<p>Mer information finns i den <a href="../messages/get-started-content.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Attributbaserad åtkomstkontroll (begränsad tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du identifiera schemafält med etiketter som definierar användningsområde för organisation eller data. Administratörer kan använda gränssnittet Behörigheter för att definiera åtkomstprinciper som omfattar XDM-schemafält och bättre hantera åtkomsten som ges till användare eller grupper av användare (interna, externa eller externa användare) samt hantera åtkomsten till specifika typer av data (dvs känsliga personuppgifter/SPD).</p>
<p>Attributbaserad åtkomstkontroll är för närvarande begränsad till vissa användare och kommer att distribueras till alla miljöer i en framtida version.</p>
<p>Mer information finns i den <a href="../administration/attribute-based-access.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Batchbeslutsjobb</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du köra batchbeslutsjobb från användargränssnittet, så att jag inte behöver någon utvecklare för att köra batchAPI-jobb och jag kan minska tiden som krävs för marknadsföring. Med det här nya gränssnittet kan du skapa jobb och hantera aktuella/tidigare jobb.</p>
<img src="assets/do-not-localize/batch.gif"/>
<p>Mer information finns i den <a href="../offers/batch-delivery.md">detaljerade dokumentationen.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Använd automatiskt det bästa erbjudandet i dina beslut (begränsad tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Ni kan nu använda personaliserade optimeringsmodellsystem i beslutshanteringen. Med den här nya typen av modell kan ni optimera och personalisera erbjudanden baserat på segment och erbjudanden.</p>
<p>Användningen av anpassade optimerings-AI-modeller är för närvarande begränsad till utvalda användare och kommer att användas i alla miljöer i en framtida version.</p>
<img src="assets/do-not-localize/ai-ranking.gif"/>
<p>Mer information finns i den <a href="../offers/ranking/personalized-optimization-model.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar

**Resor**

* **Avsluta en resa** - På arbetsytan **End** aktiviteten har tagits bort från paletten. Sluttaggar läggs nu till som standard i slutet av varje bana och kan inte tas bort. Denna förbättring gör det möjligt att bättre rapportera var en kund lämnade resan, utan att någon åtgärd krävs från kundens sida. Se [dokumentation](../building-journeys/journey-end.md) och [funktionsvideo](https://video.tv.adobe.com/v/345376){target=&quot;_blank&quot;}.


* The **Tidszon för profil** alternativet är nu avmarkerat som standard i resans egenskaper. [Läs mer](../building-journeys/timezone-management.md#timezone-from-profiles)

**Meddelanden**

* Meddelandeförinställningar är nu **kanalytor**. [Läs mer](../configuration/channel-surfaces.md)

**Administrering**

* **PTR-postversion** - När du nu uppdaterar en PTR-post tar bearbetningstiden endast upp till 3 timmar. [Läs mer](../configuration/ptr-records.md#processing)

* **Tillåtelselista UI** - Nu kan du använda Journey Optimizer användargränssnitt för att lägga till nya e-postadresser eller domäner i tillåtelselista. [Läs mer](../configuration/allow-list.md)

* **Tillåtelselista logikuppdatering** - Nu gäller logiken i tillåtelselista så snart funktionen är aktiverad, även om listan är tom. [Läs mer](../configuration/allow-list.md#logic)

* **URL-spårningsparametrar** - Du kan nu använda uttrycksredigeraren för att konfigurera parametrar för URL-spårning i dina e-postytor (t.ex. förinställningar). [Läs mer](../configuration/email-settings.md#url-tracking)

**Beslutsledning**

* **Målgruppsstorlek** - En ny uppskattningskomponent för målgruppsstorlek visas nu i användargränssnittet när du skapar en beslutsregel, när du väljer ett segment eller en regel för att ange ett erbjudande eller när du lägger till ett segment eller en regel i ett beslutsomfång.


## Version från juni 2022 {#june-2022-release}

### Nya funktioner

<table>
<thead>
<tr>
<th><strong>Skicka SMS till användarna (begränsad tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du skapa, anpassa och skicka SMS i Journey Optimizer via en integrering med <b>Sinch</b> eller <b>Twilio</b>.</p>
<!--img src="assets/do-not-localize/SMS.gif"/-->
<p>SMS-kanalen är för närvarande bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant om du vill ha mer information.</p>
<p>Lär dig hur du skapar och skickar ett SMS i det här <a href="../messages/create-sms.md">detaljerad dokumentation</a>.</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Hitta slagkraftigare bilder snabbare tack vare Adobe Stock integration</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Integreringspluginen för Adobe Stock och Adobe Journey Optimizer Email Designer ger kunderna ett enkelt sätt att navigera, licensiera och spara bilder för användning i meddelandeframställning. </br> Den nya <b>Hitta liknande Stock-foton</b> kan du också söka efter Stock-foton som matchar innehållet, färgen och kompositionen för dina bilder. </p>
<!--img src="assets/do-not-localize/stock-rn.gif"/-->
<p>Mer information finns i den <a href="../design/stock.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Använd BCC för e-post för alla e-postmeddelanden</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du använda funktionen för hemlig kopia (Email BCC) för att lagra e-postmeddelanden som skickas av Adobe Journey Optimizer. Aktivera det här alternativet i dina e-postförinställningar så att alla e-postmeddelanden som skickas är blinda och kopieras till din BCC-adress.</p>
<!--img src="assets/do-not-localize/bcc-rn.gif"/-->
<p>Mer information finns i den <a href="../configuration/archiving-support.md#bcc-email">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<!--<table>
<thead>
<tr>
<th><strong>Automatically use the best performing offer in your decisions</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now use personalized optimization model systems in Decision Management. This new type of model allows you to optimize and personalize offers based on segments and offer performance.</p>
<p>The use of personalized optimization AI models is currently restricted to selected users, and will be deployed to all environments in a future release.</p>
<img src="assets/do-not-localize/ai-ranking.gif"/>
<p>For more information, refer to the <a href="../offers/ranking/personalized-optimization-model.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>-->

<table>
<thead>
<tr>
<th><strong>Kopiera objekt mellan sandlådor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du återskapa upplevelser från en Journey Optimizer-sandlåda till en annan, till exempel från en icke-produktionssandlåda till en produktionssandlåda. Den nya funktionen kopierar en hel resa, inklusive alla objekt som resan är beroende av för att kunna köras korrekt, från en miljö till en annan. Förutom Resor kan du även kopiera andra komponenter, som erbjudanden, meddelanden, scheman, datauppsättningar, datakällor, händelser och åtgärder.</p>
<p>Mer information finns i den <a href="../building-journeys/copy-to-sandbox.md">detaljerade dokumentationen</a>.
</td>
</tr>
</tbody>
</table>




### Förbättringar

**Beslutsledning**

* **Stöd för HTML och JSON-filer** - Nu kan du dra och släppa externa HTML- och JSON-filer från Adobe Experience Cloud resursbibliotek till erbjudanderepresentationsinnehållet. [Läs mer](../offers/offer-library/add-representations.md#html-json)


**E-post**

* **Spara som mall** - Du kan nu spara ett e-postinnehåll som en mall och återanvända det när du skapar andra meddelanden. [Läs mer](../design/email-templates.md)


**Administrering**

* **URL-parametrar för förhandsspårning** - När du konfigurerar en meddelandeförinställning och definierar parametrar för URL-spårning, visas nu en dynamisk förhandsgranskning av den resulterande spårnings-URL:en. [Läs mer](../configuration/email-settings.md#url-tracking)

* **Meddelandeförinställningsutgåva** - När du nu uppdaterar en meddelandeförinställning kan bearbetningstiden bara ta upp till 3 timmar. [Läs mer](../configuration/channel-surfaces.md#edit-channel-surface)

* **IP-poolversion** - När du nu uppdaterar en IP-pool kan bearbetningstiden bara ta upp till 3 timmar. [Läs mer](../configuration/ip-pools.md#edit-ip-pool)




## Version från maj 2022 {#may-2022-release}

### Nya funktioner

<table>
<thead>
<tr>
<th><strong>Regler för meddelandefrekvens</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du ange affärsregler för flera kanaler som automatiskt utesluter överbegärda profiler från meddelanden och åtgärder.</p>
<!--img src="assets/do-not-localize/frequency-rn.gif"/-->
<p>Mer information finns i den <a href="../configuration/frequency-rules.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Beslutshantering - Automatisk optimeringsmodell för AI-rankning</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Du kan nu använda utbildade modellsystem i Beslutshantering. Den nya funktionen rankar erbjudanden som kan visas för en viss profil.</p>
<!--img src="assets/do-not-localize/optimization.gif"/-->
<p>Mer information finns i den <a href="../offers/offer-activities/configure-offer-selection.md#use-ranking-strategy">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Attribute-based Access Control (ABAC)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Permission management in Journey Optimizer has been extended to data access. You can now manage data access for specific teams or groups of users (i.e. internal, external, 3rd parties) ​and manage access to specific types of data (i.e. Sensitive Personal Data/SPD).</p>
<p>This capability is available for a limited set of customers.</p>
<p>For more information, refer to the <a href="../landing-pages/create-lp.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>Journey Optimizer granskningsloggar</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du övervaka åtgärder som utförs av användare på Adobe Journey Optimizer-resurser.</p>
<!--img src="assets/do-not-localize/audit-rn.gif"/-->
<p>Mer information finns i den <a href="../privacy/audit-logs.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar

**Personalisering**

* **Ny hjälpfunktion för dolda tecken** - `mask` hjälpfunktionen gör att du kan ersätta en del av en sträng med&quot;X&quot;-tecken. [Läs mer](../personalization/functions/string.md#mask)

**Landningssidor**

* **Landningssidor utan formulär** - Nu kan du skapa och publicera en landningssida som inte innehåller något formulär och som inte kräver någon åtgärd från besökarna.
* **Mallar för landningssidor** - Du kan nu spara en landningssida som en mall och återanvända den när du skapar andra landningssidor. [Läs mer](../landing-pages/lp-templates.md)
* **Tillbaka till den primära sidan** - Du kan nu lägga till en länk till den primära sidan från en undersida på samma landningssida.
* **Anpassat JavaScript-stöd** - Du kan nu lägga till egen JavaScript-kod i innehållet på landningssidan för att utföra avancerad formatering eller lägga till anpassade beteenden på landningssidorna.    [Läs mer](../landing-pages/lp-custom-js.md)

**Resor**

* **Lässegment** - Enbildsresor för Läs segment har flyttats till slutstatus 30 dagar efter det att resan körts. För schemalagda läs-segment är det 30 dagar efter körningen av den sista förekomsten. [Läs mer](../building-journeys/read-segment.md)
* **Uttrycksredigerare** - [limit](../building-journeys/functions/functionlimit.md) -funktionen har lagts till så att du kan begränsa antalet objekt i en lista. The [sortera](../building-journeys/functions/functionsort.md) kan du nu sortera ut ett listobjekt. Stödet för listObject har också lagts till i [urskilja](../building-journeys/functions/functiondistinct.md) och [clearWithNull](../building-journeys/functions/functiondistinctwithnull.md) funktioner.

**Administrering**

* **Uppdatering av kontrollpanelen för licensanvändning** - Kontrollpanelen för licensanvändning finns i [!DNL Adobe Journey Optimizer] användargränssnittet återspeglar nu det korrekta värdet för **Licensierad** Genomsnittlig profilrikedom. Du kommer att se en minskning i den här måttvisningen, vilket innebär att licensgränsen nu rapporteras korrekt. [Läs mer](../segment/license-usage.md)


## Version från april 2022 {#april-2022-release}

### Förbättringar

**Landningssidor**

* **Nytt alternativ för kryssrutor för anmälan/avanmälan** - Nu kan du infoga en enda kryssruta för deltagande/avanmälan på prenumerationens landningssidor. Användarna måste markera kryssrutan för att godkänna (anmälan) och avmarkera den för att ta bort sitt samtycke (avanmälan). [Läs mer](../landing-pages/design-lp.md#define-lp-specific-content)

* **förifyllda landningssidor** - Det är nu möjligt att ge användarna möjlighet att förifylla landningssidans fält med profilinformation. [Läs mer](../landing-pages/create-lp.md#configure-primary-page)

**Beslutsledning**

* **Besluts-API på Edge** - Edge Decisioning API kan leverera och återge personaliserade erbjudanden som hanteras i beslutsprocessen. Du kan skapa erbjudanden och andra relaterade objekt med hjälp av användargränssnittet (UI) eller API:erna för beslutshanteringen. [Läs mer](../offers/api-reference/offer-delivery-api/edge-decisioning-api.md)

**Administrering**

* **PTR-varaktighet** - Tidslängden för PTR-redigering är nu några timmar. [Läs mer](../configuration/ptr-records.md#processing)

**E-postdesign**

* **20 nya e-postmallar** kan nu utforma e-postinnehåll i Journey Optimizer.

**Användargränssnitt**

* **Sammanhangsberoende hjälp i Journey Optimizer UI** - Sammanhangsberoende hjälplänkar har lagts till på flera sidor i Journey Optimizer. Om den är tillgänglig klickar du på ikonen i för att visa en snabb beskrivning av den aktuella funktionen och få tillgång till relaterade artiklar.

**Integrering med Adobe Campaign Standard**

Som Adobe Campaign Standard-kund kan du nu skicka e-post, push-meddelanden och SMS med Journey Optimizer. Använd de nya inbyggda funktionerna för att utnyttja Campaign Standarden Transactional Messaging i Journey Optimizer.  [Läs mer](../action/acs-action.md)

<!--
### Fixes

* Fixed an issue which caused tracking reports not to be available as the `JourneyActionId` was not properly populated. PLATIR-19854, CJM-26006
* Fixed an error on business events which could block the journey publication. CJM-25931
* Fixed an issue which could prevent images in Email Designer templates from being displayed. PLATIR-18176, CJM-25008
-->

## Version från mars 2022 {#march-2022-release}

### Förbättringar

**Resor**

* För att undvika att det finns onödiga fält i det enhetliga profilschemat är händelseschemat för resan som standard inte längre aktiverat för profiler. Om det behövs kan du aktivera det. [Läs mer](../reports/sharing-overview.md)
* Nya steghändelser för exportjobb skickas nu av Journey Optimizer till Adobe Experience Platform. Exempel på frågor har lagts till i dokumentationen. [Läs mer](../reports/query-examples.md)

**Beslutsledning**

* Du kan nu ange om begränsningen av erbjudanden ska gälla för alla användare eller för en viss profil, och för alla placeringar eller per placering. [Läs mer](../offers/offer-library/add-constraints.md#capping)
* Med API:t för gruppbeslut kan organisationer använda beslutsstyrningsfunktioner för alla profiler i ett visst segment i ett enda anrop. Erbjudandeinnehållet för varje profil i segmentet placeras i en AEP-datauppsättning där det är tillgängligt för anpassade batcharbetsflöden. [Läs mer](../offers/api-reference/offer-delivery-api/batch-decisioning-api.md)

**Administrering**

* Du kan nu aktivera/inaktivera länken för att avbryta prenumerationen i/från e-posthuvudet på den förinställda meddelandenivån och ange en anpassad URL för att avbryta prenumerationen på meddelandenivån. [Läs mer](../configuration/channel-surfaces.md#list-unsubscribe)
* Tillåtelselista kan nu aktiveras och inaktiveras via [!DNL Journey Optimizer] gränssnitt för produktions- och icke-produktionssandlådor. [Läs mer](../configuration/allow-list.md#enable-allow-list)

**Personalisering**

* Du kan nu spara mer än 40 personaliseringsuttryck i biblioteket. [Läs mer](../personalization/personalization-library.md)

## Version från februari 2022 {#feb-2022-release}

### Nya funktioner

<table>
<thead>
<tr>
<th><strong>Prenumerationslandsidor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du skapa och utforma landningssidor i Journey Optimizer och dirigera dina användare till onlineformulär där de kan välja att inte ta emot meddelanden eller prenumerera på en viss tjänst som ett nyhetsbrev.</p>
<p>Mer information finns i <a href="../landing-pages/create-lp.md">detaljerad dokumentation</a> och relaterade <a href="../landing-pages/lp-use-cases.md">exempel</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Nytt bibliotek för anpassningsuttryck</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer har nu ett bibliotek där du kan komma åt fördefinierade personaliseringsuttryck. Uttrycken konfigureras av Admin-användare.</p>
<p>Mer information finns i den <a href="../personalization/personalization-library.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


<!--table>
<thead>
<tr>
<th><strong>API Developer Site and Suppression API</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer provide RESTful APIs that allow you to programmatically perform key operations in your applications.
Developer SDK for Journey Optimizer is now available with the Suppression API (beta).</p>
<p>With this API, you can control your outgoing messages using suppression and allow lists.
The suppression list helps you with honoring the ISPs' feedback to preserve sending IP reputation. The allow list helps you ensure that you send only to those email addresses which are in the allowed list, and typically to ensure that you don't send mails to customers from your development sandbox.</p>
<p>See <a href="https://developer.adobe.com/journey-optimizer-apis/">Adobe Journey Optimizer APIs</a>.</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>Skicka information för att spåra meddelanden med UTM-spårningsparametrar</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>I Journey Optimizer-meddelandeinnehåll kan du nu lägga till UTM-parametrar i länkarna: kan de tillhandahålla ytterligare data om länken och hjälpa dig att identifiera var och varför en person som klickat på länken.</p>
<p>Mer information finns i den <a href="../configuration/channel-surfaces.md#configure-email-settings">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar

**Resor**

* För att optimera prestandan kommer alla resor i testläge som inte har utlösts på en vecka nu att återgå till statusen Utkast. [Läs mer](../building-journeys/testing-the-journey.md#important_notes)
* Integrationen mellan Journey Optimizer och Adobe Campaign Classic har optimerats för att förbättra prestandan. Standardkonfigurationen för begränsning har ändrats till 4 000 anrop/5 minuter.    [Läs mer](../action/acc-action.md#important-notes)

**Rapportering**

* Leveranser kan nu filtreras beroende på status:
   * I listan Meddelandekörning kan du nu utesluta korrektur från leveranslistan.
   * I dina Live-/Global-rapporter kan du välja att exkludera testhändelser.

* Nu kan du få åtkomst till rapporter om optimeringsdata för sändningstid: antalet personer som var omedelbart meddelandeansvariga och antalet personer som fick meddelanden med 1 timmes optimering, 2 timmars optimering osv.

<!--* decision management reports are now available in Journey Optimizer. You can access the following metrics: Offers sent - Offers' impression rate - Offers' click rate - Breakdown report on Offers' sent.-->

**Beslutsledning**

* Rankningar och AI-rankning grupperas nu tillsammans i en enda flik.

## Version från januari 2022 {#january-2022-release}

### Nya funktioner

<table>
<thead>
<tr>
<th><strong>Journeys - Optimera din IP-uppgradering med villkor för profilliffor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>När en <strong>Villkor</strong> -aktivitet på en resa kan du nu definiera en profilövre gräns. Med den här nya villkorstypen kan du ange ett maximalt antal profiler för en resväg. När den här gränsen nås får de inmatade profilerna en alternativ sökväg. Detta gör att du kan öka volymen på dina leveranser (IP-förstärkning). Du kanske vill förbättra leveransen på en domän genom att dela körningen: skicka 1000 meddelanden dag 1, 2000 dag 2 osv.</p>
<p>Mer information finns i <a href="../building-journeys/condition-activity.md#profile_cap">detaljerad dokumentation</a> och relaterade <a href="../building-journeys/ramp-up-deliveries-uc.md">exempel</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Journeys - förbättring av läs segment</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The <strong>Inkrementell läsning</strong> har lagts till i återkommande <strong>Läs segment</strong> verksamhet. Med det här alternativet kan du bara rikta in dig på de personer som har gått in i segmentet sedan den senaste körningen av resan. Den första körningen riktar sig alltid till alla segmentmedlemmar.</p>
<p>Mer information finns i den <a href="../building-journeys/read-segment.md#configuring-segment-trigger-activity">detaljerade dokumentationen</a>.
</td>
</tr>
</tbody>
</table>

### Förbättringar

**Resor**

* Journey Optimizer steghändelser kan nu länkas till andra datauppsättningar i [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html). The **profileID** -fältet, i det inbyggda schemat för händelser i resan, definieras nu som ett identitetsfält. [Läs mer](../reports/sharing-overview.md#integration-cja)

**Beslutsledning**

* När du uppdaterar ett erbjudande, ett reserverbjudande, en erbjudandesamling eller ett erbjudandebeslut som direkt eller indirekt hänvisas till i ett publicerat meddelande, återspeglas uppdateringarna nu automatiskt i motsvarande meddelande, utan att det behöver publiceras på nytt. [Läs mer](../offers/offers-e2e.md#insert-decision-in-email)

* När du simulerar vilka erbjudanden som ska levereras för en viss testprofil kan du nu ändra standardsimuleringsinställningarna och visa koden som motsvarar dina simuleringar som kan användas i felsökningssyfte. [Läs mer](../offers/offer-activities/simulation.md#define-simulation-settings)

**Administrering**

* Administratörer kan nu redigera PTR-poster med en CNAME-konfigurerad underdomän. [Läs mer](../configuration/ptr-records.md#edit-ptr-subdomains-cname)

**Personalisering**

* **Lägg till i favoriter** - För att förbättra effektiviteten i arbetet med personalisering har vi introducerat begreppet att spara favoriter. Genom att lägga till olika attribut på Favoriter-menyn får du snabb åtkomst till de objekt du använder mest. [Läs mer](../personalization/personalize.md#fav)
