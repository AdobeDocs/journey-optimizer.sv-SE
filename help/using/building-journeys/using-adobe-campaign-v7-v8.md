---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Campaign v7/v8-åtgärder
description: Läs om åtgärder i Adobe Campaign v7/v8
feature: Journeys, Actions, Custom Actions
topic: Administration
role: User
level: Intermediate
keywords: resa, integrering, kampanj, v7, v8
exl-id: 3da712e7-0e08-4585-8ca4-b6ff79df0b68
version: Journey Orchestration
source-git-commit: a068d3a4005d8f2247755f56ffb70665dc4c957f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 0%

---

# Adobe Campaign v7/v8-åtgärder {#using_campaign_v7-v8}

>[!CONTEXTUALHELP]
>id="ajo_journey_action_custom_acc"
>title="Anpassade åtgärder"
>abstract="Det finns en integrering om du har Adobe Campaign v7 eller v8. Det gör att du kan skicka e-post, push-meddelanden och SMS med Adobe Campaign Transactional Messaging-funktioner."

Det finns en integrering om du har Adobe Campaign v7 eller v8. Det gör att du kan skicka e-post, push-meddelanden och SMS med Adobe Campaign Transactional Messaging-funktioner.

Anslutningen mellan Journey Optimizer- och Campaign-instanserna konfigureras av Adobe vid etableringstidpunkten. Kontakta Adobe.

**När du ska använda**: Använd Campaign v7/v8-åtgärder när ditt meddelande är beroende av transaktionsmallar för Campaign, kampanjspecifika datamodeller eller befintliga arbetsflöden för kampanjleverans.

**Förhandskrav**

* Din Adobe Campaign v7/v8-instans har etablerats och är ansluten till Journey Optimizer av Adobe.
* Du har tillgång till transaktionsmeddelanden för Campaign och de behörigheter som krävs.

För att detta ska fungera måste du konfigurera en dedikerad åtgärd. Se det här [avsnittet](../action/acc-action.md).

Ett slutanvändarfall visas i det här [avsnittet](../building-journeys/ajo-ac.md).

1. Designa din resa och börja med ett evenemang. Se [avsnittet](../building-journeys/journey.md).
1. Välj en Campaign-åtgärd i **Åtgärd**-delen av paletten och lägg till den på din resa.
1. I **åtgärdsparametrarna** visas alla fält som förväntas i meddelandenyttolasten. Du måste mappa vart och ett av dessa fält till det fält som du vill använda, antingen från händelsen eller från datakällan. Detta liknar anpassade åtgärder. Se det här [avsnittet](../building-journeys/using-custom-actions.md).

>[!NOTE]
>
>* Kampanjåtgärder v7/v8 kan användas tillsammans med åtgärder för inbyggda kanaler under samma resa. Detta gäller inte Campaign Standard åtgärder. Se [Garantier för kampanjaktiviteter](../start/guardrails.md#ac-g).
>* Kampanjåtgärder v7/v8 kan inte användas med aktiviteter som hör till Läs målgrupp eller Audience Qualification. Se Läs skyddsutkast för målgrupps- och målgruppskvalitet på sidan Guardrails (GuarDRAils).

![Åtgärdskonfiguration och integreringsinställningar för Adobe Campaign v7/v8](assets/accintegration2.png)
