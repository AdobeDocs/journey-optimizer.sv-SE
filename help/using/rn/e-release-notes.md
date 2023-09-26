---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
description: Journey Optimizer tidiga versionsinformation
hide: true
hidefromtoc: true
source-git-commit: 75a03fbd6a369d9b8f75db819cfa995257eaf77f
workflow-type: tm+mt
source-wordcount: '634'
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

<table>
<thead>
<tr>
<th><strong>Beräknade attribut</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Beräknade attribut gör det enkelt att sammanfatta händelsedata i profilattribut via ett intuitivt användargränssnitt för förbättrad beteendebaserad segmentering, personalisering och aktivering. Med den här funktionen kan du skapa beräknade attribut på ett självbetjäningssätt, hantera dem och använda dem vid segmentering, kundprofilmål i realtid eller Journey Optimizer.<br/><br/>
Beräknade attribut förenklar dessutom arbetsflödena för segmentering och resor så att ni smidigt kan leverera relevanta upplevelser. Läs mer i <a href="https://experienceleague.adobe.com/docs/experience-platform/profile/computed-attributes/overview.html">detaljerad dokumentation</a>.</p>
<img src="assets/computed-attributes.png">
</tr>
</tbody>
</table>


### Förbättringar {#sept-2023-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

<!--**Audiences**

* You can now target audiences uploaded from a CSV file into journeys and campaigns.
* You can now target audiences resulting from composition workflows into journeys. -->

**Personalisering**

* Förutom visuella fragment går det nu att skapa, spara och återanvända uttrycksfragment från Journey Optimizer-gränssnittet via uttrycksredigeraren. Uttrycksfragment ersätter uttryck som sparats tidigare.

**Varningar**

* En ny typ av systemvarning har införts. Nu kan ni få meddelanden när en läsare misslyckas.

**Webbkanal**

* Enkelsidiga program (SPA) kan nu redigeras i webbdesignerns visuella redigerare, där du kan välja vilka specifika vyer du vill använda webbsidesändringarna på. En vy kan definieras som en hel webbplats eller som en grupp visuella element på en webbplats, till exempel hemsidan, hela produktwebbplatsen eller leveransinställningsramen på alla utcheckningssidor. Om du vill skapa och köra Adobe Journey Optimizer webbkampanjer på SPA måste du konfigurera en gång för utvecklare för att definiera vyerna i Adobe Experience Platform Web SDK-implementeringen.

* När du redigerar en sida med hjälp av webbdesignern kan du nu lägga till nya ändringar i innehållet direkt från **Ändringar** utan att behöva markera en komponent och redigera den i designergränssnittet.
* När du konfigurerar webbunderdomäner kan du nu lägga till en egen underdomän, förutom att använda en underdomän som redan har delegerats till Adobe.

**Resor**

* Stöd för anpassade åtgärdssvar är nu GA. På så sätt kan ni utnyttja API-anropssvar i anpassade åtgärder och samordna er resa baserat på dessa svar. Dessutom har ett nytt skyddsräcke lagts till för att begränsa alla tullåtgärder till 5000 samtal/s per slutpunkt.
* När du duplicerar en resa kan du nu definiera namnet på kopian av resan.

<!--
* The maximum duration that you can define in the Wait activity is now 29 days instead of 30.
-->

**E-postkanal**

Ett nytt alternativ i konfigurationen av e-postytan gör att du kan välja att skicka transaktionsmeddelanden till profiler även om deras e-postadresser finns i listan över Adobe Journey Optimizer-undertryckningar.

**SMS-kanal**

Två nya fält, **Inloggningsmeddelande** och **Hjälpmeddelande**, har lagts till i API-konfigurationsskärmen, vilket gör att användare kan anpassa svar för inkommande nyckelord. Observera att det här endast är tillgängligt för SMS-providern för Sinch.

**Rapportering**

Nu kan du exportera Journey Optimizer-rapporter som CSV-filer. [Läs mer](../reports/global-report.md#export-reports)

<!--**Decision management**

Enhancements have been made to the audience picker in journeys or campaigns, with the addition of new columns displaying the origin and update frequency of audiences.    -->