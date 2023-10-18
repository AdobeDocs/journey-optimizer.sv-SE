---
solution: Journey Optimizer
product: journey optimizer
title: Publikkvalificeringshändelser
description: Läs mer om kvalificeringshändelser för målgrupper
feature: Journeys, Activities, Audiences
topic: Content Management
role: User
level: Intermediate
keywords: kvalificering, evenemang, målgrupp, resa, plattform
exl-id: 7e70b8a9-7fac-4450-ad9c-597fe0496df9
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: tm+mt
source-wordcount: '934'
ht-degree: 0%

---

# Publikkvalificeringshändelser {#segment-qualification}

## Om kvalificeringshändelser för målgrupper{#about-segment-qualification}

>[!CONTEXTUALHELP]
>id="ajo_journey_event_segment_qualification"
>title="Elevkvalificeringshändelser"
>abstract="Med den här aktiviteten kan din resa lyssna på ingångar och utgångar för profiler i Adobe Experience Platform-målgrupper för att få individer att komma in på eller gå framåt under en resa."

Med den här aktiviteten kan din resa lyssna på ingångar och utgångar för profiler i Adobe Experience Platform-målgrupper för att få individer att komma in på eller gå framåt under en resa. Mer information om att skapa målgrupper finns i [section](../audience/about-audiences.md).

Säg att ni har en&quot;silverkund&quot; som målgrupp. Med den här aktiviteten kan ni få alla nya silverkunder att ta sig in på en resa och skicka en serie personaliserade meddelanden till dem.

Den här typen av händelse kan placeras som det första steget eller senare under resan.

### Viktiga anteckningar{#important-notes-segment-qualification}

* Kom ihåg att Adobe Experience Platform-målgrupper beräknas antingen en gång om dagen (**batch** målgrupper) eller i realtid (**strömmad** målgrupper, med alternativet High Frequency Audiences i Adobe Experience Platform).

* Om den valda publiken direktuppspelas kan de personer som tillhör den här publiken komma in på resan i realtid. Om målgruppen är en batch kommer personer som nyligen är kvalificerade för den här målgruppen att kunna delta i resan när målgruppsberäkningen görs på Adobe Experience Platform.

* Det går inte att använda fältgrupper för upplevelsehändelser på resor som börjar med en läsare, en målgrupp eller en affärshändelseaktivitet.

* När du använder en målgruppskvalifikation på en resa kan det ta upp till 10 minuter innan målgruppsaktiviteten är aktiv och lyssnar på profiler som kommer in eller lämnar målgruppen.

### Konfigurera aktiviteten{#cnfigure-segment-qualification}

1. Ta fram **[!UICONTROL Events]** kategori och släpp en **[!UICONTROL Audience Qualification]** på arbetsytan.

   ![](assets/segment5.png)

1. Lägg till en **[!UICONTROL Label]** till aktiviteten. Det här steget är valfritt.

1. Klicka på **[!UICONTROL Audience]** och välj de målgrupper du vill använda.

   >[!NOTE]
   >
   >Observera att du kan anpassa kolumnerna som visas i listan och sortera dem.

   ![](assets/segment6.png)

   När målgruppen lagts till **[!UICONTROL Copy]** kan du kopiera dess namn och ID:

   `{"name":"Loyalty membership“,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](assets/segment-copy.png)

1. I **[!UICONTROL Behaviour]** väljer du om du vill lyssna på målgruppsinkomster, utgångar eller både och.

   >[!NOTE]
   >
   >Observera att **[!UICONTROL Enter]** och **[!UICONTROL Exit]** motsvarar **Realiserad** och **Avslutade** status för målgruppsdeltagande från Adobe Experience Platform. Mer information om hur du utvärderar en målgrupp finns i [Dokumentation för segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html#interpret-segment-results){target="_blank"}.

1. Välj ett namnutrymme. Detta behövs bara om händelsen är placerad som det första steget i resan. Som standard är fältet förifyllt med det senast använda namnutrymmet.

   >[!NOTE]
   >
   >Du kan bara välja ett personbaserat ID-namnutrymme. Om du har definierat ett namnutrymme för en uppslagstabell (till exempel: ProductID-namnutrymme för en produktsökning), är det inte tillgängligt i **Namnutrymme** listruta.

   ![](assets/segment7.png)

Nyttolasten innehåller följande kontextinformation som du kan använda i villkor och åtgärder:

* beteendet (entré, exit)
* tidsstämpel för kvalificeringen
* målgrupps-ID

När du använder uttrycksredigeraren i ett villkor eller en åtgärd som följer ett **[!UICONTROL Audience Qualification]** -aktivitet, du har tillgång till **[!UICONTROL AudienceQualification]** nod. Du kan välja mellan **[!UICONTROL Last qualification time]** och **[!UICONTROL status]** (ange eller avsluta).

Se [Villkorsaktivitet](../building-journeys/condition-activity.md#about_condition).

![](assets/segment8.png)

En ny resa som innefattar ett kvalificeringsevenemang för en målgrupp är i drift tio minuter efter att du har publicerat det. Det här tidsintervallet motsvarar cacheuppdateringsintervallet för den dedikerade tjänsten. Du måste därför vänta tio minuter innan du kan använda den här resan.

## God praxis {#best-practices-segments}

The **[!UICONTROL Audience Qualification]** Aktiviteten gör det möjligt att omedelbart ta sig in på resor för enskilda personer som är kvalificerade eller diskvalificerade för en Adobe Experience Platform-publik.

Mottagningshastigheten för den här informationen är hög. Mätningarna visar en hastighet på 10 000 mottagna händelser per sekund. Därför bör du se till att du förstår hur höga ingångstoppar kan bli, hur du undviker dem och hur du gör din resa redo för dem.

### Gruppera målgrupper{#batch-speed-segment-qualification}

Observera att när du använder målgruppskvalifikation för en grupppublik kommer det att ske en topp vid tidpunkten för den dagliga beräkningen. Storleken på toppen beror på antalet individer som kommer in (eller avslutar) per dag.

Dessutom, om målgruppen är nyskapad och omedelbart används under en resa, kan den första beräkningsgruppen få ett mycket stort antal personer att komma in på resan.

### Direktuppspelade målgrupper{#streamed-speed-segment-qualification}

När man använder målgruppskvalifikationer för direktuppspelade målgrupper är risken mindre för att få stora toppar av ingångar/utgångar på grund av den kontinuerliga utvärderingen av målgruppen. Men om målgruppsdefinitionen leder till att ett stort antal kunder kvalificerar sig samtidigt kan det ändå bli en höjdpunkt.

Mer information om direktuppspelningssegmentering finns i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html#api)

### Så här undviker du överbelastningar{#overloads-speed-segment-qualification}

Här följer några tips som hjälper dig att undvika att överbelasta system som används på resor (datakällor, anpassade åtgärder, kanalåtgärder).

Skall inte användas i **[!UICONTROL Audience Qualification]** , en batchmålgrupp omedelbart efter att den har skapats. Den första beräkningstopp undviks. Observera att det kommer att finnas en gul varning på arbetsytan om du ska använda en målgrupp som aldrig har beräknats.

![](assets/segment-error.png)

Införa en begränsning för datakällor och åtgärder som används under resor för att undvika att överbelasta dem. Läs mer i [Journey Orchestration dokumentation](https://experienceleague.adobe.com/docs/journeys/using/working-with-apis/capping.html){target="_blank"}. Observera att begränsningsregeln inte har några nya försök. Om du vill försöka igen måste du markera kryssrutan för att använda en alternativ sökväg under resan **[!UICONTROL Add an alternative path in case of a timeout or an error]** i villkor eller åtgärder.

Innan ni använder målgruppen i en produktionsresa måste ni först och främst utvärdera mängden individer som är kvalificerade för denna målgrupp varje dag. Om du vill göra det kan du kontrollera **[!UICONTROL Audience]** öppnar du publiken och tittar på **[!UICONTROL Profiles over time]** diagram.

![](assets/segment-overload.png)
