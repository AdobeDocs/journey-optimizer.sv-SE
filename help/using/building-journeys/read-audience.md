---
solution: Journey Optimizer
product: journey optimizer
title: Använda en målgrupp i en resa
description: Lär dig hur du konfigurerar och använder aktiviteten Läs publik för att få enskilda personer från Adobe Experience Platform att delta i resor.
feature: Journeys, Activities, Audiences
topic: Content Management
role: User
level: Intermediate
keywords: aktivitet, resa, läsning, målgrupp, plattform
exl-id: 7b27d42e-3bfe-45ab-8a37-c55b231052ee
version: Journey Orchestration
source-git-commit: 24d66f146ea3ed0e89a3b928b805bc53a70a8895
workflow-type: tm+mt
source-wordcount: '3003'
ht-degree: 0%

---

# Använda en målgrupp i en resa {#segment-trigger-activity}

## Om aktiviteten Läs målgrupp {#about-segment-trigger-actvitiy}

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment"
>title="Läs målgruppsaktivitet"
>abstract="Med aktiviteten Läs målgrupp kan du göra så att alla personer som tillhör en [!DNL Adobe Experience Platform]-målgrupp kan delta i en resa. Ingången till en resa kan genomföras antingen en gång eller regelbundet."

Använd aktiviteten **Läs målgrupp** för att få alla personer i en målgrupp att komma in på resan. Ingången till en resa kan genomföras antingen en gång eller regelbundet.

Låt oss som exempel ta målgruppen&quot;Luma app opening and checkout&quot; som skapats i [Build audiences](../audience/about-audiences.md) -användningsexemplet. Med aktiviteten Läs målgrupp kan du göra så att alla personer som tillhör den här målgruppen går in på en resa. De kommer att flöda in i individuella resor som utnyttjar alla resefunktioner: villkor, tidtagare, händelser, aktiviteter.

➡️ [Upptäck den här funktionen i en video](#video)

>[!NOTE]
>
>När en läsmålgruppsaktivitet körs genererar systemet interna händelser (så kallade `segmentExportJob`-händelser) som spårar målgruppsexportåtgärdens livscykel. Dessa händelser registreras på aktivitetsnivå, inte per enskild profil, och kan efterfrågas i övervaknings- och felsökningssyfte. Läs mer om [frågor om Read Audience-händelser](../reports/query-examples.md#read-segment-queries).

>[!CAUTION]
>
>* Innan du använder aktiviteten Läs målgrupp ska du [läsa GuarDRAils and Limitation](#must-read).

## Konfigurera aktiviteten {#configuring-segment-trigger-activity}

Stegen för att konfigurera aktiviteten Läs målgrupp är följande.

### Lägg till en Läs-målgruppsaktivitet och välj målgrupp

1. Öppna kategorin **[!UICONTROL Orchestration]** och släpp en **[!UICONTROL Read Audience]**-aktivitet på arbetsytan.

   Aktiviteten måste placeras som det första steget i en resa.

1. Lägg till en **[!UICONTROL Label]** i aktiviteten (valfritt).

1. I fältet **[!UICONTROL Audience]** väljer du den [!DNL Adobe Experience Platform]-målgrupp som ska delta i resan och klickar sedan på **[!UICONTROL Save]**. Du kan välja vilken [!DNL Adobe Experience Platform]-målgrupp som helst som har genererats med [segmentdefinitioner](../audience/creating-a-segment-definition.md).

   >[!NOTE]
   >
   >Dessutom kan du rikta in dig på [!DNL Adobe Experience Platform] målgrupper som skapats med [målgruppskompositioner](../audience/get-started-audience-orchestration.md) eller [överförda från en CSV-fil](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=sv-SE#import-audience){target="_blank"}. [Läs mer om hur du genererar och målgruppsanpassar i Journey Optimizer](../audience/about-audiences.md).

   Observera att du kan anpassa kolumnerna som visas i listan och sortera dem.

   ![Gränssnitt för målgruppsval som visar tillgängliga Adobe Experience Platform-målgrupper](assets/read-segment-selection.png)

   När målgruppen har lagts till kan du med knappen **[!UICONTROL Copy]** kopiera dess namn och ID:

   `{"name":"Luma app opening and checkout","id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![Kopiera-knapp för att kopiera målgruppsnamn och ID i JSON-format](assets/read-segment-copy.png)

   >[!NOTE]
   >
   >Det är bara de personer som har **Realiserad**-målgruppsdeltagarstatus som går in på resan. Mer information om hur du utvärderar en målgrupp finns i [dokumentationen för segmenteringstjänsten](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=sv-SE#interpret-segment-results){target="_blank"}.

1. I fältet **[!UICONTROL Namespace]** väljer du det namnutrymme som ska användas för att identifiera personerna. Som standard är fältet förifyllt med det senast använda namnutrymmet. [Läs mer om namnutrymmen](../event/about-creating.md#select-the-namespace).

   >[!NOTE]
   >
   >Individer som tillhör en målgrupp som inte har den valda identiteten (namnutrymmet) bland sina olika identiteter kan inte ta sig in på resan. Du kan bara välja ett personbaserat ID-namnutrymme. Om du har definierat ett namnområde för en uppslagstabell (till exempel: ProductID-namnområde för en produktsökning), är det inte tillgängligt i listrutan **Namespace**.

### Skyddsutkast och rekommendationer {#must-read}

* Endast en **[!UICONTROL Read Audience]**-aktivitet kan användas på en resa och måste vara den första aktiviteten på arbetsytan.

* Aktiviteten **[!UICONTROL Read audience]** kan bara ha en målgrupp som mål. Om det krävs flera målgrupper bör du överväga att slå samman dessa målgrupper till en enda innan du använder dem. [Lär dig hur du kombinerar målgrupper med arbetsflöden för disposition](../audience/get-started-audience-orchestration.md)

* För resor som använder en **Läs målgrupp**-aktivitet finns det ett maximalt antal resor som kan påbörjas exakt samtidigt. Nya försök utförs av systemet. Undvik dock att ha fler än fem resor (med **Läs målgrupp**, schemalagd eller starta&quot;så snart som möjligt&quot;) med början vid exakt samma tidpunkt. Det bästa är att sprida dem över tiden, till exempel mellan 5 och 10 minuter.

* Det går inte att använda fältgrupper för upplevelsehändelser på resor som börjar med en **läsmålgruppsaktivitet**, en **[målgruppsklassificeringsaktivitet](audience-qualification-events.md)** eller en affärshändelseaktivitet.

* Vi rekommenderar att du bara använder gruppmålgrupper i en **Läs målgrupp** -aktivitet. Detta ger en tillförlitlig och enhetlig räkning för de målgrupper som används under en resa. Läsarna är utformade för att gruppbearbetas. Om ditt användningsfall behöver realtidsdata använder du aktiviteten **[Målgruppskvalificering](audience-qualification-events.md)**.

* Publiker [som har importerats från en CSV-fil](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=sv-SE#import-audience) eller som är resultatet av [dispositionsarbetsflöden](../audience/get-started-audience-orchestration.md) kan väljas i aktiviteten **Läs målgrupp**. Dessa målgrupper är inte tillgängliga i aktiviteten **Målgruppskvalificering**.

* Concurrent Read Audience Limit per Organization: Varje organisation kan köra upp till fem Read Audience-instanser samtidigt. Detta omfattar både schemalagda körningar och körningar som utlöses av affärshändelser. Gränsen gäller för alla sandlådor och resor. Den här gränsen tillämpas för att säkerställa en rättvis och balanserad resursallokering för alla organisationer.

* Hantering av genomströmning i sandlådor: Systemet hanterar dynamiskt bearbetningen per sandlåda med en maximal gräns på 20 000 profiler per sekund som delas över alla Läs målgrupper-aktiviteter. Enskilda Läs Audience-aktiviteter kan konfigureras med en minsta frekvens på 500 profiler per sekund. Om genomströmningsgränserna på sandlådenivå nås, kan jobb ställas i kö för att säkerställa en rättvis resursallokering.

* Tidsgräns för jobbbearbetning: Läsa målgruppsjobb som inte kan bearbetas inom 12 timmar på grund av säkerhetsgränsen rensas automatiskt och körs aldrig. Detta förhindrar jobbackumulering och garanterar systemstabilitet.

* När du använder gruppsegment ska du se till att dina intag och uppdateringar av dagliga ögonblicksbilder är fullständiga långt innan resan börjar. Överväg en ytterligare vänteperiod om segmenten måste återspegla data som importerats samma dag. Om det är viktigt med omedelbar profilaktualitet använder du en händelsebaserad eller direktuppspelad strategi i stället för en daglig batchbaserad strategi. Du kan också infoga en väntemekanism som tillåter att uppdaterade data sprids före utvärderingen av resan.

Guardrutor för aktiviteten **Läs målgrupp** visas på [den här sidan](../start/guardrails.md#read-segment-g).

>[!CAUTION]
>
>[Garantier för kundprofildata och segmentering i realtid &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html?lang=sv-SE){target="_blank"} gäller även [!DNL Adobe Journey Optimizer].

### Hantera profilinträde under resan

Ange **[!UICONTROL Reading rate]**. Det här är det maximala antalet profiler som kan komma in på resan per sekund. Denna avgift gäller endast denna aktivitet och inga andra delar av resan. Om du till exempel vill definiera en begränsningsfrekvens för anpassade åtgärder måste du använda begränsnings-API:t. Se den här [sidan](../configuration/throttling.md).

Det här värdet lagras i transportversionens nyttolast. Standardvärdet är 5 000 profiler per sekund. Du kan ändra det här värdet från 500 till 20 000 profiler per sekund.

>[!NOTE]
>
>Den totala läshastigheten per sandlåda är satt till 20 000 profiler per sekund. Läsfrekvensen för alla läsmålgrupper som körs samtidigt i samma sandlåda uppgår därför till högst 20 000 profiler per sekund. Du kan inte ändra denna ände. Läs mer om resefrekvenser och dataflöde i [det här avsnittet](entry-management.md#journey-processing-rate).

### Schemalägg resan {#schedule}

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment_scheduler_start_date"
>title="Startdatum/tid"
>abstract="Definiera det datum och den tid som du vill ska utlösa den här resan."

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment_scheduler_repeat_until"
>title="Upprepa tills"
>abstract="Definiera slutdatum för återkommande."

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment_scheduler_repeat_every"
>title="Upprepa var"
>abstract="Definiera en frekvens för återkommande schemaläggare."

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment_scheduler_incremental_read"
>title="Inkrementell läsning"
>abstract="Tillåt endast nya profiler att gå in på resan sedan senaste läsningen."

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment_scheduler_force_reentrance"
>title="Tvinga återinträde"
>abstract="Släpp alla deltagare innan varje målgrupp läser."

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment_scheduler_synchronize_audience"
>title="Utlösare efter utvärdering av batchmålgrupp"
>abstract="Växla till det här alternativet om du vill aktivera körning av resan efter en ny utvärdering av gruppmålgruppen."

>[!CONTEXTUALHELP]
>id="ajo_journey_read_segment_scheduler_synchronize_audience_wait_time"
>title="Vänta på en ny målgruppsutvärdering"
>abstract="Ange den tid som resan väntar på att batchmålgruppen ska utvärderas nyligen. Vänteperioden är begränsad till heltalsvärden, kan anges i minuter eller timmar och måste vara mellan 1 och 6 timmar."

Som standard är resor konfigurerade att köras en gång. Följ stegen nedan för att definiera ett specifikt datum/tid och hur ofta resan ska utföras.

>[!NOTE]
>
>En bild Läs målgruppsresor flyttar till statusen **Slutförd** 91 dagar ([global tidsgräns för resa](journey-properties.md#global_timeout)) efter resan. För schemalagda läsmålgrupper är det 91 dagar efter den sista förekomsten.

1. Välj **[!UICONTROL Read audience]** i aktivitetsegenskaperna för **[!UICONTROL Edit journey schedule]**.

   ![Redigera knappen för transportschema i Läsa egenskaper för målgruppsaktivitet](assets/read-segment-schedule.png)

1. Resans egenskaper visas. I listrutan **[!UICONTROL Scheduler type]** väljer du hur ofta du vill att resan ska köras.

   ![Listruta av schemaläggartyp med frekvensalternativ: en gång, dagligen, varje vecka, varje månad](assets/read-segment-schedule-list.png)

För återkommande resor finns det specifika alternativ som hjälper dig att hantera inmatningen av profiler på resan. Expandera avsnitten nedan om du vill ha mer information om varje alternativ.

![Läs återkommande målgruppsalternativ: Inkrementell läsning, Tvinga återinträde, Utlös efter batch](assets/read-audience-options.png)

+++**[!UICONTROL Incremental read]**

När en resa med en återkommande **läsmålgrupp** körs för första gången kommer alla profiler i målgruppen in på resan. Med det här alternativet kan du efter första tillfället bara rikta in dig på de personer som har gått in i målgruppen sedan den senaste körningen av resan.

När du använder det här alternativet ser systemet tillbaka **24 timmar** från tidpunkten för det senaste målgruppsutvärderingsjobbet som utfördes av [!DNL Adobe Experience Platform]s segmenteringstjänst.

När segmenteringen är klar påbörjas ett exportjobb för ögonblicksbilder av profiler, där Journey Optimizer kan identifiera och bearbeta nya profiler. Om resan schemaläggs mellan dessa två jobb kommer den inkrementella läsningen inte att hämta profiler som blivit medlemmar av målgruppen sedan den senaste körningen av resan.

Så här minimerar du risken för saknade profiler:
* Aktivera alternativet **[!UICONTROL Trigger after batch audience evaluation]** om du vill förlänga summeringsperioden till tidpunkten för den senaste lyckade resan, oavsett hur länge den pågick
* Schemalägg resor som ska köras bra efter dagliga batchsegmenteringsjobb slutförda (vanligen 2-3 timmars buffert)
* För tidskritiska användningsfall som kräver omedelbar profilinkludering bör du överväga att använda [målgruppskvalificeringsaktiviteter](audience-qualification-events.md) med direktuppspelade målgrupper istället

>[!CAUTION]
>
>Om du har en [anpassad uppladdningsmålgrupp](../audience/about-audiences.md#about-segments) som mål för din resa hämtas profiler endast vid den första upprepningen om det här alternativet är aktiverat under en återkommande resa, eftersom dessa målgrupper är fasta.

+++

+++**[!UICONTROL Force reentrance on recurrence]**

Med det här alternativet kan du göra så att alla profiler fortfarande finns kvar i resan automatiskt avslutar den vid nästa körning.

Om du till exempel har två dagar på dig att vänta på en daglig återkommande resa, genom att aktivera det här alternativet, kommer profiler alltid att flyttas på nästa körning (så dagen efter), oavsett om de är i nästa körda målgrupp eller inte.

Om livscykeln för dina profiler under den här resan kan vara längre än frekvensen för återkommande aktiviteter ska du inte aktivera det här alternativet för att säkerställa att profilerna kan slutföra sin resa.

+++

+++**[!UICONTROL Trigger after batch audience evaluation]**

För resor som schemaläggs dagligen och som riktar sig till gruppmålgrupper kan du definiera ett tidsfönster på upp till 6 timmar innan resan väntar på nya målgruppsdata från batchsegmenteringsjobb. Om segmenteringsjobbet slutförs inom tidsfönstret utlöses resan. I annat fall hoppas resan över tills nästa förekomst uppstår. Det här alternativet ser till att resorna körs med korrekta och aktuella målgruppsdata.

Om en resa till exempel är schemalagd till 6 PM dagligen kan du ange ett antal minuter eller timmar att vänta innan resan körs. När resan återupptas kl. 18.00 söker programmet efter en ny målgrupp, vilket innebär en nyare målgrupp än den som användes under den föregående resan. Under den angivna tidsperioden verkställs resan omedelbart när den nya målgruppen identifieras. Om ingen ny målgrupp upptäcks kommer körningen att hoppas över den dagen.

+++

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

## Testa och publicera resan {#testing-publishing}

Med aktiviteten **[!UICONTROL Read Audience]** kan du testa resan med en enhetsprofil.

Det gör du genom att aktivera testläget.

![Gränssnitt för testläge för aktiviteten Läs publik med val av testprofil](assets/read-segment-test-mode.png)

Konfigurera och kör testläget som vanligt. [Lär dig testa en resa](testing-the-journey.md).

När testet har körts kan du med knappen **[!UICONTROL Show logs]** se testresultaten. Mer information finns i [det här avsnittet](testing-the-journey.md#viewing_logs)

![Testloggar som visar målgruppskörningsresultat och profilflöde](assets/read-segment-log.png)

När testerna har slutförts kan du publicera din resa (se [Publicera resan](../building-journeys/publish-journey.md)). Enskilda personer som tillhör målgruppen kommer att gå in på resan det datum/den tid som anges i avsnittet med egenskaper **[!UICONTROL Scheduler]** för resan.

>[!NOTE]
>
>För återkommande målgruppsbaserade resor stängs resan automatiskt när den sista förekomsten av den har utförts. Om inget slutdatum/sluttid har angetts måste du stänga resan till nya ingångar manuellt för att avsluta den.

## Målgruppsanpassning för målgruppsbaserade resor

Målgruppsbaserade resor börjar alltid med en **Läs målgrupp**-aktivitet för att hämta personer som tillhör en [!DNL Adobe Experience Platform] målgrupp.

Den målgrupp som tillhör målgruppen hämtas en gång eller regelbundet.

Efter att du gått in på resan kan du skapa målgruppsexempel som gör att individer från den ursprungliga målgruppen kan flöda in i olika delar av resan.

**Segmentering**

Du kan använda villkor för att utföra segmentering med aktiviteten **Villkor**. Du kan t.ex. få VIP-användare att ta en viss väg och låta andra användare än VIP flöda i en annan bana.

Segmenteringen kan baseras på:

* datakälldata
* kontexten för händelser som ingår i resedata, till exempel: klickade en person på meddelandet som togs emot för en timme sedan?
* Ett datum, till exempel: Är vi i juni när en person går igenom resan?
* en tid, till exempel: är det morgon i personens tidszon?
* en algoritm som delar den målgrupp som flödar i resan baserat på en procentandel, till exempel: 90 % - 10 % för att utesluta en kontrollgrupp

![Villkorsaktivitet för målgruppssegmentering i sökvägar i VIP och utanför VIP](assets/read-segment-audience1.png)

>[!NOTE]
>
>När du använder schemaläggartypen Dagligen med en **[!UICONTROL Read Audience]**-aktivitet kan du definiera ett tidsfönster där resan ska vänta på nya målgruppsdata. Detta garanterar korrekt målinriktning och förhindrar problem som orsakas av förseningar i gruppsegmenteringsjobb. [Lär dig schemalägga en resa](#schedule)
>
>Alternativet **[!UICONTROL Trigger after batch audience evaluation]** är bara tillgängligt för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.

**Uteslutning**

Med samma **villkorsaktivitet** som används för segmentering (se ovan) kan du även utesluta en del av populationen. Du kan till exempel utesluta VIP-personer genom att låta dem flöda in i en gren med ett slutsteg direkt efter.

Detta kan inträffa direkt efter det att målgruppen har hämtats, för att räkna antalet personer eller längs en flerstegsresa.

![Resväg med exkluderingsgren med slutaktivitet](assets/read-segment-audience2.png)

**Union**

Med Resor kan du skapa N-grenar och förena dem efter en segmentering. Det innebär att ni kan få två målgrupper att återvända till en gemensam upplevelse.

Om du till exempel har följt en annan upplevelse under tio dagar på en resa kan VIP- och icke-VIP-kunder återgå till samma resa. Efter en union kan du dela upp publiken igen genom att utföra en segmentering eller ett exkluderingsmoment.

![Resebanor som sammanfogas igen efter segmentering med union](assets/read-segment-audience3.png)

## Felsökning av antal träffar för målgrupper {#audience-count-mismatch}

Om du upptäcker skillnader mellan uppskattat antal målgrupper, kvalificerade profiler och faktiska profiler för din resa bör du tänka på följande:

### Tidsplanering och dataspridning

* **Slutförande av batchsegmenteringsjobb**: För batchmålgrupper kontrollerar du att det dagliga batchsegmenteringsjobbet har slutförts och att ögonblicksbilder uppdateras innan resan körs. Batchmålgrupper blir klara att använda cirka **2 timmar** efter att segmenteringsjobbet har slutförts. Läs mer om [metoder för målgruppsutvärdering](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=sv-SE#evaluate-segments){target="_blank"}.

* **Tidsåtgång för datainförsel**: Verifiera att inmatningen av profildata har slutförts innan resan kördes. Om profiler förtärdes kort innan resan påbörjas kanske de ännu inte återspeglas i målgruppen. Läs mer om [dataöverföring i Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=sv-SE){target="_blank"}.

* **Använd alternativet Utlösare efter utvärdering av gruppmålgrupp**: För dagliga schemalagda resor med gruppmålgrupper bör du överväga att aktivera alternativet **[!UICONTROL Trigger after batch audience evaluation]**. Detta garanterar att resan väntar på nya målgruppsdata (upp till 6 timmar) innan den körs. [Läs mer om schemaläggning](#schedule)

* **Lägg till en vänteaktivitet**: För direktuppspelande målgrupper med nyligen inspelade data bör du lägga till en **Wait**-aktivitet i början av resan, så att du kan använda tiden för dataspridning och profilkvalificering. [Läs mer om aktiviteten Vänta](wait-activity.md)

### Datavalidering och övervakning

* **Kontrollera segmenteringsjobbstatus**: Övervaka jobbsluttider för gruppsegmentering i Adobe Experience Platform [övervakningsinstrumentpanel](https://experienceleague.adobe.com/docs/experience-platform/dataflows/ui/monitor-segments.html?lang=sv-SE){target="_blank"} för att verifiera när målgruppsdata är klara.

* **Verifiera sammanfogningsprinciper**: Kontrollera att den sammanfogningsprincip som har konfigurerats för din målgrupp matchar det förväntade beteendet för att kombinera profildata från olika källor. Läs mer om [sammanslagningsprinciper i Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=sv-SE){target="_blank"}.

* **Granska segmentdefinitioner**: Bekräfta att segmentdefinitionerna är korrekt konfigurerade och inkludera alla förväntade kvalificeringskriterier. Läs mer om att [bygga målgrupper](../audience/creating-a-segment-definition.md). Var särskilt uppmärksam på:
   * Tidsbaserade villkor som kan exkludera profiler baserade på händelsetidsstämplar
   * Attributkvalifikationer som är beroende av nyligen uppdaterade data
   * Utvärderingsmetoder för direktuppspelning kontra batchbearbetning

* **Verifiera namnområdeskonfiguration**: Kontrollera att det namnutrymme som valts i aktiviteten **Läs målgrupp** matchar den primära identitet som används av profilerna i målgruppen. Profiler utan det valda namnutrymmet kommer inte att gå in på resan. Läs mer om [identitetsnamnutrymmen](../event/about-creating.md#select-the-namespace).

### Bästa tillvägagångssätt för att förhindra avvikelser

* **Schemalägg resor efter segmentering**: För batchmålgrupper schemalägger du körning av resan minst 2-3 timmar efter den typiska jobbslutstiden för batchsegmentering. [Läs mer om schemaläggning av resor](#schedule)

* **Använd direktuppspelade målgrupper för användningsfall i realtid**: Om du behöver omedelbar profilkvalificering och resepost använder du [Målgruppskvalificering](audience-qualification-events.md)-aktiviteter med direktuppspelade målgrupper i stället för **Läs målgrupper** med gruppmålgrupper.

* **Testa med mindre målgrupper först**: Innan du startar storskaliga resor bör du testa med en mindre delmängd för att verifiera att antalet matchar förväntningarna. [Lär dig hur du testar en resa](testing-the-journey.md)

* **Övervaka regelbundet**: Ställ in regelbunden övervakning av målgruppsstorlekar och resemätvärden för att upptäcka avvikelser tidigt. Läs mer om [resefrekvenser och hantering av inträde](entry-management.md).

Om antalet avvikelser kvarstår efter att du har utfört dessa steg kontaktar du Adobe support med information om målgrupp, konfiguration av resan och iakttagna avvikelser.

## Försök igen {#read-audience-retry}

Återförsök används som standard på målgruppsinlösta resor (med början från en **Läs målgrupp** eller en **affärshändelse**) när exportjobbet hämtas. Om ett fel inträffar när exportjobbet skapas görs nya försök var 10:e minut (max 1 timme). Efter det kommer vi att betrakta det som ett misslyckande. Dessa typer av resor kan därför utföras upp till en timme efter den schemalagda tiden.

**Misslyckade utlösare för läsning** fångas in och visas i **Varningar**. Varningen **Läs målgrupp** varnar dig om en **Läs målgrupp**-aktivitet inte har bearbetat någon profil 10 minuter efter den schemalagda körningstiden. Felet kan bero på tekniska problem eller på att målgruppen är tom. Om det här felet orsakas av tekniska problem ska du vara medveten om att försök fortfarande kan göras, beroende på typ av problem (t.ex. om det inte går att skapa exportjobbet kommer vi att försöka igen var 10:e minut med maximalt 1 timme). [Läs mer](../reports/alerts.md#alert-read-audiences)

## Relaterade ämnen

* [Bygg målgrupper](../audience/about-audiences.md)
* [Målgruppskvalificeringsaktivitet](audience-qualification-events.md)
* [Resetillgångar och skyddsräcken](../start/guardrails.md#read-segment-g)
* [Testa en resa](testing-the-journey.md)
* [Publicera en resa](../building-journeys/publish-journey.md)

## Instruktionsvideo {#video}

Förstå tillämpliga användningsfall för en resa som triggas av läsmålgruppsaktiviteten. Lär dig hur du bygger batchbaserade resor och vilka metodtips som ska användas.

>[!VIDEO](https://video.tv.adobe.com/v/3430367?captions=swe&quality=12)
