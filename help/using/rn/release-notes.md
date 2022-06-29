---
title: Versionsinformation
description: Versionsinformation om Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 108a7aab025aa92fab59c26d0bf5bf5339b81bb3
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 10%

---

# Versionsinformation {#release-notes}

På den här sidan listas alla nya funktioner och förbättringar i [!DNL Journey Optimizer]. Du kan även läsa [senaste dokumentationsuppdateringar](documentation-updates.md) sida för fler ändringar.

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver av sina senaste innovationer och förbättringar. Läs mer om de här ändringarna i [Versionsinformation för Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target=&quot;_blank&quot;}.

![Nyhetsbrev](../assets/do-not-localize/nl-icon.png) Registrera dig för [Adobe Journey Optimizer kvartalsvis nyhetsbrev](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target=&quot;_blank&quot;} idag och få de senaste produktuppdateringarna, spännande historier, användningsexempel, tips och mycket annat levererat direkt till inkorgen varje kvartal.

## Version från juni 2022 {#june-2022-release}

### Nya funktioner

<table>
<thead>
<tr>
<th><strong>Skicka SMS till användarna (begränsad tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du skapa, anpassa och skicka SMS i Journey Optimizer via en integrering med <b>Sinch</b> eller <b>Twilio</b>.</p>
<img src="assets/do-not-localize/SMS.gif"/>
<p>SMS-kanalen är för närvarande bara tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant om du vill ha mer information.</p>
<p>Lär dig hur du skapar och skickar ett SMS i det här <a href="../messages/create-sms.md">detaljerad dokumentation</a>.</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Hitta slagkraftigare bilder snabbare tack vare Adobe Stock integration</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Integreringspluginen för Adobe Stock och Adobe Journey Optimizer Email Designer ger kunderna ett enkelt sätt att navigera, licensiera och spara bilder för användning i meddelandeframställning. </br> Den nya <b>Hitta liknande Stock-foton</b> kan du också söka efter Stock-foton som matchar innehållet, färgen och kompositionen för dina bilder. </p>
<img src="assets/do-not-localize/stock-rn.gif"/>
<p>Mer information finns i den <a href="../design/stock.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Använd BCC för e-post för alla e-postmeddelanden</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du använda funktionen för hemlig kopia (Email BCC) för att lagra e-postmeddelanden som skickas av Adobe Journey Optimizer. Aktivera det här alternativet i dina e-postförinställningar så att alla e-postmeddelanden som skickas är blinda och kopieras till din BCC-adress.</p>
<img src="assets/do-not-localize/bcc-rn.gif"/>
<p>Mer information finns i den <a href="../configuration/bcc-email.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<!--<table>
<thead>
<tr>
<th><strong>Automatically use the best performing offer in your decisions</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now use personalized optimization model systems in Decision Management. This new type of model allows you to optimize and personalize offers based on segments and offer performance.</p>
<p>The use of personalized optimization AI models is currently restricted to selected users, and will be deployed to all environments in a future release.</p>
<img src="assets/do-not-localize/ai-ranking.gif"/>
<p>For more information, refer to the <a href="../offers/ranking/personalized-optimization-model.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>-->

<table>
<thead>
<tr>
<th><strong>Kopiera objekt mellan sandlådor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du återskapa upplevelser från en Journey Optimizer-sandlåda till en annan, till exempel från en icke-produktionssandlåda till en produktionssandlåda. Den nya funktionen kopierar en hel resa, inklusive alla objekt som resan är beroende av för att kunna köras korrekt, från en miljö till en annan. Förutom Resor kan du även kopiera andra komponenter, som erbjudanden, meddelanden, scheman, datauppsättningar, datakällor, händelser och åtgärder.</p>
<p>Mer information finns i den <a href="../building-journeys/copy-to-sandbox.md">detaljerade dokumentationen</a>.
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Dynamic Expression Builder</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now create conditional content blocks across different authoring services to personalize your content. In addition to the Personalization Expression Library, the Expression Editor provides a new Conditional Rule Builder to help you design and save your content blocks.</p>
<p>For more information, refer to the <a href="../building-journeys/read-segment.md#configuring-segment-trigger-activity">detailed documentation</a>.
</td>
</tr>
</tbody>
</table-->


### Förbättringar

**Beslutshantering**

* **Stöd för HTML och JSON-filer** - Nu kan du dra och släppa externa HTML- och JSON-filer från Adobe Experience Cloud resursbibliotek till erbjudanderepresentationsinnehållet. [Läs mer](../offers/offer-library/add-representations.md#html-json)


**E-post**

* **Spara som mall** - Du kan nu spara ett e-postinnehåll som en mall och återanvända det när du skapar andra meddelanden. [Läs mer](../design/email-templates.md)

<!--
**Journeys**

* **Ending a journey** - In the journey canvas, the **End** activity has been removed from the palette. End tags are now added by default at the end of each path and cannot be removed. This improvement allows better reporting of where a customer dropped out of the journey, without any action from the user.

-->

**Administrering**

<!--* **Allowed list in the UI** - You can now use the Journey Optimizer user interface to add new email addresses or domains to the allowed list.-->

* **URL-parametrar för förhandsspårning** - När du konfigurerar en meddelandeförinställning och definierar parametrar för URL-spårning, visas nu en dynamisk förhandsgranskning av den resulterande spårnings-URL:en. [Läs mer](../configuration/email-settings.md#url-tracking)

<!--* **Personalize tracking URL parameters** - You can now use the Expression Editor to configure URL tracking parameters in your message presets. [Learn more](../configuration/email-settings.md#url-tracking)-->

<!--
**Reporting**

* **Performance measurement** - A new **Reporting** tab is now available in the Administration > Configurations menu to set up reporting data sources.
-->
