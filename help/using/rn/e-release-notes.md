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
source-git-commit: 1b37da28e6dbb03c8c76dd9a6637dfd95447eb7e
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 2%

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

<!-- table>
<thead>
<tr>
<th><strong>Composed audiences in journeys</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now use audiences created in composition workflows in your journeys to target customers. Once an audience composition is published, and the audience saved, use a Read Audience activity to select this new audience in your journey canvas.</p>
<img src="assets/channel-reports.png"/>
<p>For more information, refer to the <a href="../audience/get-started-audience-orchestration.md">detailed documentation</a>.</p>
</tr>
</tbody>
</table -->

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
* Nu kan ni inrikta er på målgrupper som skapats genom målgruppssammansättning och utnyttja anrikningsattribut i Journeys.

>[!AVAILABILITY]
>
>Dessa funktioner är för närvarande tillgängliga som en privat beta.

<!--
**Spam scoring for emails**

* When simulating an email content, a new option enables you to check how your content performs against inboxes spam filtering. This feature is currently proposed to a set of customers only (Limited Availability), and available for the Email channel.-->

**Varningar**

* När ett fel inträffar inom en av era kampanjer visas nu en varningsikon i kampanjlistan tillsammans med kampanjens status.

**Kampanjer**

* Nu kan du stoppa en direktkampanj, göra ändringar och återuppta den igen. Denna förbättring finns tillgänglig i Beta.

**Resor**

* Den längsta väntetid du kan ange är nu 29 dagar i stället för 30. Detta gäller

   * den **Tidsmängd** fältet i [vänteaktivitet](../building-journeys/wait-activity.md)
   * den **Vänteperiod för återinträde** in [egenskaper för resa](../building-journeys/journey-gs.md#entrance)
   * den **Vänta på** fält i timeout-definitionen för [allmän](../building-journeys/general-events.md#events-specific-time) och [reaktion](../building-journeys/reaction-events.md) händelser.

**Medgivande i kanalkonfiguration**

* Nu kan du välja en marknadsföringsåtgärd på kanalnivå. När de används på en yta används alla medgivandepolicyer som är kopplade till den marknadsföringsåtgärden för att ta hänsyn till kundernas önskemål.

**Beslutshantering**

* Flera etiketter som rör anbudsbegränsning i beslutsgränssnittet har uppdaterats.
