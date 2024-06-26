---
solution: Journey Optimizer
product: journey optimizer
title: Om Adobe Experience Platform målgrupper
description: Lär dig arbeta med Adobe Experience Platform målgrupper
feature: Audiences, Profiles
topic: Content Management
role: User
level: Beginner
mini-toc-levels: 1
exl-id: 10d2de34-23c1-4a5e-b868-700b462312eb
source-git-commit: 8a1ec5acef067e3e1d971deaa4b10cffa6294d75
workflow-type: tm+mt
source-wordcount: '1854'
ht-degree: 0%

---

# Kom igång med Adobe Experience Platform målgrupper {#about-segments}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment_segment"
>title="Målgrupp"
>abstract="Genom att utnyttja kundprofildata i realtid kan Adobe Experience Platform enkelt skapa segmentdefinitioner för att skapa målgrupper som fångar upp kundernas unika beteenden och önskemål."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_audience"
>title="Välj kampanjmålgrupp"
>abstract="I den här listan visas alla tillgängliga Adobe Experience Platform-målgrupper. Välj målgrupp för er kampanj. Meddelandet som konfigurerats i kampanjen skickas till alla personer som tillhör den valda målgruppen. [Läs mer om målgrupper](../audience/about-audiences.md)"

En målgrupp är en uppsättning personer som har liknande beteenden och/eller egenskaper. Läs mer om målgrupper i [Dokumentation för Adobe Experience Platform Segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html){target="_blank"}.

[!DNL Journey Optimizer] kan ni skapa Adobe Experience Platform-målgrupper direkt från **[!UICONTROL Audiences]** och utnyttja dem i era resor eller kampanjer.

Målgrupper kan genereras på olika sätt:

* **Segmentdefinitioner**: Skapa en ny målgruppsdefinition med Adobe Experience Platform Segmentation Service. [Lär dig hur du skapar segmentdefinitioner](creating-a-segment-definition.md)
* **Anpassad överföring**: Importera en målgrupp med en CSV-fil. Lär dig hur du importerar målgrupper i Adobe Experience Platform [Dokumentation för segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#import-audience){target="_blank"}.
* **Målgruppskomposition**: Skapa ett dispositionsarbetsflöde för att kombinera befintliga Adobe Experience Platform-målgrupper till en visuell arbetsyta och utnyttja olika aktiviteter (dela, exkludera..) för att skapa nya målgrupper. [Kom igång med målgruppsmaterial](get-started-audience-orchestration.md)

## Målgrupper i [!DNL Journey Optimizer] {#segments-in-journey-optimizer}

I kampanjer och resor kan ni välja alla målgrupper som genereras med segmentdefinitioner, anpassade arbetsflöden för uppladdning och disposition.

>[!AVAILABILITY]
>
>Användningen av målgrupper och attribut från målgruppssammansättning och målgrupper med anpassad uppladdning (CSV-fil) är för närvarande inte tillgänglig för användning med hälso- och sjukvårdsskölden eller skölden för skydd av privatlivet och säkerheten. [Lär dig använda attribut för målgruppsberikning i Journey Optimizer](../audience/about-audiences.md#enrichment)

Ni kan utnyttja målgrupper i **[!DNL Journey Optimizer]** på olika sätt:

* Välj en målgrupp för **kampanj**, där meddelandet skickas till alla personer som tillhör den valda målgruppen. [Lär dig definiera målgruppen för en kampanj](../campaigns/create-campaign.md#define-the-audience-audience).

* Använd en **Läsa målgrupper** orkestreringsaktivitet på en resa för att få alla personer i publiken att komma in på resan och ta emot de meddelanden som ingår i resan. Säg att ni har en&quot;silverkund&quot; som målgrupp. Med den här aktiviteten kan ni få alla silverkunder att ta sig in på en resa och skicka en serie personaliserade meddelanden till dem. [Lär dig konfigurera en målgruppsaktivitet för läsning](../building-journeys/read-audience.md#configuring-segment-trigger-activity).

* Använd **Villkor** aktiviteter på en resa för att skapa villkor baserade på medlemskap för målgrupper. [Lär dig hur du använder målgrupper under förhållanden](../building-journeys/condition-activity.md#using-a-segment).

* Använd **Målgruppskvalifikation** händelseaktivitet på en resa för att få individer att komma in på eller gå framåt i resan baserat på Adobe Experience Platform entréer och utgångar. Du kan till exempel få alla nya silverkunder att resa och skicka meddelanden till dem. Mer information om hur du använder den här aktiviteten finns i [Lär dig hur du konfigurerar en aktivitet för målgruppskvalificering](../building-journeys/audience-qualification-events.md).

  >[!NOTE]
  >
  >På grund av batchbeskaffenheten hos målgrupper som skapats med arbetsflöden för disposition och anpassad överföring kan du inte rikta in dig på dessa målgrupper i en&quot;målgruppskompetens&quot;-aktivitet. Endast målgrupper som skapats med segmentdefinitioner kan utnyttjas i den här aktiviteten.

## Använd attribut för målgruppsberikning {#enrichment}

När ni riktar in er på en målgrupp som skapats med arbetsflöden för dispositioner kan ni utnyttja anrikningsattribut från dessa målgrupper för att bygga upp er resa och personalisera era budskap.

Om du vill använda anrikningsattribut i en resa måste du se till att de läggs till i en fältgrupp i datakällan ExperiencePlatform.

+++ Lär dig hur du lägger till anrikningsattribut i en fältgrupp

1. Navigera till Administration > Konfiguration > Datakällor.
1. Markera Experience Platform och skapa eller redigera en fältgrupp.
1. Öppna fältväljaren, sök efter de anrikningsattribut som du vill lägga till och markera kryssrutan bredvid dem.
1. Spara ändringarna.

Detaljerad information om datakällor finns i följande avsnitt:

* [Arbeta med Adobe Experience Platform datakälla](../datasource/adobe-experience-platform-data-source.md)
* [Konfigurera en datakälla](../datasource/configure-data-sources.md)

+++

När anrikningsattributen har lagts till i en fältgrupp kan du utnyttja dem på olika platser i Journey Optimizer:

* **Skapa flera vägar i en resa** baserat på regler som utnyttjar målgruppens anrikningsattribut. För att göra detta bör du rikta in dig på målgruppen med en [Läsa målgrupper](../building-journeys/read-audience.md) skapar sedan regler i en [Villkor](../building-journeys/condition-activity.md) verksamhet som bygger på målgruppens anrikningsattribut.

  ![](assets/audience-enrichment-attribute-condition.png){width="70%" zoomable="yes"}

* **Anpassa era meddelanden** på resor eller kampanjer genom att lägga till anrikningsattribut från målgruppen i personaliseringsredigeraren. [Lär dig arbeta med personaliseringsredigeraren](../personalization/personalization-build-expressions.md)

  ![](assets/audience-enrichment-attribute-perso.png){width="70%" zoomable="yes"}

>[!AVAILABILITY]
>
>Anpassade attribut för berikning av överföring är ännu inte tillgängliga för användning i Journey Optimizer.

## Metoder för utvärdering av målgrupper {#evaluation-method-in-journey-optimizer}

I Adobe Journey Optimizer genereras målgrupper från segmentdefinitioner med hjälp av någon av de tre utvärderingsmetoderna nedan.

+++ Direktuppspelningssegmentering

Profillistan för målgruppen hålls uppdaterad i realtid när nya data flödar in i systemet.

Direktuppspelningssegmentering är en kontinuerlig process för datamarkering som uppdaterar era målgrupper som svar på användaraktivitet. När en segmentdefinition har skapats och målgruppen har sparats, tillämpas segmentdefinitionen på inkommande data till Journey Optimizer. Det innebär att enskilda personer läggs till eller tas bort från målgruppen när deras profildata ändras, vilket säkerställer att målgruppen alltid är relevant. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/streaming-segmentation.html){target="_blank"}

>[!NOTE]
>
>Se till att använda rätt händelser som villkor för direktuppspelningssegmentering. [Läs mer](#streaming-segmentation-events-guardrails)

+++

+++ Gruppsegmentering

Profillistan för publiken utvärderas var 24:e timme.

Gruppsegmentering är ett alternativ till direktuppspelningssegmentering som bearbetar alla profildata samtidigt genom segmentdefinitioner. Detta skapar en ögonblicksbild av målgruppen som kan sparas och exporteras för användning. Till skillnad från direktuppspelningssegmentering kommer gruppsegmentering inte att kontinuerligt uppdatera målgruppslistan i realtid, och nya data som kommer in efter gruppbearbetningen kommer inte att återspeglas i målgruppen förrän nästa gruppbearbetning. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#batch){target="_blank"}

+++

+++ Kantsegmentering

Kantsegmentering är möjligheten att omedelbart utvärdera segment i Adobe Experience Platform [på kanten](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html){target="_blank"}, vilket möjliggör användning av personalisering på samma sida och nästa sida. För närvarande kan endast utvalda frågetyper utvärderas med kantsegmentering. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/edge-segmentation.html#query-types){target="_blank"}

+++

Om du vet vilken utvärderingsmetod du vill använda väljer du den i listrutan. Du kan också klicka på mappikonen för bläddringsikonen med ett förstoringsglas för att visa en lista över tillgängliga metoder för utvärdering av segmentdefinitioner. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html#segment-properties){target="_blank"}

![](assets/evaluation-methods.png)

<!--The determination between batch segmentation and streaming segmentation is made by the system for each audience, based on the complexity and the cost of evaluating the segment definition rule. You can view the evaluation method for each audience in the **[!UICONTROL Evaluation method]** column of the audience list.
    
![](assets/evaluation-method.png)

>[!NOTE]
>
>If the **[!UICONTROL Evaluation method]** column does not display, you  need to add it using configuration button on the top right of the list.-->

När du har definierat en målgrupp för första gången läggs profiler till i målgruppen när de kvalificerar sig.

Det kan ta upp till 24 timmar att fylla målgruppen med tidigare data. När målgruppen har fyllts i på nytt hålls målgruppen kontinuerligt uppdaterad och alltid redo för målinriktning.

### Händelseanvändning med direktuppspelningssegmentering {#streaming-segmentation-events-guardrails}

Strömmande segmentering är användbart för personalisering i realtid med värdefulla användningsexempel. Det är dock viktigt att välja höger [händelser](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html#events){target="_blank"} som ska användas som segmenteringskriterier.

Därför bör du undvika följande händelser för optimala prestanda vid direktuppspelningssegmentering:

* **Meddelandet har öppnats** Interaktionstyp-händelse

  När ni skapar er målgrupp använder ni **Meddelandet har öppnats** interaktionshändelser blev otillförlitliga eftersom de inte är faktiska indikatorer för användaraktivitet och kan påverka segmenteringsprestanda negativt. Läs varför i det här [Adobe blogginlägg](https://blog.adobe.com/en/publish/2021/06/24/what-apples-mail-privacy-protection-means-for-email-marketers){target="_blank"}. Adobe rekommenderar därför att du inte använder **Meddelandet har öppnats** interaktionshändelser med direktuppspelningssegmentering. Använd istället riktiga användaraktivitetssignaler som klickningar, köp eller beacon-data.

* **Meddelandet har skickats** Feedback Status-händelse

  The **Meddelandet har skickats** Feedback-händelse används ofta för frekvens- eller undertryckskontroll innan du skickar ett e-postmeddelande. Adobe rekommenderar att du undviker det eftersom det sätter tryck på prestandan och kan orsaka att systemet försämras. Använd därför affärsregler i stället för, för frekvens- eller undertryckningslogik **Meddelandet har skickats** feedback-händelser. Observera att det inom kort kommer att finnas ett dagligt tak för frekvenser för enskilda profiler, vilket kompletterar den befintliga månadsgränsen för affärsregler.

>[!NOTE]
>
>Du kan använda **Meddelandet har öppnats** och **Meddelande skickat** händelser i gruppsegmentering utan några prestandaproblem.


## Vanliga frågor och svar om målgruppskomposition och anpassad överföring {#faq}

I följande avsnitt visas vanliga frågor om hur målgrupper som skapats med dispositionsarbetsflöden och anpassade uppladdningar (CSV-filer) används i Journey Optimizer.

+++ Var kan jag använda målgrupper från målgruppsdisposition och anpassad uppladdning inom Journey Optimizer?

Målgrupper från målgruppssammansättning och anpassad uppladdning kan hämtas antingen från kampanjer och resor. [Lär dig målinrikta målgrupper i [!DNL Journey Optimizer]](#segments-in-journey-optimizer)

* I **Kampanjer** visas dessa målgrupper i målgruppsväljaren efter att du klickat på knappen Välj målgrupp.

* I **Resor** kan ni använda dessa målgrupper i en&quot;Läs målgrupp&quot;-aktivitet när ni väljer målgrupp och i en&quot;Villkor&quot;-aktivitet för att kontrollera målgruppsmedlemskap. På grund av deras gruppkaraktär visas dock inte dessa målgrupper i aktiviteten&quot;Audience Qualification&quot;.

  >[!NOTE]
  >
  >Om&quot;Inkrementell läsning&quot; är aktiverat i en återkommande resa hämtas profiler endast vid den första upprepningen, eftersom dessa målgrupper är fasta.

Dessutom kan dessa målgrupper användas i personaliseringsredigeraren för att personalisera meddelanden under resor och kampanjer. [Lär dig arbeta med personaliseringsredigeraren](../personalization/personalization-build-expressions.md)

+++

+++ Vad är anrikningsattribut?

Enrichment-attribut är ytterligare attribut som är sammanhangsberoende och specifika för en viss målgrupp. De är inte associerade med profilen och används vanligtvis för personalisering.

Anrikningsattribut länkas till en målgrupp via en [Förfina](composition-canvas.md#enrich) i målgruppssammansättning eller genom den anpassade överföringsprocessen.

+++

+++ Var kan jag använda anrikningsattribut i Journey Optimizer?

Anrikningsattribut från publikens komposition kan användas inom följande områden. [Lär dig använda attribut för målgruppsberikning](#enrichment)

* Villkorsaktivitet (resor)
* Anpassade åtgärdsattribut (resor)
* Meddelandepersonalisering (resor och kampanjer)

>[!AVAILABILITY]
>
>Anpassade attribut för berikning av överföring är ännu inte tillgängliga för användning i Journey Optimizer.

+++

+++ Hur aktiverar jag anrikningsattribut i Journeys?

Om du vill använda anrikningsattribut i en resa måste du se till att de läggs till i en fältgrupp i datakällan ExperiencePlatform. Information om hur du lägger till anrikningsattribut i en fältgrupp finns i [det här avsnittet](#enrichment)

+++

+++ När kan jag publicera en målgrupp från en publikkomposition eller en anpassad uppladdning i Journey Optimizer?

* Målgrupper från **publiksammansättning** exekveras dagligen så du kan behöva vänta upp till 24 timmar för att använda dem i Journey Optimizer.
* Målgrupper från **anpassad överföring** publiceras i Journey Optimizer cirka 2 timmar efter publiceringen.

+++

+++ Uppdateras värdena för anrikningsattributen när en resa börjar?

För närvarande inte. Även efter vänta- eller händelsnoder är värdena för anrikningsattributen desamma som när resan påbörjades.

+++

+++ Hur kopplas anpassade uppladdningsmålgrupper med profiler?

Under den anpassade överföringsprocessen anger du det CSV-attribut som ska användas som identitet och den profilidentitet som det mappas till. Detta skapar en länk mellan målgruppsdata och profilen. Om CSV-filen innehåller ett identitetsvärde som inte finns i profilen skapas en ny profil med det identitetsvärdet.

Detaljerad information om den anpassade överföringsprocessen finns i Adobe Experience Platform [Dokumentation för segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#import-audience){target="_blank"}.

+++

+++ Hur färska är mina data i Journey Optimizer?

Data i målgrupper från publiksammansättning och anpassad uppladdning fylls i av Audience Export Service (AES). AES läser profilattribut och målgruppsmedlemskap, som är tillgängligt för dessa målgrupper med följande tidslinjer:

* **Målgruppskomposition**: Daglig export (~24 timmar)
* **Anpassad överföring**: Dedikerat exportjobb (~2 timmar)

Alla resor som utnyttjar en målgrupp från målgruppskomposition eller anpassade uppladdningar i aktiviteten&quot;Läs målgrupp&quot; kommer att ha profilattribut som är lika färska som den senaste grupputvärderingen. Detta inkluderar samtycke/undertryckande under resan.

Dessutom är förbättrade attribut i målgrupper för målgruppssammansättning lika färska som den senaste kompositionen, som kan vara upp till 24 timmar tidigare.

+++

