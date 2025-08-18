---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
topic: Content Management
description: Versionsinformation om Adobe Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 5414f5a4c7bec643151f556375e0c58367d1c3bd
workflow-type: tm+mt
source-wordcount: '1749'
ht-degree: 0%

---

# Versionsinformation {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="Nyheter?"
>abstract="**Adobe Journey Optimizer** levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen."

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen. [!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver från de senaste innovationerna och förbättringarna. Läs mer om de här ändringarna i [Adobe Experience Platform versionsinformation](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=sv-SE){target="_blank"}.


## 25 förhandsversionsinformation augusti {#25-8-rn}

**Förhandsversionsinformationen nedan kan ändras utan föregående meddelande till releasedatumet**. Länkar, skärmar och uppdaterad dokumentation publiceras på releasedatum.

Se även [Förhandsversionsinformation för Adobe Experience Platform](https://experienceleague.adobe.com/sv/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.

**Releasedatum**: 19 augusti 2025


### Nya funktioner {#Aug-25-8-features}

De nya funktionerna i den här versionen beskrivs nedan.

<table>
<thead>
<tr>
<th><strong>Pausa och återuppta resor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du pausa och återuppta dina resor. Denna förmåga ger resenärerna större kontroll och flexibilitet genom att göra det möjligt att tillfälligt avbryta pågående resor utan att störa kundupplevelsen. När det är pausat skickas ingen kommunikation och profilerna förblir i ett uppehåll tills resan återupptas.</p>
<p>Du kan bara pausa och återuppta en resa, eller utföra grupppausningar och återuppta åtgärder på en grupp resor.</p>
<p>Dessutom kan du använda globala filter på pausade resor för att exkludera profiler baserat på deras attribut.</p>
<p><!--img src="assets/do-not-localize/PauseResume.gif"/>--></p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer (allmän tillgänglighet).</p>
<p><!--For more information, refer to the <a href="../building-journeys/journey-pause.md">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Kalendervy</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu finns en kalendervy tillgänglig i rese- och kampanjlistorna. Ni kan visualisera alla resor och kampanjaktiveringar i respektive lista.</p>
<p>Den här funktionen fanns tidigare i Begränsad tillgänglighet och är nu tillgänglig i alla miljöer. I den här allmänna tillgänglighetsversionen innehåller funktionen:</p>
<ul>
<li>Designförbättringar för navigering i datum,</li>
<li>Möjlighet att se utkast till kampanjer om du har angett ett start- och slutdatum,</li>
<li>En ny inställning som döljer och visar kalenderobjekt som körs länge.</li>
</ul>
<p><!--img src="assets/do-not-localize/calendar.gif"/>--></p>
<p><!--For more information, refer to the <a href="../building-journeys/journey-ui.md#journeys-calendar">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Dark mode in the Email Designer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The Journey Optimizer Email Designer now offers the ability to switch to dark mode view, where you can additionally define specific custom settings that will display only for recipients reading their emails in dark mode.</p>
<p>Note the following:</p>
<ul>
<li>The dark mode final rendering may vary and depends on the recipient's email client.</li>
<li>Not all email clients support custom dark mode. Moreover, some email clients only apply their own default dark mode for all emails that are received. In both cases, the custom settings that you defined in the Email Designer cannot be rendered.</li>
</ul>
<P>This capability is currently in beta version and only available to beta customers. To join the beta program, contact your Adobe representative.</p>
<p><img src="assets/do-not-localize/dark-mode.gif"/></p>
<p>For more information, refer to the <a href="../email/dark-mode.md">detailed documentation</a></p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>Använd Adobe Experience Platform-data för personalisering</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Utnyttja data från [!DNL Adobe Experience Platform] i personaliseringsredigeraren för att anpassa ditt innehåll och dina beslutsattribut. Detta gör särskilt att du kan utöka definitionen av dina attribut till ytterligare data i datauppsättningar för större uppdateringar som ändras regelbundet utan att du behöver uppdatera attributen manuellt.</p>
<p>I den här versionen har följande förbättringar införts:</p>
<ul>
<li>Stöd för inkommande kanaler,</li>
<li>Hjälpfunktionen"datasetLookup" kan nu användas i uttryck och visuella fragment för att anpassa innehåll med data från Adobe Experience Platform datamängder.</li>
<li>Med ett alternativ i datauppsättningen kan du nu aktivera datauppsättningar för sökpersonalisering, utan att behöva utföra ett API-anrop.</li>
</ul>
<p>Den här funktionen är tillgänglig med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.</p>
<p><!--img src="assets/do-not-localize/FILE.gif"/>--></p>
<p><!--For more information, refer to the <a href="../FILE.md">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Use Decisioning in email channel</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now add Decision policies into email journeys and campaigns. Decision policies are containers for your offers that leverage the Decisioning engine to dynamically return the best content to deliver for each audience member.</p>
<p>Previously released in Limited Availability, this capability is now available to all environments (General Availability).</p>
<p><img src="assets/do-not-localize/FILE.gif"/></p>
<p><For more information, refer to the <a href="../FILE.md">detailed documentation</a></p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>Optimering av resväg</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><!--Journey Optimizer now empowers you with the tools to optimize your journeys by leveraging AI and experimentation frameworks while ensuring seamless usability and differentiation between condition and optimization functionalities.--></p>
<p>Använd den nya Optimera-aktiviteten för att målinrikta, experimentera eller använda AI för att avgöra kommunikationssekvenser, hur lång tid det tar mellan dem, kombinationer av kanaler och allt du kan drömma om på arbetsytan.</p>
<p>Den här funktionen är tillgänglig med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.</p>
<p><!--img src="assets/do-not-localize/optimize.gif"/>--></p>
<p><!--For more information, refer to the <a href="../FILE.md">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Verksamhet under resor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer har stöd för en ny generisk Action-aktivitet som gör att du kan konfigurera både enskilda åtgärder och inkommande funktionsmakrogrupper för flera åtgärder, vilket ger en smidig åtgärdskonfiguration på arbetsytan. Den här nya funktionen gör det möjligt att:</p>
<ul>
<li>En förenklad inbyggd åtgärdskonfiguration på arbetsytan för resan.</li>
<li>Kapaciteten för att skapa inkommande multiaktionsnoder.</li>
<li>Möjlighet att lägga till optimering till alla inbyggda kanalåtgärder.</li>
<li>Möjlighet att lägga till både experimentella och flerspråkiga alternativ i alla funktionsmakron.</li>
</ul>
<p>Den här funktionen är tillgänglig med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.</p>
<p><!--img src="assets/do-not-localize/pdf-attachments.gif"/>--></p>
<p><!--For more information, refer to the <a href="../FILE.md">detailed documentation</a>--></p>
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
<li>För ytterligare storlekar och volymer kan du köpa ett tilläggspaket. Mer information får du av Adobe.</li>
</ul>
<p>Den här funktionen är tillgänglig med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.</p>
<p><!--img src="assets/do-not-localize/FILE.gif"/>--></p>
<p><!--For more information, refer to the <a href="../FILE.md">detailed documentation</a>--></p>
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
<p><!--This capability is currently in beta version and only available to beta customers. To join the beta program, contact your Adobe representative.--></p>
<p><!--img src="assets/do-not-localize/FILE.gif"/>--></p>
<p><!--For more information, refer to the <a href="../FILE.md">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Optimering av kampanjer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer ger er nu de verktyg ni behöver för att leverera personaliserat och optimerat innehåll till er målgrupp, så att ni kan köra innehållsexperiment, skapa regelbaserad målinriktning och använda avancerade kombinationer av båda för att maximera effektiviteten i era kampanjer.</p>
<p>Med optimering kan man</p>
<ul>
<li>Testa olika innehållsvariationer för att identifiera de mest effektiva budskapen.</li>
<li>Leverera personaliserat innehåll baserat på användarattribut och sammanhangsbaserade data.</li>
<li>Kombinera målinriktning och experiment för avancerade kampanjstrategier.</li>
<li>Filtrera bort användare som inte matchar variantvillkor.</li>
<li>Se till att reservmekanismer upprätthåller användarengagemanget.</li>
</ul>
<P>När kampanjen är aktiv utvärderas profiler mot de definierade kriterierna, och baserat på matchningskriterier levereras de med rätt erfarenhet eller innehåll från kampanjen.</p>
<p><img src="assets/do-not-localize/campaign-optimization.gif"/></p>
<p>Releasedatum: 8 augusti 2025</p>
<p>Mer information finns i <a href="../campaigns/campaigns-message-optimization.md">detaljerad dokumentation</a></p>
</td>
</tr>
</tbody>
</table>

### Förbättringar {#Aug-25-8-improv}

Förbättringar i den här versionen visas nedan.

* **Administration**

   * **Varningar för kanalkonfigurationsövervakning** - Du kan nu prenumerera för att ta emot systemvarningar, antingen via e-post eller i Journey Optimizer meddelandecenter, om <!--a channel configuration failure happens or if --> en DNS-post saknas.

* **Kampanjer**

   * **Hastighetskontroll för utgående kampanjer** - Nu kan du aktivera hastighetskontroll för utgående kampanjer (e-post, SMS, push-meddelanden), så att du kan förhindra överbelastning i efterföljande system, som landningssidor eller kundtjänstplattformar.

   * **Schemaläggning av åtgärdskampanjer** - Schemaläggaren för kampanjen dagligen, veckovis och månadsvis har uppdaterats för att ge mer detaljerad kontroll över återkommande scheman:

      * **Återkommande varje vecka**: Du kan nu välja att upprepa kampanjen varje vecka eller varannan vecka och välja vilka veckodagar den ska köras på.

      * **Månadsvis återkommande**: Du kan nu välja att upprepa kampanjen varje månad eller varannan månad och välja den dag i månaden som den ska köras.

      * **Dagliga, veckovisa eller månadsvisa scheman**: Du kan ange om det återkommande schemat ska stoppas ett visst datum eller efter ett visst antal förekomster.

   * **Schemalagda transaktionsåtgärdskampanjer** - Schemalagda transaktionsåtgärdskampanjer är nu tillgängliga för sändning av batchbaserad, målgruppsbaserad transaktionskommunikation via e-post-, SMS- och push-kanaler.

* **Kanal - tryck**

   * **Förfallodatum för push-meddelanden** - Nu kan du ange ett förfallodatum för varje push-meddelande, vilket förhindrar att tidskänsliga meddelanden (som Black Friday Sale) skickas efter ett visst datum, vilket förhindrar att dina kunder får en dålig upplevelse.

* **Kanal - SMS**

   * **Fuzzy Opt-out** - När alternativet **Fuzzy Opt-out** är aktiverat upptäcks inkommande meddelanden som liknar definierade avanmälningsnyckelord (t.ex. CANCIL) och ett bekräftelsemeddelande skickas automatiskt för att bekräfta användarens avanmälan. Om användaren bekräftar via den definierade uppmaningen, avbeställs prenumerationen.

     Observera att **Fuzzy Opt-out** endast är tillgängligt med Sinch och Infobip.

   * **Verifiera SMS-anslutning** - Nu kan du enkelt testa och verifiera dina SMS API-autentiseringsuppgifter i Adobe Journey Optimizer genom att skicka ett exempelmeddelande till en angiven enhet.

* **Konfiguration**

   * **Stöd för dynamiska domäner** - Journey Optimizer har nu stöd för personalisering i spårnings-URL:er för fördefinierade domäner som listas på kanalkonfigurationsnivån.

   * **Stöd för anpassade attribut med en klickning för att avbryta prenumeration-URL** - Om du hanterar samtycke utanför Adobe kan du ange en extern anpassad slutpunkt genom att definiera en egen länk för att avbryta prenumeration i e-postkonfigurationen med ett enda klick. När mottagarna klickar på länken för att avbryta prenumerationen lägger Journey Optimizer till vissa standardprofilspecifika parametrar i händelsen för att skicka medgivandeuppdatering.

     Om du vill anpassa länken för att avbryta prenumerationen med ett klick ytterligare kan du nu definiera anpassade attribut som även läggs till i medgivandehändelsen.

* **Beslut**

   * **Koppla fragment till beslutsobjekt** - Journey Optimizer kan nu koppla fragment till beslutsobjekt som kan utnyttjas i kodbaserade upplevelsekampanjer via beslutspolicyer.

* **Resor**

   * **Resemassåtgärder** - I listan över dina resor kan du nu välja flera objekt. När du har valt det här alternativet kan du pausa eller återuppta upp till 10 resor i taget.

   * **Stöd för omdirigering (302) i anpassade åtgärder** - Anpassade åtgärder kan nu hantera HTTP 302-omdirigeringar per begäran. På så sätt kan resor integreras med API:er som omdirigerar begäranden till lokaliserade eller regionspecifika URL:er. Omdirigeringar utförs automatiskt så att rätt innehåll levereras utan extra konfiguration.

* **Datauppsättningar**

   * **Objektarkiv för Experience Decisioning - personaliserade erbjudandeobjekt** - Inbyggd exportdatauppsättning hämtar nu alla erbjudandeattribut och livscykelstatus, vilket möjliggör fullständig personalisering och rapportering.

## Kampanjsamordning

**Tillgänglighetsdatum**: 4 augusti 2025

Journey Optimizer innehåller nu **Kampanjsamordning**, en ny funktion som är avsedd för varumärkesinitierade gruppkampanjer. I den här versionen introduceras en kampanjsamordningsyta och förbättrad datamodellering, som fungerar tillsammans för att marknadsförarna ska kunna planera, målinrikta och leverera personaliserade flerkanalskampanjer.

>[!IMPORTANT]
>
>För att få åtkomst till kampanjsamordning måste din licens innehålla antingen paketet **Journey Optimizer - Campaigns &amp; Journeys** eller paketet **Journey Optimizer - Campaigns**. Kontakta din Adobe-representant för att bekräfta din licens och uppdatera vid behov.

![Kampanjsamordning GIF](assets/do-not-localize/release.gif)

Den innehåller [Relationsscheman och datauppsättningar](#oc-relational) och [Kampanjarbetsyta](#oc-canvas). Tillsammans sätter dessa två innovationer en ny standard för att samordna batchkampanjer i Journey Optimizer. Viktiga funktioner listas nedan.

### Nyckelfunktioner {#oc-capabilities}

* **Flerstegsarbetsflöden**

  Skapa sofistikerade gruppkampanjer i flera kanaler med den nya, specialbyggda arbetsytan för kampanjhantering.

* **On demand-målgrupper**

  Segmentera målgrupper på begäran för omedelbar aktivering.

* **Segmentering för flera enheter**

  Bygg målgrupper med hjälp av företagskontext (icke-personella dimensioner) som produkt, butiker, förnyelser, reservationer med mera.

* **Synlighet före sändning**

  Granska, förfina och optimera målgrupper och kampanjer före lansering och medan kampanjer körs

### Kampanjarbetsyta {#oc-canvas}

Ett helt nytt gränssnitt för visuell samordning som är konstruerat för gruppkampanjer. På arbetsytan kan du

* Visuell planering av flerstegskampanjer för flera kanaler

* Stöd för on demand-målgrupper som bygger på relationsfrågor

* Avancerad målgruppsdelning, väntetider och villkorslogik

* Exakt antal före sändning när affärsregler och filter har tillämpats

### Relationsscheman och datauppsättningar {#oc-relational}

Adobe Journey Optimizer har nu stöd för relationsenheter (t.ex. produkter, butiker, bokningar, kontrakt) som är kopplade till personbaserade profiler. Detta möjliggör segmentering och personalisering över flerdimensionella datastrukturer, vilket möjliggör exempelvis följande:

* Ett meddelande per bokning, prenumeration eller kontrakt

* Segmentering baserad på relaterade entitetsattribut (t.ex. produktkategori eller butiksplats)

* Förbättrad adressering (t.ex. skicka till alla kända kontakter som är kopplade till en enhet)

### Varför det spelar någon roll

Den här versionen ger marknadsförarna full kontroll över varumärkesinitierad, målgruppsbaserad batchmarknadsföring, vilket kombinerar flexibel datamodellering med en specialbyggd orkestreringsupplevelse. Den är särskilt utformad för gruppkampanjsamordning från realtidsresor, samtidigt som den erbjuder avancerad personalisering och skalbarhet.

### Läs mer

Läs mer i [dokumentationen för kampanjsamordning](../orchestrated/gs-orchestrated-campaigns.md).


