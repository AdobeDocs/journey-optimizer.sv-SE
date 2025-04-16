---
solution: Journey Optimizer
product: journey optimizer
title: Use the Fork activity
description: Lär dig hur du använder gaffelaktiviteten i en orkestrerad kampanj
hide: true
hidefromtoc: true
exl-id: 52e8057b-dac1-45f5-9dd0-1b28a59adde9
source-git-commit: 3d380d2d02eb7043aebcffd00bb2092e7341b0d5
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 0%

---

# Förgrening {#fork}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_fork"
>title="Gaffelaktivitet"
>abstract="Med aktiviteten **Förena** kan du skapa utgående övergångar och starta flera aktiviteter samtidigt."


>[!CONTEXTUALHELP]
>id="ajo_orchestration_fork_transitions"
>title="Fork-aktivitetsövergångar"
>abstract="Som standard skapas två övergångar med en **Förgrening**-aktivitet. Klicka på knappen **Lägg till övergång** för att definiera ytterligare en utgående övergång och ange dess etikett."

Aktiviteten **Förena** är en **flödeskontroll**-aktivitet. It allows you to create outbound transitions to start several activities at the same time.

## Konfigurera gaffelaktiviteten{#fork-configuration}

Följ de här stegen för att konfigurera aktiviteten **Förgrening**:

![](../assets/workflow-fork.png)

1. Add a **Fork** activity to your orchestrated campaign.
1. Klicka på **Lägg till övergång** för att lägga till en ny utgående övergång. By default two transitions are defined.
1. Add a label to each of your transitions.

## Exempel{#fork-example}

In the following example, we&#39;re using two **Fork** activities:

* One before the two queries, to execute them at the same time.
* One after the intersection, to send an email and an SMS simultaneously to the targeted population.

![](../assets/workflow-fork-example.png)
