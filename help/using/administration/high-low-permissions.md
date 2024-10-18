---
solution: Journey Optimizer
product: journey optimizer
title: Behörighetsnivåer
description: Lär dig mer om höga och låga behörigheter som ger användarna tillgång till de olika funktionerna.
topic: Administration
feature: Access Management
role: Admin, Architect, Developer
level: Experienced
keywords: behörighet, hög nivå, låg nivå, profil, administratörskonsol
exl-id: 1b286f9d-43ef-4b80-b4ee-136da857bb95
source-git-commit: f316ec79958ac23e0e416f0cafd49c017f2b6d4c
workflow-type: tm+mt
source-wordcount: '1065'
ht-degree: 0%

---

# Behörighetsnivåer {#high-low-permissions}

![](assets/do-not-localize/permissions.png)

Varje roll består av behörigheter som gör att användarna kan komma åt de olika funktionerna.
De kan delas in i två typer:

* **Hög behörighet**: representerar olika behörigheter som kan tilldelas **[!UICONTROL Role]**, till exempel **[!DNL Publish journeys]** och **[!DNL Manage subdomains delegation]**. Höga behörigheter omfattar behörigheter på låg nivå. Behörigheter på hög nivå anges på [den här sidan](ootb-permissions.md).

* **Lågnivåbehörighet**: representerar de olika behörigheter som kommer från högnivåbehörigheten.

Rollen **[!DNL Journey administrator]** har till exempel tilldelats behörigheten **[!DNL Manage journeys]**. Från det här behörigheten blir de lågnivåbehörigheter som gör att reseadministratören kan skriva, läsa och ta bort resor.

## Resurs {#journey-capability}

* **[!DNL Manage journeys]** högnivåbehörighet tillåter användare att skapa nya och redigera/ta bort befintliga resor samt åtkomst till de objekt som används på arbetsytan för att skapa reseflödet.

+++ Den innehåller följande lågnivåbehörigheter:

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

+++ Den innehåller följande lågnivåbehörigheter:
   * Journey Optimizer-specifikt:
      * journeys.publish
      * journeys.read

+++

* **[!DNL View journeys]** högnivåbehörighet tillåter användare att bläddra och visa resor.

+++ Den innehåller följande lågnivåbehörigheter:

   * Journey Optimizer-specifikt:
      * journeys.read

   * Adobe Experience Platform-specifikt:
      * segments.read
      * profiles.read

+++

* **[!DNL Manage journeys events, data sources and actions]** högnivåbehörighet tillåter användare att konfigurera händelse- och datakonfigurationer.

+++ Den innehåller följande lågnivåbehörigheter:

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

+++ Den innehåller följande lågnivåbehörigheter:

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

+++ Den innehåller följande lågnivåbehörigheter:

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

+++ Den innehåller följande lågnivåbehörigheter:

   * Journey Optimizer-specifikt:
      * frequency_rules.read
      * frequency_rules.write
      * frequency_rules.delete

+++

* **[!DNL View frequency rules]** högnivåbehörighet tillåter användare att visa frekvensregler.

+++ Den innehåller följande lågnivåbehörigheter:

   * Journey Optimizer-specifikt:
      * frequency_rules.read

+++

## Kampanjresurs {#campaign-capability}

* **[!DNL Export suppression list]** högnivåbehörighet tillåter användare att hämta undertryckningslistan som en CSV-fil.

+++ Den innehåller följande lågnivåbehörigheter:

   * Journey Optimizer-specifikt:
      * suppression_list.export

   * Adobe Experience Platform-specifikt:
      * profiles.read
      * datasets.read

+++

* **[!DNL Manage campaigns]** högnivåbehörighet tillåter användare att skapa nya och redigera/ta bort kampanjer

+++ Den innehåller följande lågnivåbehörigheter:

   * Journey Optimizer-specifikt:

      * campaign.read
      * campaign.write
      * campaign.delete
     <!--* experiments.read
      * experiments.write
      * experiments.delete-->

+++

* **[!DNL Publish campaigns]** högnivåbehörighet tillåter användare att publicera kampanjer.

+++ Den innehåller följande lågnivåbehörigheter:

   * Journey Optimizer-specifikt:

      * kampanjläsning
      * campaign-publish
        <!--* experiments.activate-->

+++

* **[!DNL View campaigns report]** högnivåbehörighet tillåter användare att läsa och redigera kampanjrapporter.

+++ Den innehåller följande lågnivåbehörigheter:

   * Journey Optimizer-specifikt:
      * campaign.read
      * campaign-report.read
     <!--* experiments.read
      * experiments_report.read-->

+++

## Beslutsledningsresurs {#decisions-permissions}

* **[!DNL Manage decisions]**-behörighet på hög nivå tillåter användare att skapa nya och redigera/ta bort befintliga **[!DNL Activity entities]** samt hantera de objekt som används i dessa aktiviteter för att fatta beslut.

+++ Den innehåller följande lågnivåbehörigheter:

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

+++ Den innehåller följande lågnivåbehörigheter:

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

+++ Den innehåller följande lågnivåbehörigheter:

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

+++ Den innehåller följande lågnivåbehörigheter:

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
* **[!DNL Manage Experience decisions]** high-level permission allows users to read, create, edit, and delete Experience decisioning entities.

  +++ It includes the following low-level permissions:  

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

+++ Den innehåller följande lågnivåbehörigheter:
   * Journey Optimizer-specifikt:

      * file_routing.read
      * file_routing.write
      * file_routing.delete

+++

* **[!DNL Manage IP pools]** högnivåbehörighet tillåter användare att skapa, redigera och ta bort tillhörighetsdefinitionen.

+++ Den innehåller följande lågnivåbehörigheter:
   * Journey Optimizer-specifikt:
      * IP_pools.read
      * IP_pools.write
      * IP_pools.delete

+++

* **[!DNL Manage landing page settings]** högnivåbehörighet tillåter användare att läsa, skapa och redigera underdomäner och förinställningar för landningssidor.

+++ Den innehåller följande lågnivåbehörigheter:

   * Journey Optimizer-specifikt:

      * landing_page_subdomain.read
      * landing_page_subdomain.write
      * landing_page_subdomain.delete
      * landing_page_preset.read
      * landing_page_preset.write
      * landing_page_preset.delete

+++

* **[!DNL Manage messages general settings]** högnivåbehörighet tillåter användare att skapa, redigera och ta bort globala inställningar på sandlådenivå.

+++ Den innehåller följande lågnivåbehörigheter:

   * Journey Optimizer-specifikt:
      * messages_general_settings.read
      * messages_general_settings.write
      * messages_general_settings.delete

   * Adobe Experience Platform-specifikt:
      * schemas.read

+++

* **[!DNL Manage messages presets]** högnivåbehörighet tillåter användare att läsa, skapa, redigera och ta bort kanalkonfigurationer över kanaler på sandlådenivå.

+++ Den innehåller följande lågnivåbehörigheter:

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

+++ Den innehåller följande lågnivåbehörigheter:

   * Journey Optimizer-specifikt:
      * PTR_records.read
      * PTR_records.write
      * underdomäner_delegering.read

+++

* **[!DNL Manage Seedlist]** högnivåbehörighet tillåter användare att läsa, skapa, redigera och ta bort listan.

+++ Den innehåller följande lågnivåbehörigheter:

   * Journey Optimizer-specifikt:
      * seedlist.read
      * seedlist.write
      * seedlist.delete

+++

* **[!DNL Manage SMS subdomains]** högnivåbehörighet tillåter användare att läsa, skapa, redigera och ta bort SMS-underdomäner.

+++ Den innehåller följande lågnivåbehörigheter:

   * Journey Optimizer-specifikt:
      * sms_subdomains.read
      * sms_subdomains.write
      * sms_subdomains.delete

+++

* **[!DNL Manage subdomains delegations]** högnivåbehörighet tillåter användare att skapa, redigera och ta bort underdomänsdelegeringar (inklusive IP-pool).

+++ Den innehåller följande lågnivåbehörigheter:
   * Journey Optimizer-specifikt:

      * underdomäner_delegering.read
      * subdomains_Delegering.write
      * underdomäner_delegering.delete

+++

* **[!DNL Manage suppression]**-behörighet på hög nivå tillåter användare att definiera antalet studsar innan en e-postadress läggs till i listan över inaktiveringar, samt att lägga till och ta bort poster i/från listan över inaktiveringar.

+++ Den innehåller följande lågnivåbehörigheter:
   * Journey Optimizer-specifikt:
      * suppression_rules.read
      * suppression_rules.write
      * suppression_rules.delete
      * suppression_list.write
      * suppression_list.delete

+++

* **[!DNL View file routing]** högnivåbehörighet tillåter användare att visa filroutningskonfigurationer.

+++ Den innehåller följande lågnivåbehörigheter:
   * Journey Optimizer-specifikt:

      * file_routing.read

+++

* **[!DNL View messages general settings]** högnivåbehörighet tillåter användare att visa allmänna inställningar för meddelanden, som körningsadressen.

+++ Den innehåller följande lågnivåbehörigheter:

   * Journey Optimizer-specifikt:
      * messages_general_settings.read

   * Adobe Experience Platform-specifikt:
      * schemas.read

+++

* **[!DNL View messages presets]** högnivåbehörighet tillåter användare att visa förinställningar för meddelanden.

+++ Den innehåller följande lågnivåbehörigheter:

   * Journey Optimizer-specifikt:
      * messages_presets.read
      * underdomäner_delegering.read
      * IP_pools.read

   * Specifik datainsamling:
      * Mobil_inställning.read

+++

* **[!DNL View PTR records]** högnivåbehörighet tillåter användare att visa PTR-poster som har konfigurerats baserat på underdomänen.

+++ Den innehåller följande lågnivåbehörigheter:
   * Journey Optimizer-specifikt:

      * PTR_records.read
      * underdomäner_delegering.read

+++

<!--
### [!DNL View channel configuration] permission {#view-channel-surface}

The **[!DNL View channel configuration]** high-level permission allows users to view channel configurations in order to know which channel configurations to use. 
  +++ It includes the following low-level permissions:  

* messages_presets.read
* subdomains_delegation.read
* IP_pools.read
* mobile_setting.read (from Adobe Experience Platform Data Collection)
-->


* **[!DNL View suppression list]**-behörighet på hög nivå tillåter användare att visa innehåll och inställningar i listan över utelämnanden.

+++ Den innehåller följande lågnivåbehörigheter:

   * Journey Optimizer-specifikt:
      * suppression_list.view

   * Adobe Experience Platform-specifikt:
      * profiles.read
      * datasets.read

+++

<!--
### Manage web subdomain permission {#web-subdomain}

The **[!DNL Manage web subdomain]** high-level permission allows users to read, create, edit, and delete web subdomains.

  +++ It includes the following low-level permissions: 
-->

## AI-stödresurs {#ai-permissions}

* **[!DNL Generate content]** högnivåbehörighet ger användare åtkomst till AI Assistant Content Accelerator i Journey Optimizer.

+++ Den innehåller följande lågnivåbehörighet:

   * Journey Optimizer-specifikt:
      * ai-assistant-generated-content.generate

+++
