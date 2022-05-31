---
title: Behörighetsnivåer
description: Läs om behörigheter på hög och låg nivå
topic: Administration
role: Admin
level: Intermediate
exl-id: 1b286f9d-43ef-4b80-b4ee-136da857bb95
source-git-commit: 76eb73e875cbdeb7b5821f0c63435cf96c532adc
workflow-type: tm+mt
source-wordcount: '1139'
ht-degree: 0%

---

# Behörighetsnivåer {#high-low-permissions}

![](assets/do-not-localize/permissions.png)

Varje produktprofil består av behörigheter som ger användarna tillgång till de olika funktionerna.
De kan delas in i två typer:

* **Hög behörighet**: representerar de olika behörigheter som kan tilldelas till **[!UICONTROL Product profile]** i [!DNL Admin console], till exempel **[!DNL Publish journeys]** och **[!DNL Manage subdomains delegation]**. Höga behörigheter omfattar behörigheter på låg nivå.

* **Låg behörighet**: representerar de olika behörigheter som kommer från behörigheten på hög nivå.

Till exempel **[!DNL Journey administrator]** produktprofilen har tilldelats **[!DNL Manage journeys]** behörighet. Från det här behörigheten blir de lågnivåbehörigheter som gör att reseadministratören kan skriva, läsa och ta bort resor.

## Resekapacitet {#journey-capability}

### [!DNL Manage journeys] behörighet {#manage-journeys}

The **[!DNL Manage journeys]** behörighet på hög nivå ger användare möjlighet att skapa nya och redigera/ta bort befintliga resor samt åtkomst till de objekt som används på arbetsytan för att skapa resans flöde.

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

### [!DNL Publish journeys] behörighet {#publish-journeys}

The **[!DNL Publish journeys]** högnivåtillstånd ger användarna rätt att publicera resor.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * journeys.publish
   * journeys.read

### [!DNL View journeys] behörighet {#view-journeys}

The **[!DNL View journeys]** behörighet på hög nivå tillåter användare att bläddra och visa resor.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * journeys.read

* Specifikt för Adobe Experience Platform:
   * segments.read
   * profiles.read

### [!DNL Manage journeys events, data sources and actions] behörighet {#manage-journeys-events}

The **[!DNL Manage journeys events, data sources and actions]** behörighet på hög nivå tillåter användare att konfigurera händelse- och datakonfigurationer.

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

### [!DNL View journeys events, data sources and actions] behörighet {#view-journeys-event}

The **[!DNL View journeys events, data sources and actions]** behörighet på hög nivå tillåter användare att använda händelser och data i reseflödet.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * travel_events.read
   * travel_data_sources.read
   * travel_actions.read

* Specifikt för Adobe Experience Platform:
   * schemas.read
   * datasets.read
   * identity_namespace.read

### [!DNL View journeys report] behörighet {#view-journeys-report}

The **[!DNL View journeys report]** behörighet på hög nivå tillåter användare att läsa skrivskyddade reserapporter.

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

### [!DNL Manage messages] behörighet {#manage-messages}

The **[!DNL Manage messages]** behörighet på hög nivå ger användare möjlighet att skapa och redigera/ta bort meddelanden.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages.write
   * messages.read
   * messages.delete
   * messages_presets.read

* Specifikt för Adobe Experience Platform:
   * segments.read
   * schemas.read

### [!DNL Manage messages preview and test] behörighet {#mange-messages-preview}

The **[!DNL Manage messages preview and test]** behörighet på hög nivå ger användarna möjlighet att förhandsgranska personaliserade meddelanden.

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

### [!DNL Publish messages] behörighet {#publish-messages}

The **[!DNL Publish messages]** behörighet på hög nivå tillåter användare att publicera meddelanden.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages.publish

* Specifikt för Adobe Experience Platform:
   * profiles.read
   * schemas.read
   * datasets.read

### [!DNL View messages] behörighet {#view-messages}

The **[!DNL View messages]** behörighet på hög nivå tillåter användare att endast läsa meddelanden.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages.read
   * messages_presets.read

* Specifikt för Adobe Experience Platform:
   * schemas.read
   * segments.read

### [!DNL View messages report] behörighet {#view-message-reports}

The **[!DNL View messages report]** behörighet på hög nivå tillåter användare att läsa skrivskyddade e-postmeddelanden och skicka rapporter.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages_report.read
   * datasets.read
   * queries.read
   * queries.write
   * queries.delete
   * journey.read

## Beslutsledningskapacitet {#decisions-permissions}

### [!DNL Manage decisions] behörighet {#manage-decisioning}

The **[!DNL Manage decisions]** behörighet på hög nivå ger användare möjlighet att skapa nya och redigera/ta bort befintliga **[!DNL Activity entities]** samt hantera de objekt som används i dessa aktiviteter för att fatta beslut.

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

### [!DNL View decisions] behörighet {#view-decisions}

The **[!DNL View decisions]** behörighet på hög nivå tillåter användare att använda en befintlig aktivitet och relaterade affärsobjekt för att fatta beslut.

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

### [!DNL Publish offers decisioning] behörighet {#publish-decisions}

The **[!DNL Publish offers decisioning]** behörighet på hög nivå ger användare åtkomst till att godkänna/avgodkänna erbjudandeaktiviteter.

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

### [!DNL Manage ranking strategies] behörighet {#manage-ranking-strategies}

The **[!DNL Manage ranking strategies]** behörighet på hög nivå ger användare möjlighet att läsa, skapa, redigera och ta bort rankningsstrategier.

Den innehåller följande lågnivåbehörigheter:

* Specifik för beslutshantering:
   * ranking_strategy.read
   * ranking_strategy.write
   * ranking_strategy.delete
   * activities.read
   * offers.read
   * placements.read

## Administration {#administration-permissions}

### [!DNL Manage subdomains delegation] behörighet {#manage-subdomain}

The **[!DNL Manage subdomains delegation]** Med högnivåbehörighet kan användare skapa, redigera och ta bort underdomänsdelegeringar (inklusive IP-pool).

Den innehåller följande lågnivåbehörigheter:

* underdomäner_delegering.read
* subdomains_Delegering.write
* underdomäner_delegering.delete

### [!DNL Manage PTR records] behörighet {#manage-ptr}

The **[!DNL Manage PTR records]** behörighet på hög nivå tillåter användare att läsa och redigera PTR-poster som har konfigurerats baserat på underdomänen.

Den innehåller följande lågnivåbehörigheter:

* PTR_records.read
* PTR_records.write
* underdomäner_delegering.read

### [!DNL View PTR records] behörighet {#view-ptr}

The **[!DNL View PTR records]** behörighet på hög nivå tillåter användare att visa PTR-poster som har konfigurerats baserat på underdomänen.

Den innehåller följande lågnivåbehörigheter:

* PTR_records.read
* underdomäner_delegering.read

### [!DNL Manage IP pools] behörighet {#manage-ip-pools}

The **[!DNL Manage IP pools]** behörighet på hög nivå tillåter användare att skapa, redigera och ta bort tillhörighetsdefinitionen.

Den innehåller följande lågnivåbehörigheter:

* IP_pools.read
* IP_pools.write
* IP_pools.delete

### [!DNL Manage messages general settings] behörighet {#manage-message-settings}

The **[!DNL Manage messages general settings]** behörighet på hög nivå ger användare möjlighet att skapa, redigera och ta bort globala inställningar på sandlådenivå.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages_general_settings.read
   * messages_general_settings.write
   * messages_general_settings.delete
* Specifikt för Adobe Experience Platform:
   * schemas.read

### [!DNL View messages general settings] behörighet {#view-message-settings}

The **[!DNL View messages general settings]** behörighet på hög nivå tillåter användare att visa meddelanden med allmänna inställningar, t.ex. körningsadressen.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages_general_settings.read
* Specifikt för Adobe Experience Platform:
   * schemas.read

### [!DNL Manage messages presets] behörighet {#manage-message-presets}

The **[!DNL Manage messages presets]** behörighet på hög nivå ger användare möjlighet att skapa, redigera och ta bort meddelandeförinställningar över flera kanaler på sandlådenivå.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages_presets.read
   * messages_presets.write
   * messages_presets.delete
   * underdomäner_delegering.read
   * IP_pools.read
   * mobile_setting.read (från Adobe Experience Platform Launch)

### [!DNL View messages presets] behörighet {#view-message-presets}

The **[!DNL View messages presets]** behörighet på hög nivå gör det möjligt för användare att visa meddelandeförinställningar för att veta vilka meddelandeförinställningar som ska användas när ett meddelande skapas.

Den innehåller följande lågnivåbehörigheter:

* messages_presets.read
* underdomäner_delegering.read
* IP_pools.read
* mobile_setting.read (från Adobe Experience Platform Data Collection)

### [!DNL Manage suppression] behörighet {#manage-suppression}

The **[!DNL Manage suppression]** behörighet på hög nivå ger användare möjlighet att definiera antalet studsar innan en e-postadress läggs till i listan samt att lägga till och ta bort poster i/från listan.

Den innehåller följande lågnivåbehörigheter:

* suppression_rules.read
* suppression_rules.write
* suppression_rules.delete
* suppression_list.write
* suppression_list.delete

### [!DNL View suppression list] behörighet {#view-suppression-list}

The **[!DNL View suppression list]** behörighet på hög nivå ger användarna möjlighet att visa innehåll och inställningar i listan över utelämnanden.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * suppression_list.view

* Specifikt för Adobe Experience Platform:
   * profiles.read
   * datasets.read

### [!DNL Export suppression list] behörighet {#export-suppression-list}

The **[!DNL Export suppression list]** behörighet på hög nivå ger användarna möjlighet att ladda ned listan som en CSV-fil.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * suppression_list.export

* Specifikt för Adobe Experience Platform:
   * profiles.read
   * datasets.read

### [!DNL Manage landing page settings] behörighet {#manage-landing-page-settings}

The **[!DNL Manage landing page settings]** behörighet på hög nivå ger användare möjlighet att läsa, skapa och redigera underdomäner och förinställningar för landningssidor.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * landing_page_subdomain.read
   * landing_page_subdomain.write
   * landing_page_subdomain.delete
   * landing_page_preset.read
   * landing_page_preset.write
   * landing_page_preset.delete

### [!DNL Manage frequency rules] behörighet {#manage-frequency-rules}

The **[!DNL Manage frequency rules]** behörighet på hög nivå tillåter användare att läsa, skapa, redigera, ta bort och aktivera/inaktivera frekvensregler.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * frequency_rules.read
   * frequency_rules.write
   * frequency_rules.delete

### [!DNL View frequency rules] behörighet {#view-frequency-rules}

The **[!DNL View frequency rules]** behörighet på hög nivå tillåter användare att visa frekvensregler.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * frequency_rules.read
