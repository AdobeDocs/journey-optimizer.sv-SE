---
solution: Journey Optimizer
product: journey optimizer
title: Använda aktiviteten Spara målgrupp
description: Lär dig hur du använder aktiviteten Spara målgrupp i en orkestrerad kampanj
exl-id: 7b5b03ba-fbb1-4916-8c72-10778752d8e4
version: Campaign Orchestration
source-git-commit: e486aae3a6635d8eec0c398bfe03b6a63a007ef1
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 0%

---


# Spara målgrupp {#save-audience}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_save_audience"
>title="Spara målgruppsaktivitet"
>abstract="Aktiviteten **Spara målgrupp** är en **målgruppsaktivitet** som gör att du kan uppdatera en befintlig målgrupp eller skapa en ny från den målgrupp som genererades tidigare i den orkestrerade kampanjen. När de har skapats läggs dessa målgrupper till i listan över programmålgrupper och kan nås från menyn **Publiker** ."

Aktiviteten **[!UICONTROL Save audience]** är en **[!UICONTROL Targeting]**-aktivitet som används för att skapa en ny målgrupp eller uppdatera en befintlig utifrån den population som skapades tidigare i den orchestrerade-kampanjen. När målgruppen har sparats läggs den till i listan över programmålgrupper och blir tillgänglig på menyn **[!UICONTROL Audiences]**.

Det används ofta för att fånga målgruppssegment som skapats i samma kampanjarbetsflöde, så att de kan återanvändas i framtida kampanjer. Det är vanligtvis kopplat till andra målinriktningsaktiviteter, som **[!UICONTROL Build audience]** eller **[!UICONTROL Combine]**, för att spara den slutliga målpopulationen.
Observera att du inte kan uppdatera en befintlig målgrupp med aktiviteten **[!UICONTROL Save audience]**. Du kan bara skapa en ny målgrupp eller skriva över en befintlig med en ny definition.

## Konfigurera aktiviteten Spara målgrupp {#save-audience-configuration}

Så här konfigurerar du aktiviteten **[!UICONTROL Save audience]**:

1. Lägg till en **[!UICONTROL Save audience]**-aktivitet i din Orchestrated-kampanj.

1. Ange en **[!UICONTROL Audience label]** som identifierar den sparade målgruppen.

   >[!NOTE]
   >
   >Publiken **[!UICONTROL Label]** måste vara unik för alla kampanjer. Du kan inte återanvända ett målgruppsnamn som redan har använts i en annan kampanjs **[!UICONTROL Save audience]**-aktivitet.

1. Välj en **[!UICONTROL Profile mapping field&#x200B;]** från din Campaign-måldimension. Den här mappningen definierar hur profiler i den **sparade målgruppen** länkas till kampanjens måldimension under körningen.

   Endast mappningar som är kompatibla med den aktuella måldimensionen, dvs. den från den inkommande övergången, kommer att vara tillgängliga i listrutan för att säkerställa korrekt avstämning mellan målgruppen och kampanjsammanhanget.

   ➡️ [Följ stegen som beskrivs på den här sidan för att skapa din Campaign Targeting-dimension](../target-dimension.md)

   ![](../assets/save-audience-1.png)

1. Klicka på **[!UICONTROL Add audience mappings]** om du vill ta med ytterligare data från attribut för **[!UICONTROL Target dimension]** eller berikad **[!UICONTROL Profile attributes]**.

   Detta gör att du kan associera mer information med aktiviteten **[!UICONTROL Saved audience]** utöver den primära profilmappningen, vilket förbättrar alternativen för målinriktning och personalisering.

   ![](../assets/save-audience-2.png)

1. Slutför konfigurationen genom att spara och publicera den orkestrerade kampanjen. Detta genererar och lagrar er målgrupp.

1. Publicera kampanjen för målgruppen som ska skapas eller ersättas eftersom aktiviteten **[!UICONTROL Save audience]** inte körs när kampanjen är i **[!UICONTROL Draft mode]**.

Innehållet i den sparade målgruppen är sedan tillgängligt i detaljvyn för målgruppen, som du kommer åt via menyn **[!UICONTROL Audiences]**, eller kan väljas när du riktar dig till en målgrupp, till exempel med en **[!UICONTROL Read audience]** -aktivitet.

![](../assets/save-audience-4.png)

>[!NOTE]
>
>Om målgruppsdefinitionen använder Experience Platform-schemaattribut som är märkta med dataanvändning (DULE), ärvs dessa etiketter automatiskt av den sparade målgruppen. Du behöver inte tillämpa dem igen. [Läs mer om datastyrning](../../action/action-privacy.md)

## Exempel {#save-audience-example}

I följande exempel visas hur du skapar en enkel målgrupp med målinriktning. En fråga identifierar alla mottagare som har bokat en resa de senaste 30 dagarna genom att filtrera populationen i din Orchestrated-kampanj. Genom att välja **Mottagare - CRMID** som **måldimension**, målgruppen för varje enskild bokningshändelse i stället för bara mottagaren som helhet. Aktiviteten **[!UICONTROL Save audience]** hämtar sedan dessa profiler för att skapa en återanvändbar målgrupp med nyligen använda köpare.

![](../assets/save-audience-3.png)
