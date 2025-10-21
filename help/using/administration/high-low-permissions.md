---
solution: Journey Optimizer
product: journey optimizer
title: Behörighetsnivåer
description: Lär dig mer om höga och låga behörigheter som ger användarna tillgång till de olika funktionerna.
topic: Administration
feature: Access Management
role: Admin, Developer
level: Experienced
keywords: behörighet, hög nivå, låg nivå, profil, administratörskonsol
exl-id: 1b286f9d-43ef-4b80-b4ee-136da857bb95
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '1302'
ht-degree: 0%

---

# Behörighetsnivåer {#high-low-permissions}


Varje roll består av behörigheter som gör att användarna kan komma åt de olika funktionerna.

De kan delas in i två typer:

* **Hög behörighet**: representerar olika behörigheter som kan tilldelas **[!UICONTROL Role]**, till exempel **[!DNL Publish journeys]** och **[!DNL Manage subdomains delegation]**. Behörigheter på hög nivå omfattar behörigheter på låg nivå. Behörigheter på hög nivå finns på [den här sidan](ootb-permissions.md).

* **Lågnivåbehörighet**: representerar de olika behörigheter som kommer från högnivåbehörigheten.

Rollen **[!DNL Journey administrator]** har till exempel tilldelats behörigheten **[!DNL Manage journeys]**. Från det här behörigheten blir de lågnivåbehörigheter som gör att reseadministratören kan skriva, läsa och ta bort resor.

![](assets/do-not-localize/permissions.png){width="70%"}


## Resurs {#journey-capability}

* **[!DNL Manage journeys]** högnivåbehörighet tillåter användare att skapa nya och redigera/ta bort/stoppa/pausa befintliga resor samt åtkomst till de objekt som används på arbetsytan för att skapa färdens flöde.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  

   * Journey Optimizer-specifikt:

      * journeys.read
      * journeys.write
      * journeys.delete
      * messages.read

   * Adobe Experience Platform-specifikt:

      * segments.read
      * profiles.read
      * datasets.read
      * schemas.read

  +++

* **[!DNL Publish journeys]** högnivåbehörighet tillåter användare att publicera resor.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  
   * Journey Optimizer-specifikt:
      * journeys.publish
      * journeys.read

  +++

* **[!DNL View journeys]** högnivåbehörighet tillåter användare att bläddra och visa resor.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  

   * Journey Optimizer-specifikt:
      * journeys.read

   * Adobe Experience Platform-specifikt:
      * segments.read
      * profiles.read

  +++

* **[!DNL Manage journeys events, data sources and actions]** högnivåbehörighet tillåter användare att konfigurera händelse- och datakonfigurationer.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  

   * Journey Optimizer-specifikt:
      * travel_events.read
      * travel_events.write
      * travel_events.delete
      * travel_data_sources.read
      * travel_data_sources.write
      * travel_data_sources.delete
      * travel_actions.read
      * travel_actions.write
      * travel_actions.delete

   * Adobe Experience Platform-specifikt:
      * schemas.read
      * datasets.read
      * identity_namespace.read

  +++

* **[!DNL View journeys events, data sources and actions]** högnivåbehörighet tillåter användare att använda händelser och data i reseflödet.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  

   * Journey Optimizer-specifikt:
      * travel_events.read
      * travel_data_sources.read
      * travel_actions.read

   * Adobe Experience Platform-specifikt:
      * schemas.read
      * datasets.read
      * identity_namespace.read

  +++

* **[!DNL View journeys report]** högnivåbehörighet tillåter användare att läsa en skrivskyddad reserapport.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  

   * Journey Optimizer-specifikt:
      * travel_report.read
      * messages_report.read

   * Adobe Experience Platform-specifikt:
      * datasets.read
      * queries.read
      * queries.write
      * queries.delete

  +++

## Journey Optimizer regelresurs {#journey-rules-capability}

* **[!DNL Manage frequency rules]** högnivåbehörighet tillåter användare att läsa, skapa, redigera, ta bort och aktivera/inaktivera frekvensregler.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  

   * Journey Optimizer-specifikt:
      * frequency_rules.read
      * frequency_rules.write
      * frequency_rules.delete

  +++

* **[!DNL View frequency rules]** högnivåbehörighet tillåter användare att visa frekvensregler.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  

   * Journey Optimizer-specifikt:
      * frequency_rules.read

  +++

## Kampanjresurs {#campaign-capability}

* **[!DNL Export suppression list]** högnivåbehörighet tillåter användare att hämta undertryckningslistan som en CSV-fil.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter: 

   * Journey Optimizer-specifikt:
      * suppression_list.export

   * Adobe Experience Platform-specifikt:
      * profiles.read
      * datasets.read

  +++

* **[!DNL Manage campaigns]** högnivåbehörighet tillåter användare att skapa nya och redigera/ta bort kampanjer

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  

   * Journey Optimizer-specifikt:

      * campaign.read
      * campaign.write
      * campaign.delete
     <!--* experiments.read
      * experiments.write
      * experiments.delete-->

  +++

* **[!DNL Publish campaigns]** högnivåbehörighet tillåter användare att publicera kampanjer.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:

   * Journey Optimizer-specifikt:

      * kampanjläsning
      * campaign-publish
        <!--* experiments.activate-->

  +++

* **[!DNL View campaigns report]** högnivåbehörighet tillåter användare att läsa och redigera kampanjrapporter.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  

   * Journey Optimizer-specifikt:
      * campaign.read
      * campaign-report.read
     <!--* experiments.read
      * experiments_report.read-->

  +++

## Beslutsledningsresurs {#decisions-permissions}

* **[!DNL Manage decisions]**-behörighet på hög nivå tillåter användare att skapa nya och redigera/ta bort befintliga **[!DNL Activity entities]** samt hantera de objekt som används i dessa aktiviteter för att fatta beslut.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  

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

   * Adobe Experience Platform-specifikt:
      * datasets.read
      * datasets.write
      * datasets.delete
      * schemas.read
      * profile.read
      * segments.read

  +++

* **[!DNL View decisions]** högnivåbehörighet tillåter användare att använda en befintlig aktivitet och relaterade affärsobjekt för att fatta beslut.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  

   * Specifik för beslutshantering:
      * activities.read
      * offers.read
      * placements.read
      * ranking_strategy.read

   * Adobe Experience Platform-specifikt:
      * schemas.read
      * segment.read
      * datasets.read

  +++

* **[!DNL Manage offers]** högnivåbehörighet tillåter användare att skapa, redigera och ta bort alla erbjudanden, komponenter, läsbeslut och samlingar.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  

   * Specifik för beslutshantering:
      * offers_activity.read
      * offers.read
      * offers.Write
      * offers.Delete
      * placements.Read
      * placements.Write
      * placements.Delete
      * ranking_strategy.read

   * Adobe Experience Platform-specifikt:
      * schemas.read
      * segment.read
      * datasets.read
      * profiles.read

  +++

* **[!DNL Manage ranking strategies]** högnivåbehörighet tillåter användare att läsa, skapa, redigera och ta bort rankningsstrategier.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  

   * Specifik för beslutshantering:
      * ranking_strategy.read
      * ranking_strategy.write
      * ranking_strategy.delete
      * activities.read
      * offers.read
      * placements.read

  +++

## Kanalkonfigurationsresurs {#administration-permissions}

<!--
* **[!DNL Manage Experience decisions]** high-level permission allows users to read, create, edit, and delete Decisioning entities.

  +++ This permission includes the following low-level permissions:  

  * Experience decisions specific:
    * ranking_strategy.read
    * offeritem.read
    * offeritem.write
    * offeritem.delete
    * itemCollection.read
    * itemCollection.write
    * itemCollection.delete
    * SelectionStrategy.read
    * SelectionStrategy.write
    * SelectionStrategy.delete
    * Decisionpolicy.read
    * Decisionpolicy.write
    * Decisionpolicy.delete
  +++
-->

* **[!DNL Manage file routing]** högnivåbehörighet tillåter användare att skapa, redigera och ta bort filroutningskonfigurationer.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  
   * Journey Optimizer-specifikt:

      * file_routing.read
      * file_routing.write
      * file_routing.delete

  +++

* **[!DNL Manage IP pools]** högnivåbehörighet tillåter användare att skapa, redigera och ta bort tillhörighetsdefinitionen.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  
   * Journey Optimizer-specifikt:
      * IP_pools.read
      * IP_pools.write
      * IP_pools.delete

  +++

* **[!DNL Manage landing page settings]** högnivåbehörighet tillåter användare att läsa, skapa och redigera underdomäner och förinställningar för landningssidor.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter: 

   * Journey Optimizer-specifikt:

      * landing_page_subdomain.read
      * landing_page_subdomain.write
      * landing_page_subdomain.delete
      * landing_page_preset.read
      * landing_page_preset.write
      * landing_page_preset.delete

  +++

* **[!DNL Manage messages general settings]** högnivåbehörighet tillåter användare att skapa, redigera och ta bort globala inställningar på sandlådenivå.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  

   * Journey Optimizer-specifikt:
      * messages_general_settings.read
      * messages_general_settings.write
      * messages_general_settings.delete

   * Adobe Experience Platform-specifikt:
      * schemas.read

  +++

* **[!DNL Manage messages presets]** högnivåbehörighet tillåter användare att läsa, skapa, redigera och ta bort kanalkonfigurationer över kanaler på sandlådenivå.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter: 

   * Journey Optimizer-specifikt:
      * messages_presets.read
      * messages_presets.write
      * messages_presets.delete
      * underdomäner_delegering.read
      * IP_pools.read

   * Specifik datainsamling:
      * Mobile_setting.read <!--(from Adobe Experience Platform Launch)-->

  +++

* **[!DNL Manage PTR records]** högnivåbehörighet tillåter användare att läsa och redigera PTR-poster som har konfigurerats baserat på underdomänen.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter: 

   * Journey Optimizer-specifikt:
      * PTR_records.read
      * PTR_records.write
      * underdomäner_delegering.read

  +++

* **[!DNL Manage Seedlist]** högnivåbehörighet tillåter användare att läsa, skapa, redigera och ta bort listan.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter: 

   * Journey Optimizer-specifikt:
      * seedlist.read
      * seedlist.write
      * seedlist.delete

  +++

* **[!DNL Manage SMS subdomains]** högnivåbehörighet tillåter användare att läsa, skapa, redigera och ta bort SMS-underdomäner.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter: 

   * Journey Optimizer-specifikt:
      * sms_subdomains.read
      * sms_subdomains.write
      * sms_subdomains.delete

  +++

* **[!DNL Manage subdomains delegations]** högnivåbehörighet tillåter användare att skapa, redigera och ta bort underdomänsdelegeringar (inklusive IP-pool).

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  
   * Journey Optimizer-specifikt:

      * underdomäner_delegering.read
      * subdomains_Delegering.write
      * underdomäner_delegering.delete

  +++

* **[!DNL Manage suppression]**-behörighet på hög nivå tillåter användare att definiera antalet studsar innan en e-postadress läggs till i listan över inaktiveringar, samt att lägga till och ta bort poster i/från listan över inaktiveringar.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  
   * Journey Optimizer-specifikt:
      * suppression_rules.read
      * suppression_rules.write
      * suppression_rules.delete
      * suppression_list.write
      * suppression_list.delete

  +++

* **[!DNL View file routing]** högnivåbehörighet tillåter användare att visa filroutningskonfigurationer.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  
   * Journey Optimizer-specifikt:

      * file_routing.read

  +++

* **[!DNL View messages general settings]** högnivåbehörighet tillåter användare att visa allmänna inställningar för meddelanden, som körningsadressen.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter: 

   * Journey Optimizer-specifikt:
      * messages_general_settings.read

   * Adobe Experience Platform-specifikt:
      * schemas.read

  +++

* **[!DNL View messages presets]** högnivåbehörighet tillåter användare att visa förinställningar för meddelanden.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter: 

   * Journey Optimizer-specifikt:
      * messages_presets.read
      * underdomäner_delegering.read
      * IP_pools.read

   * Specifik datainsamling:
      * Mobil_inställning.read

  +++

* **[!DNL View PTR records]** högnivåbehörighet tillåter användare att visa PTR-poster som har konfigurerats baserat på underdomänen.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter: 
   * Journey Optimizer-specifikt:

      * PTR_records.read
      * underdomäner_delegering.read

  +++

<!--
### [!DNL View channel configuration] permission {#view-channel-surface}

The **[!DNL View channel configuration]** high-level permission allows users to view channel configurations in order to know which channel configurations to use. 
  +++ This permission includes the following low-level permissions:  

* messages_presets.read
* subdomains_delegation.read
* IP_pools.read
* mobile_setting.read (from Adobe Experience Platform Data Collection)
-->


* **[!DNL View suppression list]**-behörighet på hög nivå tillåter användare att visa innehåll och inställningar i listan över utelämnanden.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  

   * Journey Optimizer-specifikt:
      * suppression_list.view

   * Adobe Experience Platform-specifikt:
      * profiles.read
      * datasets.read

  +++

<!--
### Manage web subdomain permission {#web-subdomain}

The **[!DNL Manage web subdomain]** high-level permission allows users to read, create, edit, and delete web subdomains.

  +++ This permission includes the following low-level permissions: 
-->

## AI-stödresurs {#ai-permissions}

* **[!DNL Generate content]**-behörighet på hög nivå ger användare åtkomst till AI Assistant i Journey Optimizer.

  +++ Den innehåller följande lågnivåbehörighet:  

   * Journey Optimizer-specifikt:
      * ai-assistant-generated-content.generate

  +++

## Orchestrated campaign resource {#ai-orchestrated-campaign}

* **[!DNL Manage orchestrated campaigns]** högnivåbehörighet tillåter användare att skapa nya och redigera/ta bort samordnade kampanjer.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  

   * Journey Optimizer-specifikt:

      * orchestrated_campaign.read
      * orchestrated_campaign.write
      * orkestrated_campaign.delete
      * cjm-web-subdomain.read
      * cjm-message.read
      * cjm-message.write
      * cjm-message.delete
      * cjm-library-item.read
      * cjm-message-general-setting.read
      * cjm-message-preset.read
      * cjm-message-preview-test.write
      * experiment.read
      * experiment.write
      * experiment.delete

   * Adobe Experience Platform-specifikt:

      * identity-graph.read
      * segments.read
      * profiles.read
      * datasets.read
      * schemas.read
      * sandboxes.view

  +++

* **[!DNL Manage orchestrated campaigns admin]** högnivåbehörighet tillåter användare att skapa nya och redigera/ta bort länkar och avstämningar mellan Adobe Experience Platform-profiler och Relational store-entiteter.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  

   * Journey Optimizer-specifikt:

      * cjm-orchestrated-campaign-admin.read
      * cjm-orchestrated-campaign-admin.write
      * cjm-orchestrated-campaign-admin.delete

  +++

* **[!DNL Publish orchestrated campaigns]** högnivåbehörighet tillåter användare att publicera Orchestrated-kampanjer.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:

   * Journey Optimizer-specifikt:

      * cjm-orchestrated-campaign.read
      * cjm-orchestrated-campaign.publish
      * cjm-web-subdomain.read
      * cjm-message.read
      * cjm-message.publish
      * cjm-library-item.read

   * Adobe Experience Platform-specifikt:

      * sandboxes.view

  +++

* **[!DNL View orchestrated campaigns]** högnivåbehörighet tillåter användare att visa orkestrerad kampanj och dess innehåll.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  

   * Journey Optimizer-specifikt:

      * cjm-orchestrated-campaign.read
      * cjm-message.read
      * cjm-library-item.read
      * cjm-message-general-setting.read
      * cjm-message-preset.read
      * experiment.read

   * Adobe Experience Platform-specifikt:

      * sandboxes.view
      * segments.read
      * profiles.read

  +++

* **[!DNL View orchestrated campaigns admin]**-behörighet på hög nivå tillåter användare att visa administratörsinställningarna men inte redigera inställningarna.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  

   * Journey Optimizer-specifikt:

      * cjm-orchestrated-campaign-admin.read

  +++

* **[!DNL View orchestrated campaigns report]** högnivåbehörighet tillåter användare att visa samordnade kampanjresultat i både live- och affärsrapporter.

  +++ Den här behörigheten innehåller följande lågnivåbehörigheter:  

   * Journey Optimizer-specifikt:

      * cjm-orchestrated-campaign-reports.read
      * cjm-message-report.read
      * cjm-channel-report.read
      * cjm-orchestrated-campaign.read
      * cjm-message.read
      * cjm-library-item.read
      * experiment.read
      * experiment-report.read

   * Adobe Experience Platform-specifikt:

      * sandboxes.view
      * datasets.read
      * queries.read
      * queries.write
      * queries.delete

  +++
