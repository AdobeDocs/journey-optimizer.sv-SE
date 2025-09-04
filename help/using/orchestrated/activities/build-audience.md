---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Skapa målgrupp
description: Lär dig hur du använder aktiviteten Skapa målgrupp i en orkestrerad kampanj
exl-id: 3959b5fa-0c47-42a5-828f-4d7ca9b7e72d
version: Campaign Orchestration
source-git-commit: 07ec28f7d64296bdc2020a77f50c49fa92074a83
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 1%

---


# Bygg målgrupper {#build-audience}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_build_audience"
>title="Bygg målgruppsaktivitet"
>abstract="Med aktiviteten **Skapa målgrupp** kan du definiera målgruppen som ska delta i den Orchestrerade kampanjen. När du skickar meddelanden i samband med en orkestrerad kampanj definieras inte meddelandemålgruppen i kanalaktiviteten, utan i en **Build-målgruppsaktivitet**."

Som marknadsförare kan ni skapa komplexa målgruppssegment via ett intuitivt gränssnitt, som gör att ni kan inrikta er på användare baserat på en mängd olika kriterier och beteenden för att skräddarsy era kampanjer mer effektivt.

Använd målinriktningsaktiviteten **[!UICONTROL Build audience]** om du vill göra det. Den här aktiviteten definierar målgruppen som går in i den orkestrerade kampanjen. När du skickar meddelanden som en del av en orkestrerad kampanj definieras målgruppen i aktiviteten **[!UICONTROL Build audience]**, inte i den orkestrerade kampanjen.

## Konfigurera aktiviteten Skapa målgrupp {#build-audience-configuration}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_build_audience_audienceselector"
>title="Målgrupp"
>abstract="Välj målgrupp på samma sätt som du använder en målgrupp när du designar en ny leverans."

Så här konfigurerar du aktiviteten **[!UICONTROL Build audience]**:

1. Lägg till en **[!UICONTROL Build audience]**-aktivitet.

   ![](../assets/build-audience.png)

1. Definiera en **[!UICONTROL Label]**.

1. Konfigurera målgruppen genom att följa stegen som beskrivs på flikarna nedan.

1. Välj **[!UICONTROL Targeting dimension]**. Med målinriktningsdimensionen kan du definiera målgruppen för operationen: mottagare, mottagare, operatör, prenumeranter osv. Som standard är målet markerat bland mottagarna.

1. Klicka på **[!UICONTROL Continue]**.

1. Använd regelbyggaren för att definiera frågan. [Läs mer om regelverktyget i det här avsnittet](../orchestrated-rule-builder.md)

1. Ange om en utgående övergång ska genereras när målgruppen är tom.

## Exempel{#build-audience-examples}

Här är ett exempel på en Orchestrated-kampanj med två **[!UICONTROL Build audience]**-aktiviteter. Den första målprofilen som innehåller artiklar i kundvagnen, följt av en e-postleverans. Den andra inriktar sig på profiler med en önskelista, följt av en SMS-leverans.

![](../assets/build-audience-2.png)
