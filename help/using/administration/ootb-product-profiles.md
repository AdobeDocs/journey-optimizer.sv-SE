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
source-git-commit: a91d5c6a22f81411d7a9acbe2bbc8e86c1a4da13
workflow-type: tm+mt
source-wordcount: '2009'
ht-degree: 5%

---

# Inbyggda roller {#ootb-product-profiles}

Inbyggda roller är en uppsättning enhetsbehörigheter som ger användarna tillgång till vissa funktioner eller objekt i gränssnittet. Se [den här sidan](ootb-permissions.md) för en lista över tillgängliga behörigheter för att skapa din roll.


## [!DNL Campaign Administrator] {#campaign-administrator}

Med rollen **[!DNL Campaign Administrator]** kan administrationsmenyerna hantera och publicera kampanjer och beslutshantering.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Adobe Experience Platform | <ul> <li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li> <li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li> <li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li> <li>**[!DNL View datasets]**: skrivskyddad åtkomst till datauppsättningar.</li> <li>**[!DNL Read Identity namespace]**: skrivskyddad åtkomst till identitetsnamnrymden.</li> <li>**[!DNL View schemas]**: skrivskyddad åtkomst till scheman.</li> <li>**[!DNL Sandbox]**: Bevilja åtkomst till sandlådor.</li> </ul> |
| Kampanjer | <ul><li> **[!DNL Manage campaigns]**: läs, skapa, redigera och ta bort kampanjer.</li><li>**[!DNL Publish campaigns]**: publiceringskampanjer.</li><li>**[!DNL View campaigns report]**: läs och redigera kampanjrapport.</li></ul> |
| Kanalkonfigurationer | <ul> <li>**[!DNL Export suppression list]**: åtkomst till en lista över undertryckande export som en CSV-fil.</li> <li>**[!DNL Manage alerts]**: aktivera/inaktivera aviseringar för kampanjer, meddelanden och berättiganden.</li> <li>**[!DNL Manage IP pools]**: läs, skapa, redigera och ta bort IP-pool.</li> <li>**[!DNL Manage landing page settings]**: läs, skapa, redigera och ta bort inställningar för landningssidor.</li> <li>**[!DNL Manage messages general settings]**: läs, skapa, redigera och ta bort allmänna inställningar för meddelanden.</li> <li>**[!DNL Manage messages presets]**: läs, skapa, redigera och ta bort innehållsmärkning.</li> <li>**[!DNL Manage PTR records]**: läs och redigera PTR-poster.</li> <li>**[!DNL Manage SMS settings]**: läs, skapa, redigera och ta bort SMS-inställningar.</li> <li>**[!DNL Manage subdomains delegation]**: läsa, skapa, redigera och ta bort underdomänsdelegering.</li> <li>**[!DNL Manage suppression rules]**: få åtkomst till regler för att läsa, skapa, redigera och ta bort inaktiveringar.</li> <li>**[!DNL View PTR records]**: skrivskyddad åtkomst till PTR-poster.</li> <li>**[!DNL View suppression list]**: läs och exportera en lokal undertryckningslista.</li> </ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslut.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort rankningsstrategier.</li></ul> |

## [!DNL Campaign Approver] {#campaign-approver}

Med rollen **[!DNL Campaign Approver]** kan användare godkänna leveranser och publicera dem. De kan senare kontrollera om deras leveranser är slutförda med **[!DNL Campaigns]**-rapporterna.

| Resurser | Behörigheter |
|-|-|
| Adobe Experience Platform | <ul><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li><li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL View datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL View schemas]**: skrivskyddad åtkomst till scheman.</li></ul> |
| Kampanjer | <ul><li>**[!DNL Manage campaigns]**: läs, skapa, redigera och ta bort kampanjer.</li><li>**[!DNL Publish campaigns]**: publiceringskampanjer.</li><li>**[!DNL View campaigns report]**: läs, redigera kampanjrapporter.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL View messages presets]**: skrivskyddad åtkomst till meddelandeförinställningar.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade meddelanderapporter och använd åtgärdsfunktioner.</li></ul> |


## [!DNL Campaign Manager] {#campaign-manager}

Med rollen **[!DNL Campaign Manager]** kan användare skapa och redigera **[!UICONTROL Campaigns]** och alla funktioner som är länkade till **[!UICONTROL Campaigns]**, men de kan inte publiceras.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Adobe Experience Platform | <ul><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li> **[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL View datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL View schemas]**: skrivskyddad åtkomst till scheman.</li></ul> |
| Kampanjer | <ul><li>**[!DNL Manage campaigns]**: läs, skapa, redigera och ta bort kampanjer.</li><li>**[!DNL View campaigns report]**: läs, redigera reserapport.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL View messages presets]**: skrivskyddad åtkomst till meddelandeförinställningar.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade meddelanderapporter och använd åtgärdsfunktioner.</li></ul> |

## [!DNL Campaign Viewer] {#campaign-viewer}

Rollen **[!DNL Campaign Viewer]** tillåter skrivskyddad åtkomst till funktionerna **[!UICONTROL Campaigns]** och **[!UICONTROL Decision management]**.

Användare som tilldelats den här rollen kan inte redigera eller publicera.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Kampanjer | <ul><li>**[!DNL View campaigns]**: skrivskyddad åtkomst till kampanjer.</li><li>**[!DNL View campaigns report]**: skrivskyddad åtkomst till kampanjrapporter.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL View decisions]**: skrivskyddad åtkomst till beslutsentiteter.</li></ul> |

## [!DNL Content Library Manager] {#content-library-manager}

Rollen **[!DNL Content Library Manager]** tillåter bara åtkomst till menyn **[!UICONTROL Content templates]**. Användare som tilldelats den här rollen kan bara komma åt mallbiblioteket för att skapa innehåll utan att komma åt resor eller kampanjer.

Den här behörigheten innehåller följande behörigheter:

| Funktion | Behörigheter |
|-|-|
| Adobe Experience Platform | <ul><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li> **[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL View datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL View schemas]**: skrivskyddad åtkomst till scheman.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade rapporter och använd åtgärdsfunktioner.</li></ul> |
| Journey Optimizer Library | <ul><li>**[!DNL Manage library items]**: läsa, skapa, redigera och ta bort objekt i Journey Optimizer-biblioteket, inklusive innehållsmallar och fragment.</li><li>**[!DNL Manage simulate content]**: åtkomst till alternativet **[!UICONTROL Simulate content]** för förhandsgranskning och korrektur.</li><li>**[!DNL Publish Fragment]**: publicera innehållsfragment.</li></ul> |

## [!DNL Decisioning manager] {#decisioning-manager}

Rollen **[!DNL Decisioning manager]** tillåter bara åtkomst till menyn **[!UICONTROL Decision management]**. Användare som tilldelats den här rollen kan bara hantera, visa och publicera beslut.

Den här behörigheten innehåller följande behörigheter:

| Funktion | Behörigheter |
|-|-|
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade rapporter och använd åtgärdsfunktioner.</li><li>**[!DNL View decisions]**: skrivskyddad åtkomst till beslutsenheter.</li><li>**[!DNL Publish decisions]**: aktivera eller inaktivera beslutsaktiviteter.</li><!--li>**[!DNL Manage Experience decisions]**: read, create, edit, and delete Decisioning entities.</li--></ul> |

## [!DNL Journey Administrator] {#journey-administrator}

Med rollen **[!DNL Journey Administrator]** kan administrationsmenyerna hantera och publicera resor och beslutshantering.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Adobe Experience Platform | <ul> <li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li> <li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li> <li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li> <li>**[!DNL View datasets]**: skrivskyddad åtkomst till datauppsättningar.</li> <li>**[!DNL Read Identity namespace]**: skrivskyddad åtkomst till identitetsnamnrymden.</li> <li>**[!DNL View schemas]**: skrivskyddad åtkomst till scheman.</li> <li>**[!DNL Sandbox]**: Bevilja åtkomst till sandlådor.</li> </ul> |
| Kanalkonfigurationer | <ul> <li>**[!DNL Manage alerts]**: aktivera/inaktivera aviseringar för resor och berättiganden.</li> <li>**[!DNL Manage IP pools]**: läs, skapa, redigera och ta bort IP-pool.</li> <li>**[!DNL Manage Landing page settings]**: skapa, redigera och ta bort deldomäner för landningssidor och förinställningar för landningssidor.</li> <li>**[!DNL Manage messages general settings]**: läs, skapa, redigera och ta bort allmänna inställningar för meddelanden.</li> <li>**[!DNL Manage messages presets]**: läs, skapa, redigera och ta bort innehållsmärkning.</li> <li>**[!DNL Manage PTR records]**: läs och redigera PTR-poster.</li> <li>**[!DNL Manage SMS settings]**: skapa, redigera och ta bort API-autentiseringsuppgifter och SMS-kanalskonfigurationer som krävs för att aktivera SMS-kanalen.</li> <li>**[!DNL Manage subdomains delegation]**: läsa, skapa, redigera och ta bort underdomänsdelegering.</li> <li>**[!DNL Manage suppression rules]**: få åtkomst till regler för att läsa, skapa, redigera och ta bort inaktiveringar.</li> <li>**[!DNL View PTR records]**: skrivskyddad åtkomst till PTR-poster.</li> <li>**[!DNL View suppression list]**: läs och exportera en lokal undertryckningslista.</li> </ul> |
| Dataförvaltning | <ul> <li>**[!DNL Manage data usage policies]**: läsa, skapa, redigera och ta bort dataanvändningsprinciper.</li> <li>**[!DNL Manage usage label]**: läs, skapa och ta bort användningsetiketter.</li> <li>**[!DNL View data usage policies]**: skrivskyddad åtkomst till dataanvändningsprinciper.</li> <li>**[!DNL View user activity log]**: skrivskyddad åtkomst för att visa inspelade granskningsloggar för Experience Platform-aktiviteter.</li> </ul> |
| Beslutshantering | <ul> <li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslut.</li> <li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort rankningsstrategier.</li> </ul> |
| Resor | <ul> <li>**[!DNL Manage journeys]**: läsa, skapa, redigera, stoppa (live, testläge och torr körning) och ta bort resor. </li> <li>**[!DNL Manage journeys events, data sources and actions]**: läs, skapa, redigera och ta bort händelser, källor eller åtgärder.</li> <li>**[!DNL Publish journeys]**: publicera, starta testläge, starta torr körning, pausa och återuppta resor. </li> <li>**[!DNL View journeys report]**: läs och redigera reserapport.</li> </ul> |
| Journey Optimizer Library | <ul> <li>**[!DNL Manage Library Items]**: lägg till och ta bort sparade uttryck i [!DNL Journey Optimizer]-biblioteket.</li> </ul> |

## [!DNL Journey Approver] {#journey-approver}

Med rollen **[!DNL Journey Approver]** kan användare godkänna leveranser och publicera dem. De kan senare kontrollera om deras leveranser är slutförda med **[!DNL Journey]**-rapporterna.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Adobe Experience Platform | <ul><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL View datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL View schemas]**: skrivskyddad åtkomst till scheman.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL View channel configurations]**: skrivskyddad åtkomst till kanalkonfigurationer.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade rapporter och använd åtgärdsfunktioner.</li></ul> |
| Resor | <ul><li>**[!DNL Manage journeys]**: läsa, skapa, redigera, stoppa (live, testläge och torr körning) och ta bort resor. </li><li>**[!DNL Publish journey]**: publicera, starta testläge, starta torr körning, pausa och återuppta resor. </li><li>**[!DNL View journeys events, data sources and actions]**: skrivskyddad åtkomst till resehändelser, anpassade åtgärder för resan och datakällor för resedata.</li><li>**[!DNL View journeys report]**: läs, redigera reserapporter.</li></ul> |

## [!DNL Journey Manager] {#journey-manager}

Med rollen **[!DNL Journey Manager]** kan användare skapa och redigera **[!UICONTROL Journeys]** och alla funktioner som är länkade till **[!UICONTROL Journeys]**, men de kan inte publiceras.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Adobe Experience Platform | <ul><li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li> **[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL View datasets]**: skrivskyddad åtkomst till datauppsättningar.</li><li>**[!DNL View schemas]**: skrivskyddad åtkomst till scheman.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL View channel configurations]**: skrivskyddad åtkomst till kanalkonfigurationer.</li></ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade rapporter och använd åtgärdsfunktioner.</li></ul> |
| Resor | <ul><li>**[!DNL Manage journeys]**: läsa, skapa, redigera, stoppa (live, testläge och torr körning) och ta bort resor.</li><li>**[!DNL View journeys events]**: skrivskyddad åtkomst till resehändelser, anpassade åtgärder för resan och datakällor för resedata.</li><li>**[!DNL View journeys report]**: läs, redigera reserapport.</li></ul> |

## [!DNL Journey Viewer] {#journey-viewer}

Rollen **[!DNL Journey viewer]** tillåter skrivskyddad åtkomst till funktionerna **[!UICONTROL Journeys]** och **[!UICONTROL Decision management]**.

Användare som tilldelats den här rollen kan inte redigera eller publicera.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Beslutshantering | <ul><li>**[!DNL View decisions]**: skrivskyddad åtkomst till beslutsentiteter.</li></ul> |
| Resor | <ul><li>**[!DNL View journeys]**: skrivskyddad åtkomst till resor.</li><li>**[!DNL View journeys event, data sources, actions]**: skrivskyddad åtkomst till resehändelser och datakällor.</li><li>**[!DNL View journeys report]**: skrivskyddad åtkomst till reserapporter.</li></ul> |

## [!DNL Orchestrated Campaign Administrators] {#orchestrated-campaign-administrator}

Med rollen **[!DNL Orchestrated Campaign Administrator]** kan administrationsmenyerna hantera och publicera Orchestrated-kampanjer.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Adobe Experience Platform | <ul> <li>**[!DNL Enable AI Assistant]**: aktivera eller få åtkomst till AI-baserade kampanjer och målgruppsfunktioner.</li> <li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li> <li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li> <li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li> <li>**[!DNL View datasets]**: skrivskyddad åtkomst till datauppsättningar.</li> <li>**[!DNL Read Identity namespace]**: skrivskyddad åtkomst till identitetsnamnrymden.</li> <li>**[!DNL View schemas]**: skrivskyddad åtkomst till scheman.</li> <li>**[!DNL Sandbox]**: Bevilja åtkomst till sandlådor.</li> <li>**[!DNL View operational insights]**: skrivskyddad åtkomst till insikter på systemnivå och övervakning av instrumentpaneler.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL Export suppression list]**: åtkomst till en lista över undertryckande export som en CSV-fil.</li> <li>**[!DNL Manage alerts]**: aktivera/inaktivera aviseringar för kampanjer, meddelanden och berättiganden.</li> <li>**[!DNL Manage custom dashboards]**: läs, skapa, redigera och ta bort anpassade instrumentpaneler.</li><li>**[!DNL Manage IP pools]**: läs, skapa, redigera och ta bort IP-pool.</li> <li>**[!DNL Manage landing page settings]**: läs, skapa, redigera och ta bort inställningar för landningssidor.</li> <li>**[!DNL Manage messages general settings]**: läs, skapa, redigera och ta bort allmänna inställningar för meddelanden.</li> <li>**[!DNL Manage messages presets]**: läs, skapa, redigera och ta bort innehållsmärkning.</li><li>**[!DNL Manage PTR records]**: läs och redigera PTR-poster.</li> <li>**[!DNL Manage SMS settings]**: läs, skapa, redigera och ta bort SMS-inställningar.</li> <li>**[!DNL Manage subdomains delegation]**: läsa, skapa, redigera och ta bort underdomänsdelegering.</li> <li>**[!DNL Manage suppression rules]**: få åtkomst till regler för att läsa, skapa, redigera och ta bort inaktiveringar.</li> <li>**[!DNL View PTR records]**: skrivskyddad åtkomst till PTR-poster.</li> <li>**[!DNL View suppression list]**: läs och exportera en lokal undertryckningslista.</li> </ul> |
| Kontrollpanel | <ul> <li>**[!DNL Manage standard dashboard]**: läs, skapa, redigera och ta bort anpassade widgetar och widgetschema via widgetbiblioteket.</li> </ul> |
| Dataförvaltning | <ul> <li>**[!DNL View user activity log]**: skrivskyddad åtkomst för att visa inspelade granskningsloggar för Experience Platform-aktiviteter. </li> </ul> |
| Intag av data | <ul> <li>**[!DNL Manage sources]**: läsa, skapa, redigera och inaktivera källor.</li> </ul> |
| Datahantering | <ul> <li>**[!DNL Manage datasets]**: läsa, skapa, redigera och ta bort datauppsättningar.</li> </ul> |
| Datamodellering | <ul> <li>**[!DNL Manage schemas]**: läs, skapa, redigera och ta bort scheman och relaterade resurser.</li> </ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslut.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort rankningsstrategier.</li></ul> |
| Journey Optimizer-regler | <ul> <li>**[!DNL View frequency rules]**: skrivskyddad åtkomst till frekvensregler.</li><li>**[!DNL Manage frequency rules]**: läsa, skapa, redigera eller ta bort frekvensregler.</li> </ul> |
| Meddelanden | <ul><li> **[!DNL Manage Messages]**: läsa, skapa, redigera och ta bort meddelanden. </li> **[!DNL Manage Messages Preview and Test]**: Godkänn och publicera meddelanden när en princip tillämpas.</li><li>**[!DNL Publish Messages]**: publiceringsmeddelanden. </li><li>**[!DNL View Messages Report]**: läs och redigera meddelanderapporter. <li></ul> |
| Samordnade kampanjer | <ul><li> **[!DNL Manage orchestrated campaigns]**: läs, skapa, redigera och ta bort samordnade kampanjer.</li> <li>**[!DNL Manage orchestrated campaigns admin]**: läs, skapa, redigera och ta bort länkar och avstämningar mellan Adobe Experience Platform-profiler och Relational store-entiteter.</li><li>**[!DNL Publish orchestrated campaigns]**: publicera samordnade kampanjer.</li><li>**[!DNL View orchestrated campaigns report]**: läs och redigera rapport om orkestrerade kampanjer.</li></ul> |

## [!DNL Orchestrated Campaign Approver] {#orchestrated-campaign-approver}

Med rollen **[!DNL Orchestrated Campaign Approver]** kan användare publicera Orchestrated-kampanjer.

| Resurser | Behörigheter |
|-|-|
| Adobe Experience Platform | <ul> <li>**[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li> <li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li> <li>**[!DNL View datasets]**: skrivskyddad åtkomst till datauppsättningar.</li> <li>**[!DNL View schemas]**: skrivskyddad åtkomst till scheman.</li> <li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li> <li>**[!DNL Enable AI Assistant]**: aktivera eller få åtkomst till AI-baserade kampanjer och målgruppsfunktioner.</li>  <li>**[!DNL View operational insights]**: skrivskyddad åtkomst till insikter på systemnivå och övervakning av instrumentpaneler.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL View messages presets]**: skrivskyddad åtkomst till meddelandeförinställningar.</li> <li>**[!DNL Manage custom dashboards]**: skapa, redigera och ta bort anpassade instrumentpaneler.</li></ul> |
| Kontrollpanel | <ul> <li>**[!DNL Manage standard dashboard]**: läs, skapa, redigera och ta bort anpassade widgetar och widgetschema via widgetbiblioteket.</li> </ul> |
| Dataförvaltning | <ul> <li>**[!DNL View user activity log]**: skrivskyddad åtkomst för att visa inspelade granskningsloggar för Experience Platform-aktiviteter.</li> </ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade meddelanderapporter och använd åtgärdsfunktioner.</li></ul> |
| Journey Optimizer-regler | <ul> <li>**[!DNL View frequency rules]**: skrivskyddad åtkomst till frekvensregler.</li></ul> |
| Meddelanden | <ul><li> **[!DNL Manage Messages]**: läsa, skapa, redigera och ta bort meddelanden. </li> **[!DNL Manage Messages Preview and Test]**: Godkänn och publicera meddelanden när en princip tillämpas.</li><li>**[!DNL Publish Messages]**: publiceringsmeddelanden. </li><li>**[!DNL View Messages Report]**: läs och redigera meddelanderapporter. <li></ul> |
| Samordnade kampanjer | <ul><li>**[!DNL Manage orchestrated campaigns]**: läs, skapa, redigera och ta bort samordnade kampanjer.</li><li>**[!DNL Publish orchestrated campaigns]**: publicera samordnade kampanjer.</li><li>**[!DNL View orchestrated campaigns admin]**: skrivskyddad åtkomst till länkar och avstämningar mellan Adobe Experience Platform-profiler och Relational store-entiteter.</li><li>**[!DNL View orchestrated campaigns report]**: läs, redigera Orchestrated-kampanjrapporter.</li></ul> |

## [!DNL Orchestrated Campaign Manager] {#orchestrated-campaign-manager}

Med rollen **[!DNL Orchestrated Campaign Manager]** kan användare skapa och redigera **[!UICONTROL Orchestrated campaigns]** och alla funktioner som är länkade till **[!UICONTROL Orchestrated campaigns]**, men de kan inte publiceras.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Adobe Experience Platform | <ul><li>**[!DNL Enable AI Assistant]**: aktivera eller få åtkomst till AI-baserade kampanjer och målgruppsfunktioner.</li> <li>**[!DNL Manage merge policies]**: läsa, skapa, redigera och ta bort sammanfogningsprinciper.</li><li>**[!DNL Manage profiles]**: läsa, skapa, redigera och ta bort profiler.</li><li> **[!DNL Manage segments]**: läsa, skapa, redigera och ta bort segmentdefinitioner.</li><li>**[!DNL View datasets]**: skrivskyddad åtkomst till datauppsättningar.</li>  <li>**[!DNL View operational insights]**: skrivskyddad åtkomst till insikter på systemnivå och övervakning av instrumentpaneler.</li><li>**[!DNL View schemas]**: skrivskyddad åtkomst till scheman.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL Manage custom dashboards]**: skapa, redigera och ta bort anpassade instrumentpaneler.</li><li>**[!DNL View messages presets]**: skrivskyddad åtkomst till meddelandeförinställningar.</li></ul> |
| Kontrollpanel | <ul> <li>**[!DNL Manage standard dashboard]**: läs, skapa, redigera och ta bort anpassade widgetar och widgetschema via widgetbiblioteket.</li> </ul> |
| Dataförvaltning | <ul> <li>**[!DNL View user activity log]**: skrivskyddad åtkomst för att visa inspelade granskningsloggar för Experience Platform-aktiviteter.</li> </ul> |
| Beslutshantering | <ul><li>**[!DNL Manage decisions]**: läsa, skapa, redigera och ta bort beslutsenheter.</li><li>**[!DNL Manage ranking strategies]**: läs, skapa, redigera och ta bort anpassade meddelanderapporter och använd åtgärdsfunktioner.</li></ul> |
| Journey Optimizer-regler | <ul> <li>**[!DNL View frequency rules]**: skrivskyddad åtkomst till frekvensregler. </li></ul> |
| Meddelanden | <ul><li> **[!DNL Manage Messages]**: läsa, skapa, redigera och ta bort meddelanden. </li> **[!DNL Manage Messages Preview and Test]**: Godkänn och publicera meddelanden när en princip tillämpas.</li><li>**[!DNL View Messages Report]**: läs och redigera meddelanderapporter. </li></ul> |
| Samordnade kampanjer | <ul><li>**[!DNL Manage orchestrated campaigns]**: läs, skapa, redigera och ta bort samordnade kampanjer.</li><li>**[!DNL View orchestrated campaigns report]**: läs, redigera orkestrerade kampanjer.</li><li>**[!DNL View orchestrated campaigns admin]**: skrivskyddad åtkomst till länkar och avstämningar mellan Adobe Experience Platform-profiler och Relational store-entiteter.</li></ul> |

## [!DNL Orchestrated Campaign Viewer] {#orchestrated-campaign-viewer}

Rollen **[!DNL Campaign Viewer]** tillåter skrivskyddad åtkomst till funktionerna i **[!UICONTROL Orchestrated campaigns]**.

Användare som tilldelats den här rollen kan inte redigera eller publicera.

Den här rollen innehåller följande behörigheter:

| Resurser | Behörigheter |
|-|-|
| Adobe Experience Platform | <ul><li>**[!DNL Enable AI Assistant]**: aktivera eller få åtkomst till AI-baserade kampanjer och målgruppsfunktioner.</li> <li>**[!DNL View operational insights]**: skrivskyddad åtkomst till insikter på systemnivå och övervakning av instrumentpaneler.</li></ul> |
| Kanalkonfigurationer | <ul><li>**[!DNL Manage custom dashboards]**: skapa, redigera och ta bort anpassade instrumentpaneler.</li></ul> |
| Kontrollpanel | <ul> <li>**[!DNL Manage standard dashboard]**: läs, skapa, redigera och ta bort anpassade widgetar och widgetschema via widgetbiblioteket.</li> </ul> |
| Dataförvaltning | <ul> <li>**[!DNL View user activity log]**: skrivskyddad åtkomst för att visa inspelade granskningsloggar för Experience Platform-aktiviteter.</li> </ul> |
| Beslutshantering | <ul><li>**[!DNL View decisions]**: skrivskyddad åtkomst till beslutsentiteter.</li></ul> |
| Journey Optimizer-regler | <ul> <li>**[!DNL View frequency rules]**: skrivskyddad åtkomst till frekvensregler.</li></ul> |
| Samordnade kampanjer | <ul><li>**[!DNL View orchestrated campaigns]**: skrivskyddad åtkomst till Orchestrated-kampanjer.</li><li>**[!DNL View orchestrated campaigns report]**: skrivskyddad åtkomst till rapporter om orkestrerade kampanjer.</li></ul> |




