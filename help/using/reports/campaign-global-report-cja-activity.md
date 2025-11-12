---
solution: Journey Optimizer
product: journey optimizer
title: Kampanjrapport
description: Lär dig hur du använder Live-aktivitetsdata från Campaign-rapporten
feature: Reporting
topic: Content Management
role: User
level: Intermediate
source-git-commit: ce6bfca78d097588b5958c10c721b29b7013b3e2
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 0%

---

# Rapport om aktiv aktivitetskampanj {#campaign-global-report-cja-activity}

>[!BEGINSHADEBOX]

Du kommer åt rapporten för din Live-aktivitetskampanj genom att klicka på knappen **[!UICONTROL Reports]** i kampanjen och sedan välja **[!UICONTROL View all time report]**. [Läs mer](report-gs-cja.md)

![](assets/report-access.png)

>[!ENDSHADEBOX]

## Skicka statistik {#sending-statistics-mobile}

![](assets/sending-statistics-mobile-live.png)

Tabellen **[!UICONTROL Sending Statistics]** innehåller en detaljerad översikt över nyckeltal relaterade till dina Live-aktivitetskampanjer. Här visas viktig information, till exempel storleken på målgruppen och antalet push-meddelanden som levererats, vilket hjälper dig att bedöma den övergripande räckvidden och prestandan för push-meddelanden.

+++ Läs mer om att skicka statistik

* **[!UICONTROL Targeted]**: Totalt antal profiler som har angetts som mål under Live-aktiviteten.

* **[!UICONTROL Sends]**: Totalt antal push-meddelanden som försökte skickas till målprofiler.

* **[!UICONTROL Delivered]**: Antal push-meddelanden som har levererats till enheter i förhållande till det totala antalet försök att skicka.

* **[!UICONTROL Send errors]**: Totalt antal push-meddelanden som inte kunde skickas på grund av fel (t.ex. ogiltiga token eller anslutningsproblem).

* **[!UICONTROL Send exclusions]**: Antal profiler som inte kan skickas av Adobe Journey Optimizer (till exempel på grund av avanmälningsstatus eller regler för behörighet).

+++

## Livscykel för aktiv aktivitet {#lifecycle}

![](assets/activity-lifecycle.png)

Tabellen **[!UICONTROL Live activity lifecycle]** innehåller en heltäckande bild av hur dina Live-aktiviteter utvecklas över tid. Det ger insyn i viktiga händelser, som när aktiviteter startas, uppdateras eller avslutas, och hjälper er att förstå användarengagemanget och hela livscykeln för era Live-aktivitetskampanjer.

+++ Läs mer om Live activity lifecycle metrics

* **[!UICONTROL Remote starts]**: Antal Live-aktiviteter som har initierats på fjärrbasis och som oftast aktiveras av servern eller serverdelen.

* **[!UICONTROL Local starts]**: Antal Live-aktiviteter som har startats lokalt på en användares enhet, ofta till följd av användarinteraktion eller klientutlösare.

**[!UICONTROL Updates]**: Totalt antal Live-aktivitetsuppdateringar som skickats till enheter. Uppdateringarna kan innehålla statusändringar, nytt innehåll eller statusmeddelanden.

**[!UICONTROL Ends]**: Antal Live-aktiviteter som har avslutats, antingen automatiskt efter slutförande eller manuellt via en definierad utlösare eller timeout.

**[!UICONTROL Totals count]**: Totalt antal alla Live-aktivitetslivscyklhändelser, inklusive start, uppdateringar och slut, som ger ett fullständigt mått på Live-aktivitetsvolymen.

+++

## Felorsaker {#error-reasons}

![](assets/error-reasons-activity.png)

I tabellen **[!UICONTROL Error Reasons]** kan du identifiera de specifika fel som uppstod under sändningsprocessen för dina Live-aktiviteter, vilket underlättar en grundlig analys av eventuella problem som uppstått.

## Undantagna orsaker {#excluded-reasons}

![](assets/excluded-activity.png)

Tabellen **[!UICONTROL Excluded Reasons]** visar de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen, vilket förhindrar dem från att ta emot din Live-aktivitet.
