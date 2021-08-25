---
title: Versionsinformation
description: Versionsinformation om Journey Optimizer
source-git-commit: ff48c78cfa5c48f32073e9df1f126504e291ab5a
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 9%

---


# Versionsinformation {#release-notes}

På den här sidan listas alla nya funktioner och förbättringar i [!DNL Journey Optimizer]. Du kan även läsa de senaste [dokumentationsuppdateringarna](documentation-updates.md).


## Versionen från augusti 2021 {#august-2021-release}

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
<p>Mer information finns i den <a href="building-journeys/journeys-message.md#send-time-optimization">detaljerade dokumentationen</a>.</p>
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
<p>Mer information finns i den <a href="event/experience-event-schema.md#leverage_schema_relationships">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>
<!--
<table>
<thead>
<tr>
<th><strong>Personalized URLs</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Personalized URLs take recipients to specific pages of a website, or to a personalized microsite, depending on the profile attributes. In Adobe Journey Optimizer, you can now add personalization to URLs in your message content. URL personalization can be applied to text and images, and use profile data or contextual data.</p>
<p>For more information, refer to the <a href="documentation-updates.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>
-->

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
<p>Mer information finns i den <a href="configuration/retries.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>
<!--
<table>
<thead>
<tr>
<th><strong>Customer Alerts</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now subscribe to event-based alerts regarding Adobe Journey Optimizer activities. The user interface allows you to view a history of received alerts based on metrics revealed by Adobe Experience Platform Observability Insights. The UI also allows you to view, enable, and disable available alert rules.</p>
<p>This feature is currently in beta version and only available to beta customers. To join the beta program, contact Adobe Customer Care.
</p>
<p>For more information, refer to the <a href="https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/overview.html">Adobe Experience Platform documentation</a>.</p>
</td>
</tr>
</tbody>
</table>
-->

### Förbättringar

**Resor**

* **Dynamiska rubriker**  - Nu kan du skicka dynamiska data i HTTP-rubrikparametrar. De här parametrarna kan användas av de integreringssystem som tar emot resans åtgärd via HTTP-anrop, till exempel tidsstämpel eller spårnings-ID. [Läs mer](action/about-custom-action-configuration.md#url-configuration)
* **Dynamiska URL-sökvägar**  - Du kan nu ställa in dynamiska URL-sökvägar för anpassade åtgärder. [Läs mer](action/about-custom-action-configuration.md#url-configuration)
* Den totala begränsningsfrekvensen för lässegment har ändrats från 17 000 till 20 000 meddelanden per sekund. [Läs mer](building-journeys/read-segment.md#configuring-segment-trigger-activity)

**Användargränssnitt**

* **Sök**  - På varje sida kan du nu söka efter affärsobjekt och hjälpartiklar direkt från sökfältet för enhetliga Experience Cloud. [Läs mer](user-interface.md#unified-search)
* **Senaste nytt**  - Nu kan du visa nya element från Adobe Journey Optimizer hemsida även för andra affärsobjekt. I den här uppdateringen finns genvägar till nyligen använda meddelanden, resor, segment, scheman, datauppsättningar, datakällor, händelser, åtgärder, källor och mål. [Läs mer](action/about-custom-action-configuration.md#passing-collection)

**Innehållsdesign**

* **Bakgrund**  - Bakgrundsbilder stöds nu i direktförhandsvisning. [Läs mer](preview.md)
* **Länk**  för avanmälan med ett klick - Du kan infoga en ny typ av länk i ditt e-postinnehåll: Med  **Opt-** outlink kan man avsluta abonnemanget på att få meddelanden med bara ett klick, utan att man behöver omdirigeras till en landningssida för att bekräfta avanmälan. [Läs mer](message-tracking.md#one-click-opt-out-link)

**Personalisering**

* **Uttrycksredigeraren**  - Nu kan du enkelt lägga till ett reservvärde när du definierar personalisering: när anpassningsfältet är tomt för en profil visas reservvärdet. [Läs mer](documentation-updates.md)

**E-postkonfiguration**

* **Tillåtelselista**  - tillåtelselista kan nu aktiveras och inaktiveras i en icke-produktionssandlåda via ett API-anrop. [Läs mer](allow-list.md#enable-allow-list)

<!--* **Suppression list** - Adding email addresses and domains into the suppression list is now available from the user interface, either one by one, either in bulk mode through a CSV file upload. [Learn more](configuration/manage-suppression-list.md#add-addresses-and-domains)-->
<!--* **Navigation** - The suppression list, which was accessible under the **Channels > Email configuration > General** menu, has been moved to the **Channels > Email configuration > Suppression list** menu for easier access. [Learn more](configuration/manage-suppression-list.md#access-suppression-list)-->


### Korrigeringar

* Korrigerade ett tillgänglighetsproblem vid navigering på meddelandeflikar.
* Ett lokaliseringsfel har korrigerats i e-postdesignerns etiketter.
* Ett problem har korrigerats när du valde mer än en nod i en resa och klickade på Ta bort på egenskapspanelen.
* Korrigerade ett fel som förhindrade att ett nytt huvud lades till i en åtgärd som användes under en resa.
* Du kan nu ta reda på varför en meddelandeförinställning inte kunde skapas med hjälp av en tydligare varning i användargränssnittet.


## juliversion 2021 {#july-2021-release}

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
<p>Berika era upplevelser med referensdata som ni har läst in i Journey Optimizer. Det kan till exempel vara att söka efter metadata på ett reservations-ID i en upplevelsehändelse eller söka efter produktinformation från en sku i en upplevelsehändelse för användning på arbetsytan. </p>
<p>Nu kan du utnyttja relationer mellan scheman för att använda en datauppsättning som en uppslagstabell för en annan. Sedan kan ni utnyttja alla fält från de länkade tabellerna när ni konfigurerar en enhetshändelse, när ni använder villkor under en resa, i meddelandepersonalisering och i personalisering av anpassade åtgärder.</p>
<p>Mer information finns i den <a href="event/experience-event-schema.md#leverage_schema_relationships">detaljerade dokumentationen</a>.</p>
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
<p>Mer information finns i den <a href="allow-list.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar

**Resor**

* Den totala begränsningsfrekvensen för alla lässegment som körs samtidigt i samma sandlåda är begränsad till 17 000 meddelanden per sekund. [Läs mer](building-journeys/read-segment.md#configuring-segment-trigger-activity)
* Fältet **Cachevaraktighet** har tagits bort från konfigurationspanelen för datakällan. [Läs mer](datasource/about-data-sources.md)
* För externa datakällor definieras nu en begränsningsregel på 15 anrop per sekund automatiskt. [Läs mer](configuration/external-systems.md#capping)
* För direktresor visas nu publiceringsdatumet och namnet på den användare som publicerade resan på skärmen för reseegenskaper. [Läs mer](building-journeys/journey-gs.md#change-properties)
* På skärmen för reselistan har filtret för resetyp lagts till. [Läs mer](user-interface.md#section_lgm_hpz_pgb)
* Parametern **[!UICONTROL Throttling rate]** har lagts till i Läs-segmentsaktiviteten. [Läs mer](building-journeys/read-segment.md#configuring-segment-trigger-activity)

**Förhandsgranska och testa meddelanden**

* Identitet och namnutrymme visas nu på skärmen **[!UICONTROL Preview]**. [Läs mer](preview.md#preview-your-messages)
* Antalet testmeddelanden för korrektur är nu begränsat till 10.
* Tecken som tillåts för **ämnesradsprefixet** i korrektur är nu begränsade. [Läs mer](preview.md#send-proofs)

**Redigerare för anpassningsuttryck**

* Hjälplistan har bytt namn och ordnats om.

### Korrigeringar

* Korrigerade ett problem som medförde att dubblettmeddelanden levererades för batche-postleverans.
* Händelser genereras nu i enlighet med detta när e-postutskick inte utförs när återförsöksperioden är slut.
* Ett problem där IP-information saknades på PTR-inspelningsskärmen har korrigerats.
* Lokalisering i erbjudandefältet i Expression Editor är nu implementerat.
* Felaktigt avstånd i informationspopup-fönster har korrigerats.
* Korrigerade ett fel i e-postdesignern vid överföring av en HTML-fil där en intern formatmall med egenskapen `background-image` inte stöds.

