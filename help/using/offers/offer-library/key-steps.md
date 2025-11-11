---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: Viktiga steg för att skapa ett erbjudande
description: Upptäck de viktigaste stegen som krävs för att skapa ett erbjudande
badge: label="Äldre" type="Informative"
feature: Decision Management
topic: Integrations
role: User
level: Intermediate
exl-id: e375fd3a-b10d-45f4-a95b-ceb48116e841
version: Journey Orchestration
source-git-commit: d6a9a8a392f0492aa6e4f059198ce77b6b2cd962
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 1%

---

# Viktiga steg för att skapa och hantera erbjudanden {#key-steps-to-manage-offers}

Nedan beskrivs de viktigaste stegen för att skapa, konfigurera och hantera erbjudanden samt för att använda dem i ett beslut.

![](../assets/offer-create-manage-process.png)

Ett fullständigt exempel från början till slut som visar hur du konfigurerar erbjudanden får du om du använder dem i ett beslut och använder det här beslutet i ett e-postmeddelande. Läs [den här sidan](../offers-e2e.md).

## Skapa komponenter {#create-components}

Innan du börjar skapa erbjudanden måste du definiera flera komponenter som du ska använda i dina erbjudanden.

1. [Skapa placeringar](creating-placements.md), som är behållare som ska användas för att visa upp dina erbjudanden. Du kan till exempel skapa en placering som är dedikerad till erbjudanden i endast bildformatet och som ligger högst upp i dina meddelanden.

1. [Skapa beslutsregler](creating-decision-rules.md) som anger villkoren som erbjudandena presenteras under.

1. [Skapa samlingskvalificerare](creating-tags.md) (kallas tidigare&quot;taggar&quot;) som du kopplar till erbjudandena så att du enkelt kan ordna och söka efter dem i biblioteket.

1. Om du vill definiera regler som avgör vilket erbjudande som ska presenteras först för en viss placering (i stället för att ta hänsyn till offertens prioritetspoäng), kan du [skapa en rankningsformel](../ranking/create-ranking-formulas.md).

<!--
<table style="table-layout:fixed">
<tr style="border: 0;">
<td>
<img src="../../assets/do-not-localize/icon-placement.svg" width="60px">
<div>
<a href="../offer-library/creating-placements.md">Create placements</a>
</div>
<p>
</td>
<td>
<img src="../../assets/do-not-localize/icon-rules.svg" width="60px">
<div>
<a href="../offer-library/creating-decision-rules.md">Create decision rules</a>
</div>
<p>
<td>
<img src="../../assets/do-not-localize/icon-tags.svg" width="60px">
<div>
<a href="../offer-library/creating-tags.md">Create collection qualifiers</a>
</div>
<p>
</td>
<td>
<img src="../../assets/do-not-localize/icon-ranking.svg" width="60px">
<div>
<a href="../ranking/create-ranking-formulas.md">Create ranking formulas</a>
</div>
<p>
</td>
</tr>
</table>
-->

## Skapa och hantera erbjudanden {#create-and-manage-offers}

1. [Skapa erbjudanden](creating-personalized-offers.md) och konfigurera deras innehåll och egenskaper.

1. [Skapa reserverbjudanden](creating-fallback-offers.md), som är det sista erbjudandet som visas om kunderna inte är berättigade till något av de valda erbjudandena.

1. [Skapa en samling](creating-collections.md) för att inkludera de anpassade erbjudanden du har skapat och använda dem i ett beslut.

<!--
<table style="table-layout:fixed">
<tr style="border: 0;">
<td>
<img src="../../assets/do-not-localize/icon-offer.svg" width="60px">
<div>
<a href="../offer-library/creating-personalized-offers.md">Create offers</a>
</div>
<p>
</td>
<td>
<img src="../../assets/do-not-localize/icon-fallback.svg" width="60px">
<div>
<a href="../offer-library/creating-fallback-offers.md">Create fallback offers</a>
</div>
<p>
</td>
<td>
<img src="../../assets/do-not-localize/icon-collection.svg" width="60px">
<div>
<a href="../offer-library/creating-collections.md">Create collections</a>
</div>
<p>
</td>
</tr>
</table>
-->

## Skapa och konfigurera beslut {#create-and-configure-decisions}

1. [Skapa ett beslut](../offer-activities/create-offer-activities.md) som kombinerar ersättningar med personaliserade erbjudanden och reserverbjudanden. Den här kombinationen används av beslutsmotorn för att hitta det bästa erbjudandet för en viss profil.

1. [Konfigurera beslutet](../offer-activities/create-offer-activities.md#add-decision-scopes). Om du vill göra det markerar du placeringarna och för varje placering väljer du en samling och en reserv.

1. Vid behov kan du [tilldela en rankningsformel](../offer-activities/configure-offer-selection.md#assign-ranking-formula) eller [AI-rankning](../offer-activities/configure-offer-selection.md#use-ranking-strategy) till en placering när du konfigurerar beslutet.

<!--
<table style="table-layout:fixed">
<tr style="border: 0;">
<td>
<img src="../../assets/do-not-localize/icon-decision.svg" width="60px">
<div>
<a href="../offer-activities/create-offer-activities.md">Create decisions</a>
</div>
<p>
</td>
<td>
<img src="../../assets/do-not-localize/icon-configure-decision.svg" width="60px">
<div>
<a href="../offer-activities/create-offer-activities.md#add-offers">Configure decisions</a>
</div>
<p>
</td>
<td>
<img src="../../assets/do-not-localize/icon-assign-ranking.svg" width="60px">
<div>
<a href="../offer-activities/configure-offer-selection.md#assign-ranking-formula">Assign ranking</a>
</div>
<p>
</td>
</tr>
</table>
-->