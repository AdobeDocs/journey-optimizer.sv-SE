---
title: Versionsinformation 2022
description: Versionsinformation om Journey Optimizer 2022
source-git-commit: 4626237ce629dcaec8d20c89db3cb8b517671502
workflow-type: tm+mt
source-wordcount: '1069'
ht-degree: 8%

---

# Versionsinformation för 2022 {#release-notes-2022}

På den här sidan visas alla funktioner och förbättringar för [!DNL Journey Optimizer] släppt 2022.

Den senaste versionsinformationen är tillgänglig [på den här sidan](release-notes.md).

## Version från april 2022 {#april-2022-release}

### Förbättringar

**Landningssidor**

* **Nytt alternativ för kryssrutor för anmälan/avanmälan** - Nu kan du infoga en enda kryssruta för deltagande/avanmälan på prenumerationens landningssidor. Användarna måste markera kryssrutan för att godkänna (anmälan) och avmarkera den för att ta bort sitt samtycke (avanmälan). [Läs mer](../landing-pages/design-lp.md#define-lp-specific-content)

* **förifyllda landningssidor** - Det är nu möjligt att ge användarna möjlighet att förifylla landningssidans fält med profilinformation. [Läs mer](../landing-pages/create-lp.md#configure-primary-page)

**Beslutshantering**

* **Besluts-API på Edge** - Edge Decisioning API kan leverera och återge personaliserade erbjudanden som hanteras i Offer decisioning. Du kan skapa erbjudanden och andra relaterade objekt med hjälp av användargränssnittet (UI) eller API:erna för Offera decisioningen. [Läs mer](../offers/api-reference/offer-delivery-api/edge-decisioning-api.md)

**Administrering**

* **PTR-varaktighet** - Tidslängden för PTR-redigering är nu några timmar. [Läs mer](../configuration/ptr-records.md#processing)

**E-postdesign**

* **20 nya e-postmallar** kan nu utforma e-postinnehåll i Journey Optimizer.

**Användargränssnitt**

* **Sammanhangsberoende hjälp i Journey Optimizer UI** - Sammanhangsberoende hjälplänkar har lagts till på flera sidor i Journey Optimizer. Om den är tillgänglig klickar du på ikonen i för att visa en snabb beskrivning av den aktuella funktionen och få tillgång till relaterade artiklar.

**Integrering med Adobe Campaign Standard**

Som Adobe Campaign Standard-kund kan du nu skicka e-post, push-meddelanden och SMS med Journey Optimizer. Använd de nya inbyggda funktionerna för att utnyttja Campaign Standarden Transactional Messaging i Journey Optimizer.  [Läs mer](../action/acs-action.md)

<!--
### Fixes

* Fixed an issue which caused tracking reports not to be available as the `JourneyActionId` was not properly populated. PLATIR-19854, CJM-26006
* Fixed an error on business events which could block the journey publication. CJM-25931
* Fixed an issue which could prevent images in Email Designer templates from being displayed. PLATIR-18176, CJM-25008
-->

## Version från mars 2022 {#march-2022-release}

### Förbättringar

**Resor**

* För att undvika att det finns onödiga fält i det enhetliga profilschemat är händelseschemat för resan som standard inte längre aktiverat för profiler. Om det behövs kan du aktivera det. [Läs mer](../reports/sharing-overview.md)
* Nya steghändelser för exportjobb skickas nu av Journey Optimizer till Adobe Experience Platform. Exempel på frågor har lagts till i dokumentationen. [Läs mer](../reports/query-examples.md)

**Beslutshantering**

* Du kan nu ange om begränsningen av erbjudanden ska gälla för alla användare eller för en viss profil, och för alla placeringar eller per placering. [Läs mer](../offers/offer-library/add-constraints.md#capping)
* Med API:t för gruppbeslut kan organisationer använda offer decisioning-funktionalitet för alla profiler i ett visst segment i ett enda anrop. Erbjudandeinnehållet för varje profil i segmentet placeras i en AEP-datauppsättning där det är tillgängligt för anpassade batcharbetsflöden. [Läs mer](../offers/api-reference/offer-delivery-api/batch-decisioning-api.md)

**Administrering**

* Du kan nu aktivera/inaktivera länken för att avbryta prenumerationen i/från e-posthuvudet på den förinställda meddelandenivån och ange en anpassad URL för att avbryta prenumerationen på meddelandenivån. [Läs mer](../configuration/message-presets.md#list-unsubscribe)
* Tillåtelselista kan nu aktiveras och inaktiveras via [!DNL Journey Optimizer] gränssnitt för produktions- och icke-produktionssandlådor. [Läs mer](../reports/allow-list.md#enable-allow-list)

**Personalisering**

* Du kan nu spara mer än 40 personaliseringsuttryck i biblioteket. [Läs mer](../personalization/personalization-library.md)

## Version från februari 2022 {#feb-2022-release}

### Nya funktioner

<table>
<thead>
<tr>
<th><strong>Prenumerationslandsidor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du skapa och utforma landningssidor i Journey Optimizer och dirigera dina användare till onlineformulär där de kan välja att inte ta emot meddelanden eller prenumerera på en viss tjänst som ett nyhetsbrev.</p>
<p>Mer information finns i <a href="../landing-pages/create-lp.md">detaljerad dokumentation</a> och relaterade <a href="../landing-pages/lp-use-cases.md">exempel</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Nytt bibliotek för anpassningsuttryck</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer har nu ett bibliotek där du kan komma åt fördefinierade personaliseringsuttryck. Uttrycken konfigureras av Admin-användare.</p>
<p>Mer information finns i den <a href="../personalization/personalization-library.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


<!--table>
<thead>
<tr>
<th><strong>API Developer Site and Suppression API</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer provide RESTful APIs that allow you to programmatically perform key operations in your applications.
Developer SDK for Journey Optimizer is now available with the Suppression API (beta).</p>
<p>With this API, you can control your outgoing messages using suppression and allow lists.
The suppression list helps you with honoring the ISPs’ feedback to preserve sending IP reputation. The allow list helps you ensure that you send only to those email addresses which are in the allowed list, and typically to ensure that you don't send mails to customers from your development sandbox.</p>
<p>See <a href="https://developer.adobe.com/journey-optimizer-apis/">Adobe Journey Optimizer APIs</a>.</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>Skicka information för att spåra meddelanden med UTM-spårningsparametrar</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>I Journey Optimizer-meddelandeinnehåll kan du nu lägga till UTM-parametrar i länkarna: kan de tillhandahålla ytterligare data om länken och hjälpa dig att identifiera var och varför en person som klickat på länken.</p>
<p>Mer information finns i den <a href="../configuration/message-presets.md#configure-email-settings">detaljerade dokumentationen</a>.</p-->
</td>
</tr>
</tbody>
</table>

### Förbättringar

**Resor**

* För att optimera prestandan kommer alla resor i testläge som inte har utlösts på en vecka nu att återgå till statusen Utkast. [Läs mer](../building-journeys/testing-the-journey.md#important_notes)
* Integrationen mellan Journey Optimizer och Adobe Campaign Classic har optimerats för att förbättra prestandan. Standardkonfigurationen för begränsning har ändrats till 4 000 anrop/5 minuter.	[Läs mer](../action/acc-action.md#important-notes)

**Rapportering**

* Leveranser kan nu filtreras beroende på status:
   * I listan Meddelandekörning kan du nu utesluta korrektur från leveranslistan.
   * I dina Live-/Global-rapporter kan du välja att exkludera testhändelser.

* Nu kan du få åtkomst till rapporter om optimeringsdata för sändningstid: antalet personer som var omedelbart meddelandeansvariga och antalet personer som fick meddelanden med 1 timmes optimering, 2 timmars optimering osv.

<!--* Offer Decisioning reports are now available in Journey Optimizer. You can access the following metrics: Offers sent - Offers' impression rate - Offers' click rate - Breakdown report on Offers' sent.-->

**Beslutshantering**

* Rankningar och AI-rankning grupperas nu tillsammans i en enda flik.

## Version från januari 2022 {#january-2022-release}

### Nya funktioner

<table>
<thead>
<tr>
<th><strong>Journeys - Optimera din IP-uppgradering med villkor för profilliffor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>När en <strong>Villkor</strong> -aktivitet på en resa kan du nu definiera en profilövre gräns. Med den här nya villkorstypen kan du ange ett maximalt antal profiler för en resväg. När den här gränsen nås får de inmatade profilerna en alternativ sökväg. Detta gör att du kan öka volymen på dina leveranser (IP-förstärkning). Du kanske vill förbättra leveransen på en domän genom att dela körningen: skicka 1000 meddelanden dag 1, 2000 dag 2 osv.</p>
<p>Mer information finns i <a href="../building-journeys/condition-activity.md#profile_cap">detaljerad dokumentation</a> och relaterade <a href="../building-journeys/ramp-up-deliveries-uc.md">exempel</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Journeys - förbättring av läs segment</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The <strong>Inkrementell läsning</strong> har lagts till i återkommande <strong>Läs segment</strong> verksamhet. Med det här alternativet kan du bara rikta in dig på de personer som har gått in i segmentet sedan den senaste körningen av resan. Den första körningen riktar sig alltid till alla segmentmedlemmar.</p>
<p>Mer information finns i den <a href="../building-journeys/read-segment.md#configuring-segment-trigger-activity">detaljerade dokumentationen</a>.
</td>
</tr>
</tbody>
</table>

### Förbättringar

**Resor**

* Journey Optimizer steghändelser kan nu länkas till andra datauppsättningar i [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html). The **profileID** -fältet, i det inbyggda schemat för händelser i resan, definieras nu som ett identitetsfält. [Läs mer](../reports/sharing-overview.md#integration-cja)

**offer decisioning**

* När du uppdaterar ett erbjudande, ett reserverbjudande, en erbjudandesamling eller ett erbjudandebeslut som direkt eller indirekt hänvisas till i ett publicerat meddelande, återspeglas uppdateringarna nu automatiskt i motsvarande meddelande, utan att det behöver publiceras på nytt. [Läs mer](../offers/offers-e2e.md#insert-decision-in-email)

* När du simulerar vilka erbjudanden som ska levereras för en viss testprofil kan du nu ändra standardsimuleringsinställningarna och visa koden som motsvarar dina simuleringar som kan användas i felsökningssyfte. [Läs mer](../offers/offer-activities/simulation.md#define-simulation-settings)

**Administrering**

* Administratörer kan nu redigera PTR-poster med en CNAME-konfigurerad underdomän. [Läs mer](../configuration/ptr-records.md#edit-ptr-subdomains-cname)

**Personalisering**

* **Lägg till i favoriter** - För att förbättra effektiviteten i arbetet med personalisering har vi introducerat begreppet att spara favoriter. Genom att lägga till olika attribut på Favoriter-menyn får du snabb åtkomst till de objekt du använder mest. [Läs mer](../personalization/personalize.md#fav)
