---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Vänta i flerstegskampanjer
description: Lär dig använda aktiviteten Vänta i flerstegskampanjer
hide: true
hidefromtoc: true
source-git-commit: dfa6c6e11db10f3e843035d32e322b212361548c
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 26%

---

# Vänta {#wait}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_wait"
>title="Vänta på aktivitet"
>abstract="Aktiviteten **Wait** används för att fördröja övergången från en aktivitet till en annan."

Aktiviteten **Wait** är en **Flow control**-aktivitet. Det används för att en viss tid ska kunna förflyta mellan två aktiviteter som utförs. Om du till exempel vill vänta flera dagar efter en aktivitet där e-post levererats så analyserar du de öppningar och klick som genereras under den här perioden innan du utför några uppföljningsåtgärder (påminnelser via e-post, målgruppsgenerering osv.).

## Konfiguration{#wait-configuration}

Följ de här stegen för att konfigurera aktiviteten **Wait**:

1. Lägg till en **Vänta**-aktivitet i din flerstegskampanj.

1. Ange **Varaktighet** för väntetiden mellan inkommande och utgående övergångar.

1. Välj tidsenhet i fältet **Perioder**: sekunder, minuter, timmar, dagar.

## Exempel{#wait-example}

I följande exempel visas aktiviteten **Wait** i ett typiskt fall. En e-postinbjudan till ett event skickas.  24 timmar efter att det skickats skickas ett SMS-meddelande till samma population.

![](../assets/workflow-wait-example.png)
