---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
description: Journey Optimizer tidiga versionsinformation
feature: Release Notes
topic: Content Management
role: User
level: Beginner, Intermediate
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 51d07df4c1db10ea2e1ff76dbd29607c32fbd859
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 3%

---

# Tidig versionsinformation {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i [versionsinformation](release-notes.md).

Noteringarna nedan kan ändras utan föregående meddelande fram till releasedatum. Länkar, skärmar och uppdaterad dokumentation publiceras i [versionsinformation](release-notes.md), på releasedatum.

## Versionsinformation februari 2024 {#e-2024}

**Releasedatum**: 20-21 feb 2024

### Nya funktioner{#e-features}

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
<!--img src="assets/do-not-localize/computed-attributes.gif"-->
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Affärsregler (beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Du kan nu skapa regler för frekvensbegränsning som gäller för SMS- och Direct Mail-kanaler. Dessutom kan du ange regler för frekvensbegränsning efter kommunikationstyp.<br/><br/></p>
<!--img src="assets/do-not-localize/computed-attributes.gif"-->
</tr>
</tbody>
</table>



### Förbättringar {#e-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**Publiker**

* **Utsändningslistor** - Varianter stöds nu när de använder **listor med startsidor**. Precis som för varje profil från målgruppen får dirigeringsadresserna en kopia av alla varianter av samma budskap (till exempel olika behandlingar av ett innehållsexperiment).

Tidigare som betaversion är följande förbättringar nu tillgängliga för alla användare:

* Nu kan du ange mål **målgrupper som överförts från en CSV-fil** på resor och kampanjer. [Läs mer](../audience/about-audiences.md#segments-in-journey-optimizer)
* Nu kan du ange mål **målgrupper skapade genom målgruppssammansättning** och utnyttja anrikningsattributen i Journeys. [Läs mer](../building-journeys/read-audience.md)

**Resor**

* **Filtrera dina resor** - Nu kan du använda **anpassade datum för att filtrera resorna** lager, utöver befintliga fördefinierade datumfilter. På så sätt kan du förfina listan genom att visa resor som publicerats ett visst datum, inom en viss månad, under ett helt år eller inom angivna tidsintervall.
* **Anpassade åtgärder** - Du kan nu uppdatera rubriken &quot;content-type&quot; i **anpassade åtgärder**.
* **Konfiguration** - Attributet identityMap i stepEvents är nu förfyllt. Den primära identiteten definieras som &quot;primär = true&quot;.
* **Användargränssnitt** - Den övre ribban på skärmar har omstrukturerats för en förbättrad upplevelse. Bland de olika uppdateringarna kan du lägga märke till att pennikonen som gör att du kan komma åt färgegenskaperna nu visas till vänster om det övre fältet, bredvid resans namn.

**SMS-kanal**

* **Nyckelord för anmälan/avanmälan** - När du konfigurerar din SMS-kanal kan du nu anpassa **Nyckelord för deltagande och avanmälan** enligt dina önskemål. Journey Optimizer utlöser svaret baserat på dessa angivna nyckelord.

**Kampanjer**

* **API-utlösta kampanjer** - Information har lagts till i **cURL-begäran** avsnitt i **API-utlösta kampanjer** som finns i **Utkast** för att ange att exempelbegäran om cURL bara visas när kampanjen har publicerats och körts.

**Beslutsledning**

* **Begränsningsregler** - Nu kan du lägga till **regler för flera begränsningar** för ett erbjudande. På så sätt kan ni öka kontrollen över hur erbjudandena skickas.

**Innehållsmallar**

* **Miniatyrbild** - A **miniatyrbildsvisning** är nu tillgängligt för innehållsmallar och fragment för förbättrad visuell åtkomst.
* **Mallar för flera kanaler** - Innehållsmallar är nu tillgängliga för **alla kanaler**, förutom webben.