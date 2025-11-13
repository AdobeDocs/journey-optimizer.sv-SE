---
solution: Journey Optimizer
product: journey optimizer
title: Publikkvalificeringshändelser
description: Lär dig hur du använder och konfigurerar kvalificeringshändelser för målgrupper
feature: Journeys, Activities, Audiences
topic: Content Management
role: User
level: Intermediate
keywords: kvalificering, evenemang, målgrupp, resa, plattform
exl-id: 7e70b8a9-7fac-4450-ad9c-597fe0496df9
version: Journey Orchestration
source-git-commit: 7822e9662d03e6c6b2d5bc5ecb9ca85dc32f0942
workflow-type: tm+mt
source-wordcount: '1247'
ht-degree: 1%

---

# Publikkvalificeringshändelser {#segment-qualification}

>[!CONTEXTUALHELP]
>id="ajo_journey_event_segment_qualification"
>title="Elevkvalificeringshändelser"
>abstract="Med den här aktiviteten kan din resa lyssna på ingångar och utgångar för profiler i Adobe Experience Platform-målgrupper för att få individer att komma in på eller gå framåt under en resa."

## Om kvalificeringshändelser för målgrupper{#about-segment-qualification}

Med den här aktiviteten kan din resa lyssna på ingångar och utgångar för profiler i Adobe Experience Platform-målgrupper för att få individer att komma in på eller gå framåt under en resa. Mer information om att skapa målgrupper finns i det här [avsnittet](../audience/about-audiences.md).

Säg att ni har en&quot;silverkund&quot; som målgrupp. Med den här aktiviteten kan ni få alla nya silverkunder att ta sig in på en resa och skicka en serie personaliserade meddelanden till dem.

Den här typen av händelse kan placeras som det första steget eller senare under resan.

➡️ [Upptäck den här funktionen i en video](#video)


>[!CAUTION]
>
>Innan du börjar konfigurera en målgruppskvalifikation ska du [läsa GuarDRAils and Limitation](#audience-qualification-guardrails).


## Konfigurera aktiviteten {#configure-segment-qualification}

Så här konfigurerar du aktiviteten **[!UICONTROL Audience Qualification]**:

1. Öppna kategorin **[!UICONTROL Events]** och släpp en **[!UICONTROL Audience Qualification]**-aktivitet på arbetsytan.

   ![Publikkvalificeringshändelse på resepaletten](assets/segment5.png)

1. Lägg till en **[!UICONTROL Label]** i aktiviteten. Det här steget är valfritt.

1. Klicka i fältet **[!UICONTROL Audience]** och välj de målgrupper du vill använda.

   >[!NOTE]
   >
   >Du kan anpassa kolumnerna som visas i listan och sortera dem.

   ![Listruta för val av publik för konfiguration av kvalificeringshändelse](assets/segment6.png)

   När målgruppen har lagts till kan du med knappen **[!UICONTROL Copy]** kopiera dess namn och ID:

   `{"name":"Loyalty membership","id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![Kopiera-knapp för att kopiera målgruppsnamn och ID i JSON-format](assets/segment-copy.png)

1. I fältet **[!UICONTROL Behaviour]** väljer du om du vill lyssna på målgruppsinkomster, utgångar eller både och.

   >[!NOTE]
   >
   >**[!UICONTROL Enter]** och **[!UICONTROL Exit]** motsvarar **Realiserad** och **Avslutade** målgruppsdeltagarstatus från Adobe Experience Platform. Mer information om hur du utvärderar en målgrupp finns i [dokumentationen för segmenteringstjänsten](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=sv-SE#interpret-segment-results){target="_blank"}.

1. Välj ett namnutrymme. Detta behövs bara om händelsen är placerad som det första steget i resan. Som standard är fältet förifyllt med det senast använda namnutrymmet.

   >[!NOTE]
   >
   >Du kan bara välja ett personbaserat ID-namnutrymme. Om du har definierat ett namnområde för en uppslagstabell (till exempel: ProductID-namnområde för en produktsökning), är det inte tillgängligt i listrutan **Namespace**.

   ![Namnområdesval för publikens kvalificeringsidentitet](assets/segment7.png)

Nyttolasten innehåller följande kontextinformation som du kan använda i villkor och åtgärder:

* beteendet (entré, exit)
* tidsstämpel för kvalificeringen
* målgrupps-ID

När du använder uttrycksredigeraren i ett villkor eller en åtgärd som följer efter en **[!UICONTROL Audience Qualification]**-aktivitet har du tillgång till noden **[!UICONTROL AudienceQualification]**. Du kan välja mellan **[!UICONTROL Last qualification time]** och **[!UICONTROL status]** (ange eller avsluta).

Se [Villkorsaktivitet](../building-journeys/condition-activity.md#about_condition).

![Konfigurationen av målgruppsinkomst och -avslutning i händelseinställningarna](assets/segment8.png)

En ny resa som innehåller en **publikkvalificeringshändelse** tas i bruk tio minuter efter att du har publicerat den. Det här tidsintervallet motsvarar cacheuppdateringsintervallet för den dedikerade tjänsten. Du måste därför vänta tio minuter innan du kan använda den här resan.

## Bästa praxis {#best-practices-segments}

Aktiviteten **[!UICONTROL Audience Qualification]** gör att enskilda personer som är kvalificerade eller diskvalificerade från en Adobe Experience Platform-publik kan komma in direkt på resor.

Mottagningshastigheten för den här informationen är hög. Mätningarna visar en hastighet på 10 000 mottagna händelser per sekund. Det innebär att ni måste förstå hur höga ingångspetsarna kan vara, hur ni undviker dem och hur ni gör er resa redo för dem. Läs mer om resefrekvenser och dataflödesgränser i [det här avsnittet](entry-management.md#journey-processing-rate).

### Gruppera målgrupper {#batch-speed-segment-qualification}

När du använder Audience Qualification för en grupppublik bör du tänka på att en ingångstopp inträffar vid tidpunkten för den dagliga beräkningen. Toppens storlek beror på hur många personer som dagligen går in (eller avslutar) i publiken.

Dessutom, om målgruppen är nyskapad och omedelbart används under en resa, kan den första beräkningsgruppen leda till att ett mycket stort antal individer kommer in på resan.

### Direktuppspelade målgrupper {#streamed-speed-segment-qualification}

När man använder sig av Audience Qualification för direktuppspelade målgrupper är risken mindre för höga ingångs-/utgångstoppar på grund av den kontinuerliga utvärderingen av målgruppen. Men om målgruppsdefinitionen leder till en stor mängd kunder som kvalificerar sig samtidigt kan det ändå bli en topp.

Undvik att använda öppna och skicka händelser med direktuppspelningssegmentering. Använd istället riktiga användaraktivitetssignaler som klickningar, köp eller beacon-data. Använd affärsregler i stället för att skicka händelser för frekvens- eller undertryckningslogik. [Läs mer](../audience/about-audiences.md)

Mer information om direktuppspelningssegmentering finns i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/sv/docs/experience-platform/segmentation/methods/streaming-segmentation){target="_blank"}.

### Så här undviker du överbelastningar {#overloads-speed-segment-qualification}

Här följer några tips för att undvika att överbelasta system som används i resor (datakällor, anpassade åtgärder, kanalåtgärder):

* Använd inte en gruppmålgrupp omedelbart efter att den har skapats i en **[!UICONTROL Audience Qualification]**-aktivitet. På så sätt undviks den första beräkningstopp. En gul varning visas på arbetsytan om du ska använda en målgrupp som aldrig har beräknats.

  ![Felmeddelande när målgruppen inte hittas i Adobe Experience Platform](assets/segment-error.png)

* Införa en begränsning för datakällor och åtgärder som används under resor för att undvika att överbelasta dem. Läs mer i [Journey Orchestration-dokumentation](https://experienceleague.adobe.com/docs/journeys/using/working-with-apis/capping.html?lang=sv-SE){target="_blank"}. Observera att begränsningsregeln inte har några nya försök. Om du behöver göra ett nytt försök använder du en alternativ sökväg under resan genom att markera kryssrutan **[!UICONTROL Add an alternative path in case of a timeout or an error]** i villkor eller åtgärder.

* Innan målgruppen används i en produktionsresa bör man utvärdera den mängd individer som är kvalificerade för denna målgrupp varje dag. Det gör du genom att kontrollera menyn **[!UICONTROL Audience]**, öppna målgruppen och titta på diagrammet **[!UICONTROL Profiles over time]**.

  ![Varningsmeddelande när målgruppen har för många händelser för realtidsbearbetning](assets/segment-overload.png)

Läs mer om hastighetsbegränsningar och dataflöde i [det här avsnittet](entry-management.md#profile-entrance-rate).

## Skyddsritningar och begränsningar {#audience-qualification-guardrails}

Följ skyddsutkastet och rekommendationerna nedan för att skapa målgruppskompetensresor. Se även [Bästa praxis för målgruppskvalifikation](#best-practices-segments).


* Målgruppskompetensresor är främst utformade för att fungera med direktuppspelande målgrupper. Den här kombinationen ger en bättre realtidsupplevelse. Vi rekommenderar starkt att du använder **direktuppspelade målgrupper** i aktiviteten Audience Qualification.

  Men om du vill använda batchmatningsbaserade attribut i en direktuppspelande målgrupp eller en batchmålgrupp för en Audience Qualification-resa, bör du överväga tidsrymden för målgruppsutvärdering/aktivering. En gruppmålgrupp eller målgrupp som använder batchimporterade attribut blir klar att använda i aktiviteten **Målgruppskvalificering** ungefär **timmar** efter att segmenteringsjobbet har slutförts. Jobbet körs en gång om dagen vid den tidpunkt som anges av din Adobe-administratör.

* Adobe Experience Platform-målgrupper beräknas antingen en gång om dagen (**batch** målgrupper) eller i realtid (för **direktuppspelade** målgrupper, med alternativet High Frequency Audiences i Adobe Experience Platform).

   * Om den valda publiken direktuppspelas kan individer som tillhör den här publiken komma in på resan i realtid.
   * Om målgruppen är en batch kommer personer som nyligen är kvalificerade för den här målgruppen att kunna delta i resan när målgruppsberäkningen görs på Adobe Experience Platform.

  Det är en god praxis att använda direktuppspelade målgrupper i en **målgruppskvalificeringsaktivitet**. Använd en **[Läs målgruppsaktivitet](read-audience.md)** för gruppanvändningsfall.

  >[!NOTE]
  >
  >På grund av batchbeskaffenheten hos målgrupper som skapats med kompositionsarbetsflöden och anpassade överföringar kan dessa målgrupper inte ingå i en&quot;målgruppskompetens&quot;-aktivitet. Endast målgrupper som skapats med segmentdefinitioner kan utnyttjas i den här aktiviteten.


* Det går inte att använda fältgrupper för upplevelsehändelser i resor som börjar med en **Läs målgrupp**, en **målkvalificering** eller en **affärshändelse**-aktivitet.

* När du använder en **målgruppskvalifikation**-aktivitet på en resa kan det ta upp till 10 minuter innan aktiviteten är aktiv och avlyssnar profiler som kommer in eller lämnar målgruppen.


>[!CAUTION]
>
>[Garantier för kundprofildata och segmentering i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html?lang=sv-SE){target="_blank"} gäller även för Adobe Journey Optimizer.



## Instruktionsvideo {#video}

Lär dig mer om tillämpliga användningsfall för målgruppskvalificeringsresor i den här videon. Lär dig hur du bygger en resa med målgruppskvalifikation och vilka bästa metoder som ska användas.

>[!VIDEO](https://video.tv.adobe.com/v/3446208?captions=swe&quality=12)
