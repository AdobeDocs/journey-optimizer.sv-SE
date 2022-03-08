---
title: Adobe Campaign v7/v8-åtgärder
description: Läs om åtgärder i Adobe Campaign v7/v8
feature: Actions
topic: Administration
role: Admin
level: Intermediate
exl-id: 3da712e7-0e08-4585-8ca4-b6ff79df0b68
source-git-commit: 51254efaab08a572def118d475dc18f74c9d29b7
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---

# Adobe Campaign v7/v8-åtgärder {#using_campaign_classic}

Det finns en integrering om du har Adobe Campaign v7 eller v8. Det gör att du kan skicka e-post, push-meddelanden och SMS med Adobe Campaign Transactional Messaging-funktioner.

Anslutningen mellan Journey Optimizer- och Campaign-instanserna konfigureras av Adobe vid etableringstidpunkten. Kontakta Adobe.

För att detta ska fungera måste du konfigurera en dedikerad åtgärd. Se detta [section](../action/acc-action.md).

Ett heltäckande exempel på användning presenteras i detta [section](../building-journeys/campaign-classic-use-case.md).

1. Designa din resa och börja med ett evenemang. Se det här [section](../building-journeys/journey.md).
1. I **Åtgärd** väljer du en Campaign-åtgärd och lägger till den på din resa.
1. I **Åtgärdsparametrar** visas alla fält som förväntas i meddelandets nyttolast. Du måste mappa vart och ett av dessa fält till det fält som du vill använda, antingen från händelsen eller från datakällan. Detta liknar anpassade åtgärder. Se detta [section](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)
