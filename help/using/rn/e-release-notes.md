---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
description: Journey Optimizer tidiga versionsinformation
feature: Release Notes
hide: true
hidefromtoc: true
topic: Content Management
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 1cbc5512fe23db22eca4fe1a2cb512a154b01844
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 2%

---

# Tidig versionsinformation {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras i slutet av varje månad i [versionsinformationen](release-notes.md).

**Noteringar om tidig version nedan kan ändras utan föregående meddelande till releasedatum**. Länkar, skärmar och uppdaterad dokumentation publiceras i [versionsinformationen](release-notes.md) på releasedatum.

## Versionsinformation juli 2024 {#e-2024}

**Releasedatum**: 30-31 juli 2024

### Nya funktioner {#e-features}

Den här versionen innehåller de nya funktionerna som beskrivs nedan.

<table>
<thead>
<tr>
<th><strong>Arbetsflöde för IP Warmup (GA)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Om du skickar e-post till en helt ny IP-adress kan du nu enkelt utföra arbetsflöden för IP-värmare direkt från användargränssnittet. Adobe Journey Optimizer erbjuder ett standardiserat och effektivt sätt att värma upp era IP-adresser som följer de bästa metoderna för optimal leverans.</p>
<!--p>For more information, refer to the <a href="../configuration/ip-warmup-gs.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>SMS-kanal med valfri leverantör (Beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du konfigurera ytterligare SMS-leverantörer i Journey Optimizer, utöver standardleverantörerna Sinch, Infobip och Twilio.</p>
<!--p>For more information, refer to the <a href="../configuration/ip-warmup-gs.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>



<table>
<thead>
<tr>
<th><strong>Marketo Engage, anpassad åtgärd</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan ni integrera Adobe Journey Optimizer med Adobe Marketo Engage för att skapa era B2B-användningsfall. Från en resa kan ni med en ny anpassad åtgärd importera data till Marketo.</p>
<!--p>For more information, refer to the <a href="../configuration/ip-warmup-gs.md">detailed documentation</a>.</p-->
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
<!--p>For more information, refer to the <a href="../configuration/ip-warmup-gs.md">detailed documentation</a>.</p-->
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

* (Tillgänglighet: 8 juli) Du kan nu använda den avancerade uttrycksredigeraren när du konfigurerar en händelse, så att du kan definiera mer komplexa uttryck eller använda funktioner i händelse-ID-villkoret. [Läs mer](../event/about-creating.md#adv-exp-editor)

<!--* The `event-id` condition is now automatically filled during test mode. -->

**SMS-kanal**

* Du kan nu ändra befintliga SMS-konfigurationer.

**Kanal i appen**

* Uttrycksfragment är nu tillgängliga för kanalen i appen.

**Skjut kanalen**

* Nu kan du lägga till dina push-autentiseringsuppgifter för mobilprogram i Adobe Journey Optimizer kanalkonfigurationsinställningar. Du behöver inte längre skapa en appyta i Adobe Experience Platform Data Collection.

**Publiker**

* Målgrupper och attribut från målgruppssammansättning och anpassad uppladdning (CSV-fil) kan nu användas med hälso- och sjukvårdsskölden eller skölden för skydd av privatlivet och säkerheten.