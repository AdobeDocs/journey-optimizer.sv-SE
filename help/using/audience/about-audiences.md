---
solution: Journey Optimizer
product: journey optimizer
title: Om Adobe Experience Platform målgrupper
description: Lär dig arbeta med Adobe Experience Platform målgrupper
feature: Audiences, Profiles
topic: Content Management
role: User
level: Beginner
exl-id: 10d2de34-23c1-4a5e-b868-700b462312eb
source-git-commit: cdcce470481393c821d1c5df95639602510a690a
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 1%

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
* **Import av CSV-filer**: Importera en målgrupp med en CSV-fil. Lär dig hur du importerar målgrupper i Adobe Experience Platform [Dokumentation för segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#import-audience){target="_blank"}.
* **Målgruppskomposition**: Skapa ett dispositionsarbetsflöde för att kombinera befintliga Adobe Experience Platform-målgrupper till en visuell arbetsyta och utnyttja olika aktiviteter (dela, exkludera..) för att skapa nya målgrupper. [Kom igång med målgruppsmaterial](get-started-audience-orchestration.md)

## Målgrupper i [!DNL Journey Optimizer] {#segments-in-journey-optimizer}

I kampanjer och resor kan du välja vilken Adobe Experience Platform-målgrupp som helst som genereras med [segmentdefinitioner](../audience/creating-a-segment-definition.md).

>[!NOTE]
>
>För närvarande är målgrupper resultatet av [målgruppskompositioner](../audience/get-started-audience-orchestration.md) kan endast användas i kampanjer. Den här funktionen är tillgänglig som en privat betaversion för resor.
>
>Användning av målgrupper [överförd från en CSV-fil](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#import-audience){target="_blank"} i kampanjer och resor är för närvarande tillgängliga som en privat betaversion.
>
>Kontakta din Adobe-representant om du vill veta mer.

Ni kan utnyttja målgrupper i **[!DNL Journey Optimizer]** på olika sätt:

* Välj en målgrupp för **kampanj**, där meddelandet skickas till alla personer som tillhör den valda målgruppen. [Lär dig definiera målgruppen för en kampanj](../campaigns/create-campaign.md#define-the-audience-audience).

* Använd en **Läsa målgrupper** orkestreringsaktivitet på en resa för att få alla personer i publiken att komma in på resan och ta emot de meddelanden som ingår i resan.

  Säg att ni har en&quot;silverkund&quot; som målgrupp. Med den här aktiviteten kan ni få alla silverkunder att ta sig in på en resa och skicka en serie personaliserade meddelanden till dem. [Lär dig konfigurera en målgruppsaktivitet för läsning](../building-journeys/read-audience.md#configuring-segment-trigger-activity).

* Använd **Målgruppskvalifikation** händelseaktivitet på en resa för att få individer att komma in på eller gå framåt i resan baserat på Adobe Experience Platform entréer och utgångar.

  Du kan till exempel få alla nya silverkunder att resa och skicka meddelanden till dem. Mer information om hur du använder den här aktiviteten finns i [Lär dig hur du konfigurerar en aktivitet för målgruppskvalificering](../building-journeys/audience-qualification-events.md).

* Använd **Villkor** aktiviteter på en resa för att skapa villkor baserade på medlemskap för målgrupper. [Lär dig hur du använder målgrupper under förhållanden](../building-journeys/condition-activity.md#using-a-segment).

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

Kantsegmentering är möjligheten att omedelbart utvärdera segment i Adobe Experience Platform [på kanten](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html){target="_blank"}, enabling same-page and next-page personalization use cases. Currently only select query types can be evaluated with edge segmentation. [Learn more](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/edge-segmentation.html#query-types){target="_blank"}

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

  När ni skapar er målgrupp använder ni **Meddelandet har öppnats** interaktionshändelser blev otillförlitliga eftersom de inte är faktiska indikatorer för användaraktivitet och kan påverka segmenteringsprestanda negativt. Läs varför i det här [Adobe blogginlägg](https://blog.adobe.com/en/publish/2021/06/24/what-apples-mail-privacy-protection-means-for-email-marketers){target="_blank"}.

  Adobe rekommenderar därför att du inte använder **Meddelandet har öppnats** interaktionshändelser med direktuppspelningssegmentering. Använd istället riktiga användaraktivitetssignaler som klickningar, köp eller beacon-data.

* **Meddelandet har skickats** Feedback Status-händelse

  The **Meddelandet har skickats** Feedback-händelse används ofta för frekvens- eller undertryckskontroll innan du skickar ett e-postmeddelande. Adobe rekommenderar att du undviker det eftersom det sätter tryck på prestandan och kan orsaka att systemet försämras.

  Använd därför affärsregler i stället för, för frekvens- eller undertryckningslogik **Meddelandet har skickats** feedback-händelser. Observera att det inom kort kommer att finnas ett dagligt tak för frekvenser för enskilda profiler, vilket kompletterar den befintliga månadsgränsen för affärsregler.

>[!NOTE]
>
>Du kan använda **Meddelandet har öppnats** och **Meddelande skickat** händelser i gruppsegmentering utan några prestandaproblem.
