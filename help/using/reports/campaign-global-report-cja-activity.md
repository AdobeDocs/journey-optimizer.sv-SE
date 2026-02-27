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
source-git-commit: 2fc4b1ee34b44fb6c5bcddb13f1b2b02f7094ff1
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 0%

---

# Rapport om aktiv aktivitetskampanj {#campaign-global-report-cja-activity}

>[!BEGINSHADEBOX]

Du kommer åt rapporten för din Live-aktivitetskampanj genom att klicka på knappen **[!UICONTROL Reports]** i kampanjen och sedan välja **[!UICONTROL View all time report]**. [Läs mer](report-gs-cja.md)

![](assets/report-access.png)

>[!ENDSHADEBOX]

## Skicka statistik {#sending-statistics-mobile}

![](assets/sending-statistics-mobile-live.png)

Tabellen **[!UICONTROL Sending Statistics]** innehåller en detaljerad översikt över nyckeltal relaterade till din Live-aktivitetskampanj. Här visas viktig information, till exempel storleken på målgruppen och antalet aktiva aktiviteter som levererats, vilket hjälper dig att bedöma den övergripande räckvidden och prestandan för din aktiva aktivitet.

+++ Läs mer om att skicka statistik

* **[!UICONTROL Targeted]**: Antal profiler som kvalificerats för målgruppen innan undantag, inaktiveringar eller medgivandeborttagningar tillämpades.

* **[!UICONTROL Sends]**: Totalt antal försök att skicka live-aktiviteter till målprofiler.

* **[!UICONTROL Delivered]**: Antal aktiva aktiviteter som har levererats till enheter i förhållande till det totala antalet försök att skicka.

* **[!UICONTROL Send errors]**: Totalt antal aktiva aktiviteter som inte kunde skickas på grund av fel (t.ex. ogiltiga token eller anslutningsproblem).

* **[!UICONTROL Send exclusions]**: Antal profiler som inte kan skickas av Adobe Journey Optimizer (till exempel på grund av avanmälningsstatus eller regler för behörighet).

+++

## Livscykel för aktiv aktivitet {#lifecycle}

Tabellen **[!UICONTROL Live activity lifecycle]** innehåller en heltäckande bild av hur din Live-aktivitet utvecklas över tid. Den ger insyn i viktiga händelser, som när aktiviteten startas, uppdateras eller avslutas, och hjälper er att förstå användarengagemanget bättre och hela livscykeln för er Live-aktivitetskampanj.

Rapporterna skiljer sig åt beroende på om du använder transaktions- eller marknadsföringskampanjer.

### Transactional Live-aktivitet

![](assets/activity-lifecycle.png)

För Transactional campaign visar rapporten för Live-aktivitetskampanjen alla livscykelhändelser inklusive fjärrstart, lokala starter, uppdateringar och slut.

+++ Läs mer om Live activity lifecycle metrics med Transactional campaign

* **[!UICONTROL Remote starts]**: Totalt antal Live-aktivitetsstarthändelser som har initierats på fjärrbasis, som oftast aktiveras av servern eller backend-systemen.

* **[!UICONTROL Local starts]**: Totalt antal Live-aktivitetsstarthändelser som initierats lokalt på en användares enhet, ofta till följd av användarinteraktion eller klientutlösare.

* **[!UICONTROL Updates]**: Totalt antal Live-aktivitetsuppdateringar som skickats till enheter. Uppdateringarna kan innehålla statusändringar, nytt innehåll eller statusmeddelanden.

* **[!UICONTROL Ends]**: Totalt antal Live-aktivitetssluthändelser som skickats till enheter.

* **[!UICONTROL Totals count]**: Totalt antal alla Live-aktivitetslivscyklhändelser, inklusive start, uppdateringar och slut, som ger ett fullständigt mått på Live-aktivitetsvolymen.

+++

### Marketing Live-aktivitet

![](assets/activity-lifecycle-broadcast.png)

Marknadsföringskampanjer använder Live-aktivitet för sändningsbruk och skickar uppdateringar till flera enheter samtidigt.

För iOS Live-aktivitet i marknadsföringskampanjer visas endast **[!UICONTROL Remote Starts]** händelser och **[!UICONTROL Remote starts errors]** vid start i rapporten. Händelserna **[!UICONTROL Updates]** och **[!UICONTROL Ends]** spåras inte eftersom APN:er distribuerar uppdateringar till alla enheter utan att ge feedback. Använd **[!UICONTROL Updates]** Apple Push Notification-konsol **[!UICONTROL Ends]** om du vill visa [- och &#x200B;](https://developer.apple.com/notifications/push-notifications-console/)-händelser.

+++ Läs mer om Live activity lifecycle metrics med marknadsföringskampanjer

* **[!UICONTROL Remote starts]**: Totalt antal Live-aktivitetsstarthändelser som har initierats på fjärrbasis, som oftast aktiveras av servern eller backend-systemen.

* **[!UICONTROL Remote starts errors]**: Totalt antal fel som uppstod när Live-aktiviteten skulle fjärrstartas (t.ex. ogiltiga token eller anslutningsproblem).

+++

#### Hämta uppdateringar och slutantal via API {#retrieving-updates-end-api}

Som ett alternativ till att använda Apple push-meddelandekonsol kan antalet uppdateringar och slut hämtas via headless API-anrop.

När API-anrop för uppdatering eller slut körs för sändningsanvändningsfall, innehåller svaret ett `controlBreakdown`-avsnitt som ger räknare som anger hur många uppdaterings- och slutanrop som har utförts för körningen av den aktiva aktiviteten. Det här blocket saknas för äldre körningar utan livscykeldata. Körningsstatus kan också hämtas explicit med GET-slutpunkten vid behov.

**UPPDATERA/SLUTA SVAR (200 OK)**

```json
{
  "executionId": "HA-exec-abc",
  "campaignId": "campaign-abc-123",
  "campaignVersionId": "v1",
  "audienceId": "audience-segment-id",
  "status": "processing",
  "targetedProfileCount": 150000,
  "createdAt": "2026-02-27T10:00:00Z",
  "executionLifecycle": {
    "lastControlAt": "2026-02-27T10:45:00Z",
    "controlBreakdown": {
      "update": 5,
      "end": 1
    }
  }
}
```

**Körningsstatus (GET)**

```
GET /im/executions/audience/{executionId}
```

## Felorsaker {#error-reasons}

![](assets/error-reasons-activity.png)

I tabellen **[!UICONTROL Error Reasons]** kan du identifiera de specifika fel som uppstod under sändningsprocessen för din Live-aktivitet, vilket underlättar en grundlig analys av eventuella problem som uppstått.

## Undantagna orsaker {#excluded-reasons}

![](assets/excluded-activity.png)

Tabellen **[!UICONTROL Excluded Reasons]** visar de olika faktorer som ledde till att användarprofiler exkluderades från målgruppen, vilket förhindrar dem från att ta emot din Live-aktivitet.
