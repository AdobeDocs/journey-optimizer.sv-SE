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
source-git-commit: ee2e07353762a81aadd3d63580c528f617599623
workflow-type: tm+mt
source-wordcount: '1159'
ht-degree: 5%

---

# Inbyggda roller {#ootb-product-profiles}

Inbyggda roller är en uppsättning enhetsbehörigheter som ger användarna tillgång till vissa funktioner eller objekt i gränssnittet. Se [den här sidan](ootb-permissions.md) för en lista över tillgängliga behörigheter för att skapa din roll.

## [!DNL Content Library Manager] {#content-library-manager}

Rollen **[!DNL Content Library Manager]** tillåter bara åtkomst till menyn **[!UICONTROL Content templates]**. Användare som tilldelats den här rollen kan bara komma åt mallbiblioteket för att skapa innehåll utan att komma åt resor eller kampanjer.

Den här rollen innehåller följande behörigheter:

| Funktion | Behörigheter |
|-|-|
| Journey Optimizer Library | <ul><li>**[!DNL Manage library items]**: läsa, skapa, redigera och ta bort objekt i Journey Optimizer-biblioteket, inklusive innehållsmallar och fragment.</li><li>**[!DNL Manage simulate content]**: åtkomst till alternativet **[!UICONTROL Simulate content]** för förhandsgranskning och korrektur.</li><li>**[!DNL Publish Fragment]**: publicera innehållsfragment.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade rapporter och använd åtgärdsfunktioner.</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li> **[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL View datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL View schemas]**: skrivskyddad åtkomst till scheman.</li></ul> |

## [!DNL Decisioning manager] {#decisioning-manager}

Rollen **[!DNL Decisioning manager]** tillåter bara åtkomst till menyn **[!UICONTROL Decision management]**. Användare som tilldelats den här rollen kan bara hantera, visa och publicera beslut.

Den här rollen innehåller följande behörigheter:

| Funktion | Behörigheter |
|-|-|
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade rapporter och använd åtgärdsfunktioner.</li><li>**[!DNL View decisions]**: skrivskyddad åtkomst till beslutsenheter.</li><li>**[!DNL Publish decisions]**: aktivera eller inaktivera beslutsaktiviteter.</li><!--li>**[!DNL Manage Experience decisions]**: read, create, edit, and delete Decisioning entities.</li--></ul> |

## [!DNL Campaign Administrator] {#campaign-administrator}

Med rollen **[!DNL Campaign Administrator]** kan administrationsmenyerna hantera och publicera kampanjer och beslutshantering.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Kampanjer | <ul><li> **[!DNL Manage campaigns]**: läs, skapa, redigera och ta bort kampanjer.</li><li>**[!DNL Publish campaigns]**: publiceringskampanjer.</li><li>**[!DNL View campaigns report]**: läs och redigera kampanjrapport.</li></ul> |
| Kanalkonfigurationer | <ul> <li>**[!DNL Export suppression list]**: åtkomst till en lista över undertryckande export som en CSV-fil.</li> <li>**[!DNL Manage alerts]**: aktivera/inaktivera aviseringar för kampanjer, meddelanden och berättiganden.</li> <li>**[!DNL Manage IP pools]**: läs, skapa, redigera och ta bort IP-pool.</li> <li>**[!DNL Manage landing page settings]**: läs, skapa, redigera och ta bort inställningar för landningssidor.</li> <li>**[!DNL Manage messages general settings]**: läs, skapa, redigera och ta bort allmänna inställningar för meddelanden.</li> <li>**[!DNL Manage messages presets]**: läs, skapa, redigera och ta bort innehållsmärkning.</li> <li>**[!DNL Manage PTR records]**: läs och redigera PTR-poster.</li> <li>**[!DNL Manage SMS settings]**: läs, skapa, redigera och ta bort SMS-inställningar.</li> <li>**[!DNL Manage subdomains delegation]**: läsa, skapa, redigera och ta bort underdomänsdelegering.</li> <li>**[!DNL Manage suppression rules]**: få åtkomst till regler för att läsa, skapa, redigera och ta bort inaktiveringar.</li> <li>**[!DNL View PTR records]**: skrivskyddad åtkomst till PTR-poster.</li> <li>**[!DNL View suppression list]**: läs och exportera en lokal undertryckningslista.</li> </ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslut.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort rankningsstrategier.</li></ul> |
| Adobe Experience Platform | <ul> <li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li> <li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li> <li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li> <li>**[!DNL View datasets]**: skrivskyddad åtkomst till datauppsättningar.</li> <li>**[!DNL Read Identity namespace]**: skrivskyddad åtkomst till identitetsnamnrymden.</li> <li>**[!DNL View schemas]**: skrivskyddad åtkomst till scheman.</li> <li>**[!DNL Sandbox]**: Bevilja åtkomst till sandlådor.</li> </ul> |

## [!DNL Campaign Approver] {#campaign-approver}

Med rollen **[!DNL Campaign Approver]** kan användare godkänna leveranser och publicera dem. De kan senare kontrollera om deras leveranser är slutförda med **[!DNL Campaigns]**-rapporterna.

| Resurser | Behörigheter |
|-|-|
| Kampanjer | <ul><li>**[!DNL Manage campaigns]**: läs, skapa, redigera och ta bort kampanjer.</li><li>**[!DNL Publish campaigns]**: publiceringskampanjer.</li><li>**[!DNL View campaigns report]**: läs, redigera kampanjrapporter.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade meddelanderapporter och använd åtgärdsfunktioner.</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li><li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL View datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL View schemas]**: skrivskyddad åtkomst till scheman.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL View messages presets]**: skrivskyddad åtkomst till meddelandeförinställningar.</li></ul> |

## [!DNL Campaign Manager] {#campaign-manager}

Med rollen **[!DNL Campaign Manager]** kan användare skapa och redigera **[!UICONTROL Campaigns]** och alla funktioner som är länkade till **[!UICONTROL Campaigns]**, men de kan inte publiceras.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Kampanjer | <ul><li>**[!DNL Manage campaigns]**: läs, skapa, redigera och ta bort kampanjer.</li><li>**[!DNL View campaigns report]**: läs, redigera reserapport.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade meddelanderapporter och använd åtgärdsfunktioner.</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li> **[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL View datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL View schemas]**: skrivskyddad åtkomst till scheman.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL View messages presets]**: skrivskyddad åtkomst till meddelandeförinställningar.</li></ul> |

## [!DNL Campaign Viewer] {#campaign-viewer}

Rollen **[!DNL Campaign Viewer]** tillåter skrivskyddad åtkomst till funktionerna **[!UICONTROL Campaigns]** och **[!UICONTROL Decision management]**.

Användare som tilldelats den här rollen kan inte redigera eller publicera.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Kampanjer | <ul><li>**[!DNL View campaigns]**: skrivskyddad åtkomst till kampanjer.</li><li>**[!DNL View campaigns report]**: skrivskyddad åtkomst till kampanjrapporter.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL View decisions]**: skrivskyddad åtkomst till beslutsentiteter.</li></ul> |

## [!DNL Journey Administrator] {#journey-administrator}

Med rollen **[!DNL Journey Administrator]** kan administrationsmenyerna hantera och publicera resor och beslutshantering.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Resor | <ul> <li>**[!DNL Manage journeys]**: läs, skapa, redigera och ta bort resor.</li> <li>**[!DNL Manage journeys events, data sources and actions]**: läs, skapa, redigera och ta bort händelser, källor eller åtgärder.</li> <li>**[!DNL Publish journeys]**: publicera resor.</li> <li>**[!DNL View journeys report]**: läs och redigera reserapport.</li> </ul> |
| Kanalkonfigurationer | <ul> <li>**[!DNL Manage alerts]**: aktivera/inaktivera aviseringar för resor och berättiganden.</li> <li>**[!DNL Manage IP pools]**: läs, skapa, redigera och ta bort IP-pool.</li> <li>**[!DNL Manage Landing page settings]**: skapa, redigera och ta bort deldomäner för landningssidor och förinställningar för landningssidor.</li> <li>**[!DNL Manage messages general settings]**: läs, skapa, redigera och ta bort allmänna inställningar för meddelanden.</li> <li>**[!DNL Manage messages presets]**: läs, skapa, redigera och ta bort innehållsmärkning.</li> <li>**[!DNL Manage PTR records]**: läs och redigera PTR-poster.</li> <li>**[!DNL Manage SMS settings]**: skapa, redigera och ta bort API-autentiseringsuppgifter och SMS-kanalskonfigurationer som krävs för att aktivera SMS-kanalen.</li> <li>**[!DNL Manage subdomains delegation]**: läsa, skapa, redigera och ta bort underdomänsdelegering.</li> <li>**[!DNL Manage suppression rules]**: få åtkomst till regler för att läsa, skapa, redigera och ta bort inaktiveringar.</li> <li>**[!DNL View PTR records]**: skrivskyddad åtkomst till PTR-poster.</li> <li>**[!DNL View suppression list]**: läs och exportera en lokal undertryckningslista.</li> </ul> |
| Beslutshantering | <ul> <li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslut.</li> <li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort rankningsstrategier.</li> </ul> |
| Adobe Experience Platform | <ul> <li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li> <li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li> <li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li> <li>**[!DNL View datasets]**: skrivskyddad åtkomst till datauppsättningar.</li> <li>**[!DNL Read Identity namespace]**: skrivskyddad åtkomst till identitetsnamnrymden.</li> <li>**[!DNL View schemas]**: skrivskyddad åtkomst till scheman.</li> <li>**[!DNL Sandbox]**: Bevilja åtkomst till sandlådor.</li> </ul> |
| Journey Optimizer Library | <ul> <li>**[!DNL Manage Library Items]**: lägg till och ta bort sparade uttryck i [!DNL Journey Optimizer]-biblioteket.</li> </ul> |
| Dataförvaltning | <ul> <li>**[!DNL Manage data usage policies]**: läsa, skapa, redigera och ta bort dataanvändningsprinciper.</li> <li>**[!DNL Manage usage label]**: läs, skapa och ta bort användningsetiketter.</li> <li>**[!DNL View data usage policies]**: skrivskyddad åtkomst till dataanvändningsprinciper.</li> <li>**[!DNL View user activity log]**: läs och exportera granskningsloggar.</li> </ul> |

## [!DNL Journey Approver] {#journey-approver}

Med rollen **[!DNL Journey Approver]** kan användare godkänna leveranser och publicera dem. De kan senare kontrollera om deras leveranser är slutförda med **[!DNL Journey]**-rapporterna.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Resor | <ul><li>**[!DNL Manage journeys]**: läs, skapa, redigera och ta bort resor.</li><li>**[!DNL Publish journey]**: publicera resor.</li><li>**[!DNL View journeys events, data sources and actions]**: skrivskyddad åtkomst till resehändelser, anpassade åtgärder för resan och datakällor för resedata.</li><li>**[!DNL View journeys report]**: läs, redigera reserapporter.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade rapporter och använd åtgärdsfunktioner.</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL View datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL View schemas]**: skrivskyddad åtkomst till scheman.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL View channel configurations]**: skrivskyddad åtkomst till kanalkonfigurationer.</li></ul> |

## [!DNL Journey Manager] {#journey-manager}

Med rollen **[!DNL Journey Manager]** kan användare skapa och redigera **[!UICONTROL Journeys]** och alla funktioner som är länkade till **[!UICONTROL Journeys]**, men de kan inte publiceras.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Resor | <ul><li>**[!DNL Manage journeys]**: läs, skapa, redigera och ta bort resor.</li><li>**[!DNL View journeys events]**: skrivskyddad åtkomst till resehändelser, anpassade åtgärder för resan och datakällor för resedata.</li><li>**[!DNL View journeys report]**: läs, redigera reserapport.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade rapporter och använd åtgärdsfunktioner.</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li> **[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL View datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL View schemas]**: skrivskyddad åtkomst till scheman.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL View channel configurations]**: skrivskyddad åtkomst till kanalkonfigurationer.</li></ul> |

## [!DNL Journey Viewer] {#journey-viewer}

Rollen **[!DNL Journey viewer]** tillåter skrivskyddad åtkomst till funktionerna **[!UICONTROL Journeys]** och **[!UICONTROL Decision management]**.

Användare som tilldelats den här rollen kan inte redigera eller publicera.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Resor | <ul><li>**[!DNL View journeys]**: skrivskyddad åtkomst till resor.</li><li>**[!DNL View journeys event, data sources, actions]**: skrivskyddad åtkomst till resehändelser och datakällor.</li><li>**[!DNL View journeys report]**: skrivskyddad åtkomst till reserapporter.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL View decisions]**: skrivskyddad åtkomst till beslutsentiteter.</li></ul> |

<!--
## [!DNL Orchestrated Campaign Administrators] {#orchestrated-campaign-administrator}

The **[!DNL Orchestrated Campaign Administrator]** role allows the administration menus with the possibility to manage and publish Orchestrated Campaigns. 

This role includes the following permissions:

| Resources | Permissions|
|-|-|
|Orchestrated Campaigns| <ul><li> **[!DNL Manage orchestrated campaigns]**: read, create, edit, and delete orchestrated campaigns.</li><li>**[!DNL Publish orchestrated campaigns]**: publish orchestrated campaigns.</li><li>**[!DNL View orchestrated campaigns report]**: read and edit orchestrated campaigns report.</li></ul>|
|Messages| <ul><li>**[!DNL Manage messages]**: read, create, edit, and delete messages.</li><li>**[!DNL Manage messages preview and test]**: preview and test messages before sending.</li><li>**[!DNL Publish messages]**: publish messages.</li><li>**[!DNL View messages report]**: view and edit message reports.</li></ul>|
|Channel configurations|<ul><li>**[!DNL Export suppression list]**: access to export suppression list as a CSV file.</li> <li>**[!DNL Manage alerts]**: enable/disable alerts for campaigns, messages and entitlements.</li> <li>**[!DNL Manage custom dashboards]**: read, create, edit, and delete custom dashboards.</li><li>**[!DNL Manage IP pools]**: read, create, edit, and delete ip pool.</li> <li>**[!DNL Manage landing page settings]**: read, create, edit, and delete landing page settings.</li> <li>**[!DNL Manage messages general settings]**: read, create, edit, and delete message general settings.</li> <li>**[!DNL Manage messages presets]**: read, create, edit, and delete content branding.</li> <li>**[!DNL Manage orchestrated campaign administrator]**: Read, create, edit and delete links and reconciliations between Adobe Experience Platform Profiles and Relational store entities.</li><li>**[!DNL Manage PTR records]**: read and edit PTR records.</li> <li>**[!DNL Manage SMS settings]**: read, create, edit, and delete SMS settings.</li> <li>**[!DNL Manage subdomains delegation]**: read, create, edit, and delete subdomain delegation.</li> <li>**[!DNL Manage suppression rules]**: access read, create, edit and delete suppression rules.</li> <li>**[!DNL View PTR records]**: read-only access to PTR records.</li> <li>**[!DNL View suppression list]**: read and export local suppression list.</li> </ul>|
|Decision management|<ul><li>**[!DNL Manage decisions]**: read, create, edit, and delete decisions.</li><li>**[!DNL Manage ranking strategies]**: read, create, edit, and delete ranking strategies.</li></ul>|
|Adobe Experience Platform|<ul> <li>**[!DNL Manage merge policies]**: read, create, edit, and delete merge policies.</li> <li>**[!DNL Manage profiles]**: read, create, edit, and delete profiles.</li> <li>**[!DNL Manage segments]**: read, create, edit, and delete segment definitions.</li> <li>**[!DNL View datasets]**: read-only access to datasets.</li> <li>**[!DNL View Identity namespace]**: read-only access to identity namespace.</li> <li>**[!DNL View schemas]**: read-only access to schemas.</li> <li>**[!DNL View sandbox]**: grant access to sandboxes.</li> </ul>|

## [!DNL Orchestrated Campaign Approver] {#orchestrated-campaign-approver}

The **[!DNL Orchestrated Campaign Approver]** role allows users to publish Orchestrated campaigns. 

This role includes the following permissions:

| Resources | Permissions|
|-|-|
|Orchestrated campaigns| <ul><li>**[!DNL Manage orchestrated campaigns]**: read, create, edit, and delete campaigns.</li><li>**[!DNL Publish orchestrated campaigns]**: publish campaigns.</li><li>**[!DNL View orchestrated campaigns report]**: read orchestrated campaign reports.</li></ul>|
|Messages| <ul><li>**[!DNL Manage messages]**: read, create, edit, and delete messages.</li><li>**[!DNL Manage messages preview and test]**: preview and test messages before sending.</li><li>**[!DNL Publish messages]**: publish messages.</li><li>**[!DNL View messages report]**: view and edit message reports.</li></ul>|
|Decision management| <ul><li>**[!DNL Manage decisions]**: read, create, edit, and delete decisioning entities.</li><li>**[!DNL Manage ranking strategies]**: read, create, edit, and delete custom messages reports and use action features.</li></ul>|
|Adobe Experience Platform|<ul> <li>**[!DNL Manage segments]**: read, create, edit, and delete segment definitions.</li> <li>**[!DNL Manage profiles]**: read, create, edit, and delete profiles.</li> <li>**[!DNL View datasets]**: read-only access to datasets.</li> <li>**[!DNL View schemas]**: read-only access to schemas.</li> <li>**[!DNL Manage merge policies]**: read, create, edit, and delete merge policies.</li> <li>**[!DNL Enable AI Assistant]**: enable or access AI-powered campaign and audience features.</li>  <li>**[!DNL View operational insights]**: read-only access to system-level insights and monitoring dashboards.</li></ul>|
|Channel configurations|<ul><li>**[!DNL Manage custom dashboards]**: create, edit, and delete custom dashboards.</li> <li>**[!DNL View messages presets]**: read-only access to messages presets.</li><li>**[!DNL View orchestrated campaigns admin]**: Read-only access to links and reconciliations between Adobe Experience Platform Profiles and Relational store entities section.</li> </ul>|

## [!DNL Orchestrated Campaign Manager] {#orchestrated-campaign-manager}

The **[!DNL Orchestrated Campaign Manager]** role allows users to create and edit **[!UICONTROL Orchestrated campaigns]** and every capability linked to **[!UICONTROL Orchestrated campaigns]** but will not be able to publish them.

This role includes the following permissions:

| Resources | Permissions|
|-|-|
|Orchestrated campaigns| <ul><li>**[!DNL Manage orchestrated campaigns]**: read, create, edit, and delete campaigns.</li><li>**[!DNL View orchestrated campaigns report]**: read orchestrated campaigns report.</li></ul>|
|Messages| <ul><li>**[!DNL Manage messages]**: read, create, edit, and delete messages.</li><li>**[!DNL Manage messages preview and test]**: preview and test messages before sending.</li><li>**[!DNL View messages report]**: view and edit message reports.</li></ul>|
|Decision management| <ul><li>**[!DNL Manage decisions]**: read, create, edit, and delete decisioning entities.</li><li>**[!DNL Manage ranking strategies]**: read, create, edit, and delete custom messages reports and use action features.</li></ul>|
|Adobe Experience Platform| <ul><li>**[!DNL Enable AI Assistant]**: enable or access AI-powered campaign and audience features.</li> <li>**[!DNL Manage merge policies]**: read, create, edit, and delete merge policies.</li><li>**[!DNL Manage profiles]**: read, create, edit, and delete profiles.</li><li> **[!DNL Manage segments]**: read, create, edit, and delete segment definitions.</li><li>**[!DNL View datasets]**: read-only access to datasets.</li>  <li>**[!DNL View operational insights]**: read-only access to system-level insights and monitoring dashboards.</li><li>**[!DNL View schemas]**: read-only access to schemas.</li></ul>|
|Channel configurations| <ul><li>**[!DNL Manage custom dashboards]**: create, edit, and delete custom dashboards.</li><li>**[!DNL View messages presets]**: read-only access to messages presets.</li><li>**[!DNL View orchestrated campaigns admin]**: Read-only access to links and reconciliations between Adobe Experience Platform Profiles and Relational store entities section.</li></ul>|

## [!DNL Orchestrated Campaign Viewer] {#orchestrated-campaign-viewer}

The **[!DNL Campaign Viewer]** role allows read-only access to the **[!UICONTROL Orchestrated campaigns]** capabilities. 

Users assigned to this role will not be able to edit or publish. 

This role includes the following permissions:

| Resources | Permissions|
|-|-|
|Orchestrated campaigns| <ul><li>**[!DNL View orchestrated campaigns]**: read-only access to campaigns.</li><li>**[!DNL View orchestrated campaigns report]**: read-only access to campaigns reports.</li></ul>|
|Messages|<ul><li>**[!DNL View messages]**: view messages.</li><li>**[!DNL View messages report]**: view and edit message reports.</li></ul>|
|Decision management| <ul><li>**[!DNL View decisions]**: read-only access to decisions entities.</li></ul>|
|Adobe Experience Platform| <ul><li>**[!DNL Enable AI Assistant]**: enable or access AI-powered campaign and audience features.</li> <li>**[!DNL View operational insights]**: read-only access to system-level insights and monitoring dashboards.</li></ul>|
|Channel configurations| <ul><li>**[!DNL Manage custom dashboards]**: create, edit, and delete custom dashboards.</li><li>**[!DNL View orchestrated campaigns admin]**: Read-only access to links and reconciliations between Adobe Experience Platform Profiles and Relational store entities section.</li></ul>|

-->