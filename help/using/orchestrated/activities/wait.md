---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Vänta i orkestrerade kampanjer
description: Lär dig hur du använder aktiviteten Vänta i orkestrerade kampanjer
exl-id: 11ef095b-77ec-4e2e-ab4d-49a248354f08
source-git-commit: 3a44111345c1627610a6b026d7b19b281c4538d3
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 2%

---


# Vänta {#wait}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_wait"
>title="Vänta på aktivitet"
>abstract="Aktiviteten **Wait** används för att fördröja övergången från en aktivitet till en annan."

Aktiviteten **[!UICONTROL Wait]** är en **[!UICONTROL Flow control]**-komponent som används för att skapa en fördröjning mellan två aktiviteter i en orchestrerad kampanj. Detta bidrar till att säkerställa att era uppföljningsaktiviteter är bättre tajmade och mer relevanta för användarengagemanget.

Du kan till exempel vänta några dagar efter en e-postleverans för att spåra öppningar och klickningar innan du skickar ett uppföljningsmeddelande.

## Konfiguration{#wait-configuration}

Så här konfigurerar du aktiviteten **[!UICONTROL Wait]**:

1. Lägg till en **[!UICONTROL Wait]**-aktivitet i din Orchestrated-kampanj.

1. Välj den vänttyp som bäst passar dina behov:

   * **[!UICONTROL Duration]**: Ange en fördröjning i sekunder, minuter, timmar eller dagar innan du fortsätter till nästa aktivitet.

   * **[!UICONTROL Fixed time]**: Ange ett specifikt datum och en speciell tid efter vilket nästa aktivitet startar.

   ![](../assets/wait_activity.png)

## Exempel{#wait-example}

I följande exempel visas aktiviteten **[!UICONTROL Wait]** i ett typiskt användningsfall.  Ett e-postmeddelande med en kampanjkod skickas till profiler som firar sina födelsedagar. Efter 29 dagar skickas ett SMS till samma grupp som en påminnelse om att deras födelsedagskod snart går ut.

![](../assets/wait-example.png)
