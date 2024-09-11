---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
topic: Content Management
description: Versionsinformation om Adobe Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: b1f23144d996e152018519b540d70f45b7c58695
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 8%

---

# Versionsinformation {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="Nyheter?"
>abstract="**Adobe Journey Optimizer** levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen."

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen.

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver från de senaste innovationerna och förbättringarna. Läs mer om de här ändringarna i [Adobe Experience Platform versionsinformation](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target="_blank"}.

![Nyhetsbrev](../assets/do-not-localize/nl-icon.png) Registrera dig för [Adobe Journey Optimizer kvartalsnyhetsbrev](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"} idag och få de senaste produktuppdateringarna, spännande historier, användningsexempel, tips och mycket mer levererade direkt till din inkorg varje kvartal.

## September-uppdateringar {#9-2024}

<table>
<thead>
<tr>
<th><strong>AI Assistant - Content Accelerator </strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>När du har skapat och skräddarsytt ditt budskap går du ett steg längre med AI Assistant i Journey Optimizer for Content Acceleration. Nu kan du använda AI-assistenten för att optimera budskapets effekt genom att experimentera med olika huvudtitlar och bilder. Varje variant hanteras som en unik behandling för att mäta och jämföra vilken titel som effektivt genererar fler klick.</p>
<p>Fördjupa dig i en praktisk upplevelse med <a href="https://experienceleague.adobe.com/en/apps/journey-optimizer/ai-assistant-content-accelerator">vår förhandsvisning av aktiva funktioner</a>, som är utformad för att du först ska kunna utforska dess funktioner och till fullo förstå dess funktioner.</a>.</p>
<p>Mer information finns i den <a href="../content-management/gs-generative.md">detaljerade dokumentationen</a>.</p>
<img src="assets/do-not-localize/ai-content.gif"/>
<p>Tillgänglighetsdatum: 12 sept</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Inställningar för guidad kanal</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med Guided Channel Setup kan man automatisera och validera kanalkonfigurationen i en enhetlig upplevelse och därmed få igång Journey Optimizer snabbare. Denna nya guidade installation effektiviserar konfigurationen av kanaler så att alla nödvändiga resurser snabbt kan installeras och användas i Experience Platform, Journey Optimizer och datainsamling. På så sätt kan marknadsförings-, produkt- och datateknikteam snabbt börja med att skapa kampanjer och resor.</p>
<p>Mer information finns i den <a href="../configuration/set-mobile-config.md">detaljerade dokumentationen</a>.</p>
<img src="assets/do-not-localize/guided-setup.gif"/>
<p>Tillgänglighetsdatum: 3 september</p>
</br>
</td>
</tr>
</tbody>
</table>

**Resor**

(Tillgänglighetsdatum: 10 sep) **Återförsöksfunktion** - Återförsök används nu som standard på målgruppsinställda resor (med början från **Läs målgrupp** eller en **affärshändelse**) när exportjobbet hämtas. Om ett fel inträffar när exportjobbet skapas görs nya försök var 10:e minut (max 1 timme). Efter det kommer vi att betrakta det som ett misslyckande. Dessa typer av resor kan därför utföras upp till en timme efter den schemalagda tiden. [Läs mer](../building-journeys/read-audience.md#retries)

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

<!--
<table>
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

<table>
<thead>
<tr>
<th><strong>Förbättrade kanalkonfigurationer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>De nuvarande kanalens ytfunktioner har förbättrats för att alla kanaler ska fungera enhetligt. Nu kan du definiera, hantera och återanvända dessa konfigurationer för alla kanaler, inklusive webb, meddelanden i appen eller kodbaserad upplevelse.</p>
<p><ul>
<li>Kanalytorna har nu bytt namn till <strong>Kanalkonfigurationer</strong></li>
<li>Du kan bifoga en eller flera marknadsföringsåtgärder för att tillämpa policyer för samtycke och datastyrning</li>
<li>Åtkomstkontroll på objektnivå (OLAC) är nu tillgänglig för varje kanalkonfiguration, så att du kan bestämma vilka användare som får skapa eller använda specifika konfigurationer</li>
<li>För vissa kanaler kan du skapa kanalkonfigurationer för flera plattformar. Ett exempel här är en konfiguration för meddelandekanal i appen som kan användas för en webbsida, en iOS-app och en Android-app.</li>
</ul></p>
<p>Mer information finns i den <a href="../configuration/channel-surfaces.md">detaljerade dokumentationen</a>.</p>
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
<!--* The License usage dashboard now shows the count of Engageable Profiles. [Read more](../audience/license-usage.md)-->

**Skjut kanalen**

* Nu kan du lägga till dina push-autentiseringsuppgifter för mobilprogram i Adobe Journey Optimizer kanalkonfigurationsinställningar. Du behöver inte längre skapa en appyta i Adobe Experience Platform Data Collection.

### Andra ändringar {#changes}

**Rapportering**

* Den aktuella rapportupplevelsen kommer att tas ur bruk i oktober-versionen. Efter detta datum kommer den nya rapportupplevelsen att bli standard. Vi rekommenderar att du behärskar de nya funktionerna så att övergången blir smidig.

[Kom igång med Journey Optimizer nya rapporteringsgränssnitt](../reports/report-gs-cja.md)

* Nya användningsfall har lagts till i den nya rapportupplevelsen:

   * Skapa anpassade beräknade mätvärden direkt i dina rapporter.
   * Skapa en publik utifrån rapportdata.
   * Använd verktyget för experimentell analys för att enkelt skapa tabeller och visualiseringar från dina valda **[!UICONTROL Dimensions]** och **[!UICONTROL Metrics]**.

  Mer information finns i den [detaljerade dokumentationen](../reports/report-cja-manage.md).
