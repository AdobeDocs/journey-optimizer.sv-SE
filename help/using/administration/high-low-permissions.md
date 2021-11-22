---
title: Behörighetsnivåer
description: Läs om behörigheter på hög och låg nivå
page-status-flag: never-activated
uuid: null
contentOwner: null
products: null
audience: administrators
content-type: reference
topic-tags: null
discoiquuid: null
internal: n
snippet: y
feature: Control Groups
topic: Administration
role: Admin
level: Intermediate
exl-id: 1b286f9d-43ef-4b80-b4ee-136da857bb95
source-git-commit: da885bd5e29ff3454fef1c6b362f0e646fe8c39a
workflow-type: tm+mt
source-wordcount: '1093'
ht-degree: 0%

---

# Behörighetsnivåer {#high-low-permissions}

![](../assets/do-not-localize/permissions.png)

Varje produktprofil består av behörigheter som ger användarna tillgång till de olika funktionerna.
De kan delas in i två typer:

* **Hög behörighet**: representerar de olika behörigheter som kan tilldelas till **[!UICONTROL Product profile]** i [!DNL Admin console], till exempel **[!UICONTROL Publish journeys]** och **[!UICONTROL Manage subdomains delegation]**. Höga behörigheter omfattar behörigheter på låg nivå.

* **Låg behörighet**: representerar de olika behörigheter som kommer från behörigheten på hög nivå.

Till exempel **[!UICONTROL Journey administrator]** produktprofilen har tilldelats **[!UICONTROL Manage journeys]** behörighet. Från det här behörigheten blir de lågnivåbehörigheter som gör att reseadministratören kan skriva, läsa och ta bort resor.

## Resekapacitet {#journey-capability}

### Hantera resetillstånd {#manage-journeys}

The **[!UICONTROL Manage journeys]** behörighet på hög nivå ger användare möjlighet att skapa nya och redigera/ta bort befintliga resor samt åtkomst till de objekt som används på arbetsytan för att skapa resans flöde.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:

   * journeys.read
   * journeys.write
   * journeys.delete
   * messages.read

* Specifikt för Adobe Experience Platform:

   * segments.read
   * profiles.read
   * datasets.read
   * schemas.read

### Publicera resetillstånd {#publish-journeys}

The **[!UICONTROL Publish journeys]** högnivåtillstånd ger användarna rätt att publicera resor.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * journeys.publish
   * journeys.read

### Visa resetillstånd {#view-journeys}

The **[!UICONTROL View journeys]** behörighet på hög nivå tillåter användare att bläddra och visa resor.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * journeys.read

* Specifikt för Adobe Experience Platform:
   * segments.read
   * profiles.read

### Hantera resthändelser, datakällor och behörigheter för åtgärder {#manage-journeys-events}

The **[!UICONTROL Manage journeys events, data sources and actions]** behörighet på hög nivå tillåter användare att konfigurera händelse- och datakonfigurationer.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * travel_events.read
   * travel_events.write
   * travel_events.delete
   * travel_data_sources.read
   * travel_data_sources.write
   * travel_data_sources.delete
   * travel_actions.read
   * travel_actions.write
   * travel_actions.delete
* Specifikt för Adobe Experience Platform:
   * schemas.read
   * datasets.read
   * identity_namespace.read

### Visa resehändelser, datakällor och åtgärdsbehörigheter {#view-journeys-event}

The **[!UICONTROL View journeys events, data sources and actions]** behörighet på hög nivå tillåter användare att använda händelser och data i reseflödet.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * travel_events.read
   * travel_data_sources.read
   * travel_actions.read

* Specifikt för Adobe Experience Platform:
   * schemas.read
   * datasets.read
   * identity_namespace.read

### Visa behörighet för reserapport {#view-journeys-report}

The **[!UICONTROL View journeys report]** behörighet på hög nivå tillåter användare att läsa skrivskyddade reserapporter.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * travel_report.read
   * messages_report.read

* Specifikt för Adobe Experience Platform:
   * datasets.read
   * queries.read
   * queries.write
   * queries.delete

## Meddelandefunktion {#message-capability}

### Hantera meddelandebehörigheter {#manage-messages}

The **[!UICONTROL Manage messages]** behörighet på hög nivå ger användare möjlighet att skapa och redigera/ta bort meddelanden.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages.write
   * messages.read
   * messages.delete
   * messages_presets.read

* Specifikt för Adobe Experience Platform:
   * segments.read
   * schemas.read

### Hantera förhandsgranskning och testbehörighet för meddelanden {#mange-messages-preview}

The **[!UICONTROL Manage messages preview and test]** behörighet på hög nivå ger användarna möjlighet att förhandsgranska personaliserade meddelanden.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages.publish
   * messages_preview_and_test.write
   * messages.publish

* Specifikt för Adobe Experience Platform:
   * profiles.read
   * profiles.write
   * schemas.read
   * datasets.write
   * datasets.read
   * identity_namespace.read
   * segments.read
   * queries.write
   * merge_policies.read

### Publicera meddelanden - behörighet {#publish-messages}

The **[!UICONTROL Publish messages]** behörighet på hög nivå tillåter användare att publicera meddelanden.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages.publish

* Specifikt för Adobe Experience Platform:
   * profiles.read
   * schemas.read
   * datasets.read

### Visa meddelandebehörighet {#view-messages}

The **[!UICONTROL View messages]** behörighet på hög nivå tillåter användare att endast läsa meddelanden.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages.read
   * messages_presets.read

* Specifikt för Adobe Experience Platform:
   * schemas.read
   * segments.read

### Visa rapportbehörighet för meddelanden {#view-message-reports}

The **[!UICONTROL View messages report]** behörighet på hög nivå tillåter användare att läsa skrivskyddade e-postmeddelanden och skicka rapporter.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages_report.read
   * datasets.read
   * queries.read
   * queries.write
   * queries.delete
   * journey.read

## Beslutsledningskapacitet {#decisions-permissions}

### Hantera beslutsbehörighet {#manage-decisioning}

The **[!UICONTROL Manage decisions]** behörighet på hög nivå ger användare möjlighet att skapa nya och redigera/ta bort befintliga **[!UICONTROL Activity entities]** samt hantera de objekt som används i dessa aktiviteter för att fatta beslut.

Den innehåller följande lågnivåbehörigheter:

* Specifik för beslutshantering:
   * activities.read
   * activities.write
   * activities.delete
   * offers.read
   * offers.write
   * offers.delete
   * placements.read
   * placements.write
   * placements.delete
   * ranking_strategy.read

* Specifikt för Adobe Experience Platform:
   * datasets.read
   * datasets.write
   * datasets.delete
   * schemas.read
   * profile.read
   * segments.read

### Visa beslutsbehörighet {#view-decisions}

The **[!UICONTROL View decisions]** behörighet på hög nivå tillåter användare att använda en befintlig aktivitet och relaterade affärsobjekt för att fatta beslut.

Den innehåller följande lågnivåbehörigheter:

* Specifik för beslutshantering:
   * activities.read
   * offers.read
   * placements.read
   * ranking_strategy.read

* Specifikt för Adobe Experience Platform:
   * schemas.read
   * segment.read
   * datasets.read
   * datasets.write
   * datasets.delete

### Publicera erbjuder beslutsbehörighet {#publish-decisions}

The **[!UICONTROL Publish offers decisioning]** behörighet på hög nivå ger användare åtkomst till att godkänna/avgodkänna erbjudandeaktiviteter.

Den innehåller följande lågnivåbehörigheter:

* Specifik för beslutshantering:
   * offers_activity.read
   * offers.read
   * offers.write
   * offers.delete
   * placements.read
   * placements.write
   * placements.delete
   * ranking_strategy.read

* Specifikt för Adobe Experience Platform:
   * schemas.read
   * segment.read
   * datasets.read
   * profiles.read

### Hantera behörighet för rankningsstrategier {#manage-decisions}

The **[!UICONTROL Manage ranking strategies]** behörighet på hög nivå tillåter användare att läsa, skapa, redigera och ta bort anpassade meddelanden och använda åtgärdsfunktioner.

Den innehåller följande lågnivåbehörigheter:

* Specifik för beslutshantering:
   * ranking_strategy.read
   * ranking_strategy.write
   * ranking_strategy.delete
   * activities.read
   * offers.read
   * placements.read

## Administration {#administration-permissions}

### Hantera delegeringsbehörighet för underdomäner {#manage-subdomain}

The **[!UICONTROL Manage subdomains delegation]** Med högnivåbehörighet kan användare skapa, redigera och ta bort underdomänsdelegeringar (inklusive IP-pool).

Den innehåller följande lågnivåbehörigheter:

* underdomäner_delegering.read
* subdomains_Delegering.write
* underdomäner_delegering.delete

### Visa behörighet för PTR-poster {#view-ptr}

The **[!UICONTROL View PTR records]** behörighet på hög nivå tillåter användare att visa PTR-poster som har konfigurerats baserat på underdomänen.

Den innehåller följande lågnivåbehörigheter:

* PTR_records.read
* underdomäner_delegering.read

### Hantera behörighet för IP-pooler {#manage-ip-pools}

The **[!UICONTROL Manage IP pools]** behörighet på hög nivå tillåter användare att skapa, redigera och ta bort tillhörighetsdefinitionen.

Den innehåller följande lågnivåbehörigheter:

* IP_pools.read
* IP_pools.write
* IP_pools.delete

### Hantera meddelanden med allmänna inställningar, behörighet {#manage-message-settings}

The **[!UICONTROL Manage messages general settings]** behörighet på hög nivå ger användare möjlighet att skapa, redigera och ta bort globala inställningar på sandlådenivå.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages_general_settings.read
   * messages_general_settings.write
   * messages_general_settings.delete
* Specifikt för Adobe Experience Platform:
   * schemas.read

### Visa allmänna inställningar för meddelanden {#view-message-settings}

The **[!UICONTROL View messages general settings]** behörighet på hög nivå tillåter användare att visa meddelanden med allmänna inställningar, t.ex. körningsadressen.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages_general_settings.read
* Specifikt för Adobe Experience Platform:
   * schemas.read

### Hantera behörigheter för meddelandeförinställningar {#manage-message-presets}

The **[!UICONTROL Manage messages presets]** behörighet på hög nivå ger användare möjlighet att skapa, redigera och ta bort meddelandeförinställningar över flera kanaler på sandlådenivå.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages_presets.read
   * messages_presets.write
   * messages_presets.delete
   * underdomäner_delegering.read
   * IP_pools.read
   * mobile_setting.read (från Adobe Experience Platform Launch)

### Visa förinställda meddelanden, behörighet {#view-message-presets}

The **[!UICONTROL View messages presets]** behörighet på hög nivå gör det möjligt för användare att visa meddelandeförinställningar för att veta vilka meddelandeförinställningar som ska användas när ett meddelande skapas.

Den innehåller följande lågnivåbehörigheter:

* messages_presets.read
* underdomäner_delegering.read
* IP_pools.read
* mobile_setting.read (från Adobe Experience Platform Launch)

### Hantera undertryckningsbehörighet {#manage-suppression}

The **[!UICONTROL Manage suppression]** behörighet på hög nivå ger användare möjlighet att definiera antalet studsar innan en e-postadress läggs till i listan samt att lägga till och ta bort poster i/från listan.

Den innehåller följande lågnivåbehörigheter:

* suppression_rules.read
* suppression_rules.write
* suppression_rules.delete
* suppression_list.write
* suppression_list.delete

### Visa behörighet för undertryckningslista {#view-suppresion-list}

The **[!UICONTROL View suppression list]** behörighet på hög nivå ger användarna möjlighet att visa innehåll och inställningar i listan över utelämnanden.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * suppression_list.view
* Specifikt för Adobe Experience Platform:
   * profiles.read
   * datasets.read

### Behörighet för att exportera undertryckningslista {#export-suppression-list}

The **[!UICONTROL Export suppression list]** behörighet på hög nivå ger användarna möjlighet att ladda ned listan som en CSV-fil.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * suppression_list.export
* Specifikt för Adobe Experience Platform:
   * profiles.read
   * datasets.read
