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
source-git-commit: 47185cdcfb243d7cb3becd861fec87abcef1f929
workflow-type: tm+mt
source-wordcount: '1654'
ht-degree: 0%

---

# Använda en målgrupp i en resa {#segment-trigger-activity}

## Lägg till aktiviteten Läs målgrupp {#about-segment-trigger-actvitiy}

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment"
>title="Läs målgruppsaktivitet"
>abstract="Med aktiviteten Läs målgrupp kan du få alla som tillhör en Adobe Experience Platform-målgrupp att delta i en resa. Ingången till en resa kan genomföras antingen en gång eller regelbundet."

Använd aktiviteten **Läs målgrupp** för att få alla personer i en målgrupp att komma in på resan. Ingången till en resa kan genomföras antingen en gång eller regelbundet.

Låt oss som exempel ta målgruppen&quot;Luma app opening and checkout&quot; som skapats i [Build audiences](../audience/about-audiences.md) -användningsexemplet. Med aktiviteten Läs målgrupp kan ni få alla personer som tillhör den här målgruppen att resa in på en resa och få dem att flöda in i personaliserade resor som kan utnyttja alla resefunktioner: villkor, tidtagare, händelser och aktiviteter.

➡️ [Upptäck den här funktionen i videon](#video)

## Garantier och bästa metoder {#must-read}

* Endast en **[!UICONTROL Read Audience]**-aktivitet kan användas på en resa och måste vara den första aktiviteten på arbetsytan.

* Aktiviteten **[!UICONTROL Read audience]** kan bara ha en målgrupp som mål. Om det krävs flera målgrupper bör du överväga att slå samman dessa målgrupper till en enda innan du använder dem. [Lär dig hur du kombinerar målgrupper med arbetsflöden för disposition](../audience/get-started-audience-orchestration.md)

* För resor som använder en **Läs målgrupp**-aktivitet finns det ett maximalt antal resor som kan påbörjas exakt samtidigt. Återförsök kommer att utföras av systemet men undvik att ha fler än fem resor (med **Läs målgrupp**, schemalagd eller starta &quot;så snart som möjligt&quot;) med början vid exakt samma tidpunkt. Det bästa är att sprida dem över tiden, till exempel mellan 5 och 10 minuter.

* Det går inte att använda fältgrupper för upplevelsehändelser på resor som börjar med en **läsmålgruppsaktivitet**, en **[målgruppsklassificeringsaktivitet](audience-qualification-events.md)** eller en affärshändelseaktivitet.

* Vi rekommenderar att du bara använder gruppmålgrupper i en **Läs målgrupp** -aktivitet. Detta ger en tillförlitlig och enhetlig räkning för de målgrupper som används under en resa. Läsarna är utformade för att gruppbearbetas. Om ditt användningsfall behöver realtidsdata använder du aktiviteten **[Målgruppskvalificering](audience-qualification-events.md)**.

* Publiker [som har importerats från en CSV-fil](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#import-audience) eller som är resultatet av [dispositionsarbetsflöden](../audience/get-started-audience-orchestration.md) kan väljas i aktiviteten **Läs målgrupp**. Dessa målgrupper är inte tillgängliga i aktiviteten **Målgruppskvalificering**.


Guardrutor för aktiviteten **Läs målgrupp** visas på [den här sidan](../start/guardrails.md#read-segment-g).


## Konfigurera aktiviteten {#configuring-segment-trigger-activity}

Så här konfigurerar du aktiviteten Läs målgrupp:

1. Öppna kategorin **[!UICONTROL Orchestration]** och släpp en **[!UICONTROL Read Audience]**-aktivitet på arbetsytan.

   Aktiviteten måste placeras som det första steget i en resa.

1. Lägg till en **[!UICONTROL Label]** i aktiviteten (valfritt).

1. I fältet **[!UICONTROL Audience]** väljer du den Adobe Experience Platform-målgrupp som ska delta i resan och klickar sedan på **[!UICONTROL Save]**. Du kan välja vilken Adobe Experience Platform-målgrupp som helst som har genererats med [segmentdefinitioner](../audience/creating-a-segment-definition.md).

   >[!NOTE]
   >
   >Dessutom kan du rikta in dig på Adobe Experience Platform-målgrupper som skapats med [målgruppskompositioner](../audience/get-started-audience-orchestration.md) eller [överförda från en CSV-fil](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#import-audience){target="_blank"}.

   Observera att du kan anpassa kolumnerna som visas i listan och sortera dem.

   ![](assets/read-segment-selection.png)

   När målgruppen har lagts till kan du med knappen **[!UICONTROL Copy]** kopiera dess namn och ID:

   `{"name":"Luma app opening and checkout","id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](assets/read-segment-copy.png)

   >[!NOTE]
   >
   >Det är bara de personer som har **Realiserad**-målgruppsdeltagarstatus som går in på resan. Mer information om hur du utvärderar en målgrupp finns i [dokumentationen för segmenteringstjänsten](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html#interpret-segment-results){target="_blank"}.

1. I fältet **[!UICONTROL Namespace]** väljer du det namnutrymme som ska användas för att identifiera personerna. Som standard är fältet förifyllt med det senast använda namnutrymmet. [Läs mer om namnutrymmen](../event/about-creating.md#select-the-namespace).

   >[!NOTE]
   >
   >Individer som tillhör en målgrupp som inte har den valda identiteten (namnutrymmet) bland sina olika identiteter kan inte ta sig in på resan. Du kan bara välja ett personbaserat ID-namnutrymme. Om du har definierat ett namnområde för en uppslagstabell (till exempel: ProductID-namnområde för en produktsökning), är det inte tillgängligt i listrutan **Namespace**.

1. Ange **[!UICONTROL Reading rate]**. Det här är det maximala antalet profiler som kan komma in på resan per sekund. Denna avgift gäller endast denna aktivitet och inga andra delar av resan. Om du till exempel vill definiera en begränsningsfrekvens för anpassade åtgärder måste du använda begränsnings-API:t. Se den här [sidan](../configuration/throttling.md).

   Det här värdet lagras i transportversionens nyttolast. Standardvärdet är 5 000 profiler per sekund. Du kan ändra det här värdet från 500 till 20 000 profiler per sekund.

   >[!NOTE]
   >
   >Den totala läshastigheten per sandlåda är satt till 20 000 profiler per sekund. Läsfrekvensen för alla läsmålgrupper som körs samtidigt i samma sandlåda uppgår därför till högst 20 000 profiler per sekund. Du kan inte ändra denna ände.

1. Med aktiviteten **[!UICONTROL Read Audience]** kan du ange vid vilken tidpunkt målgruppen ska gå in på resan. Om du vill göra det klickar du på länken **[!UICONTROL Edit journey schedule]** för att komma åt resans egenskaper och konfigurerar sedan fältet **[!UICONTROL Scheduler type]**.

   ![](assets/read-segment-schedule.png)

   Som standard går målgrupper in på resan **[!UICONTROL As soon as possible]**. Om du vill att publiken ska ange resan ett visst datum/tid eller regelbundet, väljer du önskat värde i listan.

   >[!NOTE]
   >
   >Observera att avsnittet **[!UICONTROL Schedule]** bara är tillgängligt när en **[!UICONTROL Read Audience]**-aktivitet har släppts på arbetsytan.

   ![](assets/read-segment-schedule-list.png)

   **Inkrementell läsning**: När en resa med en återkommande **läsmålgrupp** körs för första gången kommer alla profiler i målgruppen in på resan. Med det här alternativet kan ni efter den första förekomsten endast inrikta er på de personer som har gått in i målgruppen sedan den senaste körningen av resan.

       >[!OBS!]
       >
       >Om du riktar in dig på en [anpassad publik för överföring](../audience/about-audiences.md#segments-in-travel-optimizer) i din resa hämtas profiler bara vid den första upprepningen om det här alternativet aktiveras i en återkommande resa, eftersom dessa målgrupper är fasta.
   
   **Tvinga återinträde vid upprepning**: Med det här alternativet kan du göra så att alla profiler som fortfarande finns i resan automatiskt avslutar den vid nästa körning. Om du till exempel har två dagar på dig att vänta på en daglig återkommande resa, genom att aktivera det här alternativet, kommer profiler alltid att flyttas på nästa körning (så dagen efter), oavsett om de är i nästa körda målgrupp eller inte. Om livscykeln för dina profiler under den här resan kan vara längre än frekvensen för återkommande aktiviteter ska du inte aktivera det här alternativet för att säkerställa att profilerna kan slutföra sin resa.

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
>En bild Läs målgruppsresor flyttar till statusen **Slutförd** 91 dagar ([global tidsgräns för resa](journey-properties.md#global_timeout)) efter resan. För schemalagda läsmålgrupper är det 91 dagar efter den sista förekomsten.

## Testa och publicera resan {#testing-publishing}

Med aktiviteten **[!UICONTROL Read Audience]** kan du testa resan med en enhetsprofil.

Det gör du genom att aktivera testläget.

![](assets/read-segment-test-mode.png)

Konfigurera och kör testläget som vanligt. [Lär dig testa en resa](testing-the-journey.md).

När testet har körts kan du med knappen **[!UICONTROL Show logs]** se testresultaten. Mer information finns i [det här avsnittet](testing-the-journey.md#viewing_logs)

![](assets/read-segment-log.png)

När testerna har slutförts kan du publicera din resa (se [Publicera resan](publishing-the-journey.md)). Enskilda personer som tillhör målgruppen kommer att gå in på resan det datum/den tid som anges i avsnittet med egenskaper **[!UICONTROL Scheduler]** för resan.

>[!NOTE]
>
>För återkommande målgruppsbaserade resor stängs resan automatiskt när den sista förekomsten av den har utförts. Om inget slutdatum/sluttid har angetts måste du stänga resan till nya ingångar manuellt för att avsluta den.

## Målgruppsanpassning för målgruppsbaserade resor

Målgruppsbaserade resor börjar alltid med en **Läs målgrupp**-aktivitet för att hämta personer som tillhör en Adobe Experience Platform-målgrupp.

Den målgrupp som tillhör målgruppen hämtas en gång eller regelbundet.

Efter att du gått in på resan kan du skapa målgruppsexempel som gör att individer från den ursprungliga målgruppen kan flöda in i olika delar av resan.

**Segmentering**

Du kan använda villkor för att utföra segmentering med aktiviteten **Villkor**. Du kan t.ex. få VIP-användare att ta en viss väg och låta andra användare än VIP flöda i en annan bana.

Segmenteringen kan baseras på:

* datakälldata
* kontexten för händelser som ingår i resedata, till exempel: klickade en person på meddelandet som togs emot för en timme sedan?
* Ett datum, till exempel: Är vi i juni när en person går genom resan?
* en tid, till exempel: är det morgon i personens tidszon?
* en algoritm som delar den målgrupp som flödar i resan baserat på en procentandel, till exempel: 90 % - 10 % för att utesluta en kontrollgrupp

![](assets/read-segment-audience1.png)

**Uteslutning**

Med samma **villkorsaktivitet** som används för segmentering (se ovan) kan du även utesluta en del av populationen. Du kan till exempel utesluta VIP-personer genom att låta dem flöda in i en gren med ett slutsteg direkt efter.

Detta kan inträffa direkt efter det att målgruppen har hämtats, för att räkna antalet personer eller längs en flerstegsresa.

![](assets/read-segment-audience2.png)

**Union**

Med Resor kan du skapa N-grenar och förena dem efter en segmentering.

Det innebär att ni kan få två målgrupper att återvända till en gemensam upplevelse.

Om du till exempel har följt en annan upplevelse under tio dagar på en resa kan VIP- och icke-VIP-kunder återgå till samma resa.

Efter en union kan du dela upp publiken igen genom att utföra en segmentering eller ett exkluderingsmoment.

![](assets/read-segment-audience3.png)


## Försök igen {#read-audience-retry}

Återförsök används som standard på målgruppsinlösta resor (med början från en **Läs målgrupp** eller en **affärshändelse**) när exportjobbet hämtas. Om ett fel inträffar när exportjobbet skapas görs nya försök var 10:e minut (max 1 timme). Efter det kommer vi att betrakta det som ett misslyckande. Dessa typer av resor kan därför utföras upp till en timme efter den schemalagda tiden.

**Misslyckade utlösare för läsning** fångas in och visas i **Varningar**. Varningen **Läs målgrupp** varnar dig om en **Läs målgrupp**-aktivitet inte har bearbetat någon profil 10 minuter efter den schemalagda körningstiden. Felet kan bero på tekniska problem eller på att målgruppen är tom. Om det här felet orsakas av tekniska problem ska du vara medveten om att försök fortfarande kan göras, beroende på typ av problem (t.ex. om det inte går att skapa exportjobbet kommer vi att försöka igen var 10:e minut med maximalt 1 timme). [Läs mer](../reports/alerts.md#alert-read-audiences)

## Instruktionsvideo {#video}

Förstå tillämpliga användningsfall för en resa som triggas av läsmålgruppsaktiviteten. Lär dig hur du bygger batchbaserade resor och vilka metodtips som ska användas.

>[!VIDEO](https://video.tv.adobe.com/v/3424997?quality=12)
