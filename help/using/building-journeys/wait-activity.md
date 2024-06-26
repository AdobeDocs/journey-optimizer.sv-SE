---
solution: Journey Optimizer
product: journey optimizer
title: Vänta på aktivitet
description: Lär dig hur du konfigurerar vänteaktiviteten
feature: Journeys, Activities
topic: Content Management
role: User
level: Intermediate
keywords: vänta, aktivitet, resa, nästa, arbetsyta
exl-id: 7268489a-38c1-44da-b043-f57aaa12d7d5
source-git-commit: cae6d394ad1c2356e55bd5f1cb4ad7494c9623dd
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 7%

---

# Vänta på aktivitet {#wait-activity}

>[!CONTEXTUALHELP]
>id="ajo_journey_wait"
>title="Vänta på aktivitet"
>abstract="Om du vill vänta innan du kör nästa aktivitet i sökvägen kan du använda en Wait-aktivitet. Du kan definiera tidpunkten då nästa aktivitet ska köras. Det finns två alternativ: duration och anpassad."

Du kan använda en **[!UICONTROL Wait]** aktivitet som definierar en varaktighet innan nästa aktivitet körs.  Maximal väntetid är **90 dagar**.

Du kan ange två typer av **Vänta** aktivitet:

* En väntetid baserad på en relativ längd. [Läs mer](#duration)
* Ett anpassat datum som använder funktioner för att beräkna det. [Läs mer](#custom)

<!--
* [Email send time optimization](#email_send_time_optimization)
* [Fixed date](#fixed_date) 
-->

## Rekommendationer {#wait-recommendations}

### Flera väntande aktiviteter {#multiple-wait-activities}

Vid användning av flera **Vänta** ska du vara medveten om att [global timeout](journey-properties.md#global_timeout) för resor är 91 dagar, vilket innebär att profiler alltid utesluts från resan högst 91 dagar efter att de passerat in i den. Läs mer på [den här sidan](journey-properties.md#global_timeout).

En individ kan ange en **Vänta** endast om de har tillräckligt med tid kvar på resan för att slutföra väntetiden före timeout för 91-dagarsresan.

### Vänta och återinträde {#wait-re-entrance}

En god vana att inte använda **Vänta** aktiviteter för att blockera återinträde. Använd i stället **Tillåt återinträde** på egenskapsnivå för resan. Läs mer på [den här sidan](../building-journeys/journey-properties.md#entrance).

### Vänta- och testläge {#wait-test-modd}

I testläge **[!UICONTROL Wait time in test]** kan du definiera tiden för varje **Vänta** aktiviteten varar. Den förinställda tiden är tio sekunder. Detta säkerställer att du får testresultaten snabbt. Läs mer på [den här sidan](../building-journeys/testing-the-journey.md).

## Konfiguration {#wait-configuration}

### Väntetid {#duration}

Välj **Varaktighet** typ för att ange den relativa väntetiden innan nästa aktivitet körs. Den maximala längden är **90 dagar**.

![Definiera väntetiden](assets/journey55.png)

<!--
## Fixed date wait{#fixed_date}

Select the date for the execution of the next activity.

![](assets/journey56.png)

-->

### Anpassad väntetid {#custom}

Välj **Egen** typ för att definiera ett anpassat datum, med hjälp av ett avancerat uttryck som baseras på ett fält som kommer från en händelse eller ett anpassat åtgärdssvar. Du kan inte definiera en relativ varaktighet direkt, till exempel 7 dagar, men du kan använda funktioner för att beräkna den om det behövs (till exempel 2 dagar efter köpet).

![Definiera en anpassad väntan med ett uttryck](assets/journey57.png)

Uttrycket i redigeraren ska innehålla en `dateTimeOnly` format. Se [den här sidan](expression/expressionadvanced.md). Mer information om formatet dateTimeOnly finns i [den här sidan](expression/data-types.md).

Det bästa sättet är att använda anpassade datum som är specifika för dina profiler och undvika att använda samma datum för alla. Definiera till exempel inte `toDateTimeOnly('2024-01-01T01:11:00Z')` men snarare `toDateTimeOnly(@event{Event.productDeliveryDate})` som är specifik för varje profil. Tänk på att användning av fasta datum kan orsaka problem vid körningen av din resa.


>[!NOTE]
>
>Du kan använda `dateTimeOnly` uttryck eller använda en funktion för att konvertera till `dateTimeOnly`. Till exempel: `toDateTimeOnly(@event{Event.offerOpened.activity.endTime})`, fältet i händelse av formatet 2023-08-12T09:46:06Z.
>
>The **tidszon** är förväntat i egenskaperna för din resa. Därför är det inte möjligt att direkt peka från användargränssnittet vid en fullständig ISO-8601-tidsstämpelblandningstid och tidszonsförskjutning som 2023-08-12T09:46:6.982-05. [Läs mer](../building-journeys/timezone-management.md).


Om du vill verifiera att vänteaktiviteten fungerar som förväntat kan du använda steghändelser. [Läs mer](../reports/query-examples.md#common-queries).

<!--## Email send time optimization{#email_send_time_optimization}

This type of wait uses a score calculated in Adobe Experience Platform. The score calculates the propensity to click or open an email in the future based on past behavior. Note that the algorithm calculating the score needs a certain amount of data to work. As a result, when it does not have enough data, the default wait time will apply. At publication time, you'll be notified that the default time applies.

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
