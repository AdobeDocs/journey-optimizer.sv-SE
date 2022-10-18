---
title: Versionsinformation
description: Versionsinformation om Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 15dc5e2854358f7f200a54a3f06fa6e98f146efe
workflow-type: tm+mt
source-wordcount: '1101'
ht-degree: 9%

---

# Versionsinformation {#release-notes}

På den här sidan listas alla nya funktioner och förbättringar i [!DNL Journey Optimizer]. Du kan även läsa [senaste dokumentationsuppdateringar](documentation-updates.md) sida för fler ändringar.

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver av sina senaste innovationer och förbättringar. Läs mer om de här ändringarna i [Versionsinformation för Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target=&quot;_blank&quot;}.

![Nyhetsbrev](../assets/do-not-localize/nl-icon.png) Registrera dig för [Adobe Journey Optimizer kvartalsvis nyhetsbrev](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target=&quot;_blank&quot;} idag och få de senaste produktuppdateringarna, spännande historier, användningsexempel, tips och mycket annat levererat direkt till inkorgen varje kvartal.


## Oktober 2022 {#oct-2022-release}

### Förbättringar{#oct-2022-improvements}

**Resor**

* The **Tvinga återinträde vid upprepning** har lagts till i återkommande parametrar för lässegmentschema. Med det här alternativet kan du göra så att alla profiler som fortfarande finns i resan automatiskt avslutar den vid nästa körning. När alternativet är inaktiverat måste profilerna slutföra resan innan de kan återkomma i en annan förekomst. [Läs mer](../building-journeys/read-segment.md#configuring-segment-trigger-activity)

## September 2022-utgåvan{#sept-2022-release}

### Nya funktioner{#sept-2022-features}

<table>
<thead>
<tr>
<th><strong>Dynamiskt innehåll och ny villkorsstyrd regelgenererare</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du skapa dynamiskt innehåll för att anpassa innehållet i dina meddelanden baserat på villkorliga regler.</p> 
<p>Villkorliga regler skapas med en visuell regelbyggare i uttrycksredigeraren, där du kan lagra dem för ytterligare återanvändning under resor och kampanjer.</p>
<img src="assets/do-not-localize/dynamic-content.gif"/>
<p>Mer information finns i den <a href="../personalization/get-started-dynamic-content.md">detaljerade dokumentationen</a>.
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>API-utlösta kampanjer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Förutom befintliga schemalagda kampanjer kan ni nu skapa API-utlösta kampanjer i Journey Optimizer och anropa dem från ett externt system med API:er.</p>
<p>På så sätt kan du täcka olika behov av användnings- och transaktionsmeddelanden, som lösenordsåterställningar och OTP-token.</p>
<img src="assets/do-not-localize/api-triggered.gif"/>
<p>Mer information finns i den <a href="../campaigns/api-triggered-campaigns.md">detaljerade dokumentationen</a>.
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Dataåtkomstkontroll</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med attributbaserad åtkomstkontroll kan administratörer styra åtkomsten till specifika objekt baserat på vissa attribut. Dessa attribut kan läggas till i ett objekt, t.ex. etiketter. Från och med den här versionen kan administratörer även definiera användarroller som bara har åtkomst till specifika fält och/eller objekt, och data som motsvarar dessa fält och/eller objekt.</p>
<p> Attributbaserad åtkomstkontroll är för närvarande begränsad till vissa kunder och kommer att användas i alla miljöer i en framtida version.</p>
<img src="assets/do-not-localize/olac.gif"/>
<p>Mer information finns i den <a href="../administration/object-based-access.md">detaljerade dokumentationen</a>.
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Datastyrning och sekretess</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med styrningsramverket DULE (Data Usage Labeling and Enforcement) kan Journey Optimizer nu utnyttja Adobe Experience Platform styrningsprinciper för att förhindra att känsliga fält exporteras till tredjepartssystem via anpassade åtgärder. Om systemet identifierar ett begränsat fält i de anpassade åtgärdsparametrarna visas ett fel som hindrar dig från att publicera resan.</p>
<p>Användningen av etiketter och tvångsåtgärder för användning av data (DULE) är för närvarande begränsad till utvalda kunder och kommer att distribueras till alla miljöer i en framtida version.</p>
<p>Mer information finns i den <a href="../action/action-privacy.md">detaljerade dokumentationen</a>.
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Automated Consent Enforcement (profiler för automatiskt samtycke)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med Adobe Experience Platform kan ni enkelt införa och tillämpa marknadsföringspolicyer för att respektera kundernas samtycke. Samtyckesregler definieras i Adobe Experience Platform. I Journey Optimizer kan du tillämpa dessa medgivandeprinciper på dina anpassade åtgärder. Du kan till exempel definiera samtyckesprofiler för att utesluta kunder som inte har samtyckt till att ta emot e-post, push-meddelanden eller SMS-kommunikation.
<p>Automated Conforcement är för närvarande endast tillgängligt för organisationer som har köpt tillägget Healthcare Shield.</p>
<p>Mer information finns i den <a href="../action/consent.md">detaljerade dokumentationen</a>.
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Behörighetshantering</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer har stöd för att definiera användarroller och åtkomstprinciper för att hantera behörigheter för funktioner och objekt. Via <strong>Adobe Experience Cloud-behörigheter</strong>kan du skapa och hantera roller samt tilldela önskade resursbehörigheter för rollerna. Med behörigheter kan du också hantera etiketter, sandlådor och användare som är kopplade till en viss roll.</p>
<p> Användningen av behörigheter är för närvarande begränsad till utvalda kunder och kommer att distribueras till alla miljöer i en framtida version.</p>
<p>Mer information finns i den <a href="../administration/attribute-based-access.md">detaljerade dokumentationen</a>.
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Varningar och övervakning</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Som Journey Optimizer-användare kan du nu få åtkomst till systemvarningar via användargränssnittet för att få meddelanden när resorna inte fungerar som förväntat. Du kan visa tillgängliga aviseringar och prenumerera på dem. Den första varningen som är tillgänglig med den här versionen varnar dig om en Läs segment-aktivitet inte har bearbetat någon profil under den definierade tidsramen. Mer kommer nu när arbetsflödet är olåst.</p>
<p>Mer information finns i den <a href="../reports/alerts.md">detaljerade dokumentationen</a>.
</td>
</tr>
</tbody>
</table>


<!--table>
<thead>
<tr>
<th><strong>Data Hygiene</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform provides a suite of data hygiene capabilities that allow you manage your stored data through programmatic deletions of consumer records and datasets. This capability is now available for Adobe Journey Optimizer. </p>
<p>You can manage your data stores to ensure that information is used as expected, is updated when incorrect data needs fixing, and is deleted when organizational policies deem it necessary.</p>
<p><strong>Caution</strong> - Data Hygiene capabilities are currently only available for organizations that have purchased the Healthcare Shield add-on offering.</p>
<p>For more information, refer to the <a href="../building-journeys/read-segment.md#configuring-segment-trigger-activity">detailed documentation</a>.
</td>
</tr>
</tbody>
</table-->

### Förbättringar{#sept-2022-improvements}

**Resor**

* The **Enhetsdatauppsättning** finns nu som en färdig datauppsättning i Adobe Journey Optimizer. Den här uppslagsuppsättningen innehåller metadata som berikar informationen om spårnings- och feedbackdatauppsättningar. Detta hjälper er att förbättra era rapporter och frågor med mer begripliga data. [Läs mer](../start/datasets-query-examples.md#entity-dataset)
* Ett nytt skyddsräcke har lagts till för enhetsresor (med början vid en händelse eller en segmentkvalificering) för att förhindra att resor utlöses felaktigt flera gånger för samma händelse. Återinträde av profiler blockeras nu tillfälligt som standard i 5 minuter. [Läs mer](../start/guardrails.md#events-g)

**Administrering**

* När du aktiverar eller inaktiverar tillåtelselista visas nu en ny varning som detaljerar effekterna av varje åtgärd. [Läs mer](../configuration/allow-list.md#enable-allow-list)
* Användargränssnittet för att skapa kanalytor, skapa IP-pooler, hantera suppressionslistan och tillåtelselista samt konfigurera SMS-kanalen har uppdaterats.
* När du nu skapar den första kanalytan för en viss underdomän tar bearbetningstiden 10 minuter till 10 dagar och bara upp till 3 timmar för efterföljande ytor som använder den underdomänen. [Läs mer](../configuration/channel-surfaces.md#create-channel-surface)

<!--* Now when downloading the suppression list as a CSV file, you can choose the file that was previously generated, or generate a new file.-->
* Användargränssnittet för att skapa förinställningar för landningssidor och underdomäner för landningssidor har uppdaterats. [Läs mer](../configuration/lp-subdomains.md)

**Granskningskontroller**

* Med Journey Optimizer kan ni identifiera vilka åtgärder som användare i systemet utför på olika tjänster och funktioner, som kampanjer, resor, meddelanden, landningssidor osv. Granskningsloggresurser innehåller nu ändringar av olika andra åtgärder och registreras automatiskt när aktiviteten utförs. Läs mer [på den här sidan](../privacy/audit-logs.md).

**Arkiveringsstöd**

* Den nya **Enhetsdatauppsättning** innehåller ett mallfält som gör att du kan exportera format och struktur för skickade meddelanden i alla kanaler för arkiveringsändamål. [Läs mer](../configuration/archiving-support.md)

**Landningssidor**

* Nu kan du använda kontextuella data från en annan sida på samma landningssida. Om du t.ex. länkar en kryssruta till en prenumerationslista på den primära landningssidan kan du använda den prenumerationslistan på undersidan&quot;Tack&quot;. [Läs mer](../landing-pages/lp-content.md#use-primary-page-context)

<!--* When configuring the primary page, you can now create additional data to enable storing information when the landing page is being submitted. [Learn more](../landing-pages/lp-content.md#use-additional-data)-->

<!--* You can now use information that was submitted on a landing page to send communications to your customers. For example, if a user subscribes to a given subscription list, you can leverage that information to send an email recommending other subscription lists to that user.-->

### Andra ändringar{#sept-2022-other}

* Reseburst-läget har ersatts av Campaign-läget för snabb leverans. [Läs mer](../campaigns/create-campaign.md#rapid-delivery)
* För att förbättra prestandan kan Experience-fältgrupper inte längre användas i resor som börjar med ett Read-segment, en Segment-kvalificering eller en affärshändelseaktivitet. Denna ändring gäller endast för nya resor. Befintliga beteenden behåller det aktuella beteendet. [Läs mer](../start/guardrails.md#expression-editor)
* Begränsningen på 1 timme för schemalagda lässegmentsresor har tagits bort. Dessa resor kan nu genomföras utan dröjsmål.

