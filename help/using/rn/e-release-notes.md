---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
description: Journey Optimizer tidiga versionsinformation
hide: true
hidefromtoc: true
source-git-commit: e5e4825996359cbe6c5bf0a06fc32a2ef116d906
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 3%

---

# Tidig versionsinformation {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i [versionsinformation](release-notes.md).

Noteringarna nedan kan ändras utan föregående meddelande fram till releasedatum. Länkar, skärmar och uppdaterad dokumentation publiceras i [versionsinformation](release-notes.md), på releasedatum.

## Versionsinformation september 2023 {#sept-rn-2023}

**Releasedatum**: 26-27 sept 2023

### Nya funktioner{#sept-2023-features}

Den här versionen innehåller de nya funktionerna som listas nedan.


<table>
<thead>
<tr>
<th><strong>Konsoliderade kanalrapporter</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med funktionen Kanalrapport kan analytiker och marknadsförare få en heltäckande översikt över trafik- och engagemangsmått på kanalnivå. Om du vill få åtkomst till menyn Rapport måste du ha behörigheten Visa kanalrapporter.</p>
<img src="assets/channel-reports.png"/>
<!--p>For more information, refer to the <a href="../in-app/get-started-in-app.md">detailed documentation</a>.</p-->
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Målgrupper för datauppsättningsexport (GA)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Export av Journey Optimizer datamängder till molnlagringsmål är nu allmänt tillgängligt. Med den här funktionen kan du upprätta en direktanslutning till molnlagringsplatser för att kunna exportera innehållet i dina datauppsättningar.</p>
<img src="../data/assets/dataset-export-setup.png">
<!--p>For more information, refer to the <a href="../audience/get-started-audience-orchestration.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Lagring av autentiseringsuppgifter för mobilprogram per sandbox</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med den här nya funktionen kan du enkelt hantera och associera push-autentiseringsuppgifter med en dedikerad sandlåda i appytor.</p>
<p>Mer information finns i den <a href="../in-app/inapp-configuration.md">detaljerade dokumentationen</a>.</p>
</tr>
</tbody>
</table>

### Förbättringar {#sept-2023-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**Publiker**

* Nu kan ni rikta in er på målgrupper som överförts från en CSV-fil till resor och kampanjer.
  <!--* Enhancements have been made to the audience picker in journeys or campaigns, with the addition of new columns displaying the origin and update frequency of audiences.-->
* Nu kan ni inrikta er på målgrupper som är resultatet av arbetsflöden för disposition på resor.

**Personalisering**

* Förutom visuella fragment går det nu att skapa, spara och återanvända uttrycksfragment från Journey Optimizer-gränssnittet via uttrycksredigeraren. Uttrycksfragment ersätter uttryck som sparats tidigare.
* Nu kan du använda Adobe Experience Platform beräknade attribut för personalisering i Journey Optimizer. Beräknade attribut är aggregerade värden som beräknas baserat på profilaktiverade Experience Event-datamängder som importerats till Adobe Experience Platform.

**Varningar**

* Två nya typer av systemvarningar har införts. Du kan nu få ett meddelande när en anpassad åtgärd eller ett lässegment misslyckas.

**Webbkanal**

* Nu kan du välja vilka specifika vyer du vill använda webbsidesändringarna på. En vy kan definieras som en hel webbplats eller som en grupp visuella element på en webbplats, till exempel hemsidan, hela produktwebbplatsen eller leveransinställningsramen på alla utcheckningssidor.
* När du redigerar en sida med webbdesignern kan du nu lägga till nya ändringar i innehållet direkt från panelen Ändringar, utan att du behöver markera en komponent och redigera den i designergränssnittet.
* När du konfigurerar webbunderdomäner kan du nu lägga till en egen underdomän, förutom att använda en underdomän som redan har delegerats till Adobe.

**Resor**

* Funktionerna för anpassade åtgärder är nu GA. På så sätt kan ni utnyttja API-anropssvar i anpassade åtgärder och samordna er resa baserat på dessa svar. Dessutom har ett nytt skyddsräcke lagts till för att begränsa alla tullåtgärder till 5000 samtal/s per slutpunkt.
* När du duplicerar en resa kan du nu definiera namnet på kopian av resan.
* Den maximala varaktighet som du kan definiera i aktiviteten Vänta är nu 29 dagar i stället för 30.

**E-postkanal**

Ett nytt alternativ i konfigurationen av e-postytan gör att du kan välja att skicka transaktionsmeddelanden till profiler även om deras e-postadresser finns i listan över Adobe Journey Optimizer-undertryckningar.

<!--**Decision management**

Enhancements have been made to the audience picker in journeys or campaigns, with the addition of new columns displaying the origin and update frequency of audiences.    -->