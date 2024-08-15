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
source-git-commit: 128a56b543f470bf967fd195fde73ff7b32b2a17
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 4%

---

# Tidig versionsinformation {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras i slutet av varje månad i [versionsinformationen](release-notes.md).

**Noteringar om tidig version nedan kan ändras utan föregående meddelande till releasedatum**. Länkar, skärmar och uppdaterad dokumentation publiceras i [versionsinformationen](release-notes.md) på releasedatum.

## Versionsinformation augusti 2024 {#e-2024}

**Releasedatum**: 20-21 augusti 2024

### Nya funktioner {#e-features}

Den här versionen innehåller de nya funktionerna som beskrivs nedan.


<table>
<thead>
<tr>
<th><strong>Inställningar för guidad kanal</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med Guided Channel Setup kan ni automatisera stegen för konfiguration av mobilkanaler i en enhetlig upplevelse och komma igång snabbare med Journey Optimizer. Denna installation underlättar snabb konfigurering av marknadsföringskanaler och säkerställer att alla nödvändiga resurser finns tillgängliga i Experience Platform, Journey Optimizer och Data Collection. På så sätt kan marknadsföringsteamet omedelbart börja med att skapa kampanjer och resor.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Innehållskort</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Innehållskortet är en ny funktion för digitala meddelanden i Adobe Journey Optimizer som levererar personaliserat och engagerande innehåll direkt inifrån mobilappar och webbplatser. Till skillnad från traditionella push-meddelanden integreras Content Cards smidigt i användargränssnittet med permanenta, icke-påträngande uppdateringar som förbättrar användarinteraktionen och upplevelsen.</p>
<p>Med den här funktionen kan marknadsförarna presentera relevant, multimediematerial för användarna, vilket ökar engagemanget och säkerställer att viktiga meddelanden syns utan att störa användarresan.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Förbättrade kanalkonfigurationer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>De nuvarande kanalens ytfunktioner har förbättrats för att alla kanaler ska fungera enhetligt. Du kan nu definiera, hantera och återanvända dessa konfigurationer för alla dina kanaler.</p>
<p><ul>
<li>Kanalytorna har nu bytt namn till <strong>Kanalkonfigurationer</strong></li>
<li>Från kanalkonfigurationslagret kan du nu skapa återanvändbara kanalkonfigurationer för alla kanaler, inklusive nu webben, meddelanden i appen eller kodbaserad upplevelse</li>
<li>Åtkomstkontroll på objektnivå (OLAC) är nu tillgänglig för varje kanalkonfiguration, så att du kan bestämma vilka användare som får skapa eller använda specifika konfigurationer</li>
<li>För vissa kanaler kan du skapa kanalkonfigurationer för flera plattformar. Ett exempel här är en konfiguration för meddelandekanal i appen som kan användas för en webbsida, en iOS-app och en Android-app.</li>
</ul></p>
<p>Mer information finns i den <a href="../configuration/ip-warmup-gs.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Anpassad åtgärd för Marketo Engage</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan ni integrera Adobe Journey Optimizer med Adobe Marketo Engage för att skapa era B2B-användningsfall. Från en resa kan ni med en ny anpassad åtgärd importera data till Marketo.</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Variabler i innehållsfragment</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Fragment kan nu använda indatavariabler, både i <a href="../personalization/use-expression-fragments.md">uttrycksfragment</a> och <a href="../email/use-visual-fragments.md">visuella fragment</a>. Ni kan använda dessa variabler för att personalisera ert meddelandeinnehåll och era parametrar i era kampanjer och resor.</p>
</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Arbetsflöde för IP-förstärkning</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Tillgänglighetsdatum: 13 aug</p>
<p>Om du skickar e-post till en helt ny IP-adress kan du nu enkelt utföra arbetsflöden för IP-värmare direkt från användargränssnittet. Adobe Journey Optimizer erbjuder ett standardiserat och effektivt sätt att värma upp era IP-adresser som följer de bästa metoderna för optimal leverans.</p>
<p>Mer information finns i den <a href="../configuration/ip-warmup-gs.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Extended personalization data - Beta</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now lookup and fetch data values within Adobe Experience Platform datasets, and use these values to build conditions in Adobe Journey Optimizer. You can leverage data from a lookup dataset when a relationship has been defined using an attribute inside of an array of objects. You can specify non-profile enabled datasets for lookup. Once enabled, you can use a profile attribute as a join key to the specified dataset to retrive further data for personalization.</p>
<p>This capability is currently available as a public beta.</p>
</td>
</tr>
</tbody>
</table-->

### Förbättringar {#e-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**Resor**

* I aktiviteten **Condition** är tidsvillkoret som standard inställt per timme, från 00:00 till 12:00. [Läs mer](../building-journeys/condition-activity.md#time_condition)
* När du skapar dina resor visas nu varningar i en nedrullningsbar lista som är anpassad efter kampanjvarningar och ger en enhetlig användarupplevelse. [Läs mer](../building-journeys/troubleshooting.md#checking-for-errors-before-testing)
* Zoomalternativen i reseverktygsfältet har förbättrats: zoomningsprocenten är nu synlig och du kan nu enkelt återställa zoomvärdet till 100 %.

**Publiker**

* Målgrupper från anpassad uppladdning (CSV-fil) kan nu användas med skölden för skydd av privatlivet och säkerheten.
* När ni riktar in er på en anpassad publik för överföring (CSV-fil) kan ni nu använda attribut från filen i era kampanjer och resor. Dessa attribut är tillgängliga i personaliseringsredigeraren, för att personalisera dina meddelanden och den avancerade uttrycksredigeraren.

<!--
**Push channel**

* You can now add your mobile application push credentials inside Adobe Journey Optimizer channel configuration settings. Creating an App surface in Adobe Experience Platform Data Collection is no longer required.-->

<!--* The `event-id` condition is now automatically filled during test mode. -->

<!--**SMS channel**

* You can now modify existing SMS configurations.-->

<!--
**In-app channel**

* Expression fragments are now available for the In-app channel.-->
