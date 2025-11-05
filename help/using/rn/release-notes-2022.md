---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation 2022
description: Versionsinformation om Journey Optimizer 2022
feature: Release Notes
topic: Content Management
role: User
level: Beginner, Intermediate
hidefromtoc: true
hide: true
exl-id: 0997a640-3f89-4460-ba93-ea21a9d4efc5
source-git-commit: 0331f8fe2439d41c08ad88a6d0bd95dd150bab90
workflow-type: tm+mt
source-wordcount: '3599'
ht-degree: 8%

---

# Versionsinformation för 2022 {#release-notes-2022}

På den här sidan visas alla funktioner och förbättringar för [!DNL Journey Optimizer] som släpptes 2022.



## Oktober 2022-versionen {#oct-2022-release}

<!--

### New capability{#oct-2022-features}

<table>
<thead>
<tr>
<th><strong>Direct Mail Channel (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now add direct mail messages in your campaigns and journeys. Direct mail is an offline channel that allows you to personalize and generate the files required by direct mail providers to send mail to your customers.</p>
<p>When you prepare a direct mail delivery, Journey Optimizer generates a file including all the targeted profiles and the chosen contact information (postal address for example). You will then be able to send this file to your direct mail provider who will take care of the actual sending.</p>
</td>
</tr>
</tbody>
</table>

-->

### Förbättringar {#oct-2022-improvements}

**Resor**

* Alternativet **Tvinga återinträde vid upprepning** har lagts till i återkommande parametrar för läsmålgruppsschema. Med det här alternativet kan du göra så att alla profiler som fortfarande finns i resan automatiskt avslutar den vid nästa körning. När alternativet är inaktiverat måste profilerna slutföra resan innan de kan återkomma i en annan förekomst. [Läs mer](../building-journeys/read-audience.md#configuring-segment-trigger-activity)

**Administration**

* Ett meddelande lades till i användargränssnittet för att varna för att underdomäner, underdomäner för landningssidor, PTR-poster och IP-poolkonfigurationer är gemensamma för alla sandlådor och därför kommer ändringar i någon av dessa konfigurationer även att påverka produktionssandlådorna.
* Stegen för att överföra undertryckningslistan som en CSV-fil från användargränssnittet har ändrats. [Läs mer](../configuration/manage-suppression-list.md#download-suppression-list)

**Kampanjer**

* Nu kan ni arkivera slutförda och stoppade kampanjer. [Läs mer](../campaigns/manage-campaigns.md#archive)


## September 2022-utgåvan{#sept-2022-release}

### Nya funktioner{#sept-2022-features}

<table>
<thead>
<tr>
<th><strong>Dynamiskt innehåll och ny villkorsstyrd regelgenererare</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du skapa dynamiskt innehåll för att anpassa innehållet i dina meddelanden baserat på villkorliga regler.</p> 
<p>Villkorliga regler skapas med en visuell regelbyggare i uttrycksredigeraren, där du kan lagra dem för ytterligare återanvändning under resor och kampanjer.</p>
<img src="assets/do-not-localize/dynamic-content.gif"/>
<p>Mer information finns i den <a href="../personalization/get-started-dynamic-content.md">detaljerade dokumentationen</a>.
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>API-utlösta kampanjer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Förutom befintliga schemalagda kampanjer kan ni nu skapa API-utlösta kampanjer i Journey Optimizer och anropa dem från ett externt system med API:er.</p>
<p>På så sätt kan du täcka olika behov av användnings- och transaktionsmeddelanden, som lösenordsåterställningar, OTP-token, bland annat.</p>
<img src="assets/do-not-localize/api-triggered.gif"/>
<p>Mer information finns i den <a href="../campaigns/api-triggered-campaigns.md">detaljerade dokumentationen</a>.
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Dataåtkomstkontroll</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med attributbaserad åtkomstkontroll kan administratörer styra åtkomsten till specifika objekt baserat på vissa attribut. Dessa attribut kan läggas till i ett objekt, till exempel etiketter. Från och med den här versionen kan administratörer även definiera användarroller som bara har åtkomst till specifika fält och/eller objekt, och data som motsvarar dessa fält och/eller objekt.</p>
<p> Attributbaserad åtkomstkontroll är för närvarande begränsad till vissa kunder och kommer att användas i alla miljöer i en framtida version.</p>
<img src="assets/do-not-localize/olac.gif"/>
<p>Mer information finns i den <a href="../administration/object-based-access.md">detaljerade dokumentationen</a>.
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Datastyrning och sekretess</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med styrningsramverket DULE (Data Usage Labeling and Enforcement) kan Journey Optimizer nu utnyttja Adobe Experience Platform styrningsprinciper för att förhindra att känsliga fält exporteras till tredjepartssystem via anpassade åtgärder. Om systemet identifierar ett begränsat fält i de anpassade åtgärdsparametrarna visas ett fel som hindrar dig från att publicera resan.</p>
<p>Användningen av etiketter och tvångsåtgärder för användning av data (DULE) är för närvarande begränsad till utvalda kunder och kommer att distribueras till alla miljöer i en framtida version.</p>
<p>Mer information finns i den <a href="../action/action-privacy.md">detaljerade dokumentationen</a>.
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Automated Consent Enforcement (profiler för automatiskt samtycke)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med Adobe Experience Platform kan ni enkelt införa och tillämpa marknadsföringspolicyer för att respektera kundernas samtycke. Samtyckesregler definieras i Adobe Experience Platform. I Journey Optimizer kan du tillämpa dessa medgivandeprinciper på dina anpassade åtgärder. Du kan till exempel definiera samtyckesprofiler för att utesluta kunder som inte har samtyckt till att ta emot e-post, push-meddelanden eller SMS-kommunikation.
<p>Automated Conforcement är för närvarande endast tillgängligt för organisationer som har köpt tillägget Healthcare Shield.</p>
<p>Mer information finns i den <a href="../action/consent.md">detaljerade dokumentationen</a>.
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Behörighetshantering</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer har stöd för att definiera användarroller och åtkomstprinciper för att hantera behörigheter för funktioner och objekt. Genom <strong>Adobe Experience Cloud-behörigheter</strong> kan du skapa och hantera roller samt tilldela önskade resursbehörigheter för dessa roller. Med behörigheter kan du också hantera etiketter, sandlådor och användare som är kopplade till en viss roll.</p>
<p> Användningen av behörigheter är för närvarande begränsad till utvalda kunder och kommer att distribueras till alla miljöer i en framtida version.</p>
<p>Mer information finns i den <a href="../administration/attribute-based-access.md">detaljerade dokumentationen</a>.
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Varningar och övervakning</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Som Journey Optimizer-användare kan du nu få åtkomst till systemvarningar via användargränssnittet för att få meddelanden när resor inte fungerar som förväntat. Du kan visa tillgängliga aviseringar och prenumerera på dem. Den första varningen som är tillgänglig med den här versionen varnar dig om en Läs publik-aktivitet inte har bearbetat någon profil under den definierade tidsramen. Mer kommer nu när arbetsflödet är olåst.</p>
<!--p>For more information, refer to the <a href="../reports/alerts.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>


<!--table>
<thead>
<tr>
<th><strong>Data Hygiene</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform provides a suite of data hygiene capabilities that allow you manage your stored data through programmatic deletions of consumer records and datasets. This capability is now available for Adobe Journey Optimizer. </p>
<p>You can manage your data stores to ensure that information is used as expected, is updated when incorrect data needs fixing, and is deleted when organizational policies deem it necessary.</p>
<p><strong>Caution</strong> - Data Hygiene capabilities are currently only available for organizations that have purchased the Healthcare Shield add-on offering.</p>
<p>For more information, refer to the <a href="../building-journeys/read-audience.md#configuring-segment-trigger-activity">detailed documentation</a>.
</td>
</tr>
</tbody>
</table-->

### Förbättringar{#sept-2022-improvements}

**Resor**

* **Entitetsdatauppsättningen** är nu tillgänglig som en färdig datauppsättning i Adobe Journey Optimizer. Den här uppslagsuppsättningen innehåller metadata som berikar informationen om spårnings- och feedbackdatauppsättningar. Detta hjälper er att förbättra era rapporter och frågor med mer begripliga data. [Läs mer](../data/datasets-query-examples.md#entity-dataset)
* Ett nytt skyddsräcke har lagts till för enstaka resor (med början vid en händelse eller en målgruppskompetens) för att förhindra att resor utlöses felaktigt flera gånger för samma händelse. Profilåterinträde blockeras nu tillfälligt som standard i 5 minuter. [Läs mer](../start/guardrails.md#events-g)

**Administration**

* När du aktiverar eller inaktiverar tillåtelselista visas nu en ny varning som detaljerar effekterna av varje åtgärd. [Läs mer](../configuration/allow-list.md#enable-allow-list)
* Användargränssnittet för att skapa kanalkonfigurationer, skapa IP-pooler, hantera inaktiveringslistan och tillåtelselista samt konfigurera SMS-kanalen har uppdaterats.
* När du nu skapar den första kanalkonfigurationen för en viss underdomän tar bearbetningstiden 10 minuter till 10 dagar och endast upp till 3 timmar för efterföljande ytor som använder den underdomänen. [Läs mer](../configuration/channel-surfaces.md#create-channel-surface)
* Användargränssnittet för att skapa förinställningar för landningssidor och underdomäner för landningssidor har uppdaterats. [Läs mer](../landing-pages/lp-subdomains.md)

**Granskningskontroller**

* Med Journey Optimizer kan ni identifiera vilka åtgärder som användare i systemet utför på olika tjänster och funktioner, som kampanjer, resor, meddelanden, landningssidor osv. Granskningsloggresurser innehåller nu ändringar av olika andra åtgärder och registreras automatiskt när aktiviteten utförs. Läs mer [på den här sidan](../privacy/audit-logs.md).

**Arkiveringsstöd**

* Den nya **entitetsdatauppsättningen** innehåller ett mallfält som gör att du kan exportera format och struktur för skickade meddelanden i alla kanaler för arkiveringsändamål. [Läs mer](../configuration/archiving-support.md)

**Landningssidor**

* Nu kan du använda kontextuella data från en annan sida på samma landningssida. Om du t.ex. länkar en kryssruta till en prenumerationslista på den primära landningssidan kan du använda den prenumerationslistan på undersidan&quot;Tack&quot;. [Läs mer](../landing-pages/lp-content.md#use-primary-page-context)

<!--* When configuring the primary page, you can now create additional data to enable storing information when the landing page is being submitted. [Learn more](../landing-pages/lp-content.md#use-additional-data)-->

<!--* You can now use information that was submitted on a landing page to send communications to your customers. For example, if a user subscribes to a given subscription list, you can leverage that information to send an email recommending other subscription lists to that user.-->

### Andra ändringar{#sept-2022-other}

* Reseburst-läget har ersatts av Campaign-läget för snabb leverans. [Läs mer](../push/create-push.md#rapid-delivery)
* För att förbättra prestandan kan inte längre fältgrupper för Experience-händelser användas på resor som börjar med en läsare, en målgrupp eller en affärshändelseaktivitet. Denna ändring gäller endast för nya resor. Befintliga beteenden behåller det aktuella beteendet. [Läs mer](../start/guardrails.md#expression-editor)
* Begränsningen på en timme för schemalagda läsningar av målgruppsresor har tagits bort. Dessa resor kan nu genomföras utan dröjsmål.




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
<p>Använd Journey Optimizer kampanjer för att leverera engångsinnehåll till en viss målgrupp via olika kanaler. När du använder resor är åtgärderna utformade för att utföras i sekvens. Med kampanjer utförs åtgärder samtidigt, antingen omedelbart eller baserat på ett angivet schema. </p>
<img src="assets/do-not-localize/campaigns.gif"/>
<p>Lär dig hur du skapar en kampanj i videon <a href="../campaigns/get-started-with-campaigns.md">med detaljerad dokumentation</a> och <a href="https://video.tv.adobe.com/v/346680">funktioner</a>.
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
<p>Lär dig hur du skapar och skickar ett SMS i den här <a href="../sms/create-sms.md">detaljerade dokumentationen</a>.</p>
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
<p>For more information, refer to the <a href="../building-journeys/read-audience.md#configuring-segment-trigger-activity">detailed documentation</a>.
</td>
</tr>
</tbody>
</table-->


### Förbättringar

**Rapportering**

* Policytabell och diagram för samtycke finns nu tillgängliga i globala rapporter om resor. Med dessa widgetar kan du spåra de uteslutna profilerna från profilerna i dina anpassade åtgärder. [Läs mer](../reports/journey-global-report-cja.md#journey-global)

  Observera att du måste återställa de olika rapportinstrumentpanelerna för att få tillgång till de senaste widgetarna. Mer information om anpassning av kontrollpanelen finns i [den detaljerade dokumentationen](../reports/report-gs-cja.md).

**Administration**

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
<p>Mer information finns i <a href="../offers/batch-delivery.md">den detaljerade dokumentationen.</p>
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
<p>Ni kan nu använda personaliserade optimeringsmodellsystem i beslutshanteringen. Med den här nya typen av modell kan ni optimera och personalisera erbjudanden baserat på målgrupper och erbjuda resultat.</p>
<p>Användningen av anpassade optimerings-AI-modeller är för närvarande begränsad till utvalda användare och kommer att användas i alla miljöer i en framtida version.</p>
<img src="assets/do-not-localize/ai-ranking.gif"/>
<p>Mer information finns i den <a href="../offers/ranking/personalized-optimization-model.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar

**Resor**

* **Slutar en resa** - I arbetsytan har aktiviteten **Slut** tagits bort från paletten. Sluttaggar läggs nu till som standard i slutet av varje bana och kan inte tas bort. Denna förbättring gör det möjligt att bättre rapportera var en kund lämnade resan, utan att någon åtgärd krävs från kundens sida. Se videon [documentation](../building-journeys/end-journey.md) och [feature ](https://video.tv.adobe.com/v/345376){target="_blank"}.


* Alternativet **Tidszon för profil** är nu avmarkerat som standard i resans egenskaper. [Läs mer](../building-journeys/timezone-management.md#timezone-from-profiles)

**Meddelanden**

* Meddelandeförinställningar är nu **kanalkonfigurationer**. [Läs mer](../configuration/channel-surfaces.md)

**Administration**

* **PTR-postversion** - När en PTR-post uppdateras tar bearbetningstiden endast upp till 3 timmar. [Läs mer](../configuration/ptr-records.md#processing)

* **Tillåtelselista-gränssnitt** - Nu kan du använda Journey Optimizer användargränssnitt för att lägga till nya e-postadresser eller domäner i tillåtelselista. [Läs mer](../configuration/allow-list.md)

* **Tillåtelselista-logikuppdatering** - Nu gäller logiken i tillåtelselista så snart funktionen är aktiverad, även om listan är tom. [Läs mer](../configuration/allow-list.md#logic)

* **Parametrar för URL-spårning** - Nu kan du använda uttrycksredigeraren för att konfigurera parametrar för URL-spårning i e-postytorna (t.ex. förinställningar). [Läs mer](../email/email-settings.md#url-tracking)

**Beslutshantering**

* **Målgruppsstorlek** - En ny uppskattningskomponent för målgruppsstorlek visas nu i användargränssnittet när du skapar en beslutsregel, när du väljer en målgrupp eller en regel för att ange ett erbjudande eller när du lägger till en målgrupp eller en regel i ett beslutsomfång.


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
<p>SMS-kanalen är för närvarande bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant om du vill veta mer.</p>
<p>Lär dig hur du skapar och skickar ett SMS i den här <a href="../sms/create-sms.md">detaljerade dokumentationen</a>.</p>
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
<p>Integreringspluginen Adobe Stock och Adobe Journey Optimizer Email Designer ger kunderna ett enkelt sätt att navigera, licensiera och spara bilder för användning vid framtagning av meddelanden. </br> Med det nya alternativet <b>Sök efter liknande Stock-foton</b> kan du även söka efter Stock-foton som matchar innehållet, färgen och kompositionen för dina bilder. </p>
<p>Mer information finns i den <a href="../integrations/stock.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Använd BCC för e-post för alla dina e-postmeddelanden</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du använda funktionen för hemlig kopia (Email BCC) för att lagra e-postmeddelanden som skickas av Adobe Journey Optimizer. Aktivera det här alternativet i dina e-postförinställningar så att alla e-postmeddelanden som skickas blir blinda och kopieras till din BCC-adress.</p>
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
<p>You can now use personalized optimization model systems in Decision Management. This new type of model allows you to optimize and personalize offers based on audiences and offer performance.</p>
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

**Beslutshantering**

* **HTML- och JSON-filer stöder** - Nu kan du dra och släppa externa HTML- och JSON-filer från Adobe Experience Cloud Asset-biblioteket till erbjudanderepresentationsinnehållet. [Läs mer](../offers/offer-library/add-representations.md#html-json)


**E-post**

* **Spara som mall** - Nu kan du spara ett e-postinnehåll som en mall och återanvända det när du skapar andra meddelanden. [Läs mer](../content-management/content-templates.md#save-as-template)


**Administration**

* **URL-parametrar för förhandsgranskningsspårning** - Om du definierar URL-spårningsparametrar när du konfigurerar en meddelandeförinställning visas nu en dynamisk förhandsgranskning av den resulterande spårnings-URL:en. [Läs mer](../email/email-settings.md#url-tracking)

* **Meddelandeförinställning** - När du uppdaterar en meddelandeförinställning kan bearbetningstiden bara ta upp till 3 timmar. [Läs mer](../configuration/channel-surfaces.md#edit-channel-surface)

* **IP-poolversion** - När du uppdaterar en IP-pool kan bearbetningstiden bara ta upp till 3 timmar. [Läs mer](../configuration/ip-pools.md#edit-ip-pool)




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
<p>Mer information finns i den <a href="../conflict-prioritization/rule-sets.md">detaljerade dokumentationen</a>.</p>
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
<p>Mer information finns i den <a href="../privacy/audit-logs.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar

**Personalization**

* **Ny hjälpfunktion för tecken som döljs** - Med hjälpfunktionen `mask` kan du ersätta en del av en sträng med X-tecken. [Läs mer](../personalization/functions/string.md#mask)

**Landningssidor**

* **Landningssidor utan formulär** - Nu kan du skapa och publicera en landningssida som inte innehåller något formulär och som inte kräver någon åtgärd från besökarna.
* **Landningssidmallar** - Nu kan du spara en landningssida som en mall och återanvända den när du skapar andra landningssidor. [Läs mer](../landing-pages/lp-templates.md)
* **Tillbaka till den primära sidan** - Nu kan du lägga till en länk till den primära sidan från en undersida inom samma landningssida.
* **Anpassat stöd för JavaScript** - Nu kan du lägga till anpassad JavaScript till ditt landningssidinnehåll för att utföra avancerad formatering eller lägga till anpassade beteenden på dina landningssidor.    [Läs mer](../landing-pages/lp-custom-js.md)

**Resor**

* **Läsa målgrupp** - En bild Läs målgruppsresor flyttar nu till slutstatus 30 dagar efter resan. För schemalagda läsningsmålgrupper är det 30 dagar efter att den senaste förekomsten har körts. [Läs mer](../building-journeys/read-audience.md)
* **Uttrycksredigeraren** - Funktionen [limit](../building-journeys/functions/list-functions.md#limit) har lagts till så att du kan begränsa antalet objekt i en lista. Med funktionen [sort](../building-journeys/functions/list-functions.md#sort) kan du nu sortera ett listobjekt. Stöd för listObject har också lagts till i funktionerna [disctinct](../building-journeys/functions/list-functions.md#distinct) och [distinktWithNull](../building-journeys/functions/list-functions.md#distinctWithNull) .

**Administration**

* **Kontrollpanelsuppdatering för licensanvändning** - Kontrollpanelen för licensanvändning som finns i användargränssnittet i [!DNL Adobe Journey Optimizer] visar nu det korrekta värdet för den genomsnittliga profilrikedomen i **Licensierad**. Du kommer att se en minskning i den här måttvisningen, vilket innebär att licensgränsen nu rapporteras korrekt. [Läs mer](../audience/license-usage.md)


## Version från april 2022 {#april-2022-release}

### Förbättringar

**Landningssidor**

* **Nytt alternativ för kryssrutor för anmälan/avanmälan** - Nu kan du infoga en enda kryssruta för avanmälan/avanmälan på prenumerationens landningssidor. Användarna måste markera kryssrutan för att godkänna (anmälan) och avmarkera den för att ta bort sitt samtycke (avanmälan). [Läs mer](../landing-pages/design-lp.md#define-lp-specific-content)

* **Fyll i fält för landningssidor i förväg** - Nu kan användarna fylla i fält för landningssidor i förväg med profilinformation. [Läs mer](../landing-pages/create-lp.md#configure-primary-page)

**Beslutshantering**

* **API för beslutsfattande på Edge** - API för Edge Decisioning kan leverera och återge personaliserade erbjudanden som hanteras i beslutsprocessen. Du kan skapa erbjudanden och andra relaterade objekt med hjälp av användargränssnittet (UI) eller API:erna för beslutshanteringen. [Läs mer](../offers/api-reference/offer-delivery-api/edge-decisioning-api.md)

**Administration**

* **Varaktighet för PTR-sändning** - Varaktigheten för PTR-redigering är nu några timmar. [Läs mer](../configuration/ptr-records.md#processing)

**E-postdesign**

* **20 nya e-postmallar** finns nu tillgängliga för att utforma ditt e-postinnehåll i Journey Optimizer.

**Användargränssnitt**

* **Sammanhangsberoende hjälp i Journey Optimizer UI** - Sammanhangsberoende hjälplänkar har lagts till på flera sidor i Journey Optimizer. Om den är tillgänglig klickar du på ikonen i för att visa en snabb beskrivning av den aktuella funktionen och få tillgång till relaterade artiklar.

**Integrering med Adobe Campaign Standard**

Som Adobe Campaign Standard-kund kan du nu skicka e-post, push-meddelanden och SMS med Journey Optimizer. Använd de nya inbyggda funktionerna för att utnyttja Campaign Standard Transactional Messaging i Journey Optimizer.  [Läs mer](../action/acs-action.md)

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

**Beslutshantering**

* Du kan nu ange om begränsningen av erbjudanden ska gälla för alla användare eller för en viss profil, och för alla placeringar eller per placering. [Läs mer](../offers/offer-library/add-constraints.md#capping)
* Med API:t för gruppbeslut kan organisationer använda beslutsfunktioner för alla profiler i en viss målgrupp i ett enda anrop. Erbjudandeinnehållet för varje profil i målgruppen placeras i en AEP-datauppsättning där det är tillgängligt för anpassade grupparbetsflöden. [Läs mer](../offers/api-reference/offer-delivery-api/batch-decisioning-api.md)

**Administration**

* Du kan nu aktivera/inaktivera länken för att avbryta prenumerationen i/från e-posthuvudet på den förinställda meddelandenivån och ange en anpassad URL för att avbryta prenumerationen på meddelandenivån. [Läs mer](../configuration/channel-surfaces.md#list-unsubscribe)
* Tillåtelselista kommer nu att kunna aktiveras och inaktiveras via [!DNL Journey Optimizer]-gränssnittet i sandlådor för produktion och icke-produktion. [Läs mer](../configuration/allow-list.md#enable-allow-list)

**Personalization**

* Du kan nu spara mer än 40 personaliseringsuttryck i biblioteket. [Läs mer](../personalization/use-expression-fragments.md)

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
<p>Mer information finns i <a href="../landing-pages/create-lp.md">detaljerad dokumentation</a> och relaterat <a href="../landing-pages/lp-use-cases.md">exempel på användning</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Nytt Personalization Expression Library</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer har nu ett bibliotek där du kan komma åt fördefinierade personaliseringsuttryck. Uttrycken konfigureras av Admin-användare.</p>
<p>Mer information finns i den <a href="../personalization/use-expression-fragments.md">detaljerade dokumentationen</a>.</p>
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
The suppression list helps you with honoring the ISPs' feedback to preserve sending IP reputation. The allow list helps you ensure that you send only to those email addresses which are in the allowed list, and typically to ensure that you do not send mails to customers from your development sandbox.</p>
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
<p>I Journey Optimizer-meddelandeinnehåll kan du nu lägga till UTM-parametrar i länkarna: de kan tillhandahålla ytterligare data om länken och hjälpa dig att identifiera var och varför en person klickade på länken.</p>
<p>Mer information finns i den <a href="../configuration/channel-surfaces.md#configure-email-settings">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar

**Resor**

* För att optimera prestandan kommer alla resor i testläge som inte har utlösts på en vecka nu att återgå till statusen Utkast. [Läs mer](../building-journeys/testing-the-journey.md#important_notes)
* Integrationen mellan Journey Optimizer och Adobe Campaign v7/v8 har optimerats för att förbättra prestandan. Standardkonfigurationen för begränsning har ändrats till 4 000 anrop/5 minuter. [Läs mer](../action/acc-action.md#important-notes)

**Rapportering**

* Leveranser kan nu filtreras beroende på status:
   * I listan Meddelandekörning kan du nu utesluta korrektur från leveranslistan.
   * I dina Live-/Global-rapporter kan du välja att exkludera testhändelser.

* Nu kan du få åtkomst till rapporter om data för tidsoptimering för sändning: antalet personer som var meddelanden omedelbart och antalet personer som fick meddelanden med 1 timmes optimering, 2 timmars optimering osv.

<!--* decision management reports are now available in Journey Optimizer. You can access the following metrics: Offers sent - Offers' impression rate - Offers' click rate - Breakdown report on Offers' sent.-->

**Beslutshantering**

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
<p>När du konfigurerar en <strong>villkorsaktivitet</strong> på en resa kan du nu definiera en profillistlinje. Med den här nya villkorstypen kan du ange ett maximalt antal profiler för en resväg. När den här gränsen nås får de inmatade profilerna en alternativ sökväg. Detta gör att du kan öka volymen på dina leveranser (IP-förstärkning). Du kan till exempel vilja förbättra leveransen på en domän genom att dela upp körningen: skicka 1 000 meddelanden dag 1, 2 000 dag 2 osv.</p>
<p>Mer information finns i den <a href="../building-journeys/condition-activity.md#profile_cap">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Journeys - läs målgruppsförbättring</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Alternativet <strong>Inkrementell läsning</strong> har lagts till i återkommande <strong>läs målgruppsaktiviteter</strong>. Med det här alternativet kan ni endast rikta er mot de personer som har gått in i målgruppen sedan den senaste körningen av resan. Den första exekveringen riktar sig alltid till alla målgruppsmedlemmar.</p>
<p>Mer information finns i den <a href="../building-journeys/read-audience.md#configuring-segment-trigger-activity">detaljerade dokumentationen</a>.
</td>
</tr>
</tbody>
</table>

### Förbättringar

**Resor**

* Journey Optimizer steghändelser kan nu länkas till andra datauppsättningar i [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html). Fältet **profileID**, i det inbyggda händelseschemat för kundsteg, har nu definierats som ett identitetsfält. [Läs mer](../reports/sharing-overview.md#integration-cja)

**Beslutshantering**

* När du uppdaterar ett erbjudande, ett reserverbjudande, en erbjudandesamling eller ett erbjudandebeslut som direkt eller indirekt hänvisas till i ett publicerat meddelande, återspeglas uppdateringarna nu automatiskt i motsvarande meddelande, utan att det behöver publiceras på nytt. [Läs mer](../offers/offers-e2e.md#insert-decision-in-email)

* När du simulerar vilka erbjudanden som ska levereras för en viss testprofil kan du nu ändra standardsimuleringsinställningarna och visa koden som motsvarar dina simuleringar som kan användas i felsökningssyfte. [Läs mer](../offers/offer-activities/simulation.md#define-simulation-settings)

**Administration**

* Administratörer kan nu redigera PTR-poster med en CNAME-konfigurerad underdomän. [Läs mer](../configuration/ptr-records.md#edit-ptr-subdomains-cname)

**Personalization**

* **Lägg till i favoriter** - För att förbättra effektiviteten när vi arbetar med personalisering har vi introducerat begreppet att spara favoriter. Genom att lägga till olika attribut på Favoriter-menyn får du snabb åtkomst till de objekt du använder mest. [Läs mer](../personalization/personalize.md#fav)
