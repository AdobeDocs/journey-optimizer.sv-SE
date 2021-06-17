---
title: Starta körning av resa
description: Lär dig hur du påbörjar din resa och skickar meddelanden
source-git-commit: 9e152f50c2360010d83ffccbe536380879ffb5da
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 2%

---


# Resekörning {#message-execution}

## Testa din resa

Du kan testa din resa med testprofiler. Det här steget rekommenderas för att validera dina inställningar och meddelanden.

Läs mer i det här [avsnittet](testing-the-journey.md).

## Aktivera din resa

Du måste publicera din resa för att aktivera den.

![](../assets/jo-journeyuc2_32bis.png)

Läs mer i det här [avsnittet](publishing-the-journey.md).


När den publicerats kan ni övervaka er resa med de dedikerade rapporteringsverktygen för att mäta hur effektiv resan är.

![](../assets/jo-dynamic_report_journey_12.png)

[Läs mer om rapporter](../reports/live-report.md)

## Skicka meddelanden {#send-messages}

När ditt meddelande har ett definierat innehåll och publiceras är det klart att skickas via en [resa](journey.md).

>[!NOTE]
>
>Du kan lägga till ett meddelande som fortfarande är i utkastläge för en resa, men se till att meddelandet publiceras innan du publicerar resan.

När ett meddelande har skickats kan du övervaka dess körning med hjälp av flera indikatorer. [Läs mer om övervakning av meddelandekörning](../message-monitoring.md).

## Schemalägg meddelanden {#schedule-messages}

Meddelanden kan schemaläggas via aktiviteten **[!UICONTROL Read Segment]** i en [resa](journey.md). Du kan ange när segmentet ska gå in i resan. [Läs mer om Läs segment-aktiviteten](read-segment.md).

Följ stegen nedan för att göra detta:

1. Redigera en resa, dra och släpp en **[!UICONTROL Read Segment]**-aktivitet och börja konfigurera den. [Läs mer om hur du konfigurerar Läs segment-aktiviteten](read-segment.md#configuring-segment-trigger-activity).

1. Klicka på länken **[!UICONTROL Edit journey schedule]** för att komma åt resans egenskaper.

   ![](../assets/message-read-segment-schedule.png)

1. Konfigurera fältet **[!UICONTROL Scheduler type]**: välj önskat värde i listan för att få segmentet att komma in på resan ett visst datum/tid eller på återkommande basis.

   >[!NOTE]
   >
   >Avsnittet **[!UICONTROL Schedule]** är bara tillgängligt när en **[!UICONTROL Read Segment]**-aktivitet har släppts till arbetsytan.

   ![](../assets/message-read-segment-scheduler.png)

1. Om du väljer **[!UICONTROL Once]** anger du ett specifikt datum och en speciell tid då segmentet kommer in på resan.

   ![](../assets/message-read-segment-scheduler-once.png)

1. Om du väljer en återkommande metod redigerar du startdatum och starttid. Du kan också definiera ett valfritt slutdatum och en valfri sluttid.

   ![](../assets/message-read-segment-scheduler-daily.png)

   >[!NOTE]
   >
   >Som standard anges resan **[!UICONTROL As soon as possible]** i segment, vilket innebär en timme efter att resan har publicerats.

1. Klicka på **[!UICONTROL OK]** för att spara ändringarna.

<!--Unitary messages that are triggered by an event within a journey cannot be scheduled.-->
