---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer built-in Roles
description: Learn about the built-in Roles
feature: Access Management
topic: Administration
role: Admin, User
level: Intermediate
keywords: permissions, authoring, messages
exl-id: 5a968bd8-cf76-4242-aa80-3cfb3d551511
source-git-commit: ac8ccb52bd16a26c14dea148f989256e28170765
workflow-type: tm+mt
source-wordcount: '1159'
ht-degree: 5%

---

# Built-in roles {#ootb-product-profiles}

Built-in roles are a set of unitary rights which allows users access to certain functionalities or objects in the interface. Se [den här sidan](ootb-permissions.md) för en lista över tillgängliga behörigheter för att skapa din roll.

## [!DNL Campaign Administrator] {#campaign-administrator}

Med rollen **[!DNL Campaign Administrator]** kan administrationsmenyerna hantera och publicera kampanjer och beslutshantering.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Kampanjer | <ul><li> **[!DNL Manage campaigns]**: läs, skapa, redigera och ta bort kampanjer.</li><li>**[!DNL Publish campaigns]**</li><li>**[!DNL View campaigns report]**</li></ul> |
| Channel configurations | <ul><li>**[!DNL Manage subdomains delegation]**</li><li>**[!DNL Manage IP pools]**: läs, skapa, redigera och ta bort IP-pool.</li><li>**[!DNL Manage PTR records]**: läs och redigera PTR-poster.</li><li>**[!DNL View PTR records]**: skrivskyddad åtkomst till PTR-poster.</li><li> **[!DNL Manage messages general settings]**: läs, skapa, redigera och ta bort allmänna inställningar för meddelanden.</li><li>**[!DNL Manage messages presets]**: läs, skapa, redigera och ta bort innehållsmärkning.</li><li>**[!DNL Manage suppression rules]**: få åtkomst till regler för att läsa, skapa, redigera och ta bort inaktiveringar.</li><li>**[!DNL Export suppression list]**: åtkomst till en lista över undertryckande export som en CSV-fil.</li><li>**[!DNL View suppression list]**: läs och exportera en lokal undertryckningslista.</li><li>**[!DNL Manage alerts]**: aktivera/inaktivera aviseringar för kampanjer, meddelanden och berättiganden.</li><li>**[!DNL Manage landing page settings]**: läs, skapa, redigera och ta bort inställningar för landningssidor.</li><li>**[!DNL Manage SMS settings]**: läs, skapa, redigera och ta bort SMS-inställningar.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslut.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort rankningsstrategier.</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Sandbox]**: Bevilja åtkomst till sandlådor.</li><li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL Manage profiles]**</li><li>**[!DNL Read datasets]**</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Read Identity namespace]**: skrivskyddad åtkomst till identitetsnamnrymden.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul> |

## [!DNL Campaign Approver] {#campaign-approver}

Med rollen **[!DNL Campaign Approver]** kan användare godkänna leveranser och publicera dem. De kan senare kontrollera om deras leveranser är slutförda med **[!DNL Campaigns]**-rapporterna.

| Resurser | Permissions |
|-|-|
| Kampanjer | <ul><li>**[!DNL Manage campaigns]**</li><li>**[!DNL Publish campaigns]**</li><li>**[!DNL View Campaigns report]**</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**</li><li>**[!DNL Manage ranking strategies]**</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Manage segments]**</li><li>**[!DNL Manage profiles]**</li><li>**[!DNL Read datasets]**</li><li>**[!DNL Read schemas]**</li><li>**[!DNL Manage merge policies]**</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL View messages presets]**: skrivskyddad åtkomst till meddelandeförinställningar.</li></ul> |

## [!DNL Campaign Manager] {#campaign-manager}

Med rollen **[!DNL Campaign Manager]** kan användare skapa och redigera **[!UICONTROL Campaigns]** och alla funktioner som är länkade till **[!UICONTROL Campaigns]**, men de kan inte publiceras.

This role includes the following permissions:

| Resurser | Permissions |
|-|-|
| Kampanjer | <ul><li>**[!DNL Manage campaigns]**</li><li>**[!DNL View campaigns report]**</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade meddelanderapporter och använd åtgärdsfunktioner.</li></ul> |
| Adobe Experience Platform | <ul><li> **[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul> |
| Channel configurations | <ul><li>**[!DNL View messages presets]**</li></ul> |

## [!DNL Campaign Viewer] {#campaign-viewer}

**[!DNL Campaign Viewer]****[!UICONTROL Campaigns]****[!UICONTROL Decision management]**

Users assigned to this role will not be able to edit or publish.

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
| Resor | <ul><li> **[!DNL Manage journeys]**: läs, skapa, redigera och ta bort resor.</li><li>**[!DNL Publish journeys]**: publicera resor.</li><li>**[!DNL Manage journeys events, data sources and actions]**: läs, skapa, redigera och ta bort händelser, källor eller åtgärder.</li><li>**[!DNL View journeys report]**: läs och redigera reserapport.</li></ul> |
| Channel configurations | <ul><li>**[!DNL Manage subdomains delegation]**</li><li>**[!DNL Manage IP pools]**: läs, skapa, redigera och ta bort IP-pool.</li><li>**[!DNL Manage PTR records]**: läs och redigera PTR-poster.</li><li>**[!DNL View PTR records]**: skrivskyddad åtkomst till PTR-poster.</li><li>**[!DNL Manage messages presets]**: läs, skapa, redigera och ta bort innehållsmärkning.</li><li>**[!DNL Manage Landing page settings]**: skapa, redigera och ta bort deldomäner för landningssidor och förinställningar för landningssidor.</li><li> **[!DNL Manage messages general settings]**: läs, skapa, redigera och ta bort allmänna inställningar för meddelanden.</li><li>**[!DNL Manage SMS settings]**: skapa, redigera och ta bort API-autentiseringsuppgifter och SMS-kanalskonfigurationer som krävs för att aktivera SMS-kanalen.</li><li>**[!DNL Manage suppression rules]**: få åtkomst till regler för att läsa, skapa, redigera och ta bort inaktiveringar.</li><li>**[!DNL View suppression list]**: läs och exportera en lokal undertryckningslista.</li><li>**[!DNL Manage alerts]**: aktivera/inaktivera aviseringar för resor och berättiganden.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslut.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort rankningsstrategier.</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Sandbox]**</li><li>**[!DNL Manage segments]**</li><li>**[!DNL Manage profiles]**</li><li>**[!DNL Read datasets]**</li><li>**[!DNL Read schemas]**</li><li>**[!DNL Read Identity namespace]**: skrivskyddad åtkomst till identitetsnamnrymden.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul> |
| Journey Optimizer Library | <ul><li>**[!DNL Manage Library Items]**: lägg till och ta bort sparade uttryck i [!DNL Journey Optimizer]-biblioteket.</li></ul> |
| Dataförvaltning | <ul><li>**[!DNL Manage usage label]**</li><li>**[!DNL Manage data usage policies]**</li><li>**[!DNL View data usage policies]**</li><li>**[!DNL View user activity log]**</li></ul> |

## [!DNL Journey Approver] {#journey-approver}

**[!DNL Journey Approver]** **[!DNL Journey]**

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Resor | <ul><li>**[!DNL Manage journeys]**: läs, skapa, redigera och ta bort resor.</li><li>**[!DNL Publish journey]**: publicera resor.</li><li>**[!DNL View journeys events, data sources and actions]**: skrivskyddad åtkomst till resehändelser, anpassade åtgärder för resan och datakällor för resedata.</li><li>**[!DNL View journeys report]**</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**</li><li>**[!DNL Manage ranking strategies]**</li></ul> |
| Adobe Experience Platform | <ul><li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL View channel configurations]**: skrivskyddad åtkomst till kanalkonfigurationer.</li></ul> |

## [!DNL Journey Manager] {#journey-manager}

Med rollen **[!DNL Journey Manager]** kan användare skapa och redigera **[!UICONTROL Journeys]** och alla funktioner som är länkade till **[!UICONTROL Journeys]**, men de kan inte publiceras.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Resor | <ul><li>**[!DNL Manage journeys]**: läs, skapa, redigera och ta bort resor.</li><li>**[!DNL View journeys events]**</li><li>**[!DNL View journeys report]**</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**</li><li>**[!DNL Manage ranking strategies]**</li></ul> |
| Adobe Experience Platform | <ul><li> **[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL View channel configurations]**: skrivskyddad åtkomst till kanalkonfigurationer.</li></ul> |

## [!DNL Journey Viewer] {#journey-viewer}

Rollen **[!DNL Journey viewer]** tillåter skrivskyddad åtkomst till funktionerna **[!UICONTROL Journeys]** och **[!UICONTROL Decision management]**.

Användare som tilldelats den här rollen kan inte redigera eller publicera.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Resor | <ul><li>**[!DNL View journeys]**: skrivskyddad åtkomst till resor.</li><li>**[!DNL View journeys event, data sources, actions]**</li><li>**[!DNL View journeys report]**</li></ul> |
| Beslutshantering | <ul><li>**[!DNL View decisions]**</li></ul> |

## [!DNL Decisioning manager] {#decisioning-manager}

**[!DNL Decisioning manager]****[!UICONTROL Decision management]** Användare som tilldelats den här rollen kan bara hantera, visa och publicera beslut.

Den här rollen innehåller följande behörigheter:

| Funktion | Behörigheter |
|-|-|
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**</li><li>**[!DNL View decisions]**</li><li>**[!DNL Manage ranking strategies]**</li><li>**[!DNL Publish decisions]**</li><!--li>**[!DNL Manage Experience decisions]**: read, create, edit, and delete Decisioning entities.</li--></ul> |

## [!DNL Content Library Manager] {#content-library-manager}

**[!DNL Content Library Manager]****[!UICONTROL Content templates]** Users assigned to this role will only be able to access the template library to create content without accessing the journeys or campaigns.

This role includes the following permissions:

| Capability | Behörigheter |
|-|-|
| Journey Optimizer Library | <ul><li>**[!DNL Manage library items]**: läsa, skapa, redigera och ta bort objekt i Journey Optimizer-biblioteket, inklusive innehållsmallar och fragment.</li><li>**[!DNL Manage simulate content]**: åtkomst till alternativet **[!UICONTROL Simulate content]** för förhandsgranskning och korrektur.</li><li>**[!DNL Publish Fragment]**</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**</li><li>**[!DNL Manage ranking strategies]**</li></ul> |
| Adobe Experience Platform | <ul><li> **[!DNL Manage segments]**</li><li>**[!DNL Manage profiles]**</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**</li></ul> |