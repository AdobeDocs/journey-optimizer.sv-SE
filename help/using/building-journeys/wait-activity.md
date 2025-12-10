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
version: Journey Orchestration
source-git-commit: c30a74ccdaec81cbbb28e3129d5c351a0fe64bfc
workflow-type: tm+mt
source-wordcount: '886'
ht-degree: 2%

---

# Vänta på aktivitet {#wait-activity}

>[!CONTEXTUALHELP]
>id="ajo_journey_wait"
>title="Vänta på aktivitet"
>abstract="Om du vill vänta innan du kör nästa aktivitet i sökvägen kan du använda en Wait-aktivitet. Du kan definiera tidpunkten då nästa aktivitet ska köras. Det finns två alternativ: duration och anpassad."

Du kan använda en **[!UICONTROL Wait]**-aktivitet för att definiera en varaktighet innan du kör nästa aktivitet.  Maximal väntetid är **90 dagar**.

Du kan ange två typer av **Wait**-aktivitet:

* En väntetid baserad på en relativ längd. [Läs mer](#duration)
* Ett anpassat datum som använder funktioner för att beräkna det. [Läs mer](#custom)

<!--
* [Email send time optimization](#email_send_time_optimization)
* [Fixed date](#fixed_date) 
-->

## Rekommendationer {#wait-recommendations}

### Flera väntande aktiviteter {#multiple-wait-activities}

När du använder flera **Wait**-aktiviteter på en resa ska du vara medveten om att den [globala tidsgränsen](journey-properties.md#global_timeout) för resor är 91 dagar, vilket innebär att profiler alltid tas bort från resan högst 91 dagar efter att de har registrerat sig. Läs mer på [den här sidan](journey-properties.md#global_timeout).

En individ kan bara ange en **Wait**-aktivitet om han eller hon har tillräckligt med tid kvar på resan för att slutföra väntetiden innan tidsgränsen på 91 dagars resa har uppnåtts.

### Vänta och återinträde {#wait-reentrance}

Det är en god vana att inte använda **Wait**-aktiviteter för att blockera återinträde. Använd i stället alternativet **Tillåt återinträde** på resans egenskapsnivå. Läs mer på [den här sidan](../building-journeys/journey-properties.md#entrance).

### Vänta- och testläge {#wait-test-mode}

I testläge kan du med parametern **[!UICONTROL Wait time in test]** definiera den tid som varje **Wait** -aktivitet ska hålla. Den förinställda tiden är tio sekunder. Detta säkerställer att du får testresultaten snabbt. Läs mer på [den här sidan](../building-journeys/testing-the-journey.md).

### Vänta och mobila kanaler {#wait-mobile-channels}

Om du vill visa ett [in-app-meddelande](../in-app/create-in-app.md) kort efter att du har skickat ett [push-meddelande](../../rp_landing_pages/push-landing-page.md) använder du en **Wait**-aktivitet för att tillåta inläsningstiden för meddelanden i appen att spridas. Vanligtvis rekommenderas en 5-15 minuters väntan, men de exakta tiderna kan variera beroende på nyttolastens komplexitet och personaliseringsbehov.

## Konfiguration {#wait-configuration}

### Väntetid {#duration}

Välj typen **Varaktighet** om du vill ange den relativa väntetiden innan nästa aktivitet körs. Maximala längden är **90 dagar**.

![Definiera väntetiden](assets/journey55.png)

<!--
## Fixed date wait{#fixed_date}

Select the date for the execution of the next activity.

![Wait activity configuration panel with duration and fixed date options](assets/journey56.png)

-->

### Anpassad väntetid {#custom}

Välj typen **Egen** om du vill definiera ett anpassat datum, med hjälp av ett avancerat uttryck som baseras på ett fält som kommer från en händelse eller ett anpassat åtgärdssvar. Du kan inte definiera en relativ varaktighet direkt, till exempel 7 dagar, men du kan använda funktioner för att beräkna den om det behövs (till exempel 2 dagar efter köpet).

![Definiera en anpassad väntan med ett uttryck](assets/journey57.png)

Uttrycket i redigeraren ska ha formatet `dateTimeOnly`. Se [den här sidan](expression/expressionadvanced.md). Mer information om formatet dateTimeOnly finns på [den här sidan](expression/data-types.md).

Det bästa sättet är att använda anpassade datum som är specifika för dina profiler och undvika att använda samma datum för alla. Definiera till exempel inte `toDateTimeOnly('2024-01-01T01:11:00Z')` utan `toDateTimeOnly(@event{Event.productDeliveryDate})` som är specifik för varje profil. Tänk på att användning av fasta datum kan orsaka problem vid körningen av din resa. Läs mer om hur vänteaktiviteter påverkar bearbetningshastigheten för resan i [det här avsnittet](entry-management.md#wait-activities-impact).


>[!NOTE]
>
>Du kan utnyttja ett `dateTimeOnly`-uttryck eller använda en funktion för att konvertera till en `dateTimeOnly`. Till exempel: `toDateTimeOnly(@event{Event.offerOpened.activity.endTime})`, fältet i händelsen har formatet 2023-08-12T09:46:06Z.
>
>**Tidszonen** förväntas i egenskaperna för din resa. Därför är det inte möjligt att direkt peka från användargränssnittet vid en fullständig ISO-8601-tidsstämpelblandningstid och tidszonsförskjutning som 2023-08-12T09:46:06.982-05. [Läs mer](../building-journeys/timezone-management.md).

>[!CAUTION]
>
>När du skapar ett anpassat vänteuttryck med `toDateTimeOnly()` ska du undvika att lägga till Z eller någon tidszonsförskjutning (t.ex. -05:00) i uttrycksresultatet. Uttrycket måste använda en giltig ISO-syntax för datum/tid som refererar till kundens konfigurerade tidszon utan explicita tidszonsdesigners.
>
>**Korrekt exempel:** `toDateTimeOnly(concat(toString(toDateOnly(nowWithDelta(2, "days"))),"T10:00:00"))`
>
>**Felaktigt exempel:** `toDateTimeOnly(concat(toString(toDateOnly(nowWithDelta(2, "days"))),"T10:00:00Z"))` ❌ (innehåller &#39;Z&#39;)
>
>Om tidszonsdesigners som inte stöds används kan det leda till att profiler fastnar i vänteaktiviteten i stället för att utvecklas som förväntat.

Om du vill verifiera att vänteaktiviteten fungerar som förväntat kan du använda steghändelser. [Läs mer](../reports/query-examples.md#common-queries).

## Profiluppdatering efter väntan {#profile-refresh}

När en profil har parkerats vid en **Wait**-aktivitet på en resa som börjar med en **Läs målgrupp** -aktivitet, uppdaterar resan automatiskt profilens attribut från UPS (Unified Profile Service) för att hämta de senaste tillgängliga data.

* **Vid resepost**: Profiler använder attributvärden från målgruppsögonblicksbilden som utvärderades när resan påbörjades.
* **Efter en väntenod**: Under resan utförs en sökning för att hämta de senaste profildata från UPS, inte de äldre ögonblicksbildsdata. Detta innebär att profilattributen kan ha ändrats sedan resan påbörjades.

Detta beteende säkerställer att efterföljande aktiviteter använder aktuell profilinformation efter en vänteperiod. Det kan dock ge oväntade resultat om du förväntar dig att resan bara ska använda ursprungliga ögonblicksbildsdata under hela körningen.

Exempel: Om en profil kvalificerar sig för en&quot;silverkund&quot;-målgrupp när resan börjar, men uppgraderar till&quot;guldkund&quot; under en 3-dagars väntetid, kommer aktiviteter efter väntetiden att se den uppdaterade statusen&quot;guldkund&quot;.

## Automatisk väntenod  {#auto-wait-node}

>[!CONTEXTUALHELP]
>id="ajo_journey_auto_wait_node "
>title="Om den automatiska väntenoden"
>abstract="En **Vänta**-aktivitet läggs automatiskt till efter den här aktiviteten. Den är inställd på 3 dagar. Du kan ta bort eller konfigurera den efter behov."

Varje inkommande upplevelseaktivitet (meddelande i appen, kodbaserad upplevelse eller kort) levereras med en 3-dagars **Wait** -aktivitet. Eftersom inkommande meddelanden automatiskt avslutas när en profil når ut utanför kundens slut, antar vi att du vill att användarna ska se den i minst tre dagar. Du kan ta bort den här **Vänta**-aktiviteten eller ändra dess konfiguration om det behövs.
