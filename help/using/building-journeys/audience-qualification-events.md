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
source-git-commit: 817f9c16ae48b1127e5092add6fbcefa8dd3ba9f
workflow-type: tm+mt
source-wordcount: '1053'
ht-degree: 0%

---

# Publikkvalificeringshändelser {#segment-qualification}

## Om kvalificeringshändelser för målgrupper{#about-segment-qualification}

>[!CONTEXTUALHELP]
>id="ajo_journey_event_segment_qualification"
>title="Elevkvalificeringshändelser"
>abstract="Med den här aktiviteten kan din resa lyssna på ingångar och utgångar för profiler i Adobe Experience Platform-målgrupper för att få individer att komma in på eller gå framåt under en resa."

Med den här aktiviteten kan din resa lyssna på ingångar och utgångar för profiler i Adobe Experience Platform-målgrupper för att få individer att komma in på eller gå framåt under en resa. Mer information om att skapa målgrupper finns i det här [avsnittet](../audience/about-audiences.md).

Säg att ni har en&quot;silverkund&quot; som målgrupp. Med den här aktiviteten kan ni få alla nya silverkunder att ta sig in på en resa och skicka en serie personaliserade meddelanden till dem.

Den här typen av händelse kan placeras som det första steget eller senare under resan.

➡️ [Upptäck den här funktionen i videon](#video)

### Viktiga anteckningar{#important-notes-segment-qualification}

* Kom ihåg att Adobe Experience Platform-målgrupper beräknas antingen en gång om dagen (**batch** målgrupper) eller i realtid (för **direktuppspelade** målgrupper, med alternativet High Frequency Audiences i Adobe Experience Platform).

   * Om den valda publiken direktuppspelas kan de personer som tillhör den här publiken komma in på resan i realtid.
   * Om målgruppen är en batch kommer personer som nyligen är kvalificerade för den här målgruppen att kunna delta i resan när målgruppsberäkningen görs på Adobe Experience Platform.

  Som en god praxis rekommenderar vi därför att du bara använder direktuppspelade målgrupper i en **målgruppsklassificeringsaktivitet**. Använd en **[Läs målgruppsaktivitet](read-audience.md)** för gruppanvändningsfall.

  >[!NOTE]
  >
  >På grund av batchbeskaffenheten hos målgrupper som skapats med arbetsflöden för disposition och anpassad överföring kan du inte rikta in dig på dessa målgrupper i en&quot;målgruppskompetens&quot;-aktivitet. Endast målgrupper som skapats med segmentdefinitioner kan utnyttjas i den här aktiviteten.

* Det går inte att använda fältgrupper för upplevelsehändelser på resor som börjar med en läsare, en målgrupp eller en affärshändelseaktivitet.

* När du använder en målgruppskvalifikation på en resa kan det ta upp till 10 minuter innan målgruppsaktiviteten är aktiv och lyssnar på profiler som kommer in eller lämnar målgruppen.

### Konfigurera aktiviteten{#cnfigure-segment-qualification}

Så här konfigurerar du aktiviteten **[!UICONTROL Audience Qualification]**:

1. Öppna kategorin **[!UICONTROL Events]** och släpp en **[!UICONTROL Audience Qualification]**-aktivitet på arbetsytan.

   ![](assets/segment5.png)

1. Lägg till en **[!UICONTROL Label]** i aktiviteten. Det här steget är valfritt.

1. Klicka i fältet **[!UICONTROL Audience]** och välj de målgrupper du vill använda.

   >[!NOTE]
   >
   >Observera att du kan anpassa kolumnerna som visas i listan och sortera dem.

   ![](assets/segment6.png)

   När målgruppen har lagts till kan du med knappen **[!UICONTROL Copy]** kopiera dess namn och ID:

   `{"name":"Loyalty membership","id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](assets/segment-copy.png)

1. I fältet **[!UICONTROL Behaviour]** väljer du om du vill lyssna på målgruppsinkomster, utgångar eller både och.

   >[!NOTE]
   >
   >Observera att **[!UICONTROL Enter]** och **[!UICONTROL Exit]** motsvarar de **Realiserade** och **Avslutade** målgruppsdeltagarstatusarna från Adobe Experience Platform. Mer information om hur du utvärderar en målgrupp finns i [dokumentationen för segmenteringstjänsten](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html#interpret-segment-results){target="_blank"}.

1. Välj ett namnutrymme. Detta behövs bara om händelsen är placerad som det första steget i resan. Som standard är fältet förifyllt med det senast använda namnutrymmet.

   >[!NOTE]
   >
   >Du kan bara välja ett personbaserat ID-namnutrymme. Om du har definierat ett namnområde för en uppslagstabell (till exempel: ProductID-namnområde för en produktsökning), är det inte tillgängligt i listrutan **Namespace**.

   ![](assets/segment7.png)

Nyttolasten innehåller följande kontextinformation som du kan använda i villkor och åtgärder:

* beteendet (entré, exit)
* tidsstämpel för kvalificeringen
* målgrupps-ID

När du använder uttrycksredigeraren i ett villkor eller en åtgärd som följer efter en **[!UICONTROL Audience Qualification]**-aktivitet har du tillgång till noden **[!UICONTROL AudienceQualification]**. Du kan välja mellan **[!UICONTROL Last qualification time]** och **[!UICONTROL status]** (ange eller avsluta).

Se [Villkorsaktivitet](../building-journeys/condition-activity.md#about_condition).

![](assets/segment8.png)

En ny resa som innefattar ett kvalificeringsevenemang för en målgrupp är i drift tio minuter efter att du har publicerat det. Det här tidsintervallet motsvarar cacheuppdateringsintervallet för den dedikerade tjänsten. Du måste därför vänta tio minuter innan du kan använda den här resan.

## Bästa praxis {#best-practices-segments}

Aktiviteten **[!UICONTROL Audience Qualification]** gör att enskilda personer som är kvalificerade eller diskvalificerade från en Adobe Experience Platform-publik kan komma in direkt på resor.

Mottagningshastigheten för den här informationen är hög. Mätningarna visar en hastighet på 10 000 mottagna händelser per sekund. Därför bör du se till att du förstår hur höga ingångstoppar kan bli, hur du undviker dem och hur du gör din resa redo för dem.

### Gruppera målgrupper{#batch-speed-segment-qualification}

Observera att när du använder målgruppskvalifikation för en grupppublik kommer det att ske en topp vid tidpunkten för den dagliga beräkningen. Storleken på toppen beror på antalet individer som kommer in (eller avslutar) per dag.

Dessutom, om målgruppen är nyskapad och omedelbart används under en resa, kan den första beräkningsgruppen få ett mycket stort antal personer att komma in på resan.

### Direktuppspelade målgrupper{#streamed-speed-segment-qualification}

När man använder målgruppskvalifikationer för direktuppspelade målgrupper är risken mindre för att få stora toppar av ingångar/utgångar på grund av den kontinuerliga utvärderingen av målgruppen. Men om målgruppsdefinitionen leder till att ett stort antal kunder kvalificerar sig samtidigt kan det ändå bli en höjdpunkt.

Undvik att använda öppna och skicka händelser med direktuppspelningssegmentering. Använd istället riktiga användaraktivitetssignaler som klickningar, köp eller beacon-data. Använd affärsregler i stället för att skicka händelser för frekvens- eller undertryckningslogik. [Läs mer](../audience/about-audiences.md#open-and-send-event-guardrails)

Mer information om direktuppspelningssegmentering finns i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html#api).

### Så här undviker du överbelastningar{#overloads-speed-segment-qualification}

Här följer några tips som hjälper dig att undvika att överbelasta system som används på resor (datakällor, anpassade åtgärder, kanalåtgärder).

Använd inte en gruppmålgrupp i en **[!UICONTROL Audience Qualification]**-aktivitet omedelbart efter att den har skapats. Den första beräkningstopp undviks. Observera att det kommer att finnas en gul varning på arbetsytan om du ska använda en målgrupp som aldrig har beräknats.

![](assets/segment-error.png)

Införa en begränsning för datakällor och åtgärder som används under resor för att undvika att överbelasta dem. Läs mer i [Journey Orchestration-dokumentationen](https://experienceleague.adobe.com/docs/journeys/using/working-with-apis/capping.html){target="_blank"}. Observera att begränsningsregeln inte har några nya försök. Om du behöver göra ett nytt försök måste du använda en alternativ sökväg under resan genom att markera kryssrutan **[!UICONTROL Add an alternative path in case of a timeout or an error]** i villkor eller åtgärder.

Innan ni använder målgruppen i en produktionsresa måste ni först och främst utvärdera mängden individer som är kvalificerade för denna målgrupp varje dag. Om du vill göra det kan du kontrollera menyn **[!UICONTROL Audience]**, öppna målgruppen och sedan titta på diagrammet **[!UICONTROL Profiles over time]**.

![](assets/segment-overload.png)

## Instruktionsvideo {#video}

Förstå tillämpliga användningsfall för målgruppskompetensresor. Lär dig hur du bygger en resa med målgruppskvalifikation och vilka metodtips som ska användas.

>[!VIDEO](https://video.tv.adobe.com/v/3425028?quality=12)
