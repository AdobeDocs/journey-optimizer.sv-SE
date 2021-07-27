---
title: Versionsinformation
description: Versionsinformation om Journey Optimizer
source-git-commit: 4d3352184aac7fe19096c21650982e29506f2bff
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 14%

---


# Versionsinformation {#release-notes}

På den här sidan visas alla nya funktioner och förbättringar för Journey Optimizer.
Du kan även läsa de senaste [dokumentationsuppdateringarna](documentation-updates.md).

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
<p>Med Adobe Experience Platform kan du definiera relationer mellan scheman för att kunna använda en datauppsättning som en uppslagstabell för en annan. Journey Optimizer kan nu utnyttja data från ett länkat schema.</p>
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
<p>Nu kan du definiera en specifik sändningssäker lista på sandlådenivå för att undvika att skicka oönskade e-postmeddelanden till dina mottagare i en testmiljö, till exempel.
</p>
<p>Mer information finns i den <a href="allow-list.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar

* Den totala begränsningsfrekvensen för alla lässegment som körs samtidigt i samma sandlåda är begränsad till 17 000 meddelanden per sekund. [Läs mer](building-journeys/read-segment.md#configuring-segment-trigger-activity)
* Fältet **Cachevaraktighet** har tagits bort från konfigurationspanelen för datakällan. [Läs mer](datasource/about-data-sources.md)
* För externa datakällor definieras nu en begränsningsregel på 15 anrop per sekund automatiskt. [Läs mer](configuration/external-systems.md#capping)
* För direktresor visas nu publiceringsdatumet och namnet på den användare som publicerade resan på skärmen för reseegenskaper. [Läs mer](building-journeys/journey-gs.md#change-properties)
* På skärmen för reselistan har filtret för resetyp lagts till. [Läs mer](user-interface.md#section_lgm_hpz_pgb)
* Parametern [!UICONTROL Throttling rate] har lagts till i Läs-segmentsaktiviteten. [Läs mer](building-journeys/read-segment.md#configuring-segment-trigger-activity)
