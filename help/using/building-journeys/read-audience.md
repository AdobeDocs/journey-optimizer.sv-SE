---
solution: Journey Optimizer
product: journey optimizer
title: Använda en målgrupp i en resa
description: Lär dig hur du använder en målgrupp på en resa
feature: Journeys, Activities, Audiences
topic: Content Management
role: User
level: Intermediate
keywords: aktivitet, resa, läsning, målgrupp, plattform
exl-id: 7b27d42e-3bfe-45ab-8a37-c55b231052ee
source-git-commit: 6ff54583c729175c74b3a7ea4ab9188505fde897
workflow-type: tm+mt
source-wordcount: '1436'
ht-degree: 0%

---

# Använda en målgrupp i en resa {#segment-trigger-activity}

## Lägg till aktiviteten Läs målgrupp {#about-segment-trigger-actvitiy}

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment"
>title="Läs målgruppsaktivitet"
>abstract="Med aktiviteten Läs målgrupp kan du få alla som tillhör en Adobe Experience Platform-målgrupp att delta i en resa. Ingången till en resa kan genomföras antingen en gång eller regelbundet."

Använd **Läs målgrupp** aktivitet för att få alla enskilda personer i en målgrupp att komma in på resan. Ingången till en resa kan genomföras antingen en gång eller regelbundet.

Låt oss som exempel ta målgruppen&quot;Luma app opening and checkout&quot; som skapats i [Bygg målgrupper](../audience/about-audiences.md) användningsfall. Med aktiviteten Läs målgrupp kan ni få alla personer som tillhör den här målgruppen att resa in på en resa och få dem att flöda in i personaliserade resor som kan utnyttja alla resefunktioner: villkor, tidtagare, händelser och aktiviteter.

➡️ [Upptäck den här funktionen i video](#video)

## Måste läsas {#must-read}

* För resor med **Läs målgrupp** aktiviteten, det finns ett maximalt antal resor som kan påbörjas samtidigt. Nya försök kommer att utföras av systemet, men det går inte att utföra mer än fem resor (med **Läs målgrupp**, schemalagd eller med start&quot;så snart som möjligt&quot;) med början vid exakt samma tidpunkt. Det bästa är att sprida dem över tiden, till exempel mellan 5 och 10 minuter.

* Det går inte att använda fältgrupper för upplevelsehändelser i resor som börjar med en **Läsa målgrupper** aktivitet, **[Målgruppskvalifikation](audience-qualification-events.md)** aktivitet eller en affärshändelseaktivitet.

* Vi rekommenderar att du endast använder gruppmålgrupper i en **Läsa målgrupper** aktivitet. Detta ger en tillförlitlig och enhetlig räkning för de målgrupper som används under en resa. Läsarna är utformade för att gruppbearbetas. Om ditt användningsfall behöver realtidsdata ska du använda **[Målgruppskvalifikation](audience-qualification-events.md)** aktivitet.

* Målgrupper [importerad från en CSV-fil](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#import-audience) eller som härrör från [arbetsflöden för disposition](../audience/get-started-audience-orchestration.md) kan markeras i **Läs målgrupp** aktivitet. Dessa målgrupper är inte tillgängliga i **Målgruppskvalifikation** aktivitet.

## Konfigurera aktiviteten {#configuring-segment-trigger-activity}

Så här konfigurerar du aktiviteten Läs målgrupp:

1. Ta fram **[!UICONTROL Orchestration]** kategori och släpp en **[!UICONTROL Read Audience]** på arbetsytan.

   Aktiviteten måste placeras som det första steget i en resa.

1. Lägg till en **[!UICONTROL Label]** till aktiviteten (valfritt).

1. I **[!UICONTROL Audience]** väljer du den Adobe Experience Platform-målgrupp som ska delta i resan och klickar sedan **[!UICONTROL Save]**. Du kan välja vilken Adobe Experience Platform-målgrupp som helst som genereras med [segmentdefinitioner](../audience/creating-a-segment-definition.md).

   >[!NOTE]
   >
   >Dessutom kan ni inrikta er på Adobe Experience Platform målgrupper som skapats med [målgruppskompositioner](../audience/get-started-audience-orchestration.md) eller [överförd från en CSV-fil](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#import-audience){target="_blank"}.

   Observera att du kan anpassa kolumnerna som visas i listan och sortera dem.

   ![](assets/read-segment-selection.png)

   När målgruppen lagts till **[!UICONTROL Copy]** kan du kopiera dess namn och ID:

   `{"name":"Luma app opening and checkout","id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](assets/read-segment-copy.png)

   >[!NOTE]
   >
   >Endast personer med **Realiserad** och **Befintlig** Status för målgruppsdeltagande kommer att ta sig in på resan. Mer information om hur du utvärderar en målgrupp finns i [Dokumentation för segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html#interpret-segment-results){target="_blank"}.

1. I **[!UICONTROL Namespace]** väljer du det namnutrymme som ska användas för att identifiera de enskilda personerna. Som standard är fältet förifyllt med det senast använda namnutrymmet. [Läs mer om namnutrymmen](../event/about-creating.md#select-the-namespace).

   >[!NOTE]
   >
   >Individer som tillhör en målgrupp som inte har den valda identiteten (namnutrymmet) bland sina olika identiteter kan inte ta sig in på resan. Du kan bara välja ett personbaserat ID-namnutrymme. Om du har definierat ett namnutrymme för en uppslagstabell (till exempel: ProductID-namnutrymme för en produktsökning), är det inte tillgängligt i **Namnutrymme** listruta.

1. Ange **[!UICONTROL Reading rate]**. Det här är det maximala antalet profiler som kan komma in på resan per sekund. Denna avgift gäller endast denna aktivitet och inga andra delar av resan. Om du till exempel vill definiera en begränsningsfrekvens för anpassade åtgärder måste du använda begränsnings-API:t. Se detta [page](../configuration/throttling.md).

   Det här värdet lagras i transportversionens nyttolast. Standardvärdet är 5 000 profiler per sekund. Du kan ändra det här värdet från 500 till 20 000 profiler per sekund.

   >[!NOTE]
   >
   >Den totala läshastigheten per sandlåda är satt till 20 000 profiler per sekund. Läsfrekvensen för alla läsmålgrupper som körs samtidigt i samma sandlåda uppgår därför till högst 20 000 profiler per sekund. Du kan inte ändra denna ände.

1. The **[!UICONTROL Read Audience]** gör att du kan ange när målgruppen ska gå in på resan. Klicka på **[!UICONTROL Edit journey schedule]** länk för att komma åt resans egenskaper och konfigurera sedan **[!UICONTROL Scheduler type]** fält.

   ![](assets/read-segment-schedule.png)

   Som standard deltar målgrupperna i resan **[!UICONTROL As soon as possible]**. Om du vill att publiken ska ange resan ett visst datum/tid eller regelbundet, väljer du önskat värde i listan.

   >[!NOTE]
   >
   >Observera att **[!UICONTROL Schedule]** -avsnittet är bara tillgängligt när en **[!UICONTROL Read Audience]** aktiviteten har släppts på arbetsytan.

   ![](assets/read-segment-schedule-list.png)

   **Inkrementell läsning** alternativ: när en resa med återkommande **Läsa målgrupper** körs för första gången så att alla profiler i målgruppen kommer in på resan. Med det här alternativet kan ni efter den första förekomsten endast inrikta er på de personer som har gått in i målgruppen sedan den senaste körningen av resan.

       >[!OBS!]
       >
       >Om du riktar in dig på en [anpassad publik för överföring](../audience/about-audiences.md#segments-in-travel-optimizer) i din resa hämtas profiler endast vid den första upprepningen om det här alternativet är aktiverat i en återkommande resa, eftersom dessa målgrupper är fasta.
   
   **Tvinga återinträde vid upprepning**: det här alternativet gör att du kan göra så att alla profiler fortfarande finns kvar i resan automatiskt avslutar den vid nästa körning. Om du till exempel har två dagar på dig att vänta på en daglig återkommande resa, genom att aktivera det här alternativet, kommer profiler alltid att flyttas på nästa körning (så dagen efter), oavsett om de är i nästa körda målgrupp eller inte. Om livscykeln för dina profiler under den här resan kan vara längre än frekvensen för återkommande aktiviteter ska du inte aktivera det här alternativet för att säkerställa att profilerna kan slutföra sin resa.

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
>En bild Läs målgruppsresorna och gå till **Slutförd** status 91 dagar ([standardtimeout](journey-gs.md#global_timeout)) efter resan. För schemalagda läsmålgrupper är det 91 dagar efter den sista förekomsten.

## Testa och publicera resan {#testing-publishing}

The **[!UICONTROL Read Audience]** kan du testa resan med en enhetlig profil.

Det gör du genom att aktivera testläget.

![](assets/read-segment-test-mode.png)

Konfigurera och kör testläget som vanligt. [Lär dig testa en resa](testing-the-journey.md).

När testet är klart **[!UICONTROL Show logs]** kan du se testresultaten. Mer information finns i [det här avsnittet](testing-the-journey.md#viewing_logs)

![](assets/read-segment-log.png)

När testerna är klara kan du publicera din resa (se [Publicera resan](publishing-the-journey.md)). Personer som tillhör målgruppen kommer att delta i resan det datum/den tidpunkt som anges i färdens egendom **[!UICONTROL Scheduler]** -avsnitt.

>[!NOTE]
>
>För återkommande målgruppsbaserade resor stängs resan automatiskt när den sista förekomsten av den har utförts. Om inget slutdatum/sluttid har angetts måste du stänga resan till nya ingångar manuellt för att avsluta den.

## Målgruppsanpassning för målgruppsbaserade resor

Målgruppsbaserade resor börjar alltid med en **Läs målgrupp** aktivitet för att ta fram individer som tillhör en Adobe Experience Platform-publik.

Den målgrupp som tillhör målgruppen hämtas en gång eller regelbundet.

Efter att du gått in på resan kan du skapa målgruppsexempel som gör att individer från den ursprungliga målgruppen kan flöda in i olika delar av resan.

**Segmentering**

Du kan använda villkor för att utföra segmentering med **Villkor** aktivitet. Du kan t.ex. få VIP personer att ta en viss sökväg och icke-VIP i en annan bana.

Segmenteringen kan baseras på:

* datakälldata
* kontexten för händelser som ingår i resedata, till exempel: klickade en person på meddelandet som togs emot för en timme sedan?
* Ett datum, till exempel: Är vi i juni när en person går genom resan?
* en tid, till exempel: är det morgon i personens tidszon?
* en algoritm som delar den målgrupp som flödar i resan baserat på en procentandel, till exempel: 90 % - 10 % för att utesluta en kontrollgrupp

![](assets/read-segment-audience1.png)

**Uteslutning**

Samma **Villkor** som används för segmentering (se ovan) gör det även möjligt att utesluta en del av populationen. Du kan till exempel utesluta VIP personer genom att låta dem flöda in i en gren med ett slutsteg direkt efter.

Detta kan inträffa direkt efter det att målgruppen har hämtats, för att räkna antalet personer eller längs en flerstegsresa.

![](assets/read-segment-audience2.png)

**Union**

Med Resor kan du skapa N-grenar och förena dem efter en segmentering.

Det innebär att ni kan få två målgrupper att återvända till en gemensam upplevelse.

Om du till exempel har följt en annan upplevelse under tio dagar på en resa kan VIP och icke-VIP kunder återvända till samma resa.

Efter en union kan du dela upp publiken igen genom att utföra en segmentering eller ett exkluderingsmoment.

![](assets/read-segment-audience3.png)

## Instruktionsvideo {#video}

Förstå tillämpliga användningsfall för en resa som triggas av läsmålgruppsaktiviteten. Lär dig hur du bygger batchbaserade resor och vilka metodtips som ska användas.

>[!VIDEO](https://video.tv.adobe.com/v/3424997?quality=12)
