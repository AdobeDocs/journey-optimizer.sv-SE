---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
topic: Content Management
description: Versionsinformation om Adobe Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 50687bad19e4866ace1e3e94f3efcdad84e98c96
workflow-type: tm+mt
source-wordcount: '2196'
ht-degree: 6%

---

# Versionsinformation {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="Nyheter?"
>abstract="**Adobe Journey Optimizer** levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen."

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen. [!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver från de senaste innovationerna och förbättringarna. Läs mer om de här ändringarna i [Adobe Experience Platform versionsinformation](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target="_blank"}.

## Uppdateringar från 25 januari {#25-01-rn}

<table>
<thead>
<tr>
<th><strong>Customer Journey Analytics-mallar</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du förbättra dina Journey Optimizer-rapporter genom att använda Customer Journey Analytics-mallar. Med den här nya funktionen kan ni effektivisera rapporteringsprocessen med fördesignade mallar som är anpassade efter era analysbehov.
</p>
<p>Mer information finns i den <a href="../reports/report-cja-manage.md#cja-template">detaljerade dokumentationen</a>.</p>
<p> Funktionen <b>Mall</b> introduceras stegvis med fullständig allmän tillgänglighet planerad till slutet av januari</p>
</tr>
</tbody>
</table>

### Förbättringar {#25-01-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**Beslut**

* Beslutsfattandet har nu stöd för datatyperna Object när objektkatalogens schema redigeras. [Läs mer](../experience-decisioning/catalogs.md)

## 24 oktober {#24-10-rn}

**Releasedatum**: 29-30 oktober 2024

### Nya funktioner {#24-10-features}

Den här versionen innehåller de nya funktionerna som beskrivs nedan:

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
<p>Mer information finns i den <a href="../content-management/content-locking.md">detaljerade dokumentationen</a>.</p>
<img src="assets/do-not-localize/gif-content-locking.gif">
<p>Tillgänglig sedan 24 oktober 2024</p>
</td>
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
<p>Med den kodbaserade upplevelsekanalen kan du med Adobe Journey Optimizer utföra avancerad personalisering och testning för alla dina inkommande egenskaper, vilket möjliggör smidig leverans av skräddarsydda upplevelser över olika kontaktytor som webbappar, mobilappar, datorprogram, videokonsoler, tv-anslutna enheter, smarta tv-apparater, kioskdatorer, ATM-enheter, IoT-enheter med mera. Den kodbaserade upplevelsekanalen är nu tillgänglig på arbetsytan för resan.</p>
<p>Mer information finns i den <a href="../code-based/create-code-based.md">detaljerade dokumentationen</a>.</p>
<img src="../assets/do-not-localize/code-based-journey.gif"/>
<p>Tillgänglig sedan 1 oktober 2024</p>
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
<p>Med webbkanalen kan Adobe Journey Optimizer personalisera webbupplevelsen som ni levererar till era kunder via inkommande webbresor. Webbkanalen är nu tillgänglig på arbetsytan.</p>
<p>Mer information finns i den <a href="../web/create-web.md">detaljerade dokumentationen</a>.</p>
<img src="../assets/do-not-localize/web-journey.gif"/>
<p>Tillgänglig sedan 1 oktober 2024</p>
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
<p>I Journey Optimizer är det viktigt att hantera kampanjernas och resornas volym och tidpunkter för att undvika överväldigande kunder med alltför många interaktioner. Journey Optimizer har nu flera verktyg för konflikthantering och -prioritering. <p>Mer information finns i den <a href="../conflict-prioritization/gs-conflict-prioritization.md">detaljerade dokumentationen</a>.</p></p><p><ul><li><b>Resefrekvensbegränsning</b>: Nu kan du skapa regeluppsättningar som ska användas på dina resor, så att du kan begränsa antalet resor för en profil per dag, vecka eller månad, samt styra antalet samtidiga resor som körs samtidigt.</li>
<li><b>Prioritetspoäng</b>: Du kan nu tilldela en kampanj eller en resa ett prioritetspoäng, från 0 till 100. Ett högre tal anger en högre prioritet. När två kampanjer eller reseåtgärder använder samma kanalkonfiguration väljer Journey Optimizer den som har högst prioritet. Om kampanjerna har samma poäng väljs den kampanj som senast ändrades.</li>
<li><b>Visa potentiella konflikter</b>: Med en ny knapp för att visa potentiella konflikter under resor och kampanjer kan du nu identifiera överlappning med andra resor eller kampanjer, till exempel startdatum, målgrupp eller den valda kanalkonfigurationen.</li>
<li><b>Reseskiljeförfarande</b>: Med den här nya funktionen kan du prioritera de viktigaste kundresorna. Du kan skapa en regel som förhindrar inträde på en resa med lägre prioritet när en kund kvalificerar sig för en resa med högre prioritet.</li>
<li><b>Frekvensbegränsning per kommunikationstyp: </b>Med regeluppsättningar kan du nu ange detaljerade regler per kommunikationstyp (till exempel Försäljning, Kampanj) för att förhindra att kunder med liknande meddelanden överbelastas. Ni kan styra frekvensen över flera kanaler och automatiskt utesluta överbegärda profiler för att få en bättre kundupplevelse.</li></ul>

<img src="assets/do-not-localize/gif-conflict.gif">

<p>Funktioner för hantering av konflikter och prioriteter är tillgängliga i begränsad tillgänglighet för en viss kundgrupp. Observera att dessa funktioner gradvis kommer att lanseras för fler användare i framtiden. Kontakta ditt kontoteam om du vill bli tillagd i väntelistan för dessa funktioner.</p>

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
<li>Snabba upp arbetsflödena för användare av Journey Optimizer med Da Vinci för framställning och Adobe Journey Optimizer för optimering och leverans</li>
<li>Optimera Da Vinci-modeller med data från Adobe.</li></ul></p>
<p>Mer information finns i <a href="https://movableink.com/adobe-and-movable-ink">Dokumentationen för Da Vinci med flyttbara bläck</a>.</p>
</tr>
</tbody>
</table>

Tidigare tillgängligt för en uppsättning organisationer (LA), men nu är följande funktioner tillgängliga för alla användare (GA):

<table>
<thead>
<tr>
<th><strong>Anpassning av e-postkonfiguration (allmän tillgänglighet) </strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>För större flexibilitet och kontroll över e-postinställningarna kan du definiera dynamiska underdomäner och anpassade rubrikparametrar när du skapar e-postkanalskonfigurationer.
</p>
<p>Mer information finns i den <a href="../email/surface-personalization.md">detaljerade dokumentationen</a>.</p>
<img src="assets/do-not-localize/surface-perso.gif"/>
<p>Tillgänglig sedan 23 oktober 2024</p>
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
<p>Mer information finns i den <a href="../test-approve/gs-approval.md">detaljerade dokumentationen</a>.</p>
<img src="assets/do-not-localize/approval.gif"/>
<p>Tillgänglig sedan 22 oktober 2024</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Innehållsexperiment under resor (allmän tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer finns redan i kampanjer och stöder nu experiment på resor. Experimentella tester är randomiserade, vilket i samband med onlinetestning innebär att du exponerar vissa slumpmässigt utvalda användare för en viss variant av ett meddelande och en annan slumpmässigt utvald uppsättning användare för annan variation eller behandling. Efter exponering kan du mäta de resultatvärden du är intresserad av, som öppningar av e-post, prenumerationer eller inköp.</p>
<p>Mer information finns i den <a href="../content-management/content-experiment.md">detaljerade dokumentationen</a>.</p>
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
<p>Beslutsfattandet, som tidigare fanns för en uppsättning organisationer (LA) och som kallas Experience Decision, är nu tillgängligt för alla användare (GA), inklusive organisationer som har köpt tillägget Adobe Healthcare Shield eller Privacy and Security Shield.</p><p>Beslutsfattandet förenklar personaliseringen genom att erbjuda en centraliserad katalog med marknadsföringserbjudanden som kallas beslutsposter och en avancerad beslutsmotor. Den här motorn använder regler och rankningskriterier för att välja ut och presentera de mest relevanta beslutsobjekten för varje enskild person. Dessa beslutsobjekt integreras smidigt i ett stort antal inkommande ytor via den kodbaserade upplevelsekanalen.</p>
<p>Mer information finns i den <a href="../experience-decisioning/gs-experience-decisioning.md">detaljerade dokumentationen</a>.</p>
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
<p>Mer information finns i den <a href="../content-management/multilingual-gs.md">detaljerade dokumentationen</a>.</p>
<img src="assets/do-not-localize/multilingual.gif">
</td>
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
<p>Journey Optimizer rapportering är nu allmänt tillgänglig (GA) och har förbättrad interoperabilitet med Customer Journey Analytics, standardiserad rapportering för båda plattformarna och förbättrad datakonsekvens och tillförlitlighet. Denna smidiga integrering mellan Journey Optimizer och Customer Journey Analytics ger en tydligare bild av prestandamätningarna, så att användarna kan fatta mer välgrundade beslut.</p>
<p>Med General Availability introduceras fyra nya funktioner: möjlighet att skapa enkla mätvärden, skapa och publicera målgrupper, ställa ad hoc-frågor med Insight Builder och schemalägga rapporter som automatiskt ska skickas till viktiga mottagare.</p>
<p>Mer information finns i den <a href="../reports/report-cja-manage.md">detaljerade dokumentationen</a>.</p>
<img src="assets/do-not-localize/ajo-cja.gif">
<p>Viktigt: Den nuvarande rapportupplevelsen kommer att upphöra i januari 2025. Efter detta datum kommer den nya rapportupplevelsen att bli standard. Vi rekommenderar att du behärskar de nya funktionerna så att övergången blir smidig. <a href="../reports/report-gs-cja.md">Lär dig hur du kommer igång med Journey Optimizer nya rapporteringsgränssnitt</a></p>
<p>Tillgänglig sedan 16 oktober 2024</p>
</tr>
</tbody>
</table>

<!--The following capabilities are available to all customers in public beta:-->

<table>
<thead>
<tr>
<th><strong>Testa materialet med exempeldata (Beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med reseoptimeraren kan du nu testa olika varianter av ditt innehåll genom att förhandsgranska det och skicka e-postkorrektur med exempelindata som överförts från en fil eller lagts till manuellt. Alla profilattribut som används i ditt innehåll för personalisering identifieras automatiskt av systemet och kan användas för dina tester för att skapa flera varianter.</p>
<p>Den här funktionen är för närvarande tillgänglig för alla kunder som en offentlig betaversion av meddelandekanalerna för e-post, SMS och push.</p>
<p>Mer information finns i den <a href="../test-approve/simulate-sample-input.md">detaljerade dokumentationen</a>.</p>
<img src="assets/do-not-localize/gif-simulate.gif">
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Använd Adobe Experience Platform-data för personalisering (Beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Utnyttja data från Adobe Experience Platform i personaliseringsredigeraren för att personalisera ert innehåll. För att göra detta måste datauppsättningar som behövs för sökpersonalisering först aktiveras via ett API-anrop. När du är klar kan du använda deras data för att anpassa ditt innehåll till [!DNL Journey Optimizer].</p>
<p>Den här funktionen är för närvarande tillgänglig för alla kunder som en betaversion.</p>
<p>Mer information finns i den <a href="../personalization/lookup-aep-data.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar {#24-10-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**SMS-kanal**

* Nu kan du redigera eller ta bort en konfiguration för SMS API-kanal. [Läs mer](../sms/sms-configuration.md)

* Följande förbättringar har införts för att förbättra SMS-meddelandefunktionerna med Infobip och Sinch:

   * Ni kan definiera och hantera unika nyckelord för era SMS-kampanjer och resor, vilket möjliggör mer personaliserad och effektiv kommunikation.

   * Du kan skapa och leverera ett standard-SMS-meddelande när ett nyckelord inte känns igen.

  Läs mer om de här förbättringarna i SMS-konfigurationsdokumentationen för [Infobip](../sms/sms-configuration-infobip.md) och [Sinch](../sms/sms-configuration-sinch.md).


<!--**Journeys**-->

<!--* **Path experiment in journeys** - With the journey path experiment, you can now define and track key metrics for your journey paths, allowing you to measure the impact of your activities and to provide clearer insights into your performance. -->

<!--* **Max number of Live journeys** - Journey Optimizer now has a guardrail of 500 live journeys on production sandboxes, instead of 100. The number of live journeys is visible in the journey canvas. (DOCAC-10977) -->

**Webbkanal**

* **Icke-visuellt redigeringsläge för webbdesignern** - Som ett alternativ till Journey Optimizer webbdesigners kan du nu lägga till ändringar på webbplatsen med en icke-visuell redigerare. Du kan ange ändringarna manuellt utan att öppna sidorna i den visuella redigeraren. Det här icke-visuella redigeringsläget är användbart om du inte kan installera webbläsartillägg som Adobe Experience Cloud Visual Helper, som krävs för att läsa in sidorna i webbdesignern. [Läs mer](../web/web-non-visual-editor.md)


**Datauppsättningar**

* **Skicka och öppna händelser** - Med början 1 november 2024 har direktuppspelningssegmentering inte längre stöd för att skicka och öppna händelser från Journey Optimizer spårnings- och feedbackdatauppsättningar. Den här ändringen gäller för alla kundsandlådor och organisationer. [Läs mer](../data/datasets-ttl.md#segmentation-update)

* **Datauppsättning TTL (Time-to-live)** - Från och med februari 2025 introduceras ett TTL-skyddsprotokoll (time-to-live) i Journey Optimizer systemgenererade datauppsättningar i nya sandlådor och nya organ enligt följande:

   * 90 dagar för data i profilarkivet
   * 13 månader för data i sjön

  Den här ändringen kommer att introduceras i befintliga kundsandlådor i en efterföljande fas. [Läs mer](../data/datasets-ttl.md#ttl)

* **Parametrar i anpassade åtgärder** - Tillgänglighetsdatum: 3 okt 2024 - NULL och valfria parametrar stöds nu i anpassade åtgärder. [Läs mer](../action/about-custom-action-configuration.md#define-the-message-parameters)

**Rapportering**

* **Nu finns det beslutsrapporter** som ger viktiga insikter i hur besökarna interagerar med upplevelserna. [Läs mer](../reports/campaign-global-report-cja-code.md#decisioning-kpis)

**Datastyrning och samtycke** - Tillgänglighetsdatum: 7 okt 2024

* **Tillämpning av datastyrningsprinciper** sker nu i alla kanaler i Journey Optimizer. För kunder som har skapat policyer i Adobe Experience Platform tillämpas dessa på marknadsföringsåtgärder som en del av kanalkonfigurationsinställningarna. När du skapar innehåll med en konfiguration kontrollerar systemet om det finns några datastyrningsfel i alla anpassningsfält. Om en överträdelse hittas går det inte att publicera en resa eller kampanj. [Läs mer](../action/action-privacy.md)

* **Egna medgivandeprinciper** gäller nu för alla Journey Optimizer-kanaler. Vid behov innan ett meddelande skickas eller en inkommande upplevelse levereras, kontrollerar systemet att användaren har gett sitt medgivande till att använda personaliseringsfält i innehållet som han/hon får. Om inget samtycke ges visas inte upplevelsen. [Läs mer](../action/consent.md)

  >[!NOTE]
  >
  >Samtyckespolicyer är för närvarande bara tillgängliga för organisationer som har köpt tillägget **Adobe Healthcare Shield** eller **Privacy and Security Shield**.

**Publiker** - Tillgänglighetsdatum: 8 okt 2024

* När ni riktar er till en publik med CSV-filer kan ni nu använda attribut från filen i personaliseringsredigeraren och i regelbyggaren för resor och kampanjer. [Läs mer](../audience/about-audiences.md)

* Målgrupper och attribut från anpassad uppladdning (CSV-fil) kan nu användas med hälso- och sjukvårdsskölden eller skölden för skydd av privatlivet och säkerheten.

**Konfiguration** - Tillgänglighetsdatum: 23 okt 2024

* När du använder en anpassad konfiguration i en kampanj eller en resa kan du nu förhandsgranska ditt e-postinnehåll för att kontrollera om det finns potentiella fel med de dynamiska inställningar du har definierat. [Läs mer](../email/surface-personalization.md#check-configuration)

**Kodbaserad kanal**

* Innehållsmallar är nu tillgängliga. Ni kan snabba upp utvecklingen av era kodbaserade upplevelser med utgångspunkt i en innehållsmall som byggts av era utvecklare. Om du använder en innehållsmall kan marknadsföraren bara ändra vissa värden eller fält, i stället för att disponera hela HTML eller JSON-innehållets nyttolast. [Läs mer](../content-management/content-templates.md)

**Beslut**

* [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html)-användare kan nu välja anpassade modeller att optimera när de ställer in en AI-modell i Decisioning (tidigare Experience Decisioning). På så sätt kan du till exempel optimera en anpassad&quot;inköps&quot;-tabell i stället för definierade begränsningar som klickfrekvens. [Läs mer](../experience-decisioning/ranking.md)

* När du lägger till en beslutspolicy till en kodbaserad kampanj med Beslutsfattning kan du nu välja enskilda beslutsposter manuellt, utöver urvalsstrategier. Dessutom kan du nu välja mer än ett reserverbjudande. Detta garanterar att det finns ett visst antal återlämnade beslutsposter. [Läs mer](../experience-decisioning/create-decision.md)
