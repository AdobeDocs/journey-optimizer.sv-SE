---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
description: Journey Optimizer tidiga versionsinformation
feature: Release Notes
topic: Content Management
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: afe642177f690cdf873f838ec81044b7f8a7172e
workflow-type: tm+mt
source-wordcount: '1971'
ht-degree: 2%

---

# Tidig versionsinformation {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras i slutet av varje månad i [versionsinformationen](release-notes.md).

**Noteringar om tidig version nedan kan ändras utan föregående meddelande till releasedatum**. Länkar, skärmar och uppdaterad dokumentation publiceras i [versionsinformationen](release-notes.md) på releasedatum.

## Versionsinformation oktober 2024 {#e-2024}

**Releasedatum**: 29-30 oktober 2024

### Nya funktioner {#e-features}

Den här versionen innehåller de nya funktionerna som beskrivs nedan.

<table>
<thead>
<tr>
<th><strong>Låsning av e-postinnehåll</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med Journey Optimizer kan du nu låsa innehåll i e-postmallar, antingen genom att låsa hela mallen eller specifika strukturer och komponenter. På så sätt kan ni förhindra oavsiktliga redigeringar och borttagningar, vilket ger er bättre kontroll över mallanpassning och förbättrar effektiviteten och tillförlitligheten i era e-postkampanjer.</p>
<!--p>For more information, refer to the <a href="../content-management/gs-generative.md">detailed documentation</a>.</p>
<img src="assets/do-not-localize/ai-content.gif"/-->
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Godkännanden av resor och kampanjer (allmän tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med godkännandepolicyer kan ni nu skapa en godkännandeprocess i Journey Optimizer som gör det möjligt för marknadsföringsteamen att se till att kampanjer och resor granskas och signeras av lämpliga intressenter innan de publiceras.</p>
<p>Tidigare fanns godkännandepolicyer för en uppsättning organisationer (LA) och är nu tillgängliga för alla användare (GA).</p>
<p>Mer information finns i den <a href="../test-approve/gs-approval.md">detaljerade dokumentationen</a>.</p>
<img src="assets/do-not-localize/approval.gif"/>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Anpassning av e-postkonfiguration (allmän tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du definiera dynamiska underdomäner och anpassade rubrikparametrar när du skapar e-postkanalskonfigurationer, vilket ger större flexibilitet och kontroll över e-postinställningarna.</p><p>Om du använder en anpassad konfiguration i en kampanj eller resa kan du förhandsgranska ditt e-postinnehåll för att kontrollera om det finns potentiella fel med de dynamiska inställningar du har definierat.</p>
<p>Tidigare var e-postkonfigurationspersonalisering tillgänglig för en uppsättning organisationer (LA) och nu även för alla användare (GA).</p>
<p>Mer information finns i den <a href="../email/surface-personalization.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Testa materialet med exempeldata (Beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med reseoptimeraren kan du nu testa olika varianter av ditt e-postinnehåll genom att förhandsgranska det och skicka korrektur med exempelindata som överförts från en CSV-fil eller lagts till manuellt. Alla profilattribut som används i ditt innehåll för personalisering identifieras automatiskt av systemet och kan användas för dina tester för att skapa flera varianter.</p>
<p>Den här funktionen är för närvarande tillgänglig som betaversion.</p>
<!--<p>For more information, refer to the <a href="../email/surface-personalization.md">detailed documentation</a>.</p>-->
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Hantering av konflikter och prioritet (begränsad tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>I Journey Optimizer är det viktigt att hantera kampanjernas och resornas volym och tidpunkter för att undvika överväldigande kunder med alltför många interaktioner. Journey Optimizer har nu flera verktyg för konflikthantering och -prioritering.</p><p><ul><li><b>Resefrekvensbegränsning</b>: Du kan nu skapa regeluppsättningar som ska användas på dina resor, så att du kan begränsa antalet resor per dag, vecka eller månad, samt kontrollera antalet samtidiga resor som körs samtidigt.</li>
<li><b>Prioritetspoäng</b>: Du kan nu tilldela en kampanj eller en resa ett prioritetspoäng, från 0 till 100. Ett högre tal anger en högre prioritet. När två kampanjer eller reseåtgärder använder samma kanalkonfiguration väljer Journey Optimizer den som har högst prioritet. Om kampanjerna har samma poäng väljs den kampanj som senast ändrades.</li>
<li><b>Visa potentiella konflikter</b>: Med en ny knapp för att visa potentiella konflikter under resor och kampanjer kan du nu identifiera överlappning med andra resor eller kampanjer, till exempel startdatum, målgrupp eller den valda kanalkonfigurationen.</li>
<li><b>Reseskiljeförfarande</b>: Med den här nya funktionen kan du prioritera de viktigaste kundresorna. Du kan skapa en regel som förhindrar inträde på en resa med lägre prioritet när en kund kvalificerar sig för en resa med högre prioritet.</li></ul></p>
<!--<p>For more information, refer to the <a href="../email/surface-personalization.md">detailed documentation</a>.</p>-->
<p>Funktioner för hantering av konflikter och prioriteter är tillgängliga i begränsad tillgänglighet för en viss kundgrupp. Observera att dessa funktioner gradvis kommer att lanseras för fler användare i framtiden. Kontakta ditt kontoteam om du vill bli tillagd i väntelistan för dessa funktioner.</p>

</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Icke-visuellt redigeringsläge för webbdesignern</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Som ett alternativ till Journey Optimizer webbdesigner kan du nu lägga till ändringar på webbplatsen med en icke-visuell redigerare. Du kan ange ändringarna manuellt utan att öppna sidorna i den visuella redigeraren.
Det här icke-visuella redigeringsläget är användbart om du inte kan installera webbläsartillägg som Adobe Experience Cloud Visual Helper, som krävs för att läsa in sidorna i webbdesignern.</p>
<!--p>For more information, refer to the <a href="../email/surface-personalization.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Experimentera med resor (allmän tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer finns redan i kampanjer och stöder nu experiment på resor. Experimentella tester är randomiserade, vilket i samband med onlinetestning innebär att du exponerar vissa slumpmässigt utvalda användare för en viss variant av ett meddelande och en annan slumpmässigt utvald uppsättning användare för annan variation eller behandling. Efter exponering kan du mäta de resultatvärden du är intresserad av, som öppningar av e-post, prenumerationer eller inköp.</p>
<p>Tidigare fanns det för en uppsättning organisationer (LA), och nu finns körningsexperiment för alla användare (GA).</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Beslut (allmän tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Beslutsfattandet, som tidigare fanns för en uppsättning organisationer (LA) och som kallas Experience Decisioning, är nu tillgängligt för alla användare (GA). Det förenklar personaliseringen genom att erbjuda en centraliserad katalog med marknadsföringserbjudanden som kallas beslutsposter och en avancerad beslutsmotor. Den här motorn använder regler och rankningskriterier för att välja ut och presentera de mest relevanta beslutsobjekten för varje enskild person. Dessa beslutsobjekt integreras smidigt i ett stort antal inkommande ytor via den kodbaserade upplevelsekanalen.</p>

<p>För närvarande är beslut inte tillgängligt för kunder som har köpt tillägget Adobe Healthcare Shield och Privacy and Security Shield.</p>

<!--p>For more information, refer to the <a href="../configuration/business-rules.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Regeluppsättningar (begränsad tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du skapa detaljerade regler för frekvensbegränsning och tillämpa dem på meddelanden eller resor via regeluppsättningar. Med den här nya funktionen kan ni styra hur ofta era målgrupper får ett meddelande genom att ställa in flerkanalsregler som automatiskt utesluter överbegärda profiler från meddelanden och åtgärder.</p><p>Det gör det även möjligt att begränsa antalet resor per dag, vecka eller månad samt att kontrollera antalet samtidiga resor som körs samtidigt.</p>
<p>Regeluppsättningar är tillgängliga i begränsad tillgänglighet för en viss kundgrupp. Observera att dessa funktioner gradvis kommer att lanseras för fler användare i framtiden. Kontakta ditt kontoteam om du vill bli tillagd i väntelistan för den här funktionen.</p>
<!--p>For more information, refer to the <a href="../configuration/business-rules.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Flerspråkiga meddelanden under resor och kampanjer (allmän tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan ni enkelt skapa innehåll på flera språk i en enda kampanj eller resa. Med den här funktionen kan ni växla mellan olika språk när ni redigerar kampanjer eller hela kundresan, effektivisera hela redigeringsprocessen och förbättra möjligheterna att effektivt hantera flerspråkigt innehåll.</p>
<p>Tidigare var flerspråkiga meddelanden tillgängliga för en uppsättning organisationer (LA), men nu är de tillgängliga för alla användare (GA).</p>
<!--p>For more information, refer to the <a href="../configuration/business-rules.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Integrering med Movable Ink och Adobe Journey Optimizer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du integrera Movable Ink Da Vinci och Adobe Journey Optimizer. Med den nya integreringen kan du </p>
<p><ul><li>Utnyttja de kraftfulla funktionerna i Movable Inks Da Vinci-produkt för att sammanställa och personalisera e-postvarianter för gruppkampanjer</li>
<li>Snabba upp arbetsflödena för användare av Journey Optimizer med Da Vinci för framställning och AJO för optimering och leverans</li>
<li>Optimera Da Vinci-modeller med data från Adobe.</li></ul></p>
<!--p>For more information, refer to the <a href="../code-based/get-started-code-based.md">detailed documentation</a>.</p-->
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Uppdaterad rapportupplevelse (allmän tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Tillgänglig sedan 16 oktober 2024</p>
<p>Journey Optimizer rapportering är nu allmänt tillgänglig (GA) och har förbättrad interoperabilitet med Customer Journey Analytics, standardiserad rapportering för båda plattformarna och förbättrad datakonsekvens och tillförlitlighet. Denna smidiga integrering mellan Journey Optimizer och Customer Journey Analytics ger en tydligare bild av prestandamätningarna, så att användarna kan fatta mer välgrundade beslut.</p>
<p>Med allmän tillgänglighet introduceras fyra nya funktioner: möjlighet att skapa enkla mätvärden, skapa och publicera målgrupper, ställa ad hoc-frågor med Insight Builder och schemalägga rapporter som automatiskt ska skickas till viktiga mottagare.</p>
<p>Mer information finns i den <a href="../reports/report-cja-manage.md">detaljerade dokumentationen</a>.</p>
<img src="assets/do-not-localize/ajo-cja.gif">
<p>Viktigt:Den nuvarande rapportupplevelsen kommer att upphöra i januari 2025. Efter detta datum kommer den nya rapportupplevelsen att bli standard. Vi rekommenderar att du behärskar de nya funktionerna så att övergången blir smidig. <a href="../reports/report-gs-cja.md">Lär dig hur du kommer igång med Journey Optimizer nya rapporteringsgränssnitt</a></p>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Kodbaserade upplevelser under resor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Tillgänglig sedan 1 oktober 2024</p>
<p>Med den kodbaserade upplevelsekanalen kan du med Adobe Journey Optimizer utföra avancerad personalisering och testning för alla dina inkommande egenskaper, vilket möjliggör smidig leverans av skräddarsydda upplevelser över olika kontaktytor som webbappar, mobilappar, datorprogram, videokonsoler, tv-anslutna enheter, smarta tv-apparater, kioskdatorer, ATM-enheter, IoT-enheter med mera. Den kodbaserade upplevelsekanalen är nu tillgänglig på arbetsytan för resan.</p>
<p>Mer information finns i den <a href="../code-based/create-code-based.md">detaljerade dokumentationen</a>.</p>
<img src="../assets/do-not-localize/code-based-journey.gif"/>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Webbupplevelser på resorna</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Tillgänglig sedan 1 oktober 2024</p>
<p>Med webbkanalen kan Adobe Journey Optimizer personalisera webbupplevelsen som ni levererar till era kunder via inkommande webbresor. Webbkanalen är nu tillgänglig på arbetsytan.</p>
<p>Mer information finns i den <a href="../web/create-web.md">detaljerade dokumentationen</a>.</p>
<img src="../assets/do-not-localize/web-journey.gif"/>
</tr>
</tbody>
</table>

### Förbättringar {#e-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**SMS-kanal**

SMS-förbättringar har införts för att förbättra dina meddelandefunktioner:

* Ni kan definiera och hantera unika nyckelord för era SMS-kampanjer och resor, vilket möjliggör mer personaliserad och effektiv kommunikation.
* Du kan skapa och leverera ett standard-SMS-meddelande när ett nyckelord inte känns igen.

**Resor**

* **Sträckexperimentera med resor** - Med experimentet med resan kan du nu definiera och spåra nyckeltal för dina kundvägar, så att du kan mäta effekten av dina aktiviteter och få tydligare insikter i dina resultat.

* **Max antal Live-resor** - Journey Optimizer har nu 500 live-resor i produktionssandlådor, i stället för 100. Antalet direktresor visas på arbetsytan. <!-- DOCAC-10977-->

* **Tid-till-live-garanti** - Från och med 1 november 2024 kommer ett TTL-skyddsprotokoll att introduceras i Journey Optimizer systemgenererade datauppsättningar i nya sandlådor och nya organsar enligt följande:

   * 90 dagar för data i profilarkivet
   * 13 månader för data i sjön

  Den här ändringen kommer att införas i befintliga kundsandlådor senare i en andra fas.

  Från och med den 1 november har dessutom direktuppspelningssegmentering inte längre stöd för att skicka och öppna händelser från spårnings- och feedbackdatauppsättningar. Den här ändringen gäller för alla kundsandlådor och organ vid den tidpunkten. [Läs mer](../data/datasets-ttl.md)

* **Parametrar i anpassade åtgärder** (Tillgänglighetsdatum: 3 oktober 2024) - NULL och valfria parametrar stöds nu i anpassade åtgärder. [Läs mer](../action/about-custom-action-configuration.md#define-the-message-parameters)

**Rapportering**

* **Rapportering om Experience Decisioning** finns nu tillgänglig och ger viktiga insikter i hur era besökare interagerar med era upplevelser.

**Datastyrning och samtycke** - Tillgänglighetsdatum: 7 okt 2024

* **Tillämpning av datastyrningsprinciper** sker nu i alla kanaler i Journey Optimizer. För kunder som har skapat policyer i Adobe Experience Platform tillämpas dessa på marknadsföringsåtgärder som en del av kanalkonfigurationsinställningarna. När du skapar innehåll med en konfiguration kontrollerar systemet om det finns några datastyrningsfel i alla anpassningsfält. Om en överträdelse hittas går det inte att publicera en resa eller kampanj. [Läs mer](../action/action-privacy.md)

* **Egna medgivandeprinciper** gäller nu för alla Journey Optimizer-kanaler. Vid behov innan ett meddelande skickas eller en inkommande upplevelse levereras, kontrollerar systemet att användaren har gett sitt medgivande till att använda personaliseringsfält i innehållet som han/hon får. Om inget samtycke ges visas inte upplevelsen. [Läs mer](../action/consent.md)

  >[!NOTE]
  >
  >Samtyckespolicyer är för närvarande bara tillgängliga för organisationer som har köpt tillägget **Adobe Healthcare Shield** eller **Privacy and Security Shield**.

**Publiker** - Tillgänglighetsdatum: 8 okt 2024

* När ni riktar er till en publik med CSV-filer kan ni nu använda attribut från filen i personaliseringsredigeraren och i regelbyggaren för resor och kampanjer. [Läs mer](../audience/about-audiences.md)

* Målgrupper och attribut från anpassad uppladdning (CSV-fil) kan nu användas med hälso- och sjukvårdsskölden eller skölden för skydd av privatlivet och säkerheten.

**Kodbaserad kanal**

* Innehållsmallar är nu tillgängliga. Ni kan snabba upp utvecklingen av era kodbaserade upplevelser med utgångspunkt i en innehållsmall som byggts av era utvecklare. Om du använder en innehållsmall kan marknadsföraren bara ändra vissa värden eller fält, i stället för att disponera hela HTML eller JSON-innehållets nyttolast.



