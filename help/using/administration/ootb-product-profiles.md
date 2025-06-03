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
source-git-commit: 49a607e8e4b4cce7bcf41d92abe6b9fa54dfb411
workflow-type: tm+mt
source-wordcount: '1159'
ht-degree: 5%

---

# Inbyggda roller {#ootb-product-profiles}

Inbyggda roller är en uppsättning enhetsbehörigheter som ger användarna tillgång till vissa funktioner eller objekt i gränssnittet. Se [den här sidan](ootb-permissions.md) för en lista över tillgängliga behörigheter för att skapa din roll.

## [!DNL Campaign Administrator] {#campaign-administrator}

Med rollen **[!DNL Campaign Administrator]** kan administrationsmenyerna hantera och publicera kampanjer och beslutshantering.

Den här behörigheten innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Kampanjer | <ul><li> **[!DNL Manage campaigns]**: läs, skapa, redigera och ta bort kampanjer.</li><li>**[!DNL Publish campaigns]**: publiceringskampanjer.</li><li>**[!DNL View campaigns report]**: läs och redigera kampanjrapport.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL Manage subdomains delegation]**: läsa, skapa, redigera och ta bort underdomänsdelegering.</li><li>**[!DNL Manage IP pools]**: läs, skapa, redigera och ta bort IP-pool.</li><li>**[!DNL Manage PTR records]**: läs och redigera PTR-poster.</li><li>**[!DNL View PTR records]**: skrivskyddad åtkomst till PTR-poster.</li><li> **[!DNL Manage messages general settings]**: läs, skapa, redigera och ta bort allmänna inställningar för meddelanden.</li><li>**[!DNL Manage messages presets]**: läs, skapa, redigera och ta bort innehållsmärkning.</li><li>**[!DNL Manage suppression rules]**: få åtkomst till regler för att läsa, skapa, redigera och ta bort inaktiveringar.</li><li>**[!DNL Export suppression list]**: åtkomst till en lista över undertryckande export som en CSV-fil.</li><li>**[!DNL View suppression list]**: läs och exportera en lokal undertryckningslista.</li><li>**[!DNL Manage alerts]**: aktivera/inaktivera aviseringar för kampanjer, meddelanden och berättiganden.</li><li>**[!DNL Manage landing page settings]**: läs, skapa, redigera och ta bort inställningar för landningssidor.</li><li>**[!DNL Manage SMS settings]**: läs, skapa, redigera och ta bort SMS-inställningar.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslut.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort rankningsstrategier.</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Sandbox]**: Bevilja åtkomst till sandlådor.</li><li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Read Identity namespace]**: skrivskyddad åtkomst till identitetsnamnrymden.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul> |

## [!DNL Campaign Approver] {#campaign-approver}

Med rollen **[!DNL Campaign Approver]** kan användare godkänna leveranser och publicera dem. De kan senare kontrollera om deras leveranser är slutförda med **[!DNL Campaigns]**-rapporterna.

| Resurser | Behörigheter |
|-|-|
| Kampanjer | <ul><li>**[!DNL Manage campaigns]**: läs, skapa, redigera och ta bort kampanjer.</li><li>**[!DNL Publish campaigns]**: publiceringskampanjer.</li><li>**[!DNL View Campaigns report]**: läs, redigera reserapporter.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade meddelanderapporter och använd åtgärdsfunktioner.</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL View messages presets]**: skrivskyddad åtkomst till meddelandeförinställningar.</li></ul> |

## [!DNL Campaign Manager] {#campaign-manager}

Med rollen **[!DNL Campaign Manager]** kan användare skapa och redigera **[!UICONTROL Campaigns]** och alla funktioner som är länkade till **[!UICONTROL Campaigns]**, men de kan inte publiceras.

Den här behörigheten innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Kampanjer | <ul><li>**[!DNL Manage campaigns]**: läs, skapa, redigera och ta bort kampanjer.</li><li>**[!DNL View campaigns report]**: läs, redigera reserapport.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade meddelanderapporter och använd åtgärdsfunktioner.</li></ul> |
| Adobe Experience Platform | <ul><li> **[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL View messages presets]**: skrivskyddad åtkomst till meddelandeförinställningar.</li></ul> |

## [!DNL Campaign Viewer] {#campaign-viewer}

Rollen **[!DNL Campaign Viewer]** tillåter skrivskyddad åtkomst till funktionerna **[!UICONTROL Campaigns]** och **[!UICONTROL Decision management]**.

Användare som tilldelats den här rollen kan inte redigera eller publicera.

Den här behörigheten innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Kampanjer | <ul><li>**[!DNL View campaigns]**: skrivskyddad åtkomst till kampanjer.</li><li>**[!DNL View campaigns report]**: skrivskyddad åtkomst till kampanjrapporter.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL View decisions]**: skrivskyddad åtkomst till beslutsentiteter.</li></ul> |

## [!DNL Journey Administrator] {#journey-administrator}

Med rollen **[!DNL Journey Administrator]** kan administrationsmenyerna hantera och publicera resor och beslutshantering.

Den här behörigheten innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Resor | <ul><li> **[!DNL Manage journeys]**: läs, skapa, redigera och ta bort resor.</li><li>**[!DNL Publish journeys]**: publicera resor.</li><li>**[!DNL Manage journeys events, data sources and actions]**: läs, skapa, redigera och ta bort händelser, källor eller åtgärder.</li><li>**[!DNL View journeys report]**: läs och redigera reserapport.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL Manage subdomains delegation]**: läsa, skapa, redigera och ta bort underdomänsdelegering.</li><li>**[!DNL Manage IP pools]**: läs, skapa, redigera och ta bort IP-pool.</li><li>**[!DNL Manage PTR records]**: läs och redigera PTR-poster.</li><li>**[!DNL View PTR records]**: skrivskyddad åtkomst till PTR-poster.</li><li>**[!DNL Manage messages presets]**: läs, skapa, redigera och ta bort innehållsmärkning.</li><li>**[!DNL Manage Landing page settings]**: skapa, redigera och ta bort deldomäner för landningssidor och förinställningar för landningssidor.</li><li> **[!DNL Manage messages general settings]**: läs, skapa, redigera och ta bort allmänna inställningar för meddelanden.</li><li>**[!DNL Manage SMS settings]**: skapa, redigera och ta bort API-autentiseringsuppgifter och SMS-kanalskonfigurationer som krävs för att aktivera SMS-kanalen.</li><li>**[!DNL Manage suppression rules]**: få åtkomst till regler för att läsa, skapa, redigera och ta bort inaktiveringar.</li><li>**[!DNL View suppression list]**: läs och exportera en lokal undertryckningslista.</li><li>**[!DNL Manage alerts]**: aktivera/inaktivera aviseringar för resor och berättiganden.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslut.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort rankningsstrategier.</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Sandbox]**: Bevilja åtkomst till sandlådor.</li><li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Read Identity namespace]**: skrivskyddad åtkomst till identitetsnamnrymden.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul> |
| Journey Optimizer Library | <ul><li>**[!DNL Manage Library Items]**: lägg till och ta bort sparade uttryck i [!DNL Journey Optimizer]-biblioteket.</li></ul> |
| Dataförvaltning | <ul><li>**[!DNL Manage usage label]**: läs, skapa och ta bort användningsetiketter.</li><li>**[!DNL Manage data usage policies]**: läsa, skapa, redigera och ta bort dataanvändningsprinciper.</li><li>**[!DNL View data usage policies]**: skrivskyddad åtkomst till dataanvändningsprinciper.</li><li>**[!DNL View user activity log]**: läs och exportera granskningsloggar.</li></ul> |

## [!DNL Journey Approver] {#journey-approver}

Med rollen **[!DNL Journey Approver]** kan användare godkänna leveranser och publicera dem. De kan senare kontrollera om deras leveranser är slutförda med **[!DNL Journey]**-rapporterna.

Den här behörigheten innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Resor | <ul><li>**[!DNL Manage journeys]**: läs, skapa, redigera och ta bort resor.</li><li>**[!DNL Publish journey]**: publicera resor.</li><li>**[!DNL View journeys events, data sources and actions]**: skrivskyddad åtkomst till resehändelser, anpassade åtgärder för resan och datakällor för resedata.</li><li>**[!DNL View journeys report]**: läs, redigera reserapporter.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade rapporter och använd åtgärdsfunktioner.</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL View channel configurations]**: skrivskyddad åtkomst till kanalkonfigurationer.</li></ul> |

## [!DNL Journey Manager] {#journey-manager}

Med rollen **[!DNL Journey Manager]** kan användare skapa och redigera **[!UICONTROL Journeys]** och alla funktioner som är länkade till **[!UICONTROL Journeys]**, men de kan inte publiceras.

Den här behörigheten innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Resor | <ul><li>**[!DNL Manage journeys]**: läs, skapa, redigera och ta bort resor.</li><li>**[!DNL View journeys events]**: skrivskyddad åtkomst till resehändelser, anpassade åtgärder för resan och datakällor för resedata.</li><li>**[!DNL View journeys report]**: läs, redigera reserapport.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade rapporter och använd åtgärdsfunktioner.</li></ul> |
| Adobe Experience Platform | <ul><li> **[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL View channel configurations]**: skrivskyddad åtkomst till kanalkonfigurationer.</li></ul> |

## [!DNL Journey Viewer] {#journey-viewer}

Rollen **[!DNL Journey viewer]** tillåter skrivskyddad åtkomst till funktionerna **[!UICONTROL Journeys]** och **[!UICONTROL Decision management]**.

Användare som tilldelats den här rollen kan inte redigera eller publicera.

Den här behörigheten innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Resor | <ul><li>**[!DNL View journeys]**: skrivskyddad åtkomst till resor.</li><li>**[!DNL View journeys event, data sources, actions]**: skrivskyddad åtkomst till resehändelser och datakällor.</li><li>**[!DNL View journeys report]**: skrivskyddad åtkomst till reserapporter.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL View decisions]**: skrivskyddad åtkomst till beslutsentiteter.</li></ul> |

## [!DNL Decisioning manager] {#decisioning-manager}

Rollen **[!DNL Decisioning manager]** tillåter bara åtkomst till menyn **[!UICONTROL Decision management]**. Användare som tilldelats den här rollen kan bara hantera, visa och publicera beslut.

Den här behörigheten innehåller följande behörigheter:

| Funktion | Behörigheter |
|-|-|
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL View decisions]**: skrivskyddad åtkomst till beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade rapporter och använd åtgärdsfunktioner.</li><li>**[!DNL Publish decisions]**: aktivera eller inaktivera beslutsaktiviteter.</li><!--li>**[!DNL Manage Experience decisions]**: read, create, edit, and delete Decisioning entities.</li--></ul> |

## [!DNL Content Library Manager] {#content-library-manager}

Rollen **[!DNL Content Library Manager]** tillåter bara åtkomst till menyn **[!UICONTROL Content templates]**. Användare som tilldelats den här rollen kan bara komma åt mallbiblioteket för att skapa innehåll utan att komma åt resor eller kampanjer.

Den här behörigheten innehåller följande behörigheter:

| Funktion | Behörigheter |
|-|-|
| Journey Optimizer Library | <ul><li>**[!DNL Manage library items]**: läsa, skapa, redigera och ta bort objekt i Journey Optimizer-biblioteket, inklusive innehållsmallar och fragment.</li><li>**[!DNL Manage simulate content]**: åtkomst till alternativet **[!UICONTROL Simulate content]** för förhandsgranskning och korrektur.</li><li>**[!DNL Publish Fragment]**: publicera innehållsfragment.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade rapporter och använd åtgärdsfunktioner.</li></ul> |
| Adobe Experience Platform | <ul><li> **[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul> |