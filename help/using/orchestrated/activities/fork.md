---
solution: Journey Optimizer
product: journey optimizer
title: Använda aktiviteten Grupp
description: Lär dig hur du använder gaffelaktiviteten i en orkestrerad kampanj
exl-id: 52e8057b-dac1-45f5-9dd0-1b28a59adde9
source-git-commit: 3a44111345c1627610a6b026d7b19b281c4538d3
workflow-type: tm+mt
source-wordcount: '131'
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

Aktiviteten **[!UICONTROL Fork]** är en **[!UICONTROL Flow control]**-komponent som gör att du kan skapa flera utgående övergångar, vilket gör att flera aktiviteter kan köras parallellt.

## Konfigurera gaffelaktiviteten{#fork-configuration}

Så här konfigurerar du aktiviteten **[!UICONTROL Fork]**:

![](../assets/workflow-fork.png)

1. Lägg till en **[!UICONTROL Fork]**-aktivitet i din Orchestrated-kampanj.

1. Definiera en **[!UICONTROL Label]**.

1. Tilldela en etikett till varje utgående övergång. Som standard finns det två övergångar.

1. Klicka på ikonen ![](../assets/do-not-localize/Smock_Delete_18_N.svg) om du vill ta bort en övergång.

1. Om det behövs klickar du på **[!UICONTROL Add transition]** för att lägga till ytterligare en utgående övergång.
