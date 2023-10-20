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
source-git-commit: bf85321377568aae1d28de8cd494d91d9eac601e
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 4%

---

# Tidig versionsinformation {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i [versionsinformation](release-notes.md).

Noteringarna nedan kan ändras utan föregående meddelande fram till releasedatum. Länkar, skärmar och uppdaterad dokumentation publiceras i [versionsinformation](release-notes.md), på releasedatum.

## Versionsinformation oktober 2023 {#oct-rn-2023}

**Releasedatum**: 25-26 okt 2023

### Nya funktioner{#oct-2023-features}

Den här versionen innehåller de nya funktionerna som listas nedan.

<table>
<thead>
<tr>
<th><strong>Verktyg i sandlådan</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med sandlådeverktygen kan du kopiera objekt över flera sandlådor genom att utnyttja export och import av paket. Ett paket kan bestå av ett eller flera objekt. Alla objekt som ingår i ett paket måste komma från samma sandlåda.</p>
<!--img src="../data/assets/dataset-export-setup.png"-->
<!--p>For more information, refer to the <a href="../audience/get-started-audience-orchestration.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Sammansatta målgrupper under resor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan ni använda målgrupper som skapats i arbetsflöden för dispositioner på era resor för att rikta in er på kunderna. När en målgruppskomposition har publicerats och målgruppen sparats kan du använda aktiviteten Läs målgrupp för att välja den nya målgruppen på arbetsytan.</p>
<!--img src="assets/channel-reports.png"/-->
<p>Mer information finns i den <a href="../audience/get-started-audience-orchestration.md">detaljerade dokumentationen</a>.</p>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>MMS (Multimedia Message Service) i SMS (Beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med SMS-kanalen kan du nu förbättra kommunikationen genom att skicka MMS-meddelanden (Multimedia Message Service) som gör det möjligt att dela bilder, GIF eller videor med dina kunder. Observera att den här funktionen för närvarande endast är tillgänglig i Beta med Sinch.</p>
<!--img src="assets/channel-reports.png"/-->
<!--p>For more information, refer to the <a href="../in-app/get-started-in-app.md">detailed documentation</a>.</p-->
</tr>
</tbody>
</table>

### Förbättringar {#oct-2023-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**Publiker**

* Nu kan ni rikta in er på målgrupper som överförts från en CSV-fil till resor och kampanjer.

**Spam-poäng för e-post**

* När du simulerar ett e-postinnehåll kan du med ett nytt alternativ kontrollera hur innehållet fungerar mot skräppostfiltrering i inkorgar. Den här funktionen är för närvarande endast avsedd för en uppsättning kunder (begränsad tillgänglighet) och tillgänglig för e-postkanalen.

**Varningar**

* Nu finns nya varningsmeddelanden om Journey Optimizer-kampanjer i **Varningar** -menyn.

**Kampanjer**

* Nu kan du stoppa en direktkampanj, göra ändringar och återuppta den igen. Denna förbättring finns tillgänglig i Beta.

**Resor**

* Den maximala varaktighet som du kan definiera i aktiviteten Vänta är nu 29 dagar i stället för 30.

**Landningssidor**

* När du använder landningssidans formulärkomponent kan du nu lägga till ett e-postfält med egna specifika alternativ.

**Medgivande i kanalkonfiguration**

* Nu kan du välja en marknadsföringsåtgärd på kanalnivå. När de används på en yta används alla medgivandepolicyer som är kopplade till den marknadsföringsåtgärden för att ta hänsyn till kundernas önskemål.
