---
title: Villkorsaktivitet
description: Läs mer om villkorsaktivitet
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 496c7666-a133-4aeb-be8e-c37b3b9bf5f9
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 6%

---

# Villkorsaktivitet{#condition-activity}

Följande typer av villkor är tillgängliga:

* [Datakällans villkor](#data_source_condition)
* [Tidsvillkor](#time_condition)
* [Procentdelning](#percentage_split)
* [Date condition](#date_condition)
* [Profilände](#profile_cap)

![](assets/journey49.png)

## About the Condition activity {#about_condition}

När du använder flera villkor under en resa kan du definiera etiketter för var och en av dem för att lättare kunna identifiera dem.

Klicka **[!UICONTROL Add a path]** om du vill definiera flera villkor. För varje villkor läggs en ny bana till på arbetsytan efter aktiviteten.

![](assets/journey47.png)

Note that the design of journeys has functional impacts. När flera sökvägar definieras efter ett villkor kommer endast den första giltiga sökvägen att köras. It means that you can vary the prioritization of paths by placing them above or below one another.

Låt oss till exempel ta exemplet med den första sökvägens villkor&quot;Personen är en VIP&quot; och en andra sökvägs villkor&quot;Personen är en man&quot;. If a person meeting both conditions (a male who is a VIP) passes this step, the first path will be chosen even if this person is also eligible to the second one, because the first path is &quot;above&quot;. Om du vill ändra den här prioriteten flyttar du dina aktiviteter i en annan lodrät ordning.

![](assets/journey48.png)

You can create another path for audiences that are not eligible to the defined conditions by checking **[!UICONTROL Show path for other cases than the one(s) above]**. Note that this option is not available in split conditions. Se [Procentdelning](#percentage_split).

I det enkla läget kan du utföra enkla frågor baserat på en kombination av fält. Alla tillgängliga fält visas till vänster på skärmen. Dra och släpp fält till huvudzonen. Om du vill kombinera de olika elementen, låser du ihop dem till varandra för att skapa olika grupper och/eller gruppnivåer. Du kan sedan välja en logisk operatör för att kombinera element på samma nivå:

* OCH: en korsning av två kriterier. Endast de element som uppfyller alla villkor beaktas.
* ELLER: en förening av två kriterier. Element som matchar minst ett av de två villkoren beaktas.

![](assets/journey64.png)

Om du använder [Adobe Experience Platform segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html){target=&quot;_blank&quot;} för att skapa segment kan du utnyttja dem under dina reseförhållanden. Se [Använda segment i villkor](../building-journeys/condition-activity.md#using-a-segment).


>[!NOTE]
>
>Du kan inte utföra frågor på tidsserier (till exempel en lista över inköp, tidigare klick på meddelanden) med den enkla redigeraren. För detta behöver du den avancerade redigeraren. Se [Dokumentation för Adobe Journey Orchestration](expression/expressionadvanced.md).

När ett fel inträffar i en åtgärd eller ett villkor upphör en individs resa. Det enda sättet att få den att fortsätta är att markera rutan **[!UICONTROL Add an alternative path in case of a timeout or an error]**. Se [det här avsnittet](../building-journeys/using-the-journey-designer.md#paths).

In the simple editor, you will also find the Journey Properties category, below the event and data source categories. This category contains technical fields related to the journey for a given profile. Det här är den information som hämtats av systemet från direktresor, till exempel rese-ID:t eller de specifika fel som påträffats. Mer information finns i [Dokumentation för Adobe Journey Orchestration](expression/journey-properties.md)

## Datakällans villkor {#data_source_condition}

På så sätt kan du definiera ett villkor baserat på fält från datakällorna eller händelser som tidigare placerats under resan. Mer information om hur du använder uttrycksredigeraren finns i [Dokumentation för Adobe Journey Orchestration](expression/expressionadvanced.md). Med den avancerade uttrycksredigeraren kan du ställa in mer avancerade villkor för att hantera samlingar eller använda datakällor som kräver att parametrar skickas. Läs [den här sidan](../datasource/external-data-sources.md).

![](assets/journey50.png)

## Tidsvillkor{#time_condition}

På så sätt kan du utföra olika åtgärder beroende på timmen på dagen och/eller veckodagen. For example, you can decide to send SMS messages during daytime and emails at night during weekdays.

>[!NOTE]
>
>Tidszonen är inte längre specifik för ett villkor och har nu definierats på färdsnivå i färdegenskaperna. Se [den här sidan](../building-journeys/timezone-management.md).

![](assets/journey51.png)

## Procentdelning {#percentage_split}

Med det här alternativet kan du slumpmässigt dela målgruppen för att definiera olika åtgärder för varje grupp. Definiera antalet delningar och partitioneringen för varje sökväg. Delningsberäkningen är statistisk eftersom systemet inte kan förutse hur många personer som kommer att flöda i den här kundresan. As a result, the split has a very low error margin. Den här funktionen är baserad på en slumpmässig Java-mekanism (se det här [page](https://docs.oracle.com/javase/7/docs/api/java/util/Random.html)).

I testläge väljs alltid den övre grenen när en delning nås. You can reorganize the position of the split branches if you want the test to choose a different path. Se [den här sidan](../building-journeys/testing-the-journey.md)

>[!NOTE]
>
>Note that there is no button to add a path in the percentage split condition. The number of paths will depend on the number of splits. I delningsvillkor kan du inte lägga till en sökväg för andra fall eftersom det inte kan ske. Folk kommer alltid att gå in på en av de delade vägarna.

![](assets/journey52.png)

## Datumvillkor {#date_condition}

På så sätt kan du definiera ett annat flöde baserat på datumet. Om personen till exempel anger steget under&quot;försäljningsperioden&quot; skickar du ett specifikt meddelande till dem. Resten av året skickar du ett nytt meddelande.

>[!NOTE]
>
>Tidszonen är inte längre specifik för ett villkor och har nu definierats på färdsnivå i färdegenskaperna. Läs [den här sidan](../building-journeys/timezone-management.md).

![](assets/journey53.png)

## Profilände {#profile_cap}

Använd den här villkorstypen om du vill ange ett maximalt antal profiler för en resebana. När den här gränsen nås får de inmatade profilerna en alternativ sökväg. This ensures that your journeys will never exceed the limit defined.

You can use this condition type to ramp up the volume of your deliveries. Se det här [användningsfall](ramp-up-deliveries-uc.md).

Standardvärdet är 1 000.

Räknaren gäller endast den valda reseversionen. Räknaren återställs till noll efter en månad. Efter en återställning tar de infogade profilerna den nominella sökvägen igen tills räknargränsen nås.

Den nominella banan har alltid företräde framför den alternativa banan, även om du flyttar den alternativa banan ovanför den nominella banan på arbetsytan.

Här följer de tröskelvärden som ska beaktas för att se till att gränsvärdet uppnås:

* För ett lock som är större än 10000 måste antalet distinkta profiler som ska injiceras vara minst 1,3 gånger så stort som locket.
* För ett lock under 10000 måste antalet distinkta profiler som ska injiceras vara 1000 plus sockeln.

Profilände beaktas inte i testläge.

![](assets/profile-cap-condition.png)

## Använda segment i villkor {#using-a-segment}

I det här avsnittet beskrivs hur du använder ett segment i ett resevillkor. Mer information om segment och hur du skapar dem finns i [det här avsnittet](../segment/about-segments.md).

To use a segment in a journey condition, follow these steps:

1. Öppna en resa, släpp en **[!UICONTROL Condition]** och välj **Villkor för datakälla**.
   ![](assets/journey47.png)

1. Klicka **[!UICONTROL Add a path]** för varje extra sökväg som behövs. For each path, click the **[!UICONTROL Expression]** field.

   ![](assets/segment3.png)

1. På vänster sida, unfold **[!UICONTROL Segments]** nod. Dra och släpp det segment som du vill använda för villkoret. Som standard är villkoret i segmentet sant.

   ![](assets/segment4.png)

   >[!NOTE]
   >
   >Observera att endast de personer som har **Realiserad** och **Befintlig** Deltagandestatus för segment betraktas som medlemmar i segmentet. For more on how to evaluate a segment, refer to the [Segmentation Service documentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html#interpret-segment-results){target=&quot;_blank&quot;}.
