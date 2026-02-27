---
solution: Journey Optimizer
product: journey optimizer
title: Kampanjrapport
description: Lär dig hur du använder Live-aktivitetsdata från Campaign-rapporten
feature: Reporting
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
exl-id: 58034ec4-62dc-406c-99c4-d6b7aa107140
source-git-commit: 6b4e3a6c32d24861f1ea8df54fc2e4fbb19d0ce7
workflow-type: tm+mt
source-wordcount: '518'
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

* **[!UICONTROL Targeted]**: Antal profiler som kvalificerats för målgruppen innan undantag, inaktiveringar eller medgivandeborttagningar tillämpades.

* **[!UICONTROL Sends]**: Totalt antal push-meddelanden som försökte skickas till målprofiler.

* **[!UICONTROL Delivered]**: Antal push-meddelanden som har levererats till enheter i förhållande till det totala antalet försök att skicka.

* **[!UICONTROL Send errors]**: Totalt antal push-meddelanden som inte kunde skickas på grund av fel (t.ex. ogiltiga token eller anslutningsproblem).

* **[!UICONTROL Send exclusions]**: Antal profiler som inte kan skickas av Adobe Journey Optimizer (till exempel på grund av avanmälningsstatus eller regler för behörighet).

+++

## Livscykel för aktiv aktivitet {#lifecycle}

Tabellen **[!UICONTROL Live activity lifecycle]** innehåller en heltäckande bild av hur dina Live-aktiviteter utvecklas över tid. Det ger insyn i viktiga händelser, som när aktiviteter startas, uppdateras eller avslutas, och hjälper er att förstå användarengagemanget och hela livscykeln för era Live-aktivitetskampanjer.

Rapporterna skiljer sig åt beroende på om du använder transaktions- eller marknadsföringskampanjer.

### Transaktionsaktiviteter live

![](assets/activity-lifecycle.png)

För Transactional campaign visar kampanjrapporten för Live-aktiviteter alla livscykelhändelser inklusive fjärrstart, lokala starter, uppdateringar och slut.

+++ Läs mer om Live activity lifecycle metrics med Transactional campaign

* **[!UICONTROL Remote starts]**: Det totala antalet Live-aktiviteter som startar händelser som initieras på fjärrbasis, som oftast aktiveras av servern eller backend-systemen.

* **[!UICONTROL Local starts]**: Totalt antal Live-aktiviteter startar händelser som initierats lokalt på en användares enhet, ofta till följd av användarinteraktion eller klientutlösare.

* **[!UICONTROL Updates]**: Totalt antal Live-aktivitetsuppdateringar som skickats till enheter. Uppdateringarna kan innehålla statusändringar, nytt innehåll eller statusmeddelanden.

* **[!UICONTROL Ends]**: Totalt antal Live-aktiviteter som sluthändelser har skickats till enheter.

* **[!UICONTROL Totals count]**: Totalt antal alla Live-aktivitetslivscyklhändelser, inklusive start, uppdateringar och slut, som ger ett fullständigt mått på Live-aktivitetsvolymen.

+++

### Marketing Live-aktiviteter

![](assets/activity-lifecycle-broadcast.png)

Marknadsföringskampanjer använder Live-aktiviteter för sändningsbruk och skickar uppdateringar till flera enheter samtidigt.

För iOS Live-aktiviteter i marknadsföringskampanjer visar rapporten endast **[!UICONTROL Remote Starts]** händelser och **[!UICONTROL Remote starts errors]** vid start. Händelserna **[!UICONTROL Updates]** och **[!UICONTROL Ends]** spåras inte eftersom APN:er distribuerar uppdateringar till alla enheter utan att ge feedback. Använd **[!UICONTROL Updates]** Apple Push Notification-konsol **[!UICONTROL Ends]** om du vill visa [- och &#x200B;](https://developer.apple.com/notifications/push-notifications-console/)-händelser.

+++ Läs mer om Live activity lifecycle metrics med marknadsföringskampanjer

* **[!UICONTROL Remote starts]**: Det totala antalet Live-aktiviteter som startar händelser som initieras på fjärrbasis, som oftast aktiveras av servern eller backend-systemen.

* **[!UICONTROL Remote starts errors]**: Totalt antal fel som uppstod när Live-aktiviteter skulle fjärrstartas (t.ex. ogiltiga token eller anslutningsproblem).

+++

## Felorsaker {#error-reasons}

![](assets/error-reasons-activity.png)

I tabellen **[!UICONTROL Error Reasons]** kan du identifiera de specifika fel som uppstod under sändningsprocessen för dina Live-aktiviteter, vilket underlättar en grundlig analys av eventuella problem som uppstått.

## Undantagna orsaker {#excluded-reasons}

![](assets/excluded-activity.png)

Tabellen **[!UICONTROL Excluded Reasons]** visar de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen, vilket förhindrar dem från att ta emot din Live-aktivitet.
