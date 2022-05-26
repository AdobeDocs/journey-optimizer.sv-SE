---
title: Versionsinformation
description: Versionsinformation om Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: dd60e576aaded21efd9718341d1c4f26267ae001
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 11%

---

# Versionsinformation {#release-notes}

På den här sidan listas alla nya funktioner och förbättringar i [!DNL Journey Optimizer]. Du kan även läsa [senaste dokumentationsuppdateringar](documentation-updates.md) sida för fler ändringar.

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver av sina senaste innovationer och förbättringar. Läs mer om de här ändringarna i [Versionsinformation för Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target=&quot;_blank&quot;}.

![Nyhetsbrev](../assets/do-not-localize/nl-icon.png) Registrera dig för [Adobe Journey Optimizer kvartalsvis nyhetsbrev](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target=&quot;_blank&quot;} idag och få de senaste produktuppdateringarna, spännande historier, användningsexempel, tips och mycket annat levererat direkt till inkorgen varje kvartal.

## Version från maj 2022 {#may-2022-release}

### Nya funktioner

<!--table>
<thead>
<tr>
<th><strong>Message Frequency Rules</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now set cross-channel business rules that will automatically exclude over-solicited profiles from messages and actions.</p>
<img src="assets/frequency-rn.gif"/>
<p>For more information, refer to the <a href="../configuration/frequency-rules.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table-->


<table>
<thead>
<tr>
<th><strong>BCC för e-post</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du använda funktionen för hemlig kopia (Email BCC) för att lagra e-postmeddelanden som skickas av Adobe Journey Optimizer. Aktivera det här alternativet i dina e-postförinställningar så att alla e-postmeddelanden som skickas är blinda och kopieras till din BCC-adress.</p>
<img src="assets/bcc-rn.gif"/>
<p>Mer information finns i den <a href="../configuration/email-settings.md#bcc-email">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


<!--table>
<thead>
<tr>
<th><strong>Decision Management - AI Ranking auto-optimization model</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now use trained model systems in Decision Management. This new capability ranks offers to display for a given profile.</p>
<img src="assets/optimization.gif"/>
<p>For more information, refer to the <a href="../offers/offer-activities/configure-offer-selection.md#use-ranking-strategy">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>Attribute-based Access Control (ABAC)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Permission management in Journey Optimizer has been extended to data access. You can now manage data access for specific teams or groups of users (i.e. internal, external, 3rd parties) ​and manage access to specific types of data (i.e. Sensitive Personal Data/SPD).</p>
<p>This capability is available for a limited set of customers.</p>
<p>For more information, refer to the <a href="../landing-pages/create-lp.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>Journey Optimizer granskningsloggar</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du övervaka åtgärder som utförs av användare på Adobe Journey Optimizer-resurser.</p>
<img src="assets/audit-rn.gif"/>
<p>Mer information finns i den <a href="../reports/audit-logs.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar

**Personalisering**

* **Ny hjälpfunktion för dolda tecken** - `mask` hjälpfunktionen gör att du kan ersätta en del av en sträng med&quot;X&quot;-tecken. [Läs mer](../personalization/functions/string.md#mask)

**Landningssidor**

* **Landningssidor utan formulär** - Nu kan du skapa och publicera en landningssida som inte innehåller något formulär och som inte kräver någon åtgärd från besökarna.
* **Mallar för landningssidor** - Du kan nu spara en landningssida som en mall och återanvända den när du skapar andra landningssidor. [Läs mer](../landing-pages/lp-templates.md)
* **Tillbaka till den primära sidan** - Du kan nu lägga till en länk till den primära sidan från en undersida på samma landningssida.
* **Anpassat JavaScript-stöd** - Du kan nu lägga till egen JavaScript-kod i innehållet på landningssidan för att utföra avancerad formatering eller lägga till anpassade beteenden på landningssidorna.	[Läs mer](../landing-pages/lp-custom-js.md)

<!--**Decision management**

* **HTML and JSON files support** - You can now drag and drop external HTML and JSON files from the AEM repository into the offer representation content.-->

**Resor**

* **Lässegment** - Enbildsresor för Läs segment har flyttats till slutstatus 30 dagar efter det att resan körts. För schemalagda läs-segment är det 30 dagar efter körningen av den sista förekomsten. [Läs mer](../building-journeys/read-segment.md)
* **Uttrycksredigerare** - [limit](../building-journeys/functions/functionlimit.md) -funktionen har lagts till så att du kan begränsa antalet objekt i en lista. The [sortera](../building-journeys/functions/functionsort.md) kan du nu sortera ut ett listobjekt. Stödet för listObject har också lagts till i [urskilja](../building-journeys/functions/functiondistinct.md) och [clearWithNull](../building-journeys/functions/functiondistinctwithnull.md) funktioner.
