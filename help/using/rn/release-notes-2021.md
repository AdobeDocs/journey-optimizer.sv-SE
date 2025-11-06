---
solution: Journey Optimizer
product: journey optimizer
title: Information om föregående version (2021)
description: Versionsinformation om Journey Optimizer 2021
feature: Release Notes
topic: Content Management
role: User
level: Beginner, Intermediate
hidefromtoc: true
hide: true
exl-id: 0e43be98-f471-4860-be84-8f99ab93e983
source-git-commit: 0331f8fe2439d41c08ad88a6d0bd95dd150bab90
workflow-type: tm+mt
source-wordcount: '2032'
ht-degree: 8%

---

# Versionsinformation för 2021 {#release-notes-2021}

På den här sidan visas alla funktioner och förbättringar för [!DNL Journey Optimizer] som släpptes 2021.

## November 2021-utgåvan {#november-2021-release}

<table>
<thead>
<tr>
<th><strong>CNAME-delegering av underdomän</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer har nu stöd för CNAME. En CNAME-post, eller kanoniskt namnpost, är en post som pekar på en annan domänadress i stället för en IP-adress. Med CNAME-delegering av underdomäner kan du skapa en underdomän och använda CNAME för att peka mot Adobe-specifika poster. Med den här konfigurationen delar både du och Adobe ansvaret för att underhålla DNS för att konfigurera miljön för att skicka, återge och spåra e-postmeddelanden.</p>
<p>Den här metoden rekommenderas om din organisations principer begränsar den fullständiga delegeringsmetoden för underdomäner.</p>
<p>Läs mer om delegering av CNAME-underdomäner i den <a href="../configuration/delegate-subdomain.md#cname-subdomain-setup">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


## Oktober 2021-versionen {#oct-2021-release}

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
<p>Nu kan du simulera vilka erbjudanden som ska levereras till en testprofil för en viss placering i Journey Optimizer användargränssnitt. På så sätt kan du validera din beslutslogik, inklusive behörighetskrav och rangordningsalgoritmer, enkelt innan du sätter dem i produktion. Med den här funktionen kan icke-tekniska och tekniska användare snabbt testa beslutshantering och felsöka potentiella problem.</p>
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
<p>Nu kan ni personalisera innehållet i era erbjudanden med Adobe Experience Platform-profilattribut och målgrupper, med samma uttrycksredigeringskomponent som finns i hela Journey Optimizer användargränssnitt. </p>
<p>Mer information finns i den <a href="../offers/offer-library/creating-personalized-offers.md#custom-text">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


Se även [Versionsinformation för Adobe Experience Platform oktober](https://experienceleague.adobe.com/docs/experience-platform/release-notes/2021/october-2021.html?lang=sv-SE){target="_blank"} för fler ändringar.

### Förbättringar

**Resor**

* **Uttrycksredigeraren** - Som kraftfull användare kan du nu använda funktioner för att arbeta med kartor. Den här funktionen kan utnyttjas med prenumerationslistorna. Från en viss målgrupp kan du nu till exempel få en e-postadress från en prenumerationslista. [Läs mer i exemplet](../building-journeys/message-to-subscribers-uc.md)

* **Övervakning** - steghändelser för direktresor och testläge har förbättrats. [Nya fält](../reports/sharing-field-list.md#serviceevents) har lagts till i samband med profilexportjobb. För en bättre användarupplevelse är steghändelsefält nu ordnade i olika kategorier. Alla föregående steg-händelsefält är fortfarande tillgängliga i kategorin [stepEvents](../reports/sharing-legacy-fields.md).
* **Tillgänglighet** - Tillgänglighetsförbättringar har implementerats under resor.
* **Samlingar** - Nu stöds arrayer med objekt som innehåller underobjekt. [Läs mer](../building-journeys/collections.md)
* **Listor** - Listskärmar har förbättrats för resor, händelser, åtgärder och datakällor.

**Rapportering**

* **Dataformat i global vy** - Nu kan du växla mellan siffror och procenttal i den **globala vyn** på fliken **Körning**.


**Administration**

* **Redigera meddelandeförinställningar** - Nu kan du redigera meddelandeförinställningar och övervaka deras uppdateringsstatus. [Läs mer](../configuration/channel-surfaces.md#edit-channel-surface)
* **Redigera PTR-poster** - Nu kan du redigera PTR-poster och övervaka deras uppdateringsstatus. [Läs mer](../configuration/ptr-records.md#edit-ptr-record)

**Personalization**

* **Ny hjälpfunktion för datumformatering** - Nu kan du ange hur en datumsträng ska visas. [Läs mer](../personalization/functions/dates.md#format-date)


**Beslutshantering**

* **Utvärderingssekvensering** - Det nya och förbättrade beslutsflödet gör att du inte bara kan navigera mellan beslutsobjekt utan även får en fullständig kontroll över hur offertsamlingar utvärderas av beslutsmotorn. Detta inkluderar vilka samlingar som utvärderas tillsammans jämfört med separat, och i vilken ordning samlingarna ska utvärderas. [Läs mer](../offers/offer-activities/create-offer-activities.md#add-decision-scopes)

### Korrigeringar

* Korrigerade ett problem som förhindrade att reselistan, meddelandelistan och e-post-Designer visades när webbläsarspråket inte var engelska.
* Korrigerade ett syntaxfel som uppstod när personalisering lades till med ett uttryck i e-post-Designer: tecken togs bort felaktigt.
* Korrigerade ett problem som ledde till ett 404-fel vid navigering på menyn **Administration**.
* Korrigerade ett problem som utlöste andra direktresor när en resa testades med hjälp av en affärshändelse.


## September 2021-utgåvan {#september-2021-release}

### Nya funktioner

<table>
<thead>
<tr>

<th><strong>Rapportering - Bättre insikter om målgrupper</strong><br/></th>
</thead>
<tbody>
<tr>
<td>
<p>Nya mätvärden är tillgängliga vid rapportering: Riktade och exkluderade för e-post- och push-meddelanden är synliga i både live- och globala rapporter. </br> Observera att du måste återställa de olika rapportinstrumentpanelerna för varje kanal och rapporttyp för att få tillgång till de senaste mätvärdena. Mer information om anpassning av kontrollpanelen finns i den <a href="../reports/live-report.md">detaljerade dokumentationen.</a></p>
<p>En ny kolumn i meddelandekörningslistan visar antalet målprofiler för varje meddelandekörning. </p>
<p>Mer information finns i den <a href="../reports/report-gs-cja.md">detaljerade dokumentationen</a>.</p>
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
<p>Nu kan du skicka samlingar eller en lista med data i dina anpassade åtgärdsparametrar som fylls i dynamiskt vid körning. Det finns två sorters samlingar: enkla samlingar och objektsamlingar. Tidigare skapade anpassade åtgärder fortsätter att fungera. </p>
<p>Mer information om samlingar finns i <a href="../building-journeys/collections.md">detaljerad dokumentation</a>. </p>
<p>Funktionerna för att filtrera och överlappa har lagts till i listan med funktioner som är tillgängliga i den avancerade uttrycksredigeraren. Det ger fler möjligheter att filtrera och jämföra samlingar.</p>
<p>Läs dokumentationen om funktionerna <a href="../building-journeys/functions/list-functions.md#filter">filter</a> och <a href="../building-journeys/functions/list-functions.md#intersect">överlappa</a>.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar

**Resor**

* Systemgenererade scheman och datauppsättningar som har skapats under etablering av steghändelser är nu skrivskyddade, vilket skyddar mot oavsiktliga ändringar av viktiga scheman. [Läs mer](../reports/sharing-overview.md)
* Etikettera **Wait**-aktiviteten med en etikett som visas på arbetsytan. Etiketten används också i loggar för rapportering och testläge för att tydligt identifiera vad du gör. [Läs mer](../building-journeys/about-journey-activities.md#best-practices)
* Hitta dina händelser och åtgärder snabbare genom att filtrera elementen i kategorierna **Händelser** och **Åtgärd** med hjälp av sökning. Orchestration-aktiviteter är inte längre filtrerade. [Läs mer](../building-journeys/using-the-journey-designer.md)
* När du definierar ett händelse-ID-villkor i en regelbaserad händelse eller en affärshändelse är operatorn &quot;contains&quot; nu tillgänglig för strängtyper av fält. [Läs mer](../event/about-creating.md)

**E-postkonfiguration**

* När en IP-pool har kopplats till en meddelandeförinställning kan du nu redigera den, eftersom uppdateringen är asynkron. Du kan även kontrollera uppdateringsstatus för varje IP-pool. [Läs mer](../configuration/ip-pools.md#edit-ip-pool)


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
<p>Skicka automatiskt ditt push- eller e-postmeddelande vid den tidpunkt som passar varje kund du interagerar med Adobe Journey Optimizer. Med optimering för sändningstid, som bygger på Adobe AI-tjänster, förutspås den bästa tidpunkten för att skicka e-post eller push-meddelanden för att maximera engagemanget baserat på tidigare öppnings- och klickfrekvenser.</p>
<p>Den här funktionen är för närvarande i betaversion och endast tillgänglig för betakunder. Om du vill gå med i betaprogrammet kontaktar du Adobe kundtjänst.</p>
<p>Mer information finns i den <a href="../building-journeys/send-time-optimization.md">detaljerade dokumentationen</a>.</p>
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

* **Dynamiska rubriker** - Nu kan du skicka dynamiska data i HTTP-rubrikparametrar. De här parametrarna kan användas av de integreringssystem som tar emot resans åtgärd via HTTP-anrop, till exempel tidsstämpel eller spårnings-ID. [Läs mer](../action/about-custom-action-configuration.md#url-configuration)
* **Dynamiska URL-sökvägar** - Nu kan du ställa in dynamiska URL-sökvägar för anpassade åtgärder. [Läs mer](../action/about-custom-action-configuration.md#url-configuration)
* Den totala begränsningsfrekvensen för läsmålgrupper har ändrats från 17 000 till 20 000 meddelanden per sekund. [Läs mer](../building-journeys/read-audience.md#configuring-segment-trigger-activity)

**Användargränssnitt**

* **Sök** - På varje sida kan du nu söka efter affärsobjekt och hjälpartiklar direkt från sökfältet för enhetliga Experience Cloud. [Läs mer](../start/user-interface.md#unified-search)
* **Senaste** - Visningen av de senaste elementen från Adobe Journey Optimizer hemsida har nu utökats till ytterligare affärsobjekt. I den här uppdateringen finns genvägar till dina senast använda meddelanden, resor, målgrupper, scheman, datauppsättningar, datakällor, händelser, åtgärder, källor och mål. [Läs mer](../action/about-custom-action-configuration.md#passing-collection)

**Innehållsdesign**

* **Bakgrund** - Bakgrundsbilder stöds nu i direktförhandsvisning. [Läs mer](../content-management/preview-test.md)
  <!--* **One-click opt-out link** - You can insert a new type of link into your email content: the **Opt-out** link allows users to unsubscribe from receiving your communications in just one click, without being redirected to a landing page to confirm opting out. [Learn more](../privacy/opt-out.md#one-click-opt-out-link)-->

**Personalization**

* **Uttrycksredigeraren** - Nu kan du enkelt lägga till ett reservvärde när du definierar personalisering: när anpassningsfältet är tomt för en profil visas reservvärdet. [Läs mer](../personalization/functions/helpers.md)

**E-postkonfiguration**

* **Tillåtelselista** - tillåtelselista kan nu aktiveras och inaktiveras på en icke-produktionssandlåda via ett API-anrop. [Läs mer](../configuration/allow-list.md#enable-allow-list)
* **Navigering** - Den undertryckningslista som var tillgänglig under menyn **Administration > Kanaler > E-postinställningar > Allmänt** har flyttats till den nya undermenyn **Undertryckningslista** som samlar alla relaterade funktioner för enklare åtkomst. [Läs mer](../configuration/manage-suppression-list.md#access-suppression-list)

**Beslutshantering**

* Sättet på vilket du lägger till och konfigurerar representationer när du skapar ett erbjudande har uppdaterats för att förbättra användarupplevelsen. Resursbiblioteket visas nu endast när du definierar bildtypsinnehåll för en representation. [Läs mer](../offers/offer-library/creating-personalized-offers.md#representations)

### Korrigeringar

* Korrigerade ett tillgänglighetsproblem vid navigering på meddelandeflikar.
* Ett lokaliseringsfel har korrigerats i e-postetiketterna för Designer.
* Ett problem har korrigerats när du valde mer än en nod i en resa och klickade på Ta bort i egenskapsfönstret.
* Korrigerade ett problem som förhindrade att ett nytt huvud lades till i en åtgärd som användes under en resa.
* Du kan nu ta reda på varför en meddelandeförinställning inte kunde skapas med hjälp av en tydligare varning i användargränssnittet.


## Version från juli 2021 {#july-2021-release}

### Nya funktioner

<table>
<thead>
<tr>
<th><strong>Använd metadata i dina meddelanden - Uppslagstabellhantering</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Berika era upplevelser med referensdata som ni har läst in i Journey Optimizer. Det kan till exempel vara att söka efter metadata på ett reservations-ID i en upplevelsehändelse eller söka efter produktinformation från en sku i en upplevelsehändelse för användning på arbetsytan. </p>
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
<p>Mer information finns i den <a href="../configuration/allow-list.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar

**Resor**

* Den totala begränsningsfrekvensen för alla läsmålgrupper som körs samtidigt i samma sandlåda är begränsad till 17 000 meddelanden per sekund. [Läs mer](../building-journeys/read-audience.md#configuring-segment-trigger-activity)
* Fältet **Cachevaraktighet** har tagits bort från konfigurationspanelen för datakällan. [Läs mer](../datasource/about-data-sources.md)
* För externa datakällor definieras nu en begränsningsregel på 15 anrop per sekund automatiskt. [Läs mer](../configuration/external-systems.md#capping)
* För direktresor visas nu publiceringsdatumet och namnet på den användare som publicerade resan på skärmen för reseegenskaper. [Läs mer](../building-journeys/journey-gs.md#change-properties)
* På skärmen för reselistan har filtret för resetyp lagts till. [Läs mer](../start/user-interface.md#filter-lists)
* Parametern **[!UICONTROL Throttling rate]** har lagts till i aktiviteten Läsa målgrupp. [Läs mer](../building-journeys/read-audience.md#configuring-segment-trigger-activity)

**Förhandsgranska och testa**

* Identitet och namnutrymme visas nu på skärmen **[!UICONTROL Preview]**. [Läs mer](../content-management/preview-test.md#preview-your-messages)
* Antalet testmeddelanden för korrektur är nu begränsat till 10.
* Tecken som tillåts för **ämnesradsprefixet** i korrektur är nu begränsade. [Läs mer](../content-management/preview-test.md#send-proofs)

**Personalization uttrycksredigerare**

* Hjälplistan har fått ett nytt namn och ordnats om.

### Korrigeringar

* Korrigerade ett problem som medförde att dubblettmeddelanden levererades för batche-postleverans.
* Händelser genereras nu i enlighet med detta när e-postutskick inte utförs när återförsöksperioden är slut.
* Ett problem där IP-information saknades på PTR-inspelningsskärmen har korrigerats.
* Lokalisering i erbjudandefältet i Expression Editor är nu implementerat.
* Felaktigt avstånd i informationspopup-fönster har korrigerats.
* Korrigerade ett problem i e-post-Designer när en HTML-fil överfördes där en intern formatmall med egenskapen `background-image` inte stöds.
