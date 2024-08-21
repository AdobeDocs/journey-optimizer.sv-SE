---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
topic: Content Management
description: Versionsinformation om Adobe Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 068714fc2cae501fcc13a7f3112e5c1f3a3470bb
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 9%

---

# Versionsinformation {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="Nyheter?"
>abstract="**Adobe Journey Optimizer** levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen."

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen.

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver från de senaste innovationerna och förbättringarna. Läs mer om de här ändringarna i [Adobe Experience Platform versionsinformation](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target="_blank"}.

![Nyhetsbrev](../assets/do-not-localize/nl-icon.png) Registrera dig för [Adobe Journey Optimizer kvartalsnyhetsbrev](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"} idag och få de senaste produktuppdateringarna, spännande historier, användningsexempel, tips och mycket mer levererade direkt till din inkorg varje kvartal.

## Versionsinformation augusti 2024 {#8-2024}

**Releasedatum**: 20-21 augusti 2024

<!--
>[!CAUTION]
>
>**Early release notes below are subject to change without prior notice until the release date**. Links, screens and updated documentation are published at the release date.
>
-->

### Nya funktioner {#8-features}

Den här versionen innehåller de nya funktionerna som beskrivs nedan.

<!--table>
<thead>
<tr>
<th><strong>Guided Channel Setup</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Guided Channel Setup enables you to automate and validate channel setup in a unified experience, speeding up the process of getting started with Journey Optimizer. This new guided setup streamlines rapid channel configuration, ensuring all necessary resources are readily installed and working within Experience Platform, Journey Optimizer, and Data Collection. This enables marketing, product and data engineering teams to quickly begin with campaign and journey creation.</p>
</td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>Content Cards (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Content cards are a new digital messaging feature in Adobe Journey Optimizer that delivers personalized and engaging content directly within mobile apps and websites. Unlike traditional push notifications, Content Cards integrate seamlessly into the user interface, offering persistent, non-intrusive updates that enhance user interaction and experience.</p>
<p>This feature enables marketers to present relevant, rich media content to users, driving higher engagement and ensuring important messages are seen without disrupting the user journey.</p>
</br>
<p>Content card are currently only available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.</p>
</td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>Improved Channel Configurations</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The current channel surface capabilities have been enhanced for a consistent approach across all channels. You can now define, manage, and reuse these configurations for any of your channels, including Web, In-app messaging, or Code-based experience.</p>
<p><ul>
<li>Channel surfaces are now renamed to <strong>Channel configurations</strong></li>
<li>You can attach one or multiple marketing actions to enforce consent and data governance policies</li>
<li>Object level access control (OLAC) is now available for each channel configuration, allowing you to decide which of your users are allowed to create or use specific configurations</li>
<li>For some channels, you can create channel configurations that target multiple platforms. An example here would be an In-app messaging channel configuration that can target a web page, an iOS app and an Android app.</li>
</ul></p>
<p>For more information, refer to the <a href="../configuration/ip-warmup-gs.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table-->

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
<p>Mer information finns i den <a href="../action/marketo-engage.md">detaljerade dokumentationen</a>.</p>
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
<p>Fragmentglobala variabler förbättrar befintliga fragmentfunktioner för att förbättra effektiviteten vid återanvändning av innehåll och skriptanvändning. Fragment kan nu använda indatavariabler och skapa utdatavariabler som kan användas i kampanj- och reseinnehåll. Fragment kan använda indatavariabler, både i <a href="../personalization/use-expression-fragments.md">uttrycksfragment</a> och <a href="../email/use-visual-fragments.md">visuella fragment</a>. Ni kan använda dessa variabler för att personalisera ert meddelandeinnehåll och era parametrar i era kampanjer och resor.</p>
<p>Mer information finns i den <a href="../personalization/use-expression-fragments.md">detaljerade dokumentationen</a>.</p>
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


### Förbättringar {#8-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**Resor**

* I aktiviteten **Condition** anges nu **[!UICONTROL Time condition]** som standard per timme, från 00:00 till 12:00. [Läs mer](../building-journeys/condition-activity.md#time_condition)
* När du skapar dina resor visas nu varningar från knappen **Varningar** som anpassar sig till andra varningar och ger en konsekvent användarupplevelse. [Läs mer](../building-journeys/troubleshooting.md#checking-for-errors-before-testing)
* Zoomalternativen i reseverktygsfältet har förbättrats: zoomprocenten är nu synlig och du kan nu enkelt återställa zoomvärdet.

<!--**Audiences and Profiles**-->

<!--* The use of audiences from custom upload (CSV file) is now available for use with Privacy and Security Shield add-on.-->
<!--* When targeting a custom upload (CSV file) audience, you can now use attributes from the file in your campaigns and journeys. These attributes are available in the personalization editor, to personalize your messages, and the journey advanced expression editor.-->
<!--* The License usage dashboard now shows the count of Engageable Profiles. [Read more](../audience/license-usage.md)

**Push channel**

* You can now add your mobile application push credentials inside Adobe Journey Optimizer channel configuration settings. Creating an App surface in Adobe Experience Platform Data Collection is no longer required.
-->

### Andra ändringar {#changes}

**Rapportering**

* Den aktuella rapportupplevelsen kommer att tas ur bruk i oktober-versionen. Efter detta datum kommer den nya rapportupplevelsen att bli standard. Vi rekommenderar att du behärskar de nya funktionerna så att övergången blir smidig.

[Kom igång med Journey Optimizer nya rapporteringsgränssnitt](../reports/report-gs-cja.md)
