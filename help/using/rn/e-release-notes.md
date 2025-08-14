---
solution: Journey Optimizer
product: journey optimizer
title: Förhandsversionsinformation för Journey Optimizer
description: Adobe Journey Optimizer Pre Release Notes
feature: Release Notes
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 75c3db704853b8d2d8920ddd0086681d1fb02a93
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 0%

---

# Förhandsversionsinformation {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras i slutet av varje månad i [versionsinformationen](release-notes.md).


## 25 förhandsversionsinformation augusti {#25-8-rn}

**Förhandsversionsinformationen nedan kan komma att ändras utan föregående meddelande till releasedatumet**. Länkar, skärmar och uppdaterad dokumentation publiceras i versionsinformationen på releasedatum.

Se även [Förhandsversionsinformation för Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.

**Releasedatum**: 19 augusti 2025


### Nya funktioner {#Aug-25-8-features}

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
<p>Utnyttja data från Adobe Experience Platform i personaliseringsredigeraren för att personalisera ert innehåll. För att göra detta måste datauppsättningar som behövs för sökpersonalisering först aktiveras via ett API-anrop. När du är klar kan du använda deras data för att anpassa ditt innehåll till [!DNL Journey Optimizer].</p>
<p>Den här funktionen lanserades tidigare i begränsad tillgänglighet och är nu tillgänglig i alla miljöer. I den här allmänna tillgänglighetsversionen har följande förbättringar införts:</p>
<ul>
<li>Stöd för inkommande kanaler,</li>
<li>Hjälpfunktionen"datasetLookup" kan nu användas i uttryck och visuella fragment för att anpassa innehåll med data från Adobe Experience Platform datamängder.</li>
<li>Med ett alternativ i datauppsättningen kan du nu aktivera datauppsättningar för sökpersonalisering, utan att behöva utföra ett API-anrop.</li>
</ul>
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
<p>Journey Optimizer ger er nu de verktyg ni behöver för att optimera era resor genom att utnyttja AI och experimenteringsramverk samtidigt som ni säkerställer smidig användbarhet och differentiering mellan villkor och optimeringsfunktioner.</p>
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
<p>Med Journey Optimizer kan du nu skapa anpassade formulär och använda dem på landningssidor för att hämta in profilattribut i den datauppsättning som har definierats för varje formulär.</p>
<p>Den här funktionen är tillgänglig med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.</p>
<p><!--This capability is currently in beta version and only available to beta customers. To join the beta program, contact your Adobe representative.--></p>
<p><!--img src="assets/do-not-localize/FILE.gif"/>--></p>
<p><!--For more information, refer to the <a href="../FILE.md">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>


### Förbättringar {#Aug-25-8-improv}

Förbättringar i den här versionen visas nedan.

* **Administration**

   * **Varningar för kanalkonfigurationsövervakning** - Du kan nu prenumerera för att ta emot systemvarningar, antingen via e-post eller i Journey Optimizer meddelandecenter, om ett kanalkonfigurationsfel inträffar eller om en DNS-post saknas.

* **Kampanjer**

   * **Hastighetskontroll för utgående kampanjer** - Nu kan du aktivera hastighetskontroll för utgående kampanjer (e-post, SMS, push-meddelanden), så att du kan förhindra överbelastning i efterföljande system, som landningssidor eller kundtjänstplattformar.

   * **Schemaläggning av åtgärdskampanjer** - Schemaläggaren för kampanjen dagligen, veckovis och månadsvis har uppdaterats för förbättrad granularitet. Du kan till exempel nu ange antalet veckor/månader mellan scheman, definiera vilken dag som ska köras och bestämma dig för att stoppa efter ett visst antal förekomster eller ett visst datum.

   * **Schemalagda transaktionsåtgärdskampanjer** - Schemalagda transaktionsåtgärdskampanjer är nu tillgängliga för sändning av batchbaserad, målgruppsbaserad transaktionskommunikation via e-post-, SMS- och push-kanaler.

* **Kanal - tryck**

   * **Förfallodatum för push-meddelanden** - Nu kan du ange ett förfallodatum för varje push-meddelande, vilket förhindrar att tidskänsliga meddelanden (som Black Friday Sale) skickas efter ett visst datum, vilket förhindrar att dina kunder får en dålig upplevelse.

* **Kanal - e-post**

   * **PDF-bilagor till e-postmeddelanden** - Nu kan du bifoga statiska PDF-filer till e-postmeddelanden som skickas med Journey Optimizer.

* **Kanal - SMS**

   * **Fuzzy Opt-out** - När alternativet **Fuzzy Opt-out** är aktiverat upptäcks inkommande meddelanden som liknar definierade avanmälningsnyckelord (t.ex. CANCIL) och ett bekräftelsemeddelande skickas automatiskt för att bekräfta användarens avanmälan. Om användaren bekräftar via den definierade uppmaningen, avbeställs prenumerationen.

     Observera att **Fuzzy Opt-out** endast är tillgängligt med Sinch och Infobip.

   * **Verifiera SMS-anslutning** - Nu kan du enkelt testa och verifiera dina SMS API-autentiseringsuppgifter i Adobe Journey Optimizer genom att skicka ett exempelmeddelande till en angiven enhet.

* **Konfiguration**

   * **Stöd för dynamiska domäner** - Journey Optimizer har nu stöd för personalisering i spårnings-URL:er för fördefinierade domäner som listas på kanalkonfigurationsnivån.

   * **Stöd för anpassade attribut med en klickning för att avbryta prenumeration-URL** - Om du hanterar samtycke utanför Adobe kan du ange en extern anpassad slutpunkt genom att definiera en egen länk för att avbryta prenumeration i e-postkonfigurationen med ett enda klick. När mottagarna klickar på länken för att avbryta prenumerationen lägger Journey Optimizer till vissa standardprofilspecifika parametrar i händelsen för att skicka medgivandeuppdatering.

     Om du vill anpassa länken för att avbryta prenumerationen med ett klick ytterligare kan du nu definiera anpassade attribut som läggs till i medgivandehändelsen.

* **Beslut**

   * **Koppla fragment till beslutsobjekt** - Journey Optimizer kan nu koppla fragment till beslutsobjekt som kan utnyttjas i kodbaserade upplevelsekampanjer via beslutspolicyer.

* **Resor**

   * **Resemassåtgärder** - I listan över dina resor kan du nu välja flera objekt. När du har valt det här alternativet kan du pausa eller återuppta upp till 10 resor i taget.
