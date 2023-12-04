---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
topic: Content Management
role: User
level: Beginner, Intermediate
description: Versionsinformation om Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 299b34dec2e864fff5eb874b3fd491da80bc0c16
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 8%

---

# Versionsinformation {#release-notes}


>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="Nyheter?"
>abstract="**Adobe Journey Optimizer** levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen."

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen.

Tidigare versionsinformation finns i [den här sidan](release-notes-2023.md). Du kan även läsa [senaste dokumentationsuppdateringar](documentation-updates.md) sida för fler ändringar.

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver av sina senaste innovationer och förbättringar. Läs mer om de här ändringarna i [Versionsinformation för Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target="_blank"}.

![Nyhetsbrev](../assets/do-not-localize/nl-icon.png) Registrera dig för [Adobe Journey Optimizer kvartalsvis nyhetsbrev](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"} idag och få de senaste produktuppdateringarna, spännande historier, användningsexempel, tips och mycket annat levererat direkt till din inkorg varje kvartal.

## Versionsinformation oktober 2023 {#oct-rn-2023}

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
<p>Mer information finns i den <a href="../building-journeys/copy-to-sandbox.md">detaljerade dokumentationen</a>.</p>
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
<th><strong>MMS (Multimedia Message Service) i SMS</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med SMS-kanalen kan du nu förbättra kommunikationen genom att skicka MMS-meddelanden (Multimedia Message Service) som gör det möjligt att dela bilder, GIF eller videor med dina kunder. Observera att den här funktionen för närvarande endast är tillgänglig för Sinch.</p>
<img src="assets/do-not-localize/mms.gif"/>
<p>Mer information finns i den <a href="../sms/create-sms.md#mms-content">detaljerade dokumentationen</a>.</p>
</tr>
</tbody>
</table>

### Förbättringar {#oct-2023-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**Publiker**

* Nu kan ni rikta in er på målgrupper som överförts från en CSV-fil till resor och kampanjer. [Läs mer](../audience/about-audiences.md#segments-in-journey-optimizer)
* Nu kan ni inrikta er på målgrupper som skapats genom målgruppssammansättning och utnyttja anrikningsattribut i Journeys. [Läs mer](../building-journeys/read-audience.md)

>[!AVAILABILITY]
>
>Dessa funktioner är för närvarande tillgängliga som en privat beta.

<!--
**Spam scoring for emails**

* When simulating an email content, a new option enables you to check how your content performs against inboxes spam filtering. This feature is currently proposed to a set of customers only (Limited Availability), and available for the Email channel.-->

**Kampanjer**

<!--* You can now stop a live one-time campaign, make modifications and resume it again. This improvement is available in Beta.-->
* När ett fel inträffar inom en av era kampanjer visas nu en varningsikon i kampanjlistan tillsammans med kampanjens status. [Läs mer](../campaigns/modify-stop-campaign.md#statuses)

**Resor**

* Den längsta väntetid du kan ange är nu 29 dagar i stället för 30. Denna förbättring har införts för att förhindra att väntetider överskrider den 30 dagar långa transporttiden. Detta gäller

   * den **Tidsmängd** fältet i [vänteaktivitet](../building-journeys/wait-activity.md)
   * den **Vänteperiod för återinträde** in [egenskaper för resa](../building-journeys/journey-gs.md#entrance)
   * den **Vänta på** fält i timeout-definitionen för [evenemang](../building-journeys/general-events.md#events-specific-time).

<!--
**Consent in channel configuration**

* You can now select a marketing action at the channel surface level. When used in a surface, all consent policies associated with that marketing action are leveraged in order to respect the preferences of your customers.-->

**Beslutsledning**

* Flera etiketter som rör anbudsbegränsning i beslutsgränssnittet har uppdaterats. [Läs mer](../offers/offer-library/add-constraints.md#capping)

