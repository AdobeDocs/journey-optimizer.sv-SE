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
exl-id: 85fd386a-45fa-4f9a-89d1-cecc0749b90d
feature: Kontrollgrupper
topic: Administrering
role: Administrator
level: Intermediate
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '1079'
ht-degree: 0%

---

# Behörighetsnivåer {#high-low-permissions}

![](../assets/do-not-localize/permissions.png)

Varje produktprofil består av behörigheter som ger användarna tillgång till de olika funktionerna.
De kan delas in i två typer:

* **Hög behörighet**: representerar de olika behörigheter som kan tilldelas  **[!UICONTROL Product profile]** i  [!DNL Admin console], till exempel  **[!UICONTROL Publish journeys]** och  **[!UICONTROL Manage subdomains delegation]**. Höga behörigheter omfattar behörigheter på låg nivå.

* **Lågnivåbehörighet**: representerar de olika behörigheter som kommer från behörigheten på hög nivå.

Produktprofilen **[!UICONTROL Journey administrator]** har till exempel tilldelats behörigheten **[!UICONTROL Manage journeys]**. Från det här behörigheten blir de lågnivåbehörigheter som gör att reseadministratören kan skriva, läsa och ta bort resor.

## Reseförmåga {#journey-capability}

### Hantera resebehörighet {#manage-journeys}

Med behörigheten **[!UICONTROL Manage journeys]** på hög nivå kan användare skapa nya och redigera/ta bort befintliga resor samt få åtkomst till de objekt som används i arbetsytan för att skapa reseflödet.

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

### Publicera resebehörighet {#publish-journeys}

Med högnivåbehörigheten **[!UICONTROL Publish journeys]** kan användare publicera resor.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * journeys.publish
   * journeys.read

### Visa resebehörighet {#view-journeys}

Med högnivåbehörigheten **[!UICONTROL View journeys]** kan användare bläddra och visa resor.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * journeys.read

* Specifikt för Adobe Experience Platform:
   * segments.read
   * profiles.read

### Hantera resthändelser, datakällor och åtgärdsbehörigheter {#manage-journeys-events}

Med den höga behörigheten **[!UICONTROL Manage journeys events, data sources and actions]** kan användare konfigurera händelse- och datakonfigurationer.

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

Med den höga behörigheten **[!UICONTROL View journeys events, data sources and actions]** kan användare använda händelser och data i reseflödet.

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

Med **[!UICONTROL View journeys report]**-behörigheten på hög nivå kan användare skriva en skrivskyddad reserapport.

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

### Hantera meddelandebehörighet {#manage-messages}

Med den höga behörigheten **[!UICONTROL Manage messages]** kan användare skapa och redigera/ta bort meddelanden.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages.write
   * messages.read
   * messages.delete
   * messages_presets.read

* Specifikt för Adobe Experience Platform:
   * segments.read
   * schemas.read

### Hantera meddelandeförhandsgranskning och testbehörighet {#mange-messages-preview}

Med den höga behörigheten **[!UICONTROL Manage messages preview and test]** kan användare förhandsgranska personaliserade meddelanden.

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

### Publicera meddelanden, behörighet {#publish-messages}

Med den höga behörigheten **[!UICONTROL Publish messages]** kan användare publicera meddelanden.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages.publish

* Specifikt för Adobe Experience Platform:
   * profiles.read
   * schemas.read
   * datasets.read

### Visa meddelandebehörighet {#view-messages}

Med den höga behörigheten **[!UICONTROL View messages]** kan användare bara läsa meddelanden.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages.read
   * messages_presets.read

* Specifikt för Adobe Experience Platform:
   * schemas.read
   * segments.read

### Visa rapportbehörighet för meddelanden {#view-message-reports}

Med behörigheten **[!UICONTROL View messages report]** på hög nivå kan användare läsa och skicka rapporter via e-post.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages_report.read
   * datasets.read
   * queries.read
   * queries.write
   * queries.delete
   * journey.read

## Beslutshanteringsfunktion {#decisions-permissions}

### Hantera beslutsbehörighet {#manage-decisioning}

Med den höga behörigheten **[!UICONTROL Manage decisions]** kan användare skapa nya och redigera/ta bort befintliga **[!UICONTROL Activity entities]** samt hantera de objekt som används i dessa aktiviteter för att fatta beslut.

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

Med den höga behörigheten **[!UICONTROL View decisions]** kan användare använda en befintlig aktivitet och relaterade affärsobjekt för att fatta beslut.

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

Med **[!UICONTROL Publish offers decisioning]**-behörigheten på hög nivå kan användare få åtkomst till att godkänna/avgodkänna erbjudandeaktiviteter.

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

Med den höga behörigheten **[!UICONTROL Manage ranking strategies]** kan användare läsa, skapa, redigera och ta bort anpassade meddelanderapporter och använda åtgärdsfunktioner.

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

Med den höga behörigheten **[!UICONTROL Manage subdomains delegation]** kan användare skapa, redigera och ta bort underdomändelegering (inklusive IP-pool).

Den innehåller följande lågnivåbehörigheter:

* underdomäner_delegering.read
* subdomains_Delegering.write
* underdomäner_delegering.delete

### Visa behörighet för PTR-poster {#view-ptr}

Med den höga behörigheten **[!UICONTROL View PTR records]** kan användare visa PTR-poster som har konfigurerats baserat på underdomäner och som har följande lågnivåbehörigheter:

* PTR_records.read
* underdomäner_delegering.read

### Hantera behörighet för IP-pooler {#manage-ip-pools}

Med den höga behörigheten **[!UICONTROL Manage IP pools]** kan användare skapa, redigera och ta bort tillhörighetsdefinition.

Den innehåller följande lågnivåbehörigheter:

* IP_pools.read
* IP_pools.write
* IP_pools.delete

### Hantera meddelanden med allmänna inställningar, behörighet {#manage-message-settings}

Med den höga behörigheten **[!UICONTROL Manage messages general settings]** kan användare skapa, redigera och ta bort globala inställningar på sandlådenivå.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages_general_settings.read
   * messages_general_settings.write
   * messages_general_settings.delete

* Specifikt för Adobe Experience Platform:
   * schemas.read

### Visa allmänna inställningsbehörigheter för meddelanden {#view-message-settings}

Med behörigheten **[!UICONTROL View messages general settings]** på hög nivå kan användare visa allmänna inställningar för meddelanden, t.ex. inaktiveringsregler eller körningsadress.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages_general_settings.read
* Specifikt för Adobe Experience Platform:
   * schemas.read

### Hantera meddelandeförinställningar behörighet {#manage-message-presets}

Med den höga behörigheten **[!UICONTROL Manage messages presets]** kan användare skapa, redigera och ta bort meddelandeförinställningar i alla kanaler på sandlådenivå.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * messages_presets.read
   * messages_presets.write
   * messages_presets.delete
   * underdomäner_delegering.read
   * IP_pools.read
   * mobile_setting.read (från Adobe Experience Platform Launch)

### Visa meddelandeförinställningar behörighet {#view-message-presets}

Med den höga behörigheten **[!UICONTROL View messages presets]** kan användare visa meddelandeförinställningar för att veta vilka meddelandeförinställningar som ska användas när ett meddelande skapas.

Den innehåller följande lågnivåbehörigheter:

* messages_presets.read
* underdomäner_delegering.read
* IP_pools.read
* mobile_setting.read (från Adobe Experience Platform Launch)

### Hantera behörighet för undertryckningsregler {#manage-suppression-rules}

Med den höga behörigheten **[!UICONTROL Manage suppression rules]** kan användare definiera antalet studsar innan användarens e-postadress läggs till i listan över utelämnanden.

Den innehåller följande lågnivåbehörigheter:

* suppression_rules.read
* suppression_rules.write
* suppression_rules.delete

### Visa behörighet för undertryckningslista {#view-suppresion-list}

Med den höga behörigheten **[!UICONTROL View suppression list]** kan användare visa meddelandekonfigurationer, inklusive meddelandeförinställningar och allmänna meddelandeinställningar.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Journey Optimizer:
   * suppression_list.view
* Specifikt för Adobe Experience Platform:
   * profiles.read
   * datasets.read

### Behörighet för att exportera undertryckningslista {#export-suppression-list}

Med den höga behörigheten **[!UICONTROL Export suppression list]** kan användare konfigurera meddelandekonfigurationer, inklusive meddelandeförinställningar och allmänna meddelandeinställningar.

Den innehåller följande lågnivåbehörigheter:

* Specifikt för Adobe Experience Platform:
   * profiles.read
   * datasets.read
