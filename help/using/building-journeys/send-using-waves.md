---
solution: Journey Optimizer
product: journey optimizer
title: Skicka med vågor på resor
description: Schemalägg utgående resemeddelanden som ska levereras i kontrollerade satser (påfyllnader) över tid. Vågöverföring i läsmålgruppsresor hjälper till att balansera belastning och leverans av support.
feature: Journeys, Activities, Audiences
topic: Content Management
role: User
level: Intermediate
mini-toc-levels: 1
keywords: vågor, batchar, schema, resa, läsare, slutprodukt
source-git-commit: 6c509ef134c4240b243d255fd1ab7ec6bb062bf0
workflow-type: tm+mt
source-wordcount: '875'
ht-degree: 0%

---

# Skicka med vågor på resor {#send-using-waves-journeys}

>[!AVAILABILITY]
>
>Den här funktionen är begränsad. Kontakta din Adobe-representant för att få åtkomst.

Du kan leverera utgående meddelanden från en resa i grupper (vågor) över tiden i stället för alla samtidigt. Vågutsändning hjälper till att balansera belastningen, undvika överväldigande system längre fram i kedjan (t.ex. callcenters eller landningssidor) och supporttjänster som levereras och avsändarens anseende - särskilt för stora läsares resor.

<!--
>[!CAUTION]
>
>Wave sending is available for read audience journeys only and applies to **outbound** actions only (Email, SMS, Push, Direct mail).-->

Ni konfigurerar det på kundresenivå när ni definierar hur målgruppen ska gå in och hur åtgärderna ska schemaläggas. Du definierar antalet vågor, deras storlek (som en procentandel av publiken eller som absoluta tal) och när varje våg körs.

## Begränsningar och skyddsräcken {#limitations-guardrails}

* Påfyllnadssändning är bara tillgängligt för läsning av målgruppsresor med schemaläggningstyperna **[!DNL As soon as possible]** och **[!UICONTROL Once]**. Läs mer om [transportschemat](read-audience.md#schedule).
* Vågöverföring är inte tillgängligt för återkommande, händelseutlösta, affärshändelser, testläge eller körningar.
* Du måste definiera minst **2 vågor** och du kan lägga till upp till **10 vågor**.
* Det minsta intervallet mellan början av två vågor är **30 minuter**.
* Påfyllnadsstarten får inte vara före resans början eller tidigare.
* Det kan ta upp till en timme att dela publiken i vågor. Profilerna får inte passera in på resan förrän då.
* Inom en och samma resversion kan två vågor aldrig köras samtidigt. Nästa våg startar först när den föregående vågen har slutförts. Om vågor till exempel schemaläggs med en timmes mellanrum men den första vågen körs med 2 timmar, startar den andra vågen när den första vågen slutar, inte vid den schemalagda tidpunkten.
* Vågstarter kan fördröjas när plattformen tillämpar kvotgränser eller när systemkapaciteten är för hög.

## Konfigurera vågsändning i en resa {#configure-wave-sending}

1. Starta din resa med aktiviteten [Läs målgrupp](read-audience.md).

1. Dubbelklicka på aktiviteten **[!UICONTROL Read Audience]** för att öppna dess egenskaper och välj alternativet **[!UICONTROL Deliver journey action in waves]**.

   ![](assets/journey-wave-option.png){width="100%"}

1. Ange **antalet vågor** (till exempel 4).

   ![](assets/journey-wave-number.png){width="80%"}

   >[!NOTE]
   >
   >Du måste definiera minst 2 vågor och kan lägga till upp till 10 vågor.

1. Välj hur du vill definiera vågstorlek och tidsinställning enligt nedan.

### Lika vågor {#equal-waves}

Som standard delas målgruppen upp i vågor av samma storlek. Ange ett fast intervall mellan starten av varje våg (till exempel 2 timmar).

![](assets/journey-equal-waves.png){width="70%"}

>[!NOTE]
>
>Det minsta intervallet mellan början av två vågor är **30 minuter**.

Systemet schemalägger sedan efterföljande vågor automatiskt (till exempel den första vågen klockan 9:00, den andra klockan 11:00, den tredje klockan 1:00 och den fjärde klockan 3:00).

### Anpassad distribution {#custom-distribution}

Välj alternativet **[!UICONTROL Custom distribution]** om du vill definiera storleken för varje våg som en procentandel av den totala publiken (till exempel 15 %, 20 %, 25 %, 40 %).

![](assets/journey-wave-percentage.png){width="70%"}

>[!NOTE]
>
>Summan för alla vågor måste vara 100 %. Om så inte är fallet visas ett varningsmeddelande.<!--are the waves actually sent or does the system prevent user from saving the journey?-->

Välj **[!UICONTROL Numbers]** om du vill definiera storleken på varje våg som ett absolut antal profiler (till exempel 10 000; 50 000).

![](assets/journey-wave-numbers.png){width="70%"}

>[!NOTE]
>
>När du använder siffror validerar systemet inte att summan täcker hela målgruppen. Du måste se till att vågstorlekarna täcker den målgrupp du tänker skicka till. Läs mer i [Vanliga frågor](#faq).

### Anpassat schema {#custom-schedule}

Välj **[!UICONTROL Schedule each wave]** om du vill definiera ett specifikt startdatum och en specifik starttid för varje påfyllnad. Vågor behöver inte vara jämnt fördelade (t.ex. 09:00, 11:00 AM, 5:00 PM, 8:30 PM).

![](assets/journey-wave-custom-schedule.png){width="70%"}

>[!NOTE]
>
>Det minsta intervallet mellan början av två vågor är **30 minuter**.

## Användningsfall {#use-cases}

Wave-sändning hjälper er att styra när och hur många meddelanden som skickas ut, vilket kan förbättra leveransmöjligheterna, skydda avsändarens anseende och anpassa meddelandena efter din driftskapacitet. Använd vågor i följande scenarier:

* **Anropscenter eller svarshantering:** Begränsa hur många meddelanden som skickas per dag eller per timme så att underordnade team (t.ex. kundtjänst) kan hantera svar. Skicka t.ex. 20 meddelanden per dag för att matcha kapaciteten för kundtjänst.

  ![](assets/journey-waves-ex-call-center.png){width="55%"}

* **Hög volym och slutbarhet:** Undvik att skicka en mycket stor resa i ett enda foto. Sprid leveransen över tid för att bevara avsändarens rykte och minska risken för att flaggas som skräppost.

  ![](assets/journey-waves-ex-high-volume.png){width="55%"}

* **Rampup:** När du använder en ny plattform eller IP-adress ökar du volymen gradvis (till exempel 10 % i den första vågen, sedan 15 %, 20 % och så vidare) för att gradvis bygga upp anseendet.

  ![](assets/journey-waves-ex-ramp-up.png){width="55%"}

## Vanliga frågor och svar {#faq}

+++ Vad händer om summan av vågstorlekarna inte motsvarar den totala publiken?

* Om summan av dina påfyllnadsstorlekar **överstiger** målgruppen (du schemalägger till exempel 100 000 i den första påfyllnaden för en målgrupp på 100 000), kommer den första påfyllnaden att skickas till hela målgruppen och de återstående påfyllnaderna har ingen kvar att skicka till - de kommer inte att köras.
* Om summan **är mindre än** än målgruppen (du definierar t.ex. fyra vågor på totalt 40 000 profiler för en målgrupp på 100 000), kommer endast de profiler som ingår i dessa vågor att få meddelandet. Resten av publiken får inte meddelandet och kommer inte att provas igen i senare vågor.

+++

+++ Kan jag tilldela olika segment eller kriterier till enskilda vågor?

Du kan bara definiera storlek och tidpunkt för vågor. Samma målgrupp flödar genom hela resan. Du kan inte tilldela olika segment eller kriterier till enskilda vågor.

+++

## Se även {#see-also}

* [Använd en målgrupp på en resa](read-audience.md) - konfigurera aktiviteten Läs målgrupp.
