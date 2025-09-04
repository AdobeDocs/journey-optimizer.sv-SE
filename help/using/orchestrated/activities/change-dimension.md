---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Ändra dimension
description: Lär dig hur du använder aktiviteten Ändra dimension
exl-id: 83e66f10-93dd-4759-840c-2c83abc42a28
version: Campaign Orchestration
source-git-commit: 07ec28f7d64296bdc2020a77f50c49fa92074a83
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---


# Ändra dimension {#change-dimension}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_dimension_complement"
>title="Generera ett komplement"
>abstract="Du kan generera ytterligare en utgående övergång med den återstående populationen, som har uteslutits som en dubblett. Aktivera alternativet **Generera komplement** om du vill göra det."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_change_dimension"
>title="Ändra dimensionsaktivitet"
>abstract="Med den här aktiviteten kan ni ändra målgruppsdimensionen när ni skapar en målgrupp. Axeln flyttas beroende på datamallen och indatamängden. Du kan till exempel växla från dimensionen &quot;kontrakt&quot; till dimensionen &quot;kunder&quot;."

Som marknadsförare kan ni förbättra målgruppsanpassningen genom att gå över från en datatabell till en relaterad enhet i en samordnad kampanj. På så sätt kan du gå steget längre än användarprofiler och fokusera på specifika beteenden som inköp, bokningar eller andra interaktioner.

Använd aktiviteten **[!UICONTROL Change dimension]** för att uppnå detta. Ni kan anpassa målinriktningsdimensionen under den samordnade kampanjen.

<!--
>[!IMPORTANT]
>
>Please note that the **[!UICONTROL Change Dimension]** and **[!UICONTROL Change Data source]** activities should not be added in one row. If you need to use both activities consecutively, make sure you include an **[!UICONTROL Enrichement]** activity in between them. This ensures proper execution and prevents potential conflicts or errors.-->

## Konfigurera aktiviteten Ändra dimension {#configure}

Så här konfigurerar du aktiviteten **[!UICONTROL Change dimension]**:

1. Lägg till en **[!UICONTROL Change dimension]**-aktivitet i din Orchestrated-kampanj.

   ![](../assets/orchestrated-change-dimension.png)

1. Definiera **[!UICONTROL New target dimension]**. Vid dimensionsändring sparas alla poster.


## Exempel {#example}

Det här användningsexemplet fokuserar på att skicka ett SMS till profiler som har skapat en önskelista under den senaste månaden.

Börja med en **[!UICONTROL Build audience]**-aktivitet och använd målinriktningsdimensionen **[!UICONTROL Wishlist]** för att identifiera alla relevanta önskelistor.

Lägg sedan till en **[!UICONTROL Change dimension]**-aktivitet för att växla måldimensionen från **[!UICONTROL Wishlist]** till **[!UICONTROL Recipient].** Det här steget ser till att den orchestrerade kampanjen har rätt profiler länkade till dessa önskelistor, vilket gör att SMS:et kan skickas till de avsedda profilerna.

![](../assets/orchestrated-change-dimension-example.png)
