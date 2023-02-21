---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
description: Versionsinformation om Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 1565a61f2bd3b8168eaefc2e69b40c9949a0af23
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 6%

---

# Versionsinformation {#release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen.

Tidigare versionsinformation finns i [den här sidan](release-notes-2022.md). Du kan även läsa [senaste dokumentationsuppdateringar](documentation-updates.md) sida för fler ändringar.

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver av sina senaste innovationer och förbättringar. Läs mer om de här ändringarna i [Versionsinformation för Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target="_blank"}.

![Nyhetsbrev](../assets/do-not-localize/nl-icon.png) Registrera dig för [Adobe Journey Optimizer kvartalsvis nyhetsbrev](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"} idag och få de senaste produktuppdateringarna, spännande historier, användningsexempel, tips och mycket annat levererat direkt till din inkorg varje kvartal.


## Versionsinformation, februari 2023 {#feb-2023}

Det här avsnittet innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande. Detaljerad dokumentation finns tillgänglig på releasedatum.

Tillgänglighet: **22 februari 2023**

### Förbättringar {#feb-2023-improvements}

**Resor**

* The **Vänteperiod för återinträde** fältet har lagts till i reseegenskaperna. I det här fältet kan du definiera väntetiden innan du tillåter en profil att gå in på resan igen med en enda resa (med början från en händelse eller en segmentkvalificering). Detta förhindrar att resorna felaktigt aktiveras flera gånger för samma händelse. Som standard är fältet inställt på 5 minuter.

* Förbättringar har gjorts för **start- och slutdatum för resan**. Om du inte har angett något startdatum läggs det nu till automatiskt vid publiceringstidpunkten. För **Lässegment** på resor kan du nu lägga till ett slutdatum. Detta gör att profiler kan avslutas automatiskt när datumet nås.

**Administrering**

* **Tillåtelselista** - Du kan nu hämta tillåtelselista som en CSV-fil.

* **E-postyta** - Ytterligare en kontroll har lagts till i inställningarna för e-postytan: om MX-posten för den underdomän som används i **Svara på (e-postadress)** eller i **E-postadress för hemlig kopia** är inte korrekt konfigurerad. Det går inte att skapa e-postytan längre. Du måste ha den konfigurerad eller använda en annan.

* **E-postyta** - I avsnittet med parametrar för URL-spårning i inställningarna för e-postytan är begränsningen för **Värde** har uppdaterats från 255 tecken till 5 kB för kompatibilitet med Adobe Analytics tracking.

**Beslutshantering**

* **Placeringar** - Ytterligare parametrar har lagts till på skärmen där placeringar skapas. De gör det möjligt för er att styra om ett erbjudande kan dupliceras över flera ersättningar och ange om erbjudandets innehåll och metadata ska inkluderas i API-svaret.

* **URL-personalisering** - När du lägger till URL:er som innehåll till offerternas representationer kan du nu anpassa dessa URL:er med Uttrycksredigeraren.



## Version från januari 2023 {#jan-2023-release}

### Nya funktioner{#jan-2023-features}


<table>
<thead>
<tr>
<th><strong>Datahygien</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform har en serie funktioner för datthygien som gör att du kan hantera lagrade data genom att ta bort konsumentposter och datauppsättningar programmatiskt. Den här funktionen är nu tillgänglig för Adobe Journey Optimizer. </p>
<p>Du kan hantera dina datalager för att se till att informationen används som förväntat, uppdateras när felaktiga data behöver korrigeras och tas bort när organisationsprofiler anser det nödvändigt.</p>
<p><strong>Varning</strong> - Datahygienfunktionerna är för närvarande bara tillgängliga för organisationer som har köpt <strong>Hälsovårdssköld</strong> och <strong>Sköld för skydd av privatlivet och säkerheten</strong> tilläggserbjudanden.</p><p>Mer information finns i den <a href="../privacy/data-hygiene.md">detaljerade dokumentationen</a>.

</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Mallar för e-postinnehåll</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan ni skapa fristående innehållsmallar som kan utnyttjas på olika resor och i kampanjer för snabb återanvändning.</p> 
</p>
<img src="assets/do-not-localize/content-template.gif"/>
<p>Lär dig hur du skapar, redigerar och använder innehållsmallar i <a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/content-templates.html">den här videon</a>. Mer information finns i den <a href="../email/content-templates.md">detaljerade dokumentationen</a>.
</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar {#jan-2023-improvements}

**Resor**

<!--
* The **Re-entrance wait period** field has been added to the journey properties. This field allows you to define the time to wait before allowing a profile to enter the journey again in unitary journeys (starting with an event or a segment qualification). This prevents journeys from being erroneously triggered multiple times for the same event. By default the field is set to 5 minutes. [Learn more](../building-journeys/journey-gs.md#entrance)

* Improvements have been made for **journey start and end dates**. If you have not specified a start date, it is now automatically added at publication time. For **Read segment** journeys, you can now add an end date. This allows profiles to exit automatically when the date is reached. [Learn more](../building-journeys/journey-gs.md#dates)
-->

* När du lägger till en **Segmentkvalificering** eller **Lässegment** I en resa är namnutrymmet nu som standard förfyllt med det senast använda namnutrymmet. Se [Segmentkvalificering](../building-journeys/segment-qualification-events.md#about-segment-qualification) och [Lässegment](../building-journeys/read-segment.md#configuring-segment-trigger-activity) -avsnitt.

* I arbetsytan på resan finns en ny knapp i verktygsfältet som gör att du kan hämta en skärmbild av din resa.

**Email Designer**

* Du kan nu exportera e-postinnehållet från **Exportera HTML** -menyn. Exporterade filer är tillgängliga i en arkivfil (.ZIP).

**Administrering**

* Ett nytt underavsnitt ger rekommendationer om hur du skapar **Svara (e-post)** adressera och säkerställa en korrekt svarshantering. [Läs mer](../email/email-settings.md#reply-to-email)

* När du skapar eller redigerar **IP-pooler** visas nu de associerade PTR-posterna i IP-listan och när du hovrar över de valda IP-adresserna. [Läs mer](../configuration/ip-pools.md#create-ip-pool)

* När en IP-pool har valts på en kanal visas nu PTR-postinformation när du hovrar över IP-adresserna. [Läs mer](../email/email-settings.md#subdomains-and-ip-pools)

* Användargränssnittet för redigering [PTR-poster](../configuration/ptr-records.md#edit-ptr-record) och [körningsfält](../configuration/primary-email-addresses.md) har uppdaterats.

* Användargränssnittet för att skapa och redigera underdomäner har förbättrats. [Läs mer](../configuration/delegate-subdomain.md)

* Undertryckningslistan **Senaste överföringar** skärmen har uppdaterats. [Läs mer](../configuration/manage-suppression-list.md#recent-uploads)

**Kampanjer**

* Ett exempel på en cURL-begäran som tillåter körning av API-utlösta kampanjer genereras nu automatiskt och blir tillgänglig på kampanjskärmen. [Läs mer](../campaigns/api-triggered-campaigns.md)

<!--
**Decision management**

* Additional parameters have been added in placements creation screen. They allow you to control whether an offer can be duplicated across multiple placements, and to specify if the offer's content and metadata should be included in the API response. [Learn more](../offers/offer-library/creating-placements.md)-->

<!--* It is now possible to reset the offer capping counter on a daily, weekly or monthly basis. [Learn more](../offers/offer-library/add-constraints.md#capping)-->

**Personalisering**

* Det finns nya hjälpfunktioner: formatCurrency, charCodeAt, stringToDate, toString, formatNumber och toHexString. Funktionen toDateTimeOnly accepterar nu även fälttyperna string, date, long och int. [Läs mer](../personalization/functions/functions.md)
