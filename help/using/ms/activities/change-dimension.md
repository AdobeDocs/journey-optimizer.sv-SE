---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Ändra dimension
description: Lär dig hur du använder aktiviteten Ändra dimension
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 83e66f10-93dd-4759-840c-2c83abc42a28
source-git-commit: f0213f1270e9821b61a5dc396e39f5707f8f4b42
workflow-type: tm+mt
source-wordcount: '284'
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

Aktiviteten **Ändra dimension** är en **målaktivitet**. Med den här aktiviteten kan ni ändra målgruppsdimensionen när ni skapar er samordnade kampanj. Axeln flyttas beroende på datamallen och indatamängden.

Du kan t.ex. växla från&quot;profil&quot; till&quot;kontrakt&quot; för en orkestrerad kampanjs målinriktning för att skicka meddelanden till den avsedda avtalsägaren.

<!--
>[!IMPORTANT]
>
>Please note that the **[!UICONTROL Change Dimension]** and **[!UICONTROL Change Data source]** activities should not be added in one row. If you need to use both activities consecutively, make sure you include an **[!UICONTROL Enrichement]** activity in between them. This ensures proper execution and prevents potential conflicts or errors.-->

## Konfigurera aktiviteten Ändra dimension {#configure}

Följ de här stegen för att konfigurera aktiviteten **Ändra dimension**:

1. Lägg till en **Ändra dimension**-aktivitet i den orkestrerade kampanjen.

   ![](assets/change-dimension.png)

1. Definiera den **nya måldimensionen**. Vid dimensionsändring sparas alla poster.

1. Kör den orkestrerade kampanjen för att visa resultatet. Jämför data i tabellerna före och efter ändringsdimensionsaktiviteten och jämför strukturen i de samordnade kampanjtabellerna.

## Exempel {#example}

I det här exemplet vill vi skicka en SMS-leverans till alla profiler som har gjort ett köp. För att göra detta använder vi först en **[!UICONTROL Build audience]**-aktivitet som är länkad till en anpassad målgruppsdimension för inköp för alla köp som har gjorts.

Sedan använder vi en **[!UICONTROL Change dimension]**-aktivitet för att växla den orkestrerade målgruppsdimensionen för kampanjer till mottagare. På så sätt kan vi rikta in oss på de mottagare som matchar frågan.

![](assets/change-dimension-example.png)
