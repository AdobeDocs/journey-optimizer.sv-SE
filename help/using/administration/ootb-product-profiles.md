---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer inbyggda roller
description: Läs mer om de inbyggda rollerna
feature: Access Management
topic: Administration
role: Admin, User
level: Intermediate
keywords: behörigheter, författare, meddelanden
exl-id: 5a968bd8-cf76-4242-aa80-3cfb3d551511
source-git-commit: fd8835b1f9bffd887758e4015171074c5dfc16c0
workflow-type: tm+mt
source-wordcount: '1159'
ht-degree: 5%

---

# Inbyggda roller {#ootb-product-profiles}

Inbyggda roller är en uppsättning enhetsbehörigheter som ger användarna tillgång till vissa funktioner eller objekt i gränssnittet. Se [den här sidan](ootb-permissions.md) om du vill se en lista över tillgängliga behörigheter för att bygga upp din roll.

## [!DNL Campaign Administrator] {#campaign-administrator}

The **[!DNL Campaign Administrator]** rollen gör det möjligt för administrationsmenyerna att hantera och publicera kampanjer och beslutshantering.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Kampanjer | <ul><li> **[!DNL Manage campaigns]**: läs, skapa, redigera och ta bort kampanjer.</li><li>**[!DNL Publish campaigns]**: publiceringskampanjer.</li><li>**[!DNL View campaigns report]**: läs och redigera kampanjrapport.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL Manage subdomains delegation]**: läsa, skapa, redigera och ta bort delegering av underdomäner.</li><li>**[!DNL Manage IP pools]**: läsa, skapa, redigera och ta bort IP-pool.</li><li>**[!DNL Manage PTR records]**: läsa och redigera PTR-poster.</li><li>**[!DNL View PTR records]**: skrivskyddad åtkomst till PTR-poster.</li><li> **[!DNL Manage messages general settings]**: läs, skapa, redigera och ta bort allmänna inställningar för meddelanden.</li><li>**[!DNL Manage messages presets]**: läsa, skapa, redigera och ta bort innehållsmärkning.</li><li>**[!DNL Manage suppression rules]**: få åtkomst till, läsa, skapa, redigera och ta bort undertryckningsregler.</li><li>**[!DNL Export suppression list]**: åtkomst till en lista över inaktiverade exportfiler som en CSV-fil.</li><li>**[!DNL View suppression list]**: läser och exporterar en lokal undertryckningslista.</li><li>**[!DNL Manage alerts]**: aktivera/inaktivera aviseringar för kampanjer, meddelanden och berättiganden.</li><li>**[!DNL Manage landing page settings]**: läsa, skapa, redigera och ta bort inställningar för landningssidor.</li><li>**[!DNL Manage SMS settings]**: läsa, skapa, redigera och ta bort SMS-inställningar.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslut.</li><li>**[!DNL Manage ranking strategies]**: läsa, skapa, redigera och ta bort rankningsstrategier.</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Sandbox]**: Ge åtkomst till sandlådor.</li><li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Read Identity namespace]**: skrivskyddad åtkomst till identitetsnamnutrymme.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort kopplingsprofiler.</li></ul> |

## [!DNL Campaign Approver] {#campaign-approver}

The **[!DNL Campaign Approver]** Med roll kan användare godkänna leveranser och publicera dem. De kan sedan kontrollera om leveransen är klar med **[!DNL Campaigns]** rapporter.

| Resurser | Behörigheter |
|-|-|
| Kampanjer | <ul><li>**[!DNL Manage campaigns]**: läs, skapa, redigera och ta bort kampanjer.</li><li>**[!DNL Publish campaigns]**: publiceringskampanjer.</li><li>**[!DNL View Campaigns report]**: läsa, redigera reserapporter.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läsa, skapa, redigera och ta bort anpassade meddelanderapporter och använda åtgärdsfunktioner.</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort kopplingsprofiler.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL View messages presets]**: skrivskyddad åtkomst till meddelandeförinställningar.</li></ul> |

## [!DNL Campaign Manager] {#campaign-manager}

The **[!DNL Campaign Manager]** roll gör att användare kan skapa och redigera **[!UICONTROL Campaigns]** och alla funktioner som är kopplade till **[!UICONTROL Campaigns]** men kommer inte att kunna publicera dem.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Kampanjer | <ul><li>**[!DNL Manage campaigns]**: läs, skapa, redigera och ta bort kampanjer.</li><li>**[!DNL View campaigns report]**: läs, redigera reserapport.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läsa, skapa, redigera och ta bort anpassade meddelanderapporter och använda åtgärdsfunktioner.</li></ul> |
| Adobe Experience Platform | <ul><li> **[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort kopplingsprofiler.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL View messages presets]**: skrivskyddad åtkomst till meddelandeförinställningar.</li></ul> |

## [!DNL Campaign Viewer] {#campaign-viewer}

The **[!DNL Campaign Viewer]** roll tillåter skrivskyddad åtkomst till **[!UICONTROL Campaigns]** och **[!UICONTROL Decision management]** funktioner.

Användare som tilldelats den här rollen kan inte redigera eller publicera.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Kampanjer | <ul><li>**[!DNL View campaigns]**: skrivskyddad åtkomst till kampanjer.</li><li>**[!DNL View campaigns report]**: skrivskyddad åtkomst till kampanjrapporter.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL View decisions]**: skrivskyddad åtkomst till beslutsentiteter.</li></ul> |

## [!DNL Journey Administrator] {#journey-administrator}

The **[!DNL Journey Administrator]** rollen gör det möjligt för administrationsmenyerna att hantera och publicera resor och beslutshantering.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Resor | <ul><li> **[!DNL Manage journeys]**: läsa, skapa, redigera och ta bort resor.</li><li>**[!DNL Publish journeys]**: publicera resor.</li><li>**[!DNL Manage journeys events, data sources and actions]**: läs, skapa, redigera och ta bort händelser, källor eller åtgärder.</li><li>**[!DNL View journeys report]**: läs och redigera reseregistrering.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL Manage subdomains delegation]**: läsa, skapa, redigera och ta bort delegering av underdomäner.</li><li>**[!DNL Manage IP pools]**: läsa, skapa, redigera och ta bort IP-pool.</li><li>**[!DNL Manage PTR records]**: läsa och redigera PTR-poster.</li><li>**[!DNL View PTR records]**: skrivskyddad åtkomst till PTR-poster.</li><li>**[!DNL Manage messages presets]**: läsa, skapa, redigera och ta bort innehållsmärkning.</li><li>**[!DNL Manage Landing page settings]**: skapa, redigera och ta bort deldomäner för landningssidor och förinställningar för landningssidor.</li><li> **[!DNL Manage messages general settings]**: läs, skapa, redigera och ta bort allmänna inställningar för meddelanden.</li><li>**[!DNL Manage SMS settings]**: skapa, redigera och ta bort API-autentiseringsuppgifter och SMS-kanalsytor som krävs för att aktivera SMS-kanalen.</li><li>**[!DNL Manage suppression rules]**: få åtkomst till, läsa, skapa, redigera och ta bort undertryckningsregler.</li><li>**[!DNL View suppression list]**: läser och exporterar en lokal undertryckningslista.</li><li>**[!DNL Manage alerts]**: aktivera/inaktivera aviseringar om resor och berättiganden.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslut.</li><li>**[!DNL Manage ranking strategies]**: läsa, skapa, redigera och ta bort rankningsstrategier.</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Sandbox]**: Ge åtkomst till sandlådor.</li><li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Read Identity namespace]**: skrivskyddad åtkomst till identitetsnamnutrymme.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort kopplingsprofiler.</li></ul> |
| Journey Optimizer Library | <ul><li>**[!DNL Manage Library Items]**: lägg till och ta bort sparade uttryck i [!DNL Journey Optimizer] Bibliotek</li></ul> |
| Datastyrning | <ul><li>**[!DNL Manage usage label]**: läsa, skapa och ta bort användningsetiketter.</li><li>**[!DNL Manage data usage policies]**: läsa, skapa, redigera och ta bort dataanvändningsprofiler.</li><li>**[!DNL View data usage policies]**: skrivskyddad åtkomst till principer för dataanvändning.</li><li>**[!DNL View user activity log]**: läsa och exportera granskningsloggar.</li></ul> |

## [!DNL Journey Approver] {#journey-approver}

The **[!DNL Journey Approver]** Med roll kan användare godkänna leveranser och publicera dem. De kan sedan kontrollera om leveransen är klar med **[!DNL Journey]** rapporter.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Resor | <ul><li>**[!DNL Manage journeys]**: läsa, skapa, redigera och ta bort resor.</li><li>**[!DNL Publish journey]**: publicera resor.</li><li>**[!DNL View journeys events, data sources and actions]**: skrivskyddad åtkomst till resehändelser, anpassade reseåtgärder och datakällor för resan.</li><li>**[!DNL View journeys report]**: läsa, redigera reserapporter.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läsa, skapa, redigera och ta bort anpassade rapporter och använda åtgärdsfunktioner.</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort kopplingsprofiler.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL View channel surfaces]**: skrivskyddad åtkomst till kanalytor.</li></ul> |

## [!DNL Journey Manager] {#journey-manager}

The **[!DNL Journey Manager]** roll gör att användare kan skapa och redigera **[!UICONTROL Journeys]** och alla funktioner som är kopplade till **[!UICONTROL Journeys]** men kommer inte att kunna publicera dem.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Resor | <ul><li>**[!DNL Manage journeys]**: läsa, skapa, redigera och ta bort resor.</li><li>**[!DNL View journeys events]**: skrivskyddad åtkomst till resehändelser, anpassade reseåtgärder och datakällor för resan.</li><li>**[!DNL View journeys report]**: läs, redigera reserapport.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läsa, skapa, redigera och ta bort anpassade rapporter och använda åtgärdsfunktioner.</li></ul> |
| Adobe Experience Platform | <ul><li> **[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort kopplingsprofiler.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL View channel surfaces]**: skrivskyddad åtkomst till kanalytor.</li></ul> |

## [!DNL Journey Viewer] {#journey-viewer}

The **[!DNL Journey viewer]** roll tillåter skrivskyddad åtkomst till **[!UICONTROL Journeys]** och **[!UICONTROL Decision management]** funktioner.

Användare som tilldelats den här rollen kan inte redigera eller publicera.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Resor | <ul><li>**[!DNL View journeys]**: skrivskyddad åtkomst till resor.</li><li>**[!DNL View journeys event, data sources, actions]**: skrivskyddad åtkomst till resehändelser och datakällor.</li><li>**[!DNL View journeys report]**: skrivskyddad åtkomst till reserapporter.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL View decisions]**: skrivskyddad åtkomst till beslutsentiteter.</li></ul> |

## [!DNL Decisioning manager] {#decisioning-manager}

The **[!DNL Decisioning manager]** rollen tillåter endast åtkomst till **[!UICONTROL Decision management]** -menyn. Användare som tilldelats den här rollen kan bara hantera, visa och publicera beslut.

Den här rollen innehåller följande behörigheter:

| Funktion | Behörigheter |
|-|-|
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL View decisions]**: skrivskyddad åtkomst till beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läsa, skapa, redigera och ta bort anpassade rapporter och använda åtgärdsfunktioner.</li><li>**[!DNL Publish decisions]**: aktivera eller inaktivera beslutsaktiviteter.</li><!--li>**[!DNL Manage Experience decisions]**: read, create, edit, and delete Experience decisioning entities.</li--></ul> |

## [!DNL Content Library Manager] {#content-library-manager}

The **[!DNL Content Library Manager]** rollen tillåter endast åtkomst till **[!UICONTROL Content templates]** -menyn. Användare som tilldelats den här rollen kan bara komma åt mallbiblioteket för att skapa innehåll utan att komma åt resor eller kampanjer.

Den här rollen innehåller följande behörigheter:

| Funktion | Behörigheter |
|-|-|
| Journey Optimizer Library | <ul><li>**[!DNL Manage library items]**: läsa, skapa, redigera och ta bort objekt i Journey Optimizer Library, inklusive innehållsmallar och fragment.</li><li>**[!DNL Manage simulate content]**: åtkomst till **[!UICONTROL Simulate content]** för förhandsgranskning och korrektur.</li><li>**[!DNL Publish Fragment]**: publicera innehållsfragment.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läsa, skapa, redigera och ta bort anpassade rapporter och använda åtgärdsfunktioner.</li></ul> |
| Adobe Experience Platform | <ul><li> **[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort kopplingsprofiler.</li></ul> |