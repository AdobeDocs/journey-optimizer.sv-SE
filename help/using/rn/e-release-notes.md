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
source-git-commit: d3f0adab52ed8e44a6097c5079396d1e9c06e0a7
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 2%

---

# Tidig versionsinformation {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i [versionsinformation](release-notes.md).

Noteringarna nedan kan ändras utan föregående meddelande fram till releasedatum. Länkar, skärmar och uppdaterad dokumentation publiceras i [versionsinformation](release-notes.md), på releasedatum.

## Versionsinformation, februari 2024 {#e-2024}

**Releasedatum**: 21-22 feb 2024

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
<img src="assets/do-not-localize/web_inapp.gif">
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Frekvensregler för SMS och direktreklam</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Du kan nu skapa frekvensregler för SMS- och Direct Mail-kanaler. Frekvensreglerna exkluderar automatiskt överbegärda profiler från meddelanden och åtgärder när frekvensgränsen nås. <br/><br/></p>
<img src="assets/do-not-localize/sms-dm-rules.gif">
</tr>
</tbody>
</table>

### Förbättringar {#e-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**Publiker**

* **Utsändningslistor** - Varianter stöds nu när de använder **listor med startsidor**. Precis som för varje profil från målgruppen får dirigeringsadresserna en kopia av alla varianter av samma budskap (till exempel olika behandlingar av ett innehållsexperiment).

Tidigare som betaversion är följande förbättringar nu tillgängliga för alla användare:

* Nu kan du ange mål **målgrupper skapade genom målgruppssammansättning** och utnyttja anrikningsattributen i Journeys. [Läs mer](../building-journeys/read-audience.md)

* Nu kan du ange mål **målgrupper som överförts från en CSV-fil** på resor och kampanjer. [Läs mer](../audience/about-audiences.md#segments-in-journey-optimizer)

  >[!AVAILABILITY]
  >
  >* Användningen av målgrupper och attribut från målgruppssammansättning och anpassad uppladdning (CSV-fil) är för närvarande inte tillgänglig för användning med hälso- och sjukvårdsskölden eller skölden för skydd av privatlivet och säkerheten.
  >* Observera att målgruppsuppladdningen från en CSV-filförbättring kommer att introduceras gradvis under flera dagar efter den första versionen. Vissa användare har omedelbar åtkomst, men andra kan uppleva en fördröjning innan den blir tillgänglig i sina konton.

**Resor**

* **Filtrera dina resor** - Nu kan du använda **anpassade datum för att filtrera resorna** lager, utöver befintliga fördefinierade datumfilter. På så sätt kan du förfina listan genom att visa resor som skapats eller publicerats på ett visst datum, inom en viss månad, under ett helt år eller inom angivna tidsintervall.
* **Anpassade åtgärder** - Du kan nu uppdatera **content-type** header. Den här nya **content-type** ska referera till JSON-innehåll.
* **Konfiguration** - Attributet identityMap i stepEvents är nu förfyllt. Den primära identiteten definieras som &quot;primär = true&quot;.
* **Användargränssnitt** - Den övre ribban på skärmar har omstrukturerats för en förbättrad upplevelse. Bland de olika uppdateringarna kan du lägga märke till att pennikonen som gör att du kan komma åt färgegenskaperna nu visas till vänster om det övre fältet, bredvid resans namn.

**SMS-kanal**

* **Nyckelord för anmälan/avanmälan** - När du konfigurerar din SMS-kanal kan du nu anpassa **Nyckelord för deltagande och avanmälan** enligt dina önskemål. Journey Optimizer utlöser svaret baserat på dessa angivna nyckelord.

**Kampanjer**

* **API-utlösta kampanjer** - Den cURL-kod som genereras efter aktivering av en API-utlöst kampanj har förbättrats. Det innehåller nu alla personaliseringsvariabler (profil och kontext) som används i meddelandet.

**Beslutsledning**

* **Begränsningsregler** - Nu kan du lägga till **regler för flera begränsningar** för ett erbjudande. På så sätt kan ni öka kontrollen över hur erbjudandena skickas.

**Innehållsmallar**

* **Miniatyrbild** - A **miniatyrbildsvisning** är nu tillgängligt för innehållsmallar och fragment för förbättrad visuell åtkomst.

  >[!AVAILABILITY]
  >
  >Den här funktionen lanseras i begränsad tillgänglighet (LA) för en liten grupp kunder.

* **Mallar för flera kanaler** - Innehållsmallar är nu tillgängliga för **alla kanaler**, förutom webben. För E-post kan du nu välja typ (HTML eller Innehåll).
