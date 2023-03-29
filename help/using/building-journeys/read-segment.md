---
solution: Journey Optimizer
product: journey optimizer
title: Använd ett segment i en resa
description: Lär dig hur du använder ett segment i en resa
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: aktivitet, resa, läsning, segment, plattform
exl-id: 7b27d42e-3bfe-45ab-8a37-c55b231052ee
source-git-commit: 4f3d22c9ce3a5b77969a2a04dafbc28b53f95507
workflow-type: tm+mt
source-wordcount: '1303'
ht-degree: 3%

---

# Använd ett segment i en resa {#segment-trigger-activity}

## Lägg till en Läs segment-aktivitet {#about-segment-trigger-actvitiy}

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment"
>title="Läsa segmentaktivitet"
>abstract="Med Läs segment-aktiviteten kan alla personer som tillhör ett Adobe Experience Platform-segment delta i en resa. Inträde i en resa kan genomföras antingen en gång eller regelbundet."

Använd **Läs segment** aktivitet för att få alla individer i ett segment att komma in på resan. Inträde i en resa kan genomföras antingen en gång eller regelbundet.

Låt oss som exempel ta segmentet&quot;Luma app opening and checkout&quot; som skapats i [Skapa segment](../segment/about-segments.md) användningsfall. Med aktiviteten Läs segment kan du få alla personer som tillhör det här segmentet att komma in på en resa och få dem att flöda in i personaliserade resor som utnyttjar alla resefunktioner: villkor, timers, events, actions.

>[!NOTE]
>
>För resor som använder en Läs segment-aktivitet finns det ett maximalt antal resor som kan påbörjas exakt samtidigt. Återförsök kommer att utföras av systemet men undvik att ha fler än fem resor (med Läs segment, schemalagd eller starta&quot;så snart som möjligt&quot;) med början vid exakt samma tidpunkt genom att sprida dem över tiden, t.ex. mellan 5 och 10 minuter.
>
>Det går inte att använda fältgrupper för upplevelsehändelser i resor som börjar med ett Lässegment, en segmentkvalificering eller en affärshändelseaktivitet.

### Konfigurera aktiviteten {#configuring-segment-trigger-activity}

Så här konfigurerar du Läs segment-aktiviteten:

1. Ta fram **[!UICONTROL Orchestration]** kategori och släpp en **[!UICONTROL Read Segment]** på arbetsytan.

   Aktiviteten måste placeras som det första steget i en resa.

1. Lägg till en **[!UICONTROL Label]** till aktiviteten (valfritt).

1. I **[!UICONTROL Segment]** väljer du det Adobe Experience Platform-segment som ska delta i resan och klickar sedan **[!UICONTROL Save]**.

   Observera att du kan anpassa kolumnerna som visas i listan och sortera dem.

   >[!NOTE]
   >
   >Endast personer med **Realiserad** och **Befintlig** Deltagandestatus för segment kommer att gå in på resan. Mer information om hur du utvärderar ett segment finns i [Dokumentation för segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html#interpret-segment-results){target="_blank"}.

   ![](assets/read-segment-selection.png)

   När segmentet har lagts till visas **[!UICONTROL Copy]** kan du kopiera dess namn och ID:

   `{"name":"Luma app opening and checkout",”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](assets/read-segment-copy.png)

1. I **[!UICONTROL Namespace]** väljer du det namnutrymme som ska användas för att identifiera de enskilda personerna. Som standard är fältet förifyllt med det senast använda namnutrymmet. [Läs mer om namnutrymmen](../event/about-creating.md#select-the-namespace).

   >[!NOTE]
   >
   >Individer som tillhör ett segment som inte har den valda identiteten (namnutrymmet) bland sina olika identiteter kan inte ta sig in på resan. Du kan bara välja ett personbaserat ID-namnutrymme. Om du har definierat ett namnutrymme för en uppslagstabell (till exempel: ProductID-namnområde för en produktsökning), är det inte tillgängligt i **Namnutrymme** listruta.

1. Ange **[!UICONTROL Throttling rate]** till genomströmningsgränsen för lässegmentsaktiviteten.

   Det här värdet lagras i transportversionens nyttolast. Standardvärdet är 5 000 meddelanden per sekund. Du kan ändra det här värdet från 500 till 20 000 meddelanden per sekund.

   >[!NOTE]
   >
   >Den totala begränsningsfrekvensen per sandlåda är inställd på 20 000 meddelanden per sekund. Begränsningsfrekvensen för alla lässegment som körs samtidigt i samma sandlåda uppgår därför till högst 20 000 meddelanden per sekund. Du kan inte ändra denna ände.

1. The **[!UICONTROL Read Segment]** kan du ange vid vilken tidpunkt segmentet ska börja färden. Om du vill göra det klickar du på **[!UICONTROL Edit journey schedule]** länk för att komma åt resans egenskaper och konfigurera sedan **[!UICONTROL Scheduler type]** fält.

   ![](assets/read-segment-schedule.png)

   Som standard kommer segment in på resan **[!UICONTROL As soon as possible]**. Om du vill att segmentet ska anges på en viss dag/tid eller på en återkommande basis, väljer du önskat värde i listan.

   >[!NOTE]
   >
   >Observera att **[!UICONTROL Schedule]** -avsnittet är bara tillgängligt när en **[!UICONTROL Read Segment]** aktiviteten har släppts på arbetsytan.

   ![](assets/read-segment-schedule-list.png)

   **Inkrementell läsning** alternativ: när en resa med återkommande **Lässegment** körs för första gången så att alla profiler i segmentet kommer in på resan. Med det här alternativet kan du efter den första förekomsten endast rikta in dig på de personer som har gått in i segmentet sedan den senaste körningen av resan.

   **Tvinga återinträde vid upprepning**: Med det här alternativet kan du göra så att alla profiler fortfarande finns kvar på resan automatiskt avslutar den vid nästa körning. Om du till exempel har två dagar på dig att vänta på en daglig återkommande resa, genom att aktivera det här alternativet, kommer profiler alltid att flyttas på nästa körning (så dagen efter), oavsett om de är i nästa körda målgrupp eller inte. Om livscykeln för dina profiler under den här resan kan vara längre än frekvensen för återkommande aktiviteter ska du inte aktivera det här alternativet för att säkerställa att profilerna kan slutföra sin resa.

<!--

### Segment filters {#segment-filters}

[!CONTEXTUALHELP]
>id="jo_segment_filters"
>title="About segment filters"
>abstract="You can choose to target only the individuals who entered or exited a specific segment during a specific time window. For example, you can decide to only retrieve all the customers who entered the VIP segment since last week."

You can choose to target only the individuals who entered or exited a specific segment during a specific time window. For example, you can decide to only retrieve all the customers who entered the VIP segment since last week. Only the new VIP customers will be targeted. All the customers who were already part of the VIP segment before will be excluded.

To activate this mode, click the **Segment Filters** toggle. Two fields are displayed:

**Segment membership**: choose whether you want to listen to segment entrances or exits. 

**Lookback window**: define when you want to start to listen to entrances or exits. This lookback window is expressed in hours, starting from the moment the journey is triggered.  If you set this duration to 0, the journey will target all members of the segment. For recurring journeys, it will take into account all entrances/exits since the last time the journey was triggered.

-->

>[!NOTE]
>
>Enbildsresor för Läs segment flyttas till statusen Slutförd 30 dagar efter körningen. För schemalagda läs-segment är det 30 dagar efter körningen av den sista förekomsten.

### Testa och publicera resan {#testing-publishing}

The **[!UICONTROL Read Segment]** kan du testa resan antingen med en enhetlig profil eller med 100 slumpmässiga testprofiler som valts bland de profiler som är kvalificerade för segmentet.

Aktivera testläget och välj sedan önskat alternativ i den vänstra rutan.

![](assets/read-segment-test-mode.png)

Sedan kan du konfigurera och köra testläget som vanligt. [Lär dig hur du testar en resa](testing-the-journey.md).

När testet är klart **[!UICONTROL Show logs]** kan du se testresultaten enligt det valda testalternativet:

* **[!UICONTROL Single profile at a time]**: testloggarna visar samma information som när det enhetstestläget används. Mer information om detta finns i [det här avsnittet](testing-the-journey.md#viewing_logs)

* **[!UICONTROL Up to 100 profiles at once]**: Med testloggarna kan du följa hur segmentexporten från Adobe Experience Platform fortskrider samt hur alla personer som passerat resan fortskrider.

   Observera att det inte går att följa förloppet för de personer som befinner sig på resan med hjälp av det visuella flödet om du testar resan med upp till 100 profiler samtidigt.

   ![](assets/read-segment-log.png)

När testerna är klara kan du publicera din resa (se [Publicera resan](publishing-the-journey.md)). Enskilda personer som tillhör segmentet kommer att resa in på den dag/tid som anges i färdens egenskaper **[!UICONTROL Scheduler]** -avsnitt.

>[!NOTE]
>
>Vid återkommande segmentbaserade resor stängs resan automatiskt när den sista förekomsten görs. Om inget slutdatum/sluttid har angetts måste du stänga resan till nya ingångar manuellt för att avsluta den.

## Målgruppsanpassning vid segmentbaserade resor

Segmentbaserade resor börjar alltid med en **Läs segment** aktivitet för att hämta individer som tillhör ett Adobe Experience Platform-segment.

Den målgrupp som tillhör segmentet hämtas en gång eller regelbundet.

Efter att du har gått in på resan kan du skapa exempel på målgruppsanvändning, vilket gör att individer från det ursprungliga segmentet kan flöda in i olika delar av resan.

**Segmentering**

Du kan använda villkor för att utföra segmentering med **Villkor** aktivitet. Du kan t.ex. få VIP personer att ta en viss sökväg och icke-VIP i en annan bana.

Segmenteringen kan baseras på:

* datakälldata
* kontexten för händelser som ingår i resedata, t.ex. klickade någon på meddelandet som togs emot för en timme sedan?
* ett datum, till exempel: Är vi i juni när en person går igenom resan?
* en tid, till exempel: är det morgon i personens tidszon?
* en algoritm som delar den målgrupp som flödar i resan baserat på en procentandel, till exempel: 90 % - 10 % för att exkludera en kontrollgrupp

![](assets/read-segment-audience1.png)

**Uteslutning**

Samma **Villkor** som används för segmentering (se ovan) gör det även möjligt att utesluta en del av populationen. Du kan till exempel utesluta VIP personer genom att låta dem flöda in i en gren med ett slutsteg direkt efter.

Detta kan inträffa direkt efter segmenthämtning, för populationsinventering eller längs en flerstegsresa.

![](assets/read-segment-audience2.png)

**Union**

Med Resor kan du skapa N-grenar och förena dem efter en segmentering.

Det innebär att ni kan få två målgrupper att återvända till en gemensam upplevelse.

Om du till exempel har följt en annan upplevelse under tio dagar på en resa kan VIP och icke-VIP kunder återvända till samma resa.

Efter en union kan du dela upp publiken igen genom att utföra en segmentering eller ett exkluderingsmoment.

![](assets/read-segment-audience3.png)
