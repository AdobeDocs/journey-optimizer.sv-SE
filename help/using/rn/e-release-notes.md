---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
description: Journey Optimizer tidiga versionsinformation
hide: true
hidefromtoc: true
source-git-commit: b0a842232259ef2b1b930927a8c61c32bfc45123
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 4%

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
<p>Med funktionen Kanalrapport kan analytiker och marknadsförare få en heltäckande översikt över trafik- och engagemangsmått på kanalnivå. För att få åtkomst till menyn Rapport måste du ha behörigheten **Visa kanalrapporter**.</p>
<img src="assets/channel-reports.png"/>
<p>Mer information finns i den <a href="../in-app/get-started-in-app.md">detaljerade dokumentationen</a>.</p-->
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Generering av datauppsättningsexport (GA)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Export av Journey Optimizer datamängder till molnlagringsmål är nu allmänt tillgänglig. Med den här funktionen kan du upprätta en direktanslutning till molnlagringsplatser för att kunna exportera innehållet i dina datauppsättningar.</p>
<img src="../data/assets/dataset-export-setup.png">
<!--p>For more information, refer to the <a href="../audience/get-started-audience-orchestration.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>


### Förbättringar {#sept-2023-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**Publiker**

* Nu kan ni rikta in er på målgrupper som överförts från en CSV-fil till resor och kampanjer.
* Målgruppsväljaren har förbättrats under resor eller kampanjer, med nya kolumner som visar målgruppernas ursprung och uppdateringsfrekvens.
* Nu kan ni inrikta er på målgrupper som är resultatet av arbetsflöden för disposition på resor.

**Personalisering**

* Förutom visuella fragment går det nu att skapa, spara och återanvända uttrycksfragment från Journey Optimizer-gränssnittet via uttrycksredigeraren. Uttrycksfragment ersätter uttryck som sparats tidigare.
* Nu kan du använda Adobe Experience Platform beräknade attribut för personalisering i Journey Optimizer. Beräknade attribut är aggregerade värden som beräknas baserat på profilaktiverade Experience Event-datamängder som importerats till Adobe Experience Platform.

**Varningar**

En ny typ av systemvarning har införts. Du kan nu få ett meddelande när ett lässegment inte kan läsas.

**Webbkanal**

* Nu kan du välja vilka specifika vyer du vill använda webbsidesändringarna på. En vy kan definieras som en hel webbplats eller som en grupp visuella element på en webbplats, till exempel hemsidan, hela produktwebbplatsen eller leveransinställningsramen på alla utcheckningssidor.
* När du redigerar en sida med webbdesignern kan du nu lägga till nya ändringar i innehållet direkt från panelen Ändringar, utan att du behöver markera en komponent och redigera den i designergränssnittet.
* När du konfigurerar webbunderdomäner kan du nu lägga till en egen underdomän, förutom att använda en underdomän som redan har delegerats till Adobe.

**Resor**

* En ny typ av systemvarning har införts. Du kan nu få meddelanden när en anpassad åtgärd misslyckas.
* När du duplicerar en resa kan du nu definiera namnet på kopian av resan.


**E-postkanal**

Ett nytt alternativ i konfigurationen av e-postytan gör att du kan välja att skicka transaktionsmeddelanden till profiler även om deras e-postadresser finns i listan över Adobe Journey Optimizer-undertryckningar.

**Beslutshantering**

Målgruppsväljaren har förbättrats under resor eller kampanjer, med nya kolumner som visar målgruppernas ursprung och uppdateringsfrekvens.