---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
description: Journey Optimizer tidiga versionsinformation
hide: true
hidefromtoc: true
source-git-commit: 3f00453df4ba73f621b23aaba7ce4631d40b648a
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 4%

---

# Tidig versionsinformation {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i [versionsinformation](release-notes.md).

Noteringarna nedan kan ändras utan föregående meddelande fram till releasedatum. Länkar, skärmar och uppdaterad dokumentation publiceras i [versionsinformation](release-notes.md), på releasedatum.

## Versionsinformation juli 2023 {#july-rn-2023}

**Releasedatum**: 26-27 juli

### Nya funktioner{#july-2023-features}

Den här versionen innehåller de nya funktionerna som listas nedan.

<table>
<thead>
<tr>
<th><strong>Målgruppskomposition</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du skapa arbetsflöden för kompositioner för att kombinera befintliga Adobe Experience Platform-målgrupper till en visuell arbetsyta och utnyttja olika aktiviteter (dela, berika...) för att skapa nya målgrupper. Nyligen skapade målgrupper sparas tillbaka i Adobe Experience Platform tillsammans med befintliga målgrupper och kan utnyttjas i Journey Optimizer kampanjer för att nå ut till kunder.</p>
<p>Mer information finns i den <a href="../audience/get-started-audience-orchestration.md">detaljerade dokumentationen</a>.</p>
<p>Målgruppsdispositionen är helt integrerad med den nya Adobe Experience Platform-menyn"Publiker", som fungerar som en central portal till målgrupper. Nu kan du använda en bläddringssida som innehåller en ny instrumentpanel med segmenttrender och överlappningar för att hitta nya insikter och utforska organisationsverktygen för mappning och taggning. Detta innefattar styrningskontroller för standardiserad målgruppsmärkning och funktioner för hantering av målgruppslivscykler för att hantera aktiveringsarbetsflöden. Med den nya hanteringsupplevelsen kan ni nu enkelt och säkert hantera målgrupper från ett och samma ställe. Mer information finns i <a href="https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html" target="_blank">Adobe Experience Platform-dokumentation</a>.</p></p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Direct mail channel</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now add direct mail messages in your campaigns. Direct mail is an offline channel that allows you to personalize and generate the files required by direct mail providers to send mail to your customers.</p>
<p>When you prepare a direct mail delivery, Journey Optimizer generates a file including all the targeted profiles and the chosen contact information (postal address for example). You will then be able to send this file to your direct mail provider who will take care of the actual sending.</p>
<img src="../direct-mail/assets/direct-mail-properties.png">
<p>For more information, refer to the <a href="../direct-mail/create-direct-mail.md">detailed documentation</a>.</p>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>Konvertera ditt HTML-innehåll för e-postdesignern</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du importera och konvertera valfritt HTML-innehåll i Journey Optimizer e-postredigerare. Innehållsblocken identifieras automatiskt och är tillgängliga i e-postdesignern: använd de kraftfulla designfunktionerna för att uppdatera och anpassa dem!</p>
<img src="../email/assets/html-imported_2.png">
<!--p>For more information, refer to the <a href="../audience/get-started-audience-orchestration.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Använd taggar i Journey Optimizer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Förutom kampanjer och resor kan du nu tilldela enhetliga Adobe Experience Platform-taggar till landningssidor, innehållsmallar, fragment och prenumerationslistor. På så sätt kan du enkelt klassificera dem och förbättra sökning och navigering i alla listor. </p>
<img src="assets/do-not-localize/campaigns-tag.gif"/>
<p>Mer information finns i den <a href="../start/search-filter-categorize.md#tags">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>API:er för innehållsmallar</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du skapa och hantera Adobe Journey Optimizer-innehållsmallar med dedikerade API:er, vilket ger en smidig integrering med ditt befintliga innehållssystem.</p>
<!--<p>For more information, refer to the <a href="../start/search-filter-categorize.md#tags">detailed documentation</a>.</p>-->
</td>
</tr>
</tbody>
</table>


### Förbättringar {#july-2023-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

<!--
**Journeys**

* You can now leverage API call responses in custom actions and orchestrate your journey based on these responses.-->
* En ny typ av systemvarning har införts. Du kan nu få meddelanden när en anpassad åtgärd misslyckas.
—>

**Kampanjer**

* Sammanhangsberoende händelser relaterade till kampanjer är nu tillgängliga för användning på menyn Sammanhangsberoende attribut i personaliseringsredigeraren.


**Publiker**

Målgruppsväljaren har förbättrats under resor eller kampanjer, med nya kolumner som visar målgruppernas ursprung och uppdateringsfrekvens.

I och med lanseringen av Audience Composition-portalen har Adobe Experience Platform och Adobe Journey Optimizer uppdaterat användningen av&quot;målgrupper&quot; och&quot;segment&quot; i systemet och dokumentationen.

* Målgrupp: En uppsättning personer, konton, hushåll eller andra enheter som delar gemensamma egenskaper och beteenden.
* Segmentdefinition: I Adobe Experience Platform används reglerna för att beskriva nyckelegenskaper eller beteenden hos en målgrupp. Termen kallades tidigare bara&quot;segment&quot;.

I Adobe Journey Optimizer och Adobe Experience Platform kommer man att se&quot;Segments&quot; ersatt med&quot;Audiences&quot; för att visa den nya vägen för målgruppsframtagning och målgruppshantering.

**API:er**

Autentisering av Adobe Journey Optimizer API:er - JWT-metoden för att generera åtkomsttoken har tagits bort. Alla nya integreringar måste skapas med autentiseringsmetoden OAuth Server-till-server. Adobe rekommenderar också att du migrerar dina befintliga integreringar till OAuth-metoden. [Läs mer](https://developer.adobe.com/journey-optimizer-apis/references/authentication/)


**Andra ändringar**

Journey Optimizer datamängdsexport till molnlagringsdestinationer är nu tillgänglig för alla kunder som en offentlig betaversion. Med den här funktionen kan du upprätta en direktanslutning till molnlagringsplatser för att kunna exportera innehållet i dina datauppsättningar. [Läs mer](../data/export-datasets.md)




