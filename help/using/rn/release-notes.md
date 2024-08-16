---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
topic: Content Management
description: Versionsinformation om Adobe Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 2fe963b43f08a99e000a916571f5b04a4a96c845
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 4%

---

# Versionsinformation {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="Nyheter?"
>abstract="**Adobe Journey Optimizer** levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen."

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen.

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver från de senaste innovationerna och förbättringarna. Läs mer om de här ändringarna i [Adobe Experience Platform versionsinformation](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target="_blank"}.

![Nyhetsbrev](../assets/do-not-localize/nl-icon.png) Registrera dig för [Adobe Journey Optimizer kvartalsnyhetsbrev](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"} idag och få de senaste produktuppdateringarna, spännande historier, användningsexempel, tips och mycket mer levererade direkt till din inkorg varje kvartal.

## Versionsinformation augusti 2024 {#e-2024}

**Releasedatum**: 20-21 augusti 2024

>[!CAUTION]
>
>**Noteringar för tidig version nedan kan ändras utan föregående meddelande till releasedatum**. Länkar, skärmar och uppdaterad dokumentation publiceras på releasedatum.
>

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
<p>Med Guided Channel Setup kan man automatisera och validera kanalkonfigurationen i en enhetlig upplevelse och därmed få igång Journey Optimizer snabbare. Denna nya guidade installation effektiviserar konfigurationen av kanaler så att alla nödvändiga resurser snabbt kan installeras och användas i Experience Platform, Journey Optimizer och datainsamling. På så sätt kan marknadsförings-, produkt- och datateknikteam snabbt börja med att skapa kampanjer och resor.</p>
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
<p>De nuvarande kanalens ytfunktioner har förbättrats för att alla kanaler ska fungera enhetligt. Nu kan du definiera, hantera och återanvända dessa konfigurationer för alla kanaler, inklusive webb, meddelanden i appen eller kodbaserad upplevelse.</p>
<p><ul>
<li>Kanalytorna har nu bytt namn till <strong>Kanalkonfigurationer</strong></li>
<li>Du kan bifoga en eller flera marknadsföringsåtgärder för att tillämpa policyer för samtycke och datastyrning</li>
<li>Åtkomstkontroll på objektnivå (OLAC) är nu tillgänglig för varje kanalkonfiguration, så att du kan bestämma vilka användare som får skapa eller använda specifika konfigurationer</li>
<li>För vissa kanaler kan du skapa kanalkonfigurationer för flera plattformar. Ett exempel här är en konfiguration för meddelandekanal i appen som kan användas för en webbsida, en iOS-app och en Android-app.</li>
</ul></p>
<!--p>For more information, refer to the <a href="../configuration/ip-warmup-gs.md">detailed documentation</a>.</p-->
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


### Förbättringar {#e-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**Resor**

* I aktiviteten **Condition** är tidsvillkoret som standard inställt per timme, från 00:00 till 12:00. [Läs mer](../building-journeys/condition-activity.md#time_condition)
* När du skapar dina resor visas nu varningar i en nedrullningsbar lista som är anpassad efter kampanjvarningar och ger en enhetlig användarupplevelse. [Läs mer](../building-journeys/troubleshooting.md#checking-for-errors-before-testing)
* Zoomalternativen i reseverktygsfältet har förbättrats: zoomningsprocenten är nu synlig och du kan nu enkelt återställa zoomvärdet till 100 %.

**Publiker**

* Målgrupper från anpassad uppladdning (CSV-fil) kan nu användas med tillägget Privacy och Security Shield.
* När ni riktar in er på en anpassad publik för överföring (CSV-fil) kan ni nu använda attribut från filen i era kampanjer och resor. Dessa attribut är tillgängliga i personaliseringsredigeraren, för att personalisera dina meddelanden och den avancerade uttrycksredigeraren.

## Versionsinformation juli 2024 {#24-7-2024}

**Releasedatum**: 30-31 juli 2024

### Nya funktioner {#27-4-features}

Den här versionen innehåller de nya funktionerna som listas nedan.

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
<img src="assets/do-not-localize/byo_sms.gif"/>
<p>Mer information finns i den <a href="../sms/sms-configuration-custom.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Federated Audience Composition (begränsad tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Federated Audience Composition är nu tillgängligt i Adobe Journey Optimizer. Det gör det möjligt för företag att sammanställa data för bättre användning i olika användningsfall. Med detta nya tillvägagångssätt, som Adobe Real-time Customer Data Platform- och/eller Adobe Journey Optimizer-användare, kan ni federera datauppsättningar direkt från ert befintliga datalager för att skapa och berika Adobe Experience Platform målgrupper och attribut i ett och samma system.</p>
<p>Mer information finns i den <a href="https://experienceleague.adobe.com/en/docs/federated-audience-composition/using/home"  target="_blank">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar {#27-4-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**Resor**

* (Tillgänglighetsdatum: 8 juli) **Avancerad uttrycksredigerare i konfiguration av resthändelser** - Du kan nu utnyttja den avancerade uttrycksredigeraren när du konfigurerar en händelse, så att du kan definiera mer komplexa uttryck eller använda funktioner i händelse-ID-villkoret. [Läs mer](../event/about-creating.md#adv-exp-editor)

