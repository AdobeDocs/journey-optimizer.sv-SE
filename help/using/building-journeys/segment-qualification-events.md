---
title: Segmentkvalificeringshändelser
description: Learn about segment qualification events
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 7e70b8a9-7fac-4450-ad9c-597fe0496df9
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 0%

---

# Segmentkvalificeringshändelser {#segment-qualification}

## Om segmentkvalificeringshändelser{#about-segment-qualification}

Med den här aktiviteten kan din resa lyssna på ingångar och utgångar för profiler i Adobe Experience Platform-segment för att få individer att komma in på eller gå framåt under en resa. Mer information om att skapa segment finns i [section](../segment/about-segments.md).

Let&#39;s say you have a &quot;silver customer&quot; segment. Med den här aktiviteten kan ni få alla nya silverkunder att ta sig in på en resa och skicka en serie personaliserade meddelanden till dem.

This type of event can be positioned as the first step or later in the journey.

>[!IMPORTANT]
>
>Tänk på att Adobe Experience Platform-segment beräknas en gång om dagen (**batch** segment) eller i realtid (**direktuppspelad** segment, med alternativet High Frequency Audiences i Adobe Experience Platform).
>
>Om det valda segmentet direktuppspelas kan de personer som tillhör det segmentet komma in på resan i realtid. Om segmentet är en batch kan personer som nyligen är kvalificerade för det här segmentet komma in på resan när segmentberäkningen körs på Adobe Experience Platform.


1. Ta fram **[!UICONTROL Events]** kategori och släpp en **[!UICONTROL Segment Qualification]** på arbetsytan.

   ![](assets/segment5.png)

1. Lägg till en **[!UICONTROL Label]** till aktiviteten. Det här steget är valfritt.

1. Click in the **[!UICONTROL Segment]** field and select the segments you want to leverage.

   >[!NOTE]
   >
   >Observera att du kan anpassa kolumnerna som visas i listan och sortera dem.

   ![](assets/segment6.png)

   När segmentet har lagts till visas **[!UICONTROL Copy]** kan du kopiera dess namn och ID:

   `{"name":"Loyalty membership“,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](assets/segment-copy.png)

1. I **[!UICONTROL Behaviour]** väljer du om du vill lyssna på segmentingångar, utgångar eller både och.

   >[!NOTE]
   >
   >Observera att **[!UICONTROL Enter]** och **[!UICONTROL Exit]** motsvarar **Realiserad** och **Avslutade** segmentdeltagarstatus från Adobe Experience Platform. Mer information om hur du utvärderar ett segment finns i [Dokumentation för segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html#interpret-segment-results){target=&quot;_blank&quot;}.

1. Select a namespace. Detta behövs bara om händelsen är placerad som det första steget i resan.

   ![](assets/segment7.png)

The payload contains the following context information, which you can use in conditions and actions:

* beteendet (entré, exit)
* the timestamp of qualification
* segment-ID

When using the expression editor in a condition or action that follows a **[!UICONTROL Segment Qualification]** activity, you have access to the **[!UICONTROL SegmentQualification]** node. Du kan välja mellan **[!UICONTROL Last qualification time]** och **[!UICONTROL status]** (ange eller avsluta).

Se [Villkorsaktivitet](../building-journeys/condition-activity.md#about_condition).

![](assets/segment8.png)

En ny resa som innehåller en segmentkvalificeringshändelse kan användas tio minuter efter att du har publicerat den. Det här tidsintervallet motsvarar cacheuppdateringsintervallet för den dedikerade tjänsten. Therefore, you must wait ten minutes before using this journey.

## God praxis {#best-practices-segments}

The **[!UICONTROL Segment Qualification]** activity enables the immediate entrance in journeys of individuals getting qualified or disqualified from an Adobe Experience Platform segment.

Mottagningshastigheten för den här informationen är hög. Measurements made show a speed of 10 000 events received per seconds. Därför bör du se till att du förstår hur höga ingångstoppar kan bli, hur du undviker dem och hur du gör din resa redo för dem.

### Gruppsegment{#batch-speed-segment-qualification}

Observera att en ingångstopp kommer att inträffa vid tidpunkten för den dagliga beräkningen när du använder en segmentkvalificering för ett batchsegment. Toppens storlek beror på antalet personer som dagligen kommer in i (eller avslutar) segmentet.

Moreover, if the batch segment is newly created and immediately used in a journey, the first batch of calculation might make a very large number of individuals enter the journey.

### Strömmade segment{#streamed-speed-segment-qualification}

When using segment qualification for streamed segments, there is less risk of getting large peaks of entrances/exits due to the continuous evaluation of the segment. Men om segmentdefinitionen leder till att ett stort antal kunder kvalificerar sig samtidigt kan det ändå bli en topp.

Mer information om direktuppspelningssegmentering finns i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html#api)

### How to avoid overloads{#overloads-speed-segment-qualification}

Här följer några tips som hjälper dig att undvika överbelastade system som används i resor (datakällor, anpassade åtgärder, **Meddelande** verksamhet).

Använd inte **[!UICONTROL Segment Qualification]** -aktiviteten, ett batchsegment omedelbart efter att det har skapats. Den första beräkningstopp undviks. Observera att det blir en gul varning på arbetsytan om du ska använda ett segment som aldrig har beräknats.

![](assets/segment-error.png)

Införa en begränsning för datakällor och åtgärder som används under resor för att undvika att överbelasta dem. Läs mer i [Journey Orchestration dokumentation](https://experienceleague.adobe.com/docs/journeys/using/working-with-apis/capping.html){target=&quot;_blank&quot;}. Observera att begränsningsregeln inte har några nya försök. Om du vill försöka igen måste du markera kryssrutan för att använda en alternativ sökväg under resan **[!UICONTROL Add an alternative path in case of a timeout or an error]** i villkor eller åtgärder.

Innan du använder segmentet i en produktionsresa ska du alltid först utvärdera antalet individer som kvalificerar sig för det här segmentet varje dag. Om du vill göra det kan du kontrollera **[!UICONTROL Segments]** öppnar du segmentet och tittar på **[!UICONTROL Profiles over time]** diagram.

![](assets/segment-overload.png)
