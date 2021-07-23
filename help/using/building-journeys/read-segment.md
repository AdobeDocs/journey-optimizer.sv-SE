---
title: Använd ett segment i en resa
description: Lär dig hur du använder ett segment i en resa
feature: Resor
topic: Innehållshantering
role: User
level: Intermediate
source-git-commit: ac6ba317909c962a81c7043bfa2a56e94bc5c9ad
workflow-type: tm+mt
source-wordcount: '950'
ht-degree: 4%

---

# Använd ett segment i en resa {#segment-trigger-activity}

## Om aktiviteten Läs segment {#about-segment-trigger-actvitiy}

Med Läs segment-aktiviteten kan alla personer som tillhör ett Adobe Experience Platform-segment delta i en resa. Inträde i en resa kan genomföras antingen en gång eller regelbundet.

Låt oss som exempel ta segmentet&quot;Luma app opening and checkout&quot; som skapades i [Build segments](../segment/about-segments.md) use case. Med aktiviteten Läs segment kan du få alla personer som tillhör det här segmentet att komma in på en resa och få dem att flöda in i personaliserade resor som utnyttjar alla resefunktioner: villkor, timers, events, actions.

>[!NOTE]
>
>Det Burst-betalda tillägget gör det möjligt att skicka mycket snabba push-meddelanden i stora volymer för enkla resor som innehåller ett lässegment och ett enkelt push-meddelande. Mer information hittar du i [det här avsnittet](../building-journeys/journey-gs.md#burst)

### Konfigurera aktiviteten {#configuring-segment-trigger-activity}

Så här konfigurerar du Läs segment-aktiviteten:

1. Ta fram kategorin **[!UICONTROL Orchestration]** och släpp en **[!UICONTROL Read Segment]**-aktivitet på arbetsytan.

   Aktiviteten måste placeras som det första steget i en resa.

1. Lägg till en **[!UICONTROL Label]** till aktiviteten (valfritt).

1. I fältet **[!UICONTROL Segment]** väljer du det Adobe Experience Platform-segment som ska passera resan och klickar sedan på **[!UICONTROL Save]**.

   Observera att du kan anpassa kolumnerna som visas i listan och sortera dem.

   >[!NOTE]
   >
   >Det är bara de personer som har **realiserat** och **Befintliga** segmentdeltagarstatusar som kommer in på resan. Mer information om hur du utvärderar ett segment finns i [dokumentationen för segmenteringstjänsten](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html#interpret-segment-results){target=&quot;_blank&quot;}.

   ![](../assets/read-segment-selection.png)

   När segmentet har lagts till kan du med knappen **[!UICONTROL Copy]** kopiera dess namn och ID:

   `{"name":"Luma app opening and checkout",”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/read-segment-copy.png)

1. I fältet **[!UICONTROL Namespace]** väljer du det namnutrymme som ska användas för att identifiera personerna. [Läs mer om namnutrymmen](../event/about-creating.md#select-the-namespace).

   >[!NOTE]
   >
   >Individer som tillhör ett segment som inte har den valda identiteten (namnutrymmet) bland sina olika identiteter kan inte ta sig in på resan.

1. I fältet **[!UICONTROL Throttling rate]** definierar du genomströmningen för Läs-segmentsaktiviteten. Det här värdet lagras i transportversionens nyttolast. Standardvärdet är 17 000 och måste vara mellan 500 och 17 000.

1. Med aktiviteten **[!UICONTROL Read Segment]** kan du ange den tidpunkt då segmentet ska gå in i resan. Om du vill göra det klickar du på länken **[!UICONTROL Edit journey schedule]** för att komma åt resans egenskaper och konfigurerar sedan fältet **[!UICONTROL Scheduler type]**.

   ![](../assets/read-segment-schedule.png)

   Som standard anger segment resan **[!UICONTROL As soon as possible]**. Om du vill att segmentet ska anges på en viss dag/tid eller på en återkommande basis, väljer du önskat värde i listan.

   >[!NOTE]
   >
   >Observera att avsnittet **[!UICONTROL Schedule]** bara är tillgängligt när en **[!UICONTROL Read Segment]**-aktivitet har släppts på arbetsytan.

   ![](../assets/read-segment-schedule-list.png)

### Testa och publicera resan {#testing-publishing}

Med aktiviteten **[!UICONTROL Read Segment]** kan du testa resan antingen med en enhetsprofil eller med 100 slumpmässiga testprofiler som valts bland de profiler som är kvalificerade för segmentet.

Aktivera testläget och välj sedan önskat alternativ i den vänstra rutan.

![](../assets/read-segment-test-mode.png)

Sedan kan du konfigurera och köra testläget som vanligt. [Lär dig hur du testar en resa](testing-the-journey.md).

När testet är klart kan du med **[!UICONTROL Show logs]**-knappen se testresultaten enligt det valda testalternativet:

* **[!UICONTROL Single profile at a time]**: testloggarna visar samma information som när det enhetstestläget används. Mer information om detta finns i [det här avsnittet](testing-the-journey.md#viewing_logs)

* **[!UICONTROL Up to 100 profiles at once]**: Med testloggarna kan du följa hur segmentexporten från Adobe Experience Platform fortskrider samt hur alla personer som passerat resan fortskrider.

   Observera att det inte går att följa förloppet för de personer som befinner sig på resan med hjälp av det visuella flödet om du testar resan med upp till 100 profiler samtidigt.

   ![](../assets/read-segment-log.png)

När testen har slutförts kan du publicera din resa (se [Publicera resan](publishing-the-journey.md)). Individer som tillhör segmentet kommer att gå in i resan det datum/den tidpunkt som anges i avsnittet **[!UICONTROL Scheduler]** för färdens egenskaper.

>[!NOTE]
>
>Vid återkommande segmentbaserade resor stängs resan automatiskt när den sista förekomsten görs. Om inget slutdatum/sluttid har angetts måste du stänga resan till nya ingångar manuellt för att avsluta den.


## Målgruppsanpassning vid segmentbaserade resor

Segmentbaserade resor börjar alltid med en **Läs segment**-aktivitet för att hämta individer som tillhör ett Adobe Experience Platform-segment.

Den målgrupp som tillhör segmentet hämtas en gång eller regelbundet.

Efter att du har gått in på resan kan du skapa exempel på målgruppsanvändning, vilket gör att individer från det ursprungliga segmentet kan flöda in i olika delar av resan.

**Segmentering**

Du kan använda villkor för att utföra segmentering med aktiviteten **Villkor**. Du kan t.ex. få VIP personer att ta en viss sökväg och icke-VIP i en annan bana.

Segmenteringen kan baseras på:

* datakälldata
* kontexten för händelser som ingår i resedata, t.ex. klickade någon på meddelandet hon fick för en timme sedan?
* ett datum, till exempel: Är vi i juni när en person går igenom resan?
* en tid, till exempel: är det morgon i personens tidszon?
* en algoritm som delar den målgrupp som flödar i resan baserat på en procentandel, till exempel: 90 % - 10 % för att exkludera en kontrollgrupp

![](../assets/read-segment-audience1.png)

**Uteslutning**

Med samma **villkorsaktivitet** som används för segmentering (se ovan) kan du även utesluta delar av populationen. Du kan till exempel utesluta VIP personer genom att låta dem flöda in i en gren med ett slutsteg direkt efter.

Detta kan inträffa direkt efter segmenthämtning, för populationsinventering eller längs en flerstegsresa.

![](../assets/read-segment-audience2.png)

**Union**

Med Resor kan du skapa N-grenar och förena dem efter en segmentering.

Det innebär att ni kan få två målgrupper att återvända till en gemensam upplevelse.

Om du till exempel har följt en annan upplevelse under tio dagar på en resa kan VIP och icke-VIP kunder återvända till samma resa.

Efter en union kan du dela upp publiken igen genom att utföra en segmentering eller ett exkluderingsmoment.

![](../assets/read-segment-audience3.png)
