---
solution: Journey Optimizer
product: journey optimizer
title: Vänta på aktivitet
description: Läs mer om vänteaktiviteten
feature: Journeys, Activities
topic: Content Management
role: User
level: Intermediate
keywords: vänta, aktivitet, resa, nästa, arbetsyta
exl-id: 7268489a-38c1-44da-b043-f57aaa12d7d5
source-git-commit: ce1e43ce2c439b02e5c263f26de5531b26dc0980
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 5%

---

# Vänta på aktivitet{#wait-activity}

>[!CONTEXTUALHELP]
>id="ajo_journey_wait"
>title="Vänta på aktivitet"
>abstract="Om du vill vänta innan du kör nästa aktivitet i sökvägen kan du använda en Wait-aktivitet. Du kan definiera tidpunkten då nästa aktivitet ska köras. Det finns två alternativ: duration och anpassad."

Om du vill vänta innan nästa aktivitet körs i sökvägen kan du använda en **[!UICONTROL Wait]** aktivitet. Du kan definiera tidpunkten då nästa aktivitet ska köras. Följande alternativ är tillgängliga:

* [Varaktighet](#duration)
* [Anpassat](#custom)

<!--
* [Email send time optimization](#email_send_time_optimization)
* [Fixed date](#fixed_date) 
-->

## Om aktiviteten Vänta{#about_wait}

Den maximala väntetiden är 29 dagar. I testläge **[!UICONTROL Wait time in test]** kan du definiera hur länge varje vänteaktivitet ska vara. Den förinställda tiden är tio sekunder. Detta säkerställer att du får testresultaten snabbt. Läs [den här sidan](../building-journeys/testing-the-journey.md).

Var försiktig när du använder flera Wait-aktiviteter under en resa när den globala resetidsgränsen är 30 dagar, vilket innebär att en profil alltid kommer att försvinna 30 dagar efter att han/hon har registrerat sig. Läs [den här sidan](../building-journeys/journey-gs.md#global_timeout).

En enskild person kan bara förlägga en vänteaktivitet om han eller hon har tillräckligt med tid kvar på resan för att slutföra väntetiden innan tidsgränsen på 30 dagar för resan har nåtts. Om du till exempel lägger till två vänteaktiviteter som är inställda på 20 dagar vardera, kommer systemet att upptäcka att den andra väntetiden kommer att sluta efter timeout-värdet på 30 dagar. Den andra väntetiden kommer därför att ignoreras och personen kommer att avsluta resan innan den påbörjas. I det exemplet stannar kunden totalt 20 dagar under resan.

Det är bäst att inte använda väntetider för att blockera återinträde. Använd i stället **Tillåt återinträde** på egenskapsnivå för resan. Läs [den här sidan](../building-journeys/journey-gs.md#entrance).

## Väntetid{#duration}

Ange väntetiden innan nästa aktivitet körs. Maximala längden är 29 dagar.

![](assets/journey55.png)

<!--
## Fixed date wait{#fixed_date}

Select the date for the execution of the next activity.

![](assets/journey56.png)

-->

## Anpassad väntetid{#custom}

Med det här alternativet kan du definiera ett anpassat datum, till exempel 12 juli 2020 klockan 17.00, med hjälp av ett avancerat uttryck som baseras på ett fält som kommer från en händelse eller en datakälla. Du kan inte definiera en anpassad längd, till exempel 7 dagar. Uttrycket i uttrycksredigeraren ska ha formatet dateTimeOnly. Se detta [page](expression/expressionadvanced.md). Mer information om formatet dateTimeOnly finns i [page](expression/data-types.md).

>[!NOTE]
>
>Du kan återanvända ett dateTimeOnly-uttryck eller använda en funktion för att konvertera till dateTimeOnly. Till exempel: toDateTimeOnly(@{Event.offerOpened.activity.endTime}), fältet i händelsen har formatet 2016-08-12T09:46:06Z.
>
>The **tidszon** är förväntat i egenskaperna för din resa. Därför är det inte möjligt i dag från gränssnittet till en direkt punkt vid en fullständig ISO-8601-tidsstämpelblandningstid och tidszonsförskjutning som 2016-08-12T09:46:6.982-05. Läs [den här sidan](../building-journeys/timezone-management.md).

![](assets/journey57.png)

Om du vill verifiera att vänteaktiviteten fungerar som förväntat kan du använda steghändelser. Läs [den här sidan](../reports/query-examples.md#common-queries).

<!--## Email send time optimization{#email_send_time_optimization}

This type of wait uses a score calculated in Adobe Experience Platform. The score calculates the propensity to click or open an email in the future based on past behavior. Note that the algorithm calculating the score needs a certain amount of data to work. As a result, when it does not have enough data, the default wait time will apply. At publication time, you’ll be notified that the default time applies.

>[!NOTE]
>
>The first event of your journey must have a namespace.
>
>This capability is only available after an **[!UICONTROL Email]** activity. You need to have Adobe Campaign Standard.

1. In the **[!UICONTROL Amount of time]** field, define the number of hours to consider to optimize email sending.
1. In the **[!UICONTROL Optimization type]** field, choose if the optimization should increase clicks or opens.
1. In the **[!UICONTROL Default time]** field, define the default time to wait if the predictive send time score is not available.

    >[!NOTE]
    >
    >Note that the send time score can be unavailable because there is not enough data to perform the calculation. In this case, you will be informed, at publication time, that the default time applies.

![](assets/journey57bis.png)-->
