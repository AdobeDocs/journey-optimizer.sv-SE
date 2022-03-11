---
title: Versionsinformation
description: Versionsinformation om Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '2643'
ht-degree: 9%

---

# Versionsinformation {#release-notes}

På den här sidan listas alla nya funktioner och förbättringar i [!DNL Journey Optimizer]. Du kan även läsa [senaste dokumentationsuppdateringar](documentation-updates.md) sida för fler ändringar.



## Version från februari 2022 {#feb-2022-release}

### Nya funktioner

<!--table>
<thead>
<tr>
<th><strong>Subscription Landing Pages</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now create and design landing pages in Journey Optimizer, and direct your users to online forms where they can opt-in or opt-out from receiving your communications, or subscribe to a specific service such as a newsletter.</p>
<p>For more information, refer to the <a href="../landing-pages/create-lp.md">detailed documentation</a> and related <a href="../landing-pages/lp-use-cases.md">sample use case</a>.</p>
</td>
</tr>
</tbody>
</table-->

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
The suppression list helps you with honoring the ISPs’ feedback to preserve sending IP reputation. The allow list helps you ensure that you send only to those email addresses which are in the allowed list, and typically to ensure that you don't send mails to customers from your development sandbox.</p>
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
<p>Mer information finns i den <a href="../configuration/message-presets.md#configure-email-settings">detaljerade dokumentationen</a>.</p-->
</td>
</tr>
</tbody>
</table>

### Förbättringar

**Resor**

* För att optimera prestandan kommer alla resor i testläge som inte har utlösts på en vecka nu att återgå till statusen Utkast. [Läs mer](../building-journeys/testing-the-journey.md#important_notes)
* Integrationen mellan Journey Optimizer och Adobe Campaign Classic har optimerats för att förbättra prestandan. Standardkonfigurationen för begränsning har ändrats till 4 000 anrop/5 minuter.	[Läs mer](../action/acc-action.md#important-notes)

**Rapportering**

* Leveranser kan nu filtreras beroende på status:
   * From the Message Execution list, you can now exclude proofs from your deliveries&#39; list.
   * I dina Live-/Global-rapporter kan du välja att exkludera testhändelser.

* You can now access to reports on Send Time Optimization data: the number of persons who were messages immediately and the number of persons who were messaged with 1-hour optimization, 2 hours optimization, etc.

<!--* Offer Decisioning reports are now available in Journey Optimizer. You can access the following metrics: Offers sent - Offers' impression rate - Offers' click rate - Breakdown report on Offers' sent.-->

**Beslutshantering**

* Rankningar och AI-rankning grupperas nu tillsammans i en enda flik.

## Version från januari 2022 {#january-2022-release}

### New capabilities

<table>
<thead>
<tr>
<th><strong>Journeys - Optimera din IP-uppgradering med villkor för profilliffor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>När en <strong>Villkor</strong> -aktivitet på en resa kan du nu definiera en profilövre gräns. This new condition type allows you to set a maximum number of profiles for a journey path. När den här gränsen nås får de inmatade profilerna en alternativ sökväg. Detta gör att du kan öka volymen på dina leveranser (IP-förstärkning). Du kanske vill förbättra leveransen på en domän genom att dela körningen: skicka 1000 meddelanden dag 1, 2000 dag 2 osv.</p>
<p>For more information, refer to the <a href="../building-journeys/condition-activity.md#profile_cap">detailed documentation</a> and related <a href="../building-journeys/ramp-up-deliveries-uc.md">sample use case</a>.</p>
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

* Journey Optimizer step events can now be linked to other datasets in [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html). The **profileID** field, in the built-in Journey Step Event schema, is now defined as an identity field. [Läs mer](../reports/sharing-overview.md#integration-cja)

**offer decisioning**

* När du uppdaterar ett erbjudande, ett reserverbjudande, en erbjudandesamling eller ett erbjudandebeslut som direkt eller indirekt hänvisas till i ett publicerat meddelande, återspeglas uppdateringarna nu automatiskt i motsvarande meddelande, utan att det behöver publiceras på nytt. [Läs mer](../offers/offers-e2e.md#insert-decision-in-email)

* När du simulerar vilka erbjudanden som ska levereras för en viss testprofil kan du nu ändra standardsimuleringsinställningarna och visa koden som motsvarar dina simuleringar som kan användas i felsökningssyfte. [Läs mer](../offers/offer-activities/simulation.md#define-simulation-settings)

**Administrering**

* Administratörer kan nu redigera PTR-poster med en CNAME-konfigurerad underdomän. [Läs mer](../configuration/ptr-records.md#edit-ptr-subdomains-cname)

**Personalisering**

* **Add to favorites** - To help improve efficiency when working with personalization we’ve introduced the concept of saving favorites. Genom att lägga till olika attribut på Favoriter-menyn får du snabb åtkomst till de objekt du använder mest. [Läs mer](../personalization/personalize.md#fav)

## November 2021-utgåvan {#november-2021-release}

<table>
<thead>
<tr>
<th><strong>CNAME subdomain delegation</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer har nu stöd för CNAME. En CNAME-post, eller kanoniskt namnpost, är en post som pekar på en annan domänadress i stället för en IP-adress. CNAME subdomain delegation enables you to create a subdomain and use CNAMEs to point to Adobe-specific records. Using this configuration, both you and Adobe share responsibility for maintaining DNS in order to setup environment for sending, rendering and tracking emails.</p>
<p>Den här metoden rekommenderas om din organisations principer begränsar den fullständiga delegeringsmetoden för underdomäner.</p>
<p>Läs mer om delegering av CNAME-underdomäner i <a href="../configuration/delegate-subdomain.md#cname-subdomain-delegation">detaljerad dokumentation</a>.</p>
</td>
</tr>
</tbody>
</table>


## October 2021 Release {#oct-2021-release}

### Nya funktioner

<table>
<thead>
<tr>
<th><strong>Beslutshantering - simuleringar av erbjudanden</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du simulera vilka erbjudanden som ska levereras till en testprofil för en viss placering i Journey Optimizer användargränssnitt. På så sätt kan du validera din beslutslogik, inklusive behörighetskrav och rangordningsalgoritmer, enkelt innan du sätter dem i produktion. Med den här funktionen kan icke-tekniska och tekniska användare snabbt testa offer decisioning och felsöka potentiella problem.</p>
<p>Mer information finns i den <a href="../offers/offer-activities/simulation.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Beslutshantering - personalisera era erbjudanden</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan ni personalisera innehållet i era erbjudanden med Adobe Experience Platform profilattribut och segment, med samma uttrycksredigeringskomponent som finns i hela Journey Optimizer användargränssnitt. </p>
<p>Mer information finns i den <a href="../offers/offer-library/creating-personalized-offers.md#custom-text">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


Se även [Versionsinformation om Adobe Experience Platform oktober](https://experienceleague.adobe.com/docs/experience-platform/release-notes/2021/october-2021.html){target=&quot;_blank&quot;} om du vill ha fler ändringar.

### Förbättringar

**Resor**

* **Uttrycksredigerare** - Som kraftfull användare kan du nu använda funktioner för att arbeta med kartor. Den här funktionen kan utnyttjas med prenumerationslistorna. Från ett segment kan du nu till exempel hämta en e-postadress från en prenumerationslista. [Läs mer i det här exemplet](../building-journeys/message-to-subscribers-uc.md)

* **Övervakning** - Steghändelser för direktresor och testläge har förbättrats. [Nya fält](../reports/sharing-field-list.md#serviceevents) har lagts till i samband med profilexportjobb. För en bättre användarupplevelse är steghändelsefält nu ordnade i olika kategorier. Alla föregående steg-händelsefält är fortfarande tillgängliga i [stepEvents](../reports/sharing-legacy-fields.md) kategori.
* **Tillgänglighet** - Tillgänglighetsförbättringar har införts under resor.
* **Samlingar** - Arrayer med objekt som innehåller underobjekt stöds nu. [Läs mer](../building-journeys/collections.md)
* **Listor** - Listskärmar har förbättrats för resor, händelser, åtgärder och datakällor.

**Rapportering**

* **Dataformat i global vy** - Nu kan du växla mellan siffror och procenttal i dialogrutan **Global vy** i **Körning** -fliken. [Läs mer](../messages/message-monitoring.md)


**Administrering**

* **Redigera meddelandeförinställningar** - Nu kan du redigera meddelandeförinställningar och övervaka deras uppdateringsstatus. [Läs mer](../configuration/message-presets.md#edit-message-preset)
* **Edit PTR records** - You can now edit PTR records and monitor their update status. [Läs mer](../configuration/ptr-records.md#edit-ptr-record)

**Personalisering**

* **Ny hjälpfunktion för datumformatering** - Du kan nu ange hur en datumsträng ska representeras. [Läs mer](../personalization/functions/dates.md#format-date)


**Decision Management**

* **Evaluation sequencing** - The new and improved decision creation flow enables you to not only navigate between decision objects more seamlessly, but also gives you a complete control of how offer collections are evaluated by the decision engine. Detta inkluderar vilka samlingar som utvärderas tillsammans jämfört med separat, och i vilken ordning samlingarna ska utvärderas. [Läs mer](../offers/offer-activities/create-offer-activities.md#add-decision-scopes)

### Korrigeringar

* Ett problem som gjorde att reselistan, meddelandelistan och e-postdesignern inte kunde visas när webbläsarspråket inte var engelska har åtgärdats.
* Fixed a syntax error which occured when adding personalization using an expression in the Email designer: characters were wrongly escaped.
* Ett problem som orsakade ett 404-fel vid navigering i dialogrutan har korrigerats **Administration** -menyn.
* Korrigerade ett problem som utlöste andra direktresor när en resa testades med hjälp av en affärshändelse.


## September 2021-utgåvan {#september-2021-release}

### Nya funktioner

<table>
<thead>
<tr>

<th><strong>Reporting - Better insight to targeted audience</strong><br/></th>
</thead>
<tbody>
<tr>
<td>
<p>New metrics are available in reporting: Targeted and Excluded for email &amp; push messages are visible in both live and global reports. </br> To have access to the latest metrics, please note that you will have to reset the different reporting dashboards for each channel and reporting type. Mer information om anpassning av kontrollpanelen finns i <a href="../reports/live-report.md">detaljerad dokumentation.</a></p>
<p>En ny kolumn i meddelandekörningslistan visar antalet målprofiler för varje meddelandekörning. </p>
<p>Mer information finns i den <a href="../messages/message-monitoring.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>

<th><strong>Skicka listor med data dynamiskt med anpassade åtgärder</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du skicka samlingar eller en lista med data i dina anpassade åtgärdsparametrar som fylls i dynamiskt vid körning. Två sorters samlingar stöds: enkla samlingar och objektsamlingar. Previously created custom actions will continue working. </p>
<p>For more information on collections, refer to the <a href="../building-journeys/collections.md">detailed documentation</a>. </p>
<p>Funktionerna för att filtrera och överlappa har lagts till i listan med funktioner som är tillgängliga i den avancerade uttrycksredigeraren. Det ger fler möjligheter att filtrera och jämföra samlingar.</p>
<p>Consult the documentation on the <a href="../building-journeys/functions/functionfilter.md">filter</a> and <a href="../building-journeys/functions/functionintersect.md">intersect</a> functions.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar

**Resor**

* Systemgenererade scheman och datauppsättningar som har skapats under etablering av steghändelser är nu i skrivskyddat läge, vilket skyddar mot oavsiktliga ändringar av viktiga scheman. [Läs mer](../reports/sharing-overview.md)
* Etikettera **Vänta** aktivitet med en etikett som ska visas på arbetsytan. Etiketten används också i loggar för rapportering och testläge för att tydligt identifiera vad du gör. [Läs mer](../building-journeys/about-journey-activities.md#best-practices)
* Find your events and actions faster by filtering elements in the **Events** and **Action** categories using search. Orchestration-aktiviteter är inte längre filtrerade. [Läs mer](../building-journeys/using-the-journey-designer.md)
* When defining an event ID condition in a rule-based or business event, the &quot;contains&quot; operator is now available for string types of fields. [Läs mer](../event/about-creating.md)

**E-postkonfiguration**

* När en IP-pool har associerats med en meddelandeförinställning kan du nu redigera den, eftersom uppdateringen är asynkron. Du kan även kontrollera uppdateringsstatus för varje IP-pool. [Läs mer](../configuration/ip-pools.md#edit-ip-pool)


## Version från augusti 2021 {#august-2021-release}

### Nya funktioner

<table>
<thead>
<tr>

<th><strong>Skicka meddelanden vid rätt tidpunkt - optimering vid sändning</strong><br/></th>
</thead>
<tbody>
<tr>
<td>
<p>Skicka automatiskt ditt push- eller e-postmeddelande vid den tidpunkt som passar varje kund du interagerar med Adobe Journey Optimizer. Med optimering för sändningstid, som bygger på Adobe:s AI-tjänster, förutspås den bästa tidpunkten för att skicka e-post eller push-meddelanden för att maximera engagemanget baserat på tidigare öppnings- och klickfrekvenser.</p>
<p>Den här funktionen är för närvarande i betaversion och endast tillgänglig för betakunder. Om du vill gå med i betaprogrammet kontaktar du Adobe kundtjänst.</p>
<p>Mer information finns i den <a href="../building-journeys/journeys-message.md#send-time-optimization">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>

<th><strong>Utnyttja schemarelationer i affärshändelser - Uppslagstabellhantering</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du utnyttja relationer mellan scheman när du konfigurerar affärshändelser. Detta är utöver möjligheten att utnyttja fält från länkade tabeller när en enhetshändelse konfigureras, när villkor används under en resa, i meddelandepersonalisering och i personalisering av anpassade åtgärder.</p>
<p>Mer information finns i den <a href="../event/experience-event-schema.md#leverage_schema_relationships">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Personaliserade URL:er</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Personaliserade URL:er tar mottagarna till specifika sidor på en webbplats eller till en personlig mikrowebbplats, beroende på profilattributen. I Adobe Journey Optimizer kan du nu lägga till personalisering i URL:er i ditt meddelandeinnehåll. URL-personalisering kan tillämpas på text och bilder och använda profildata eller kontextuella data.</p>
<p>Mer information finns i den <a href="../personalization/personalization-syntax.md#perso-urls">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Se till att dina e-postmeddelanden når användarna - Försök igen med e-post</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Du kan nu definiera återförsöksperioden per förinställning för att säkerställa att återförsöksförsök inte utförs längre när de inte längre behövs. Du kan t.ex. ange återförsöksperioden till 24 timmar för ett transaktionsmeddelande om lösenordsåterställning som innehåller en länk som bara är giltig för en dag. Observera att inställningarna för nya försök endast gäller för e-postkanalen.</p>
<p>Mer information finns i den <a href="../configuration/retries.md#retry-duration">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Definiera adresser som ska uteslutas från sändning - Suppressionslista</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Det går nu att lägga till e-postadresser och domäner i listan över inaktiveringar från användargränssnittet, antingen en i taget, antingen i gruppläge via en CSV-filöverföring.</p>
<p>Mer information finns i den <a href="../configuration/manage-suppression-list.md#add-addresses-and-domains">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


### Förbättringar

**Resor**

* **Dynamiska rubriker** - Du kan nu skicka dynamiska data i HTTP-rubrikparametrar. These parameters can be used by the integration systems that receive the journey action HTTP calls, for example timestamp or tracking ID. [Läs mer](../action/about-custom-action-configuration.md#url-configuration)
* **Dynamiska URL-sökvägar** - Nu kan du ställa in dynamiska URL-sökvägar för anpassade åtgärder. [Läs mer](../action/about-custom-action-configuration.md#url-configuration)
* The overall throttling rate for read segments has been changed from 17,000 to 20,000 messages per second. [Läs mer](../building-journeys/read-segment.md#configuring-segment-trigger-activity)

**Användargränssnitt**

* **Sök** - På varje sida kan du nu söka efter affärsobjekt och hjälpartiklar direkt från sökfältet för enhetliga Experience Cloud. [Läs mer](../start/user-interface.md#unified-search)
* **Senaste** - Visningen av de senaste elementen från Adobe Journey Optimizer hemsida har nu utökats till ytterligare affärsobjekt. I den här uppdateringen finns genvägar till nyligen använda meddelanden, resor, segment, scheman, datauppsättningar, datakällor, händelser, åtgärder, källor och mål. [Läs mer](../action/about-custom-action-configuration.md#passing-collection)

**Innehållsdesign**

* **Bakgrund** - Nu stöds bakgrundsbilder i direktförhandsvisning. [Läs mer](../messages/preview.md)
* **Länk för avanmälan med ett klick** - Du kan infoga en ny typ av länk i ditt e-postinnehåll: den **Avanmäl dig** kan man säga upp prenumerationen från att ta emot meddelanden med bara ett klick, utan att behöva omdirigeras till en landningssida för att bekräfta avanmälan. [Läs mer](../messages/consent.md#one-click-opt-out-link)

**Personalisering**

* **Uttrycksredigeraren** - Du kan nu enkelt lägga till ett reservvärde när du definierar personalisering: när anpassningsfältet är tomt för en profil visas reservvärdet. [Läs mer](../personalization/functions/helpers.md)

**E-postkonfiguration**

* **Tillåtelselista** - tillåtelselista kan nu aktiveras och inaktiveras på en icke-produktionssandlåda via ett API-anrop. [Läs mer](../messages/allow-list.md#enable-allow-list)
* **Navigering** - Suppressionslistan, som var tillgänglig under **Administration > Kanaler > E-postkonfiguration > Allmänt** har flyttats till den nya menyn **Undertryckningslista** undermeny, som samlar alla relaterade funktioner för enklare åtkomst. [Läs mer](../configuration/manage-suppression-list.md#access-suppression-list)

**Decision management**

* Sättet på vilket du lägger till och konfigurerar representationer när du skapar ett erbjudande har uppdaterats för att förbättra användarupplevelsen. Specifikt visas nu resursbiblioteket endast när du definierar innehåll med bilder för en representation. [Läs mer](../offers/offer-library/creating-personalized-offers.md#representations)

### Korrigeringar

* Korrigerade ett tillgänglighetsproblem vid navigering på meddelandeflikar.
* Ett lokaliseringsfel har korrigerats i e-postdesignerns etiketter.
* Ett problem har korrigerats när du valde mer än en nod i en resa och klickade på Ta bort på egenskapspanelen.
* Fixed an issue which prevented from adding a new header to an action used in a journey.
* Du kan nu ta reda på varför en meddelandeförinställning inte kunde skapas med hjälp av en tydligare varning i användargränssnittet.


## Version från juli 2021 {#july-2021-release}

### Nya funktioner

<table>
<thead>
<tr>
<th><strong>Använd metadata i dina meddelanden - Sök tabellhantering</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Enrich your experiences with reference data you've loaded into Journey Optimizer. Det kan till exempel vara att söka efter metadata på ett reservations-ID i en upplevelsehändelse eller söka efter produktinformation från en sku i en upplevelsehändelse för användning på arbetsytan. </p>
<p>Nu kan du utnyttja relationer mellan scheman för att använda en datauppsättning som en uppslagstabell för en annan. Sedan kan ni utnyttja alla fält från de länkade tabellerna när ni konfigurerar en enhetshändelse, när ni använder villkor under en resa, i meddelandepersonalisering och i personalisering av anpassade åtgärder.</p>
<p>Mer information finns i den <a href="../event/experience-event-schema.md#leverage_schema_relationships">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Tillåtelselista</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Du kan nu definiera en specifik sändningssäker lista på sandlådenivå för att ha en säker miljö för testningsändamål. I icke-produktionssituationer, där misstag kan inträffa, ser tillåtelselista till att du inte löper någon risk att skicka ut oönskade meddelanden till dina kunder. Den här funktionen aktiveras med hjälp av API:er för undertryckning.</p>
<p>Mer information finns i den <a href="../messages/allow-list.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar

**Resor**

* Den totala begränsningsfrekvensen för alla lässegment som körs samtidigt i samma sandlåda är begränsad till 17 000 meddelanden per sekund. [Läs mer](../building-journeys/read-segment.md#configuring-segment-trigger-activity)
* The **Cachevaraktighet** -fältet har tagits bort från konfigurationspanelen för datakällan. [Läs mer](../datasource/about-data-sources.md)
* För externa datakällor definieras nu en begränsningsregel på 15 anrop per sekund automatiskt. [Läs mer](../configuration/external-systems.md#capping)
* För direktresor visas nu publiceringsdatumet och namnet på den användare som publicerade resan på skärmen för reseegenskaper. [Läs mer](../building-journeys/journey-gs.md#change-properties)
* På skärmen för reselistan har filtret för resetyp lagts till. [Läs mer](../start/user-interface.md#filter-lists)
* The **[!UICONTROL Throttling rate]** parametern har lagts till i Läs-segmentsaktiviteten. [Läs mer](../building-journeys/read-segment.md#configuring-segment-trigger-activity)

**Förhandsgranska och testa meddelanden**

* Identitet och namnutrymme visas nu i **[!UICONTROL Preview]** skärm. [Läs mer](../messages/preview.md#preview-your-messages)
* Antalet testmeddelanden för korrektur är nu begränsat till 10.
* Tecken tillåts för **Subject line prefix** i korrektur är nu begränsade. [Läs mer](../messages/preview.md#send-proofs)

**Redigerare för anpassningsuttryck**

* Hjälplistan har bytt namn och ordnats om.

### Korrigeringar

* Korrigerade ett problem som medförde att dubblettmeddelanden levererades för batche-postleverans.
* Händelser genereras nu i enlighet med detta när e-postutskick inte utförs när återförsöksperioden är slut.
* Ett problem där IP-information saknades på PTR-inspelningsskärmen har korrigerats.
* Lokalisering i erbjudandefältet i Expression Editor är nu implementerat.
* Felaktigt avstånd i informationspopup-fönster har korrigerats.
* Korrigerade ett fel i e-postdesignern vid överföring av en HTML-fil där en intern formatmall med `background-image` egenskapen stöds inte.
