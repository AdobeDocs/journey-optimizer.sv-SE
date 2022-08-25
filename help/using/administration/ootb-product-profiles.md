---
title: Inbyggda produktprofiler
description: Läs om de inbyggda produktprofilerna
feature: Access Management
topic: Administration
role: Admin
level: Intermediate
exl-id: 5a968bd8-cf76-4242-aa80-3cfb3d551511
source-git-commit: 711fdf1dce0688d2e21d405a4e3e8777612b2f3b
workflow-type: tm+mt
source-wordcount: '1109'
ht-degree: 7%

---

# Inbyggda produktprofiler {#ootb-product-profiles}

Adobe Journey Optimizer har släppt en ny funktion, onlineredigering, som gör att du kan skapa och skriva meddelanden direkt under en resa. Mer information om den här nya funktionen finns på den här sidan.

>[!WARNING]
>
>Om du har användare tilldelade till **[!DNL Message Manager]** endast produktprofil, utan **[!DNL Journey manager]** produktprofil måste du tilldela en ny produktprofil så att de kan fortsätta redigera innehåll.

Den här funktionen påverkar behörigheterna enligt följande:

| Behörighetens namn | Ingår i |
|:-:|:-:|
| **[!DNL View Messages]** | **[!DNL View Journeys]** |
| **[!DNL View Message reports]** | **[!DNL View Journeys Report]** |
| **[!DNL Manage Messages]** | **[!DNL Manage Journey]** |
| **[!DNL Publish Messages]** | **[!DNL Publish Journeys]** |
| **[!DNL Manage Messages Preview and Test]** | **[!DNL Manage Journeys]** |

**Efter 25 juli**, är behörigheter för meddelanden fortfarande tillgängliga eftersom meddelanden fortfarande är tillgängliga för att aktivera övergångar och du kan fortfarande spara dem som mallar.

**Från och med 6 september**, behörigheter för meddelanden tas bort och meddelanden är inte längre tillgängliga.

## [!DNL Campaign Administrator] {#campaign-administrator}

The **[!DNL Campaign Administrator]** Med produktprofilen kan administrationsmenyerna hantera och publicera kampanjer och beslutsprocesser.

Den här produktprofilen innehåller följande behörigheter:

| Funktioner | Behörigheter| |-|-| |Kampanjer| <ul><li> **[!DNL Manage campaigns]**: läsa, skapa, redigera och ta bort kampanjer.</li><li>**[!DNL Publish campaigns]**: publicera kampanjer.</li><li>**[!DNL View campaigns report]**: läsa och redigera kampanjrapporten.</li></ul>|
|Administrering|<ul><li>**[!DNL Manage subdomains delegation]**: läsa, skapa, redigera och ta bort delegering av underdomäner.</li><li>**[!DNL Manage IP pools]**: läsa, skapa, redigera och ta bort ip-pool.</li><li>**[!DNL Manage PTR records]**: läsa och redigera PTR-poster.</li><li>**[!DNL View PTR records]**: skrivskyddad åtkomst till PTR-poster.</li><li> **[!DNL Manage messages general settings]**: läsa, skapa, redigera och ta bort allmänna inställningar för meddelanden.</li><li>**[!DNL Manage messages presets]**: läsa, skapa, redigera och ta bort innehållsmärkning.</li><li>**[!DNL Manage suppression rules]**: få åtkomst till regler för att läsa, skapa, redigera och ta bort.</li><li>**[!DNL Export suppression list]**: åtkomst till en lista över inaktiverade exportfiler som en CSV-fil.</li><li>**[!DNL View suppression list]**: läsa och exportera en lokal undertryckningslista.</li><li>**[!DNL Manage alerts]**: aktivera/inaktivera aviseringar för kampanjer, meddelanden och berättiganden.</li><li>**[!DNL Manage landing page settings]**: läsa, skapa, redigera och ta bort inställningar för landningssidor.</li><li>**[!DNL Manage SMS settings]**: läsa, skapa, redigera och ta bort SMS-inställningar.</li></ul>| |Beslutshantering|<ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslut.</li><li>**[!DNL Manage ranking strategies]**: läsa, skapa, redigera och ta bort rankningsstrategier.</li></ul>|
|Adobe Experience Platform|<ul><li>**[!DNL Sandbox]**: ge åtkomst till sandlådor.</li><li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segment.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Read Identity namespace]**: skrivskyddad åtkomst till identitetsnamnutrymmet.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul>|

## [!DNL Campaign Approver] {#campaign-approver}

The **[!DNL Campaign Approver]** Med produktprofilen kan användare godkänna leveranser och publicera dem. De kan sedan kontrollera om leveransen är klar med **[!DNL Campaigns]** rapporter.

| Funktioner | Behörigheter| |-|-| |Kampanjer| <ul><li>**[!DNL Manage campaigns]**: läsa, skapa, redigera och ta bort kampanjer.</li><li>**[!DNL Publish campaigns]**: publicera kampanjer.</li><li>**[!DNL View Campaigns report]**: läsa, redigera reserapporter.</li></ul>| |Beslutshantering| <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läsa, skapa, redigera och ta bort anpassade meddelanderapporter och använda åtgärdsfunktioner.</li></ul>| |Adobe Experience Platform| <ul><li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segment.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul>|
|Administrering| <ul><li>**[!DNL View messages presets]**: skrivskyddad åtkomst till meddelandeförinställningar.</li></ul>|

## [!DNL Campaign Manager] {#campaign-manager}

The **[!DNL Campaign Manager]** Med produktprofilen kan användare skapa och redigera **[!UICONTROL Campaigns]** och alla funktioner som är kopplade till **[!UICONTROL Campaigns]** men kommer inte att kunna publicera dem.

Den här produktprofilen innehåller följande behörigheter:

| Funktioner | Behörigheter| |-|-| |Kampanjer| <ul><li>**[!DNL Manage campaigns]**: läsa, skapa, redigera och ta bort kampanjer.</li><li>**[!DNL View campaigns report]**: läsa, redigera reserapport.</li></ul>| |Beslutshantering| <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läsa, skapa, redigera och ta bort anpassade meddelanderapporter och använda åtgärdsfunktioner.</li></ul>| |Adobe Experience Platform| <ul><li> **[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segment.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul>|
|Administrering| <ul><li>**[!DNL View messages presets]**: skrivskyddad åtkomst till meddelandeförinställningar.</li></ul>|

## [!DNL Campaign viewer] {#campaign-viewer}

The **[!DNL Campaign viewer]** produktprofilen tillåter skrivskyddad åtkomst till **[!UICONTROL Campaigns]** och **[!UICONTROL Decision management]** funktioner.

Användare som är tilldelade den här produktprofilen kan inte redigera eller publicera.

Den här produktprofilen innehåller följande behörigheter:

| Funktioner | Behörigheter| |-|-| |Kampanjer| <ul><li>**[!DNL View campaigns]**: skrivskyddad åtkomst till kampanjer.</li><li>**[!DNL View campaigns report]**: skrivskyddad åtkomst till kampanjrapporter.</li></ul>| |Beslutshantering| <ul><li>**[!DNL View decisions]**: skrivskyddad åtkomst till beslutsentiteter.</li></ul>|

## [!DNL Journey Administrator] {#journey-administrator}

The **[!DNL Journey Administrator]** produktprofilen gör det möjligt för administrationsmenyerna att hantera och publicera resor och beslutsadministration.

Den här produktprofilen innehåller följande behörigheter:

| Funktioner | Behörigheter| |-|-| |Resor| <ul><li> **[!DNL Manage journeys]**: läsa, skapa, redigera och radera resor.</li><li>**[!DNL Publish journeys]**: publicera resor.</li><li>**[!DNL Manage journeys events, data sources and actions]**: läsa, skapa, redigera och ta bort händelser, källor eller åtgärder.</li><li>**[!DNL View journeys report]**: läsa och redigera reserapport.</li></ul>|
|Administrering|<ul><li>**[!DNL Manage subdomains delegation]**: läsa, skapa, redigera och ta bort delegering av underdomäner.</li><li>**[!DNL Manage IP pools]**: läsa, skapa, redigera och ta bort ip-pool.</li><li>**[!DNL Manage PTR records]**: läsa och redigera PTR-poster.</li><li>**[!DNL View PTR records]**: skrivskyddad åtkomst till PTR-poster.</li><li>**[!DNL Manage channel surfaces]**: läsa, skapa, redigera och ta bort innehållsmärkning.</li><li>**[!DNL Manage Landing page settings]**: skapa, redigera och ta bort deldomäner för landningssidor och förinställningar för landningssidor.</li><li> **[!DNL Manage messages general settings]**: läsa, skapa, redigera och ta bort allmänna inställningar för meddelanden.</li><li>**[!DNL Manage SMS settings]**: skapa, redigera och ta bort API-autentiseringsuppgifter och SMS-kanalsytor som krävs för att aktivera SMS-kanalen.</li><li>**[!DNL Manage suppression rules]**: få åtkomst till regler för att läsa, skapa, redigera och ta bort.</li><li>**[!DNL View suppression list]**: läsa och exportera en lokal undertryckningslista.</li><li>**[!DNL Manage alerts]**: aktivera/inaktivera registreringar för resor och berättiganden.</li></ul>| |Beslutshantering|<ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslut.</li><li>**[!DNL Manage ranking strategies]**: läsa, skapa, redigera och ta bort rankningsstrategier.</li></ul>| |Adobe Experience Platform|<ul><li>**[!DNL Sandbox]**: ge åtkomst till sandlådor.</li><li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segment.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Read Identity namespace]**: skrivskyddad åtkomst till identitetsnamnutrymmet.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul>| |Journey Optimizer Library|<ul><li>**[!DNL Manage Library Items]**: lägga till och ta bort sparade uttryck i [!DNL Journey Optimizer] Bibliotek.</li></ul>|

## [!DNL Journey Approver] {#journey-approver}

The **[!DNL Journey Approver]** Med produktprofilen kan användare godkänna leveranser och publicera dem. De kan sedan kontrollera om leveransen är klar med **[!DNL Journey]** rapporter.

Den här produktprofilen innehåller följande behörigheter:

| Funktioner | Behörigheter| |-|-| |Resor| <ul><li>**[!DNL Manage journeys]**: läsa, skapa, redigera och radera resor.</li><li>**[!DNL Publish journey]**: publicera resor.</li><li>**[!DNL View journeys events, data sources and actions]**: skrivskyddad åtkomst till resehändelser, anpassade reseåtgärder och datakällor för resan.</li><li>**[!DNL View journeys report]**: läsa, redigera reserapporter.</li></ul>| |Beslutshantering| <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läsa, skapa, redigera och ta bort anpassade rapporter och använda åtgärdsfunktioner.</li></ul>| |Adobe Experience Platform| <ul><li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segment.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul>|
|Administrering| <ul><li>**[!DNL View channel surfaces]**: skrivskyddad åtkomst till kanalytor.</li></ul>|

## [!DNL Journey Manager] {#journey-manager}

The **[!DNL Journey Manager]** Med produktprofilen kan användare skapa och redigera **[!UICONTROL Journeys]** och alla funktioner som är kopplade till **[!UICONTROL Journeys]** men kommer inte att kunna publicera dem.

Den här produktprofilen innehåller följande behörigheter:

| Funktioner | Behörigheter| |-|-| |Resor| <ul><li>**[!DNL Manage journeys]**: läsa, skapa, redigera och radera resor.</li><li>**[!DNL View journeys events]**: skrivskyddad åtkomst till resehändelser, anpassade reseåtgärder och datakällor för resan.</li><li>**[!DNL View journeys report]**: läsa, redigera reserapport.</li></ul>| |Beslutshantering| <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läsa, skapa, redigera och ta bort anpassade rapporter och använda åtgärdsfunktioner.</li></ul>| |Adobe Experience Platform| <ul><li> **[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segment.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Read datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL Read schemas]**: skrivskyddad åtkomst till scheman.</li><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li></ul>|
|Administrering| <ul><li>**[!DNL View channel surfaces]**: skrivskyddad åtkomst till kanalytor.</li></ul>|

## [!DNL Journey Viewer] {#journey-viewer}

The **[!DNL Journey viewer]** produktprofilen tillåter skrivskyddad åtkomst till **[!UICONTROL Journeys]** och **[!UICONTROL Decision management]** funktioner.

Användare som är tilldelade den här produktprofilen kan inte redigera eller publicera.

Den här produktprofilen innehåller följande behörigheter:

| Funktioner | Behörigheter| |-|-| |Resor| <ul><li>**[!DNL View journeys]**: skrivskyddad åtkomst till resor.</li><li>**[!DNL View journeys event, data sources, actions]**: skrivskyddad åtkomst till resevemang och datakällor.</li><li>**[!DNL View journeys report]**: skrivskyddad åtkomst till reserapporter.</li></ul>| |Beslutshantering| <ul><li>**[!DNL View decisions]**: skrivskyddad åtkomst till beslutsentiteter.</li></ul>|

## [!DNL Decisioning manager] {#decisioning-manager}

The **[!DNL Decisioning manager]** produktprofilen tillåter bara **[!UICONTROL Decision management]** -menyn. Användare som är tilldelade den här produktprofilen kan bara hantera, visa och publicera beslut.

Den här produktprofilen innehåller följande behörigheter:

| Funktioner | Behörigheter| |-|-| |Beslutshantering| <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL View decisions]**: skrivskyddad åtkomst till beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läsa, skapa, redigera och ta bort anpassade rapporter och använda åtgärdsfunktioner.</li><li>**[!DNL Publish decisions]**: aktivera eller inaktivera beslutsaktiviteter.</li></ul>|
