---
title: Versionsinformation
description: Versionsinformation om Journey Optimizer
source-git-commit: cd38b6ec9be0417f5c65e37805c0e7b072d1cb96
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 13%

---


# Versionsinformation {#release-notes}

På den här sidan listas alla nya funktioner och förbättringar i [!DNL Journey Optimizer]. Du kan även läsa de senaste [dokumentationsuppdateringarna](documentation-updates.md).

## juliversion 2021 {#july-2021-release}

<table>
<thead>
<tr>
<th><strong>Utnyttja schemarelationer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med Adobe Experience Platform kan du definiera relationer mellan scheman för att kunna använda en datauppsättning som en uppslagstabell för en annan. [!DNL Journey Optimizer] kan nu utnyttja data från ett länkat schema.</p>
<p>Dessa fält är tillgängliga i enhetlig händelsekonfiguration, resevillkor, meddelandepersonalisering och anpassad åtgärdspersonalisering.</p>
<p>Mer information finns i den <a href="event/experience-event-schema.md#leverage_schema_relationships">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Tillåtelselista</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Du kan nu definiera en specifik sändningssäker lista på sandlådenivå för att ha en säker miljö för testningsändamål. I icke-produktionssituationer, där misstag kan inträffa, ser tillåtelselista till att du inte löper någon risk att skicka ut oönskade meddelanden till dina kunder. Den här funktionen aktiveras med hjälp av API:er för undertryckning.</p>
<p>Mer information finns i den <a href="allow-list.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar

* **Resor**
   * Den totala begränsningsfrekvensen för alla lässegment som körs samtidigt i samma sandlåda är begränsad till 17 000 meddelanden per sekund. [Läs mer](building-journeys/read-segment.md#configuring-segment-trigger-activity)
   * Fältet **Cachevaraktighet** har tagits bort från konfigurationspanelen för datakällan. [Läs mer](datasource/about-data-sources.md)
   * För externa datakällor definieras nu en begränsningsregel på 15 anrop per sekund automatiskt. [Läs mer](configuration/external-systems.md#capping)
   * För direktresor visas nu publiceringsdatumet och namnet på den användare som publicerade resan på skärmen för reseegenskaper. [Läs mer](building-journeys/journey-gs.md#change-properties)
   * På skärmen för reselistan har filtret för resetyp lagts till. [Läs mer](user-interface.md#section_lgm_hpz_pgb)
   * Parametern **[!UICONTROL Throttling rate]** har lagts till i Läs-segmentsaktiviteten. [Läs mer](building-journeys/read-segment.md#configuring-segment-trigger-activity)

* **Förhandsgranska och testa**
   * Identitet och namnutrymme visas nu på skärmen **[!UICONTROL Preview]**. [Läs mer](preview.md#preview-your-messages)
   * Antalet testmeddelanden för korrektur är nu begränsat till 10.
   * Tecken som tillåts för **ämnesradsprefixet** i korrektur är nu begränsade. [Läs mer](preview.md#send-proofs)

* **Redigerare för anpassningsuttryck**
   * Hjälplistan har bytt namn och ordnats om.

### Korrigeringar

* Korrigerade ett problem som medförde att dubblettmeddelanden levererades för batche-postleverans.
* Händelser genereras nu i enlighet med detta när e-postutskick inte utförs när återförsöksperioden är slut.
* Ett problem där IP-information saknades på PTR-inspelningsskärmen har korrigerats.
* Lokalisering i erbjudandefältet i Expression Editor är nu implementerat.
* Felaktigt avstånd i informationspopup-fönster har korrigerats.
