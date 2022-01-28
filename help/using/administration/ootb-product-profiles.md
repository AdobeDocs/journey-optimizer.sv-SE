---
title: Inbyggda produktprofiler
description: Läs om de inbyggda produktprofilerna
feature: Control Groups
topic: Administration
role: Admin
level: Intermediate
exl-id: 5a968bd8-cf76-4242-aa80-3cfb3d551511
source-git-commit: bbeecbacb4838dfb0794d5625eb2774cf4b983ef
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 7%

---

# Inbyggda produktprofiler {#ootb-product-profiles}

## [!DNL Journey Administrator] {#journey-administrator}

The **[!DNL Journey Administrator]** Med produktprofilen kan administrationsmenyerna hantera och publicera resor, meddelanden och beslutsunderlag.

Den här produktprofilen innehåller följande behörigheter:

| Funktioner | Behörigheter| |-|-| |Resor| <ul><li> **[!DNL Manage journeys]**: läsa, skapa, redigera och radera resor.</li><li>**[!DNL Publish journeys]**: publicera resor.</li><li>**[!DNL Manage journeys events, data sources and actions]**: läsa, skapa, redigera och ta bort händelser, källor eller åtgärder.</li><li>**[!DNL View journeys report]**: läsa och redigera reserapport.</li></ul>| |Meddelanden|<ul><li> **[!DNL Manage messages]**: läsa, skapa, redigera förhandsgranskning av meddelanden och skicka test/korrektur.</li><li>**[!DNL Manage messages preview and test]**: publicera meddelanden.</li><li>**[!DNL Publish messages]**: läsa, skapa och redigera förhandsgranskning av meddelanden och skicka test/korrektur.</li><li>**[!DNL View messages report]**: läsa och redigera meddelanderapport.</li></ul>|
|Administrering|<ul><li>**[!DNL Manage subdomains delegation]**: läsa, skapa, redigera och ta bort delegering av underdomäner.</li><li>**[!DNL Manage IP pools]**: läsa, skapa, redigera och ta bort ip-pool.</li><li>**[!DNL Manage PTR records]**: läsa, skapa, redigera och ta bort PTR-poster.</li><li>**[!DNL View PTR records]**: skrivskyddad åtkomst till PTR-poster.</li><li> **[!DNL Manage messages general settings]**: läsa, skapa, redigera och ta bort allmänna inställningar för meddelanden.</li><li>**[!DNL Manage messages presets]**: läsa, skapa, redigera och ta bort innehållsmärkning.</li><li>**[!DNL Manage suppression rules]**: få åtkomst till regler för att läsa, skapa, redigera och ta bort.</li><li>**[!DNL View suppression list]**: läsa och exportera en lokal undertryckningslista.</li><li>**[!DNL Manage alerts]**: aktivera/inaktivera varningar för resor, meddelanden och berättiganden.</li></ul>| |Beslutshantering|<ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslut.</li><li>**[!DNL Manage ranking strategies]**: läsa, skapa, redigera och ta bort anpassade meddelanderapporter och använda åtgärdsfunktioner.</li></ul>|
|Adobe Experience Platform|<ul><li>**[!DNL Sandbox]**: ge åtkomst till sandlådor.</li><li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segment.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Read Identity namespace]**: skrivskyddad åtkomst till identitetsnamnutrymmet.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul>|

## [!DNL Journey Approver] {#journey-approver}

The **[!DNL Journey Approver]** Med produktprofilen kan användare godkänna leveranser och publicera dem. De kan sedan kontrollera om leveransen är klar med **[!DNL Message]** och **[!DNL Journey]** rapporter.

Den här produktprofilen innehåller följande behörigheter:

| Funktioner | Behörigheter| |-|-| |Resor| <ul><li>**[!DNL Manage journeys]**: läsa, skapa, redigera och radera resor.</li><li>**[!DNL Publish journey]**: publicera resor.</li><li>**[!DNL View journeys events, data sources and actions]**: skrivskyddad åtkomst till resehändelser, anpassade reseåtgärder och datakällor för resan.</li><li>**[!DNL View journeys report]**: läsa, redigera reserapporter.</li></ul>| |Meddelanden| <ul><li>**[!DNL Manage messages]**: läsa, skapa, redigera och ta bort meddelanden.</li><li>**[!DNL Publish messages]** publicera meddelanden.</li><li>**[!DNL Manage messages preview and test]**: läsa, skapa och redigera förhandsgranskning av meddelanden och skicka test/korrektur.</li><li>**[!DNL View messages report]**: läsa, skapa, redigera och ta bort meddelanderapport.</li></ul>| |Beslutshantering| <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läsa, skapa, redigera och ta bort anpassade meddelanderapporter och använda åtgärdsfunktioner.</li></ul>| |Adobe Experience Platform| <ul><li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segment.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul>|
|Administrering| <ul><li>**[!DNL View messages presets]**: skrivskyddad åtkomst till meddelandeförinställningar.</li></ul>|

## [!DNL Journey Manager] {#journey-manager}

The **[!DNL Journey Manager]** Med produktprofilen kan användare skapa och redigera **[!UICONTROL Journeys]** och alla funktioner som är kopplade till **[!UICONTROL Journeys]** men kommer inte att kunna publicera dem.

Den här produktprofilen innehåller följande behörigheter:

| Funktioner | Behörigheter| |-|-| |Resor| <ul><li>**[!DNL Manage journeys]**: läsa, skapa, redigera och radera resor.</li><li>**[!DNL View journeys events]**: skrivskyddad åtkomst till resehändelser, anpassade reseåtgärder och datakällor för resan.</li><li>**[!DNL View journeys report]**: läsa, redigera reserapport.</li></ul>| |Meddelanden| <ul><li>**[!DNL Manage messages]**: läsa, skapa, redigera och ta bort meddelanden.</li><li> **[!DNL Manage messages preview and test]**: läsa, skapa och redigera förhandsgranskning av meddelanden och skicka test/korrektur.</li><li>**[!DNL View messages report]**: läsa, skapa, redigera och ta bort meddelanderapport.</li></ul>| |Beslutshantering| <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läsa, skapa, redigera och ta bort anpassade meddelanderapporter och använda åtgärdsfunktioner.</li></ul>| |Adobe Experience Platform| <ul><li> **[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segment.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul>|
|Administrering| <ul><li>**[!DNL View messages presets]**: skrivskyddad åtkomst till meddelandeförinställningar.</li></ul>|

## [!DNL Journey viewer] {#journey-viewer}

The **[!DNL Journey viewer]** produktprofilen tillåter skrivskyddad åtkomst till **[!UICONTROL Journeys]**, **[!UICONTROL Goals]**, **[!UICONTROL Messages]** och **[!UICONTROL Decision management]** funktioner.

Användare som är tilldelade den här produktprofilen kan inte redigera eller publicera.

Den här produktprofilen innehåller följande behörigheter:

| Funktioner | Behörigheter| |-|-| |Resor| <ul><li>**[!DNL View journeys]**: skrivskyddad åtkomst till resor.</li><li>**[!DNL View journeys event, data sources, actions]**: skrivskyddad åtkomst till resevemang och datakällor.</li><li>**[!DNL View journeys report]**: skrivskyddad åtkomst till reserapporter.</li></ul>| |Meddelanden| <ul><li>**[!DNL View messages]**: skrivskyddad åtkomst till meddelanden.</li><li>**[!DNL View messages report]**: skrivskyddad åtkomst till meddelanderapporter.</li></ul>| |Beslutshantering| <ul><li>**[!DNL View decisions]**: skrivskyddad åtkomst till beslutsentiteter.</li></ul>|

## [!DNL Message Manager] {#message-manager}

The **[!DNL Message Manager]** Med produktprofilen kan användare skapa och redigera **[!UICONTROL Messages]** och **[!UICONTROL Decision management]** men kommer inte att kunna publicera dem.

Den här produktprofilen innehåller följande behörigheter:

| Funktioner | Behörigheter| |-|-| |Resor| <ul><li>**[!DNL View journeys]**: skrivskyddad åtkomst till resor.</li><li>**[!DNL View Journeys events, data sources and actions]**: skrivskyddad åtkomst till resehändelser, anpassade reseåtgärder och datakällor för resan.</li></ul>| |Meddelanden| <ul><li>**[!DNL Manage messages]**: läsa, skapa, redigera och ta bort meddelanden.</li><li>**[!DNL Manage messages preview and test]**: läsa, skapa och redigera förhandsgranskning av meddelanden och skicka test/korrektur.</li><li> **[!DNL View messages report]**: läsa, skapa, redigera och ta bort meddelanderapporter.</li></ul>| |Beslutshantering| <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li></ul>| |Adobe Experience Platform| <ul><li>**[!DNL Read profiles]**: skrivskyddad åtkomst till profil för förhandsgranskning och testning.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul>|
|Administrering| <ul><li>**[!DNL View messages presets]**: skrivskyddad åtkomst till meddelandeförinställningar.</li></ul>|

## [!DNL Decisioning manager] {#decisioning-manager}

The **[!DNL Decisioning manager]** produktprofilen tillåter bara **[!UICONTROL Decision management]** -menyn. Användare som är tilldelade den här produktprofilen kan bara hantera, visa och publicera beslut.

Den här produktprofilen innehåller följande behörigheter:

| Funktioner | Behörigheter| |-|-| |Beslutshantering| <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL View decisions]**: skrivskyddad åtkomst till beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läsa, skapa, redigera och ta bort anpassade meddelanderapporter och använda åtgärdsfunktioner.</li><li>**[!DNL Publish decisions]**: aktivera eller inaktivera beslutsaktiviteter.</li></ul>|
