---
title: Versionsinformation
description: Versionsinformation om Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: b31eb2bcf52bb57aec8e145ad8e94790a1fb44bf
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 10%

---

# Versionsinformation {#release-notes}

På den här sidan listas alla nya funktioner och förbättringar i [!DNL Journey Optimizer]. Du kan även läsa [senaste dokumentationsuppdateringar](documentation-updates.md) sida för fler ändringar.

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver av sina senaste innovationer och förbättringar. Läs mer om de här ändringarna i [Versionsinformation för Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target=&quot;_blank&quot;}.

![Nyhetsbrev](../assets/do-not-localize/nl-icon.png) Registrera dig för [Adobe Journey Optimizer kvartalsvis nyhetsbrev](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target=&quot;_blank&quot;} idag och få de senaste produktuppdateringarna, spännande historier, användningsexempel, tips och mycket annat levererat direkt till inkorgen varje kvartal.

## Version från juli 2022 {#july-2022-release}

### Nya funktioner

<table>
<thead>
<tr>
<th><strong>Nytt textbundet meddelandeflöde</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer har ett nytt flöde för att skapa meddelanden i Journeys. Med textbundna meddelanden sparar man mycket tid och effektiviserar arbetsflödet för att skapa och leverera e-post, push-meddelanden eller SMS i Journey Optimizer. Genom att ta bort meddelanden som ett separat steg och i stället göra dem redigerbara online som en del av en åtgärd på arbetsytan på resan, måste användarna klicka på färre knappar och navigera bland färre skärmar för att utforma och redigera innehållet.</p>
<img src="assets/do-not-localize/inline.gif"/>
<p>Mer information finns i den <a href="../messages/get-started-content.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Attributbaserad åtkomstkontroll (begränsad tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du identifiera schemafält med etiketter som definierar användningsområde för organisation eller data. Administratörer kan använda gränssnittet Behörigheter för att definiera åtkomstprinciper som omfattar XDM-schemafält och bättre hantera åtkomsten som ges till användare eller grupper av användare (interna, externa eller externa användare) samt hantera åtkomsten till specifika typer av data (dvs känsliga personuppgifter/SPD).</p>
<p>Attributbaserad åtkomstkontroll är för närvarande begränsad till vissa användare och kommer att distribueras till alla miljöer i en framtida version.</p>
<p>Mer information finns i den <a href="../administration/attribute-based-access.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Batchbeslutsjobb</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du köra batchbeslutsjobb från användargränssnittet, så att jag inte behöver någon utvecklare för att köra batchAPI-jobb och jag kan minska tiden som krävs för marknadsföring. Med det här nya gränssnittet kan du skapa jobb och hantera aktuella/tidigare jobb.</p>
<img src="assets/do-not-localize/batch.gif"/>
<p>Mer information finns i den <a href="../offers/batch-delivery.md">detaljerade dokumentationen.</p>
</td>
</tr>
</tbody>
</table>

<!--
<table>
<thead>
<tr>
<th><strong>Automatically use the best performing offer in your decisions (limited availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now use personalized optimization model systems in Decision Management. This new type of model allows you to optimize and personalize offers based on segments and offer performance.</p>
<p>The use of personalized optimization AI models is currently restricted to selected users, and will be deployed to all environments in a future release.</p>
<img src="assets/do-not-localize/ai-ranking.gif"/>
<p>For more information, refer to the detailed documentation.</p>
</td>
</tr>
</tbody>
</table>
-->

### Förbättringar

<!--
**Journeys**

* **Ending a journey** - In the journey canvas, the **End** activity has been removed from the palette. End tags are now added by default at the end of each path and cannot be removed. This improvement allows better reporting of where a customer dropped out of the journey, without any action from the user.
-->

**Meddelanden**

* Meddelandeförinställningar är nu **kanalytor**. [Läs mer](../configuration/channel-surfaces.md)

**Administrering**

* **PTR-postversion** - När du nu uppdaterar en PTR-post tar bearbetningstiden endast upp till 3 timmar. [Läs mer](../configuration/ptr-records.md#processing)

* **Tillåtelselista UI** - Nu kan du använda Journey Optimizer användargränssnitt för att lägga till nya e-postadresser eller domäner i tillåtelselista. [Läs mer](../configuration/allow-list.md)

* **Tillåtelselista logikuppdatering** - Nu gäller logiken i tillåtelselista så snart funktionen är aktiverad, även om listan är tom. [Läs mer](../configuration/allow-list.md#logic)

* **URL-spårningsparametrar** - Du kan nu använda uttrycksredigeraren för att konfigurera parametrar för URL-spårning i dina e-postytor (t.ex. meddelandeförinställningar). [Läs mer](../configuration/email-settings.md#url-tracking)

**offer decisioning**

* **Målgruppsstorlek** - En ny uppskattningskomponent för målgruppsstorlek visas nu i användargränssnittet när du skapar en beslutsregel, när du väljer ett segment eller en regel för att ange ett erbjudande eller när du lägger till ett segment eller en regel i ett beslutsomfång.