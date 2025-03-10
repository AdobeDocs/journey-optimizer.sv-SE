---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Ändra dimension
description: Lär dig hur du använder aktiviteten Ändra dimension
hide: true
hidefromtoc: true
source-git-commit: 00f843300a9cfe798ea4d3a92fbe89ba80e70bc5
workflow-type: tm+mt
source-wordcount: '330'
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

Aktiviteten **Ändra dimension** är en **målaktivitet**. Med den här aktiviteten kan ni ändra målinriktningsdimensionen när ni skapar flerstegskampanjer. Axeln flyttas beroende på datamallen och indatamängden.

Du kan till exempel växla en flerstegskampanj från mottagare till prenumerantprogram för att skicka push-meddelanden till målmottagarna.

>[!IMPORTANT]
>
>Observera att aktiviteterna **[!UICONTROL Change Dimension]** och **[!UICONTROL Change Data source]** inte ska läggas till på en rad. Om du behöver använda båda aktiviteterna i följd måste du ta med en **[!UICONTROL Enrichement]**-aktivitet mellan dem. Detta garanterar att programmet körs på rätt sätt och förhindrar eventuella konflikter och fel.

## Konfigurera aktiviteten Ändra dimension {#configure}

Följ de här stegen för att konfigurera aktiviteten **Ändra dimension**:

1. Lägg till en **Ändra dimension**-aktivitet i din flerstegskampanj.

   ![](../assets/workflow-change-dimension.png)

1. Definiera den **nya måldimensionen**. Vid dimensionsändring sparas alla poster. Andra alternativ är inte tillgängliga än.

1. Kör flerstegskampanjen för att visa resultatet. Jämför data i tabellerna före och efter ändringsdimensionsaktiviteten och jämför strukturen för flerstegskampanjtabellerna.

## Exempel {#example}

I det här exemplet vill vi skicka en SMS-leverans till alla profiler som har gjort ett köp. För att göra detta använder vi först en **[!UICONTROL Build audience]**-aktivitet som är länkad till en anpassad målgruppsdimension för inköp för alla köp som har gjorts.

Sedan använder vi en **[!UICONTROL Change dimension]**-aktivitet för att växla till målgruppsdimensionen för flerstegskampanjer till mottagare. På så sätt kan vi rikta in oss på de mottagare som matchar frågan.

![](../assets/workflow-change-dimension-example.png)
