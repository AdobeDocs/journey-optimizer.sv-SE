---
solution: Journey Optimizer
product: journey optimizer
title: Använda aktiviteten Grupp
description: Lär dig hur du använder gaffelaktiviteten i en flerstegskampanj
hide: true
hidefromtoc: true
source-git-commit: dfa6c6e11db10f3e843035d32e322b212361548c
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

Aktiviteten **Förena** är en **flödeskontroll**-aktivitet. Det gör att du kan skapa utgående övergångar och starta flera aktiviteter samtidigt.

## Konfigurera gaffelaktiviteten{#fork-configuration}

Följ de här stegen för att konfigurera aktiviteten **Förgrening**:

![](../assets/workflow-fork.png)

1. Lägg till en **gaffelaktivitet** i din flerstegskampanj.
1. Klicka på **Lägg till övergång** för att lägga till en ny utgående övergång. Som standard definieras två övergångar.
1. Lägg till en etikett till varje övergång.

## Exempel{#fork-example}

I följande exempel använder vi två **gaffelaktiviteter**:

* En före de två frågorna om du vill köra dem samtidigt.
* En efter skärningspunkten, för att skicka ett e-postmeddelande och ett SMS samtidigt till målpopulationen.

![](../assets/workflow-fork-example.png)
