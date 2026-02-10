---
solution: Journey Optimizer
product: journey optimizer
title: '[!DNL Adobe Campaign] v7/v8-åtgärder'
description: Läs mer om  [!DNL Adobe Campaign] v7/v8-åtgärder
feature: Journeys, Actions, Custom Actions
topic: Administration
role: User
level: Intermediate
keywords: resa, integrering, kampanj, v7, v8
exl-id: 3da712e7-0e08-4585-8ca4-b6ff79df0b68
version: Journey Orchestration
source-git-commit: 692b539f2c7623a14192558c3eba55d90c54f22d
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 0%

---

# [!DNL Adobe Campaign] v7/v8-åtgärder {#using_campaign_v7-v8}

>[!CONTEXTUALHELP]
>id="ajo_journey_action_custom_acc"
>title="Anpassade åtgärder"
>abstract="En integrering är tillgänglig om du har [!DNL Adobe Campaign] v7 eller v8. Det gör att du kan skicka e-post, push-meddelanden och SMS med hjälp av funktionerna för transaktionsmeddelanden i [!DNL Adobe Campaign]."

En integrering är tillgänglig om du har [!DNL Adobe Campaign] v7 eller v8. Det gör att du kan skicka e-post, push-meddelanden och SMS med hjälp av funktionerna för transaktionsmeddelanden i [!DNL Adobe Campaign].

Anslutningen mellan Journey Optimizer- och Campaign-instanserna konfigureras av Adobe vid etableringstidpunkten. Kontakta Adobe.

**När du ska använda**: Använd Campaign v7/v8-åtgärder när ditt meddelande är beroende av transaktionsmallar för Campaign, kampanjspecifika datamodeller eller befintliga arbetsflöden för kampanjleverans.

**Förhandskrav**

* Din [!DNL Adobe Campaign] v7/v8-instans har etablerats och är ansluten till Journey Optimizer av Adobe.
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

![[!DNL Adobe Campaign] v7/v8-åtgärdskonfiguration och integreringsinställningar ](assets/accintegration2.png)
