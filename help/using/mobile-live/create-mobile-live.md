---
solution: Journey Optimizer
product: journey optimizer
title: Skapa ett Live-aktivitetsmeddelande
description: Lär dig skapa en Live-aktivitet i Journey Optimizer
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 9864a136-e129-4279-bb09-081b72f584df
source-git-commit: 2fc4b1ee34b44fb6c5bcddb13f1b2b02f7094ff1
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 0%

---

# Skapa en Live-aktivitet {#create-mobile-live}

När du har konfigurerat din mobilkonfiguration och implementerat din mobila SDK från Adobe Experience Platform kan du börja skapa din Live-aktivitet i Journey Optimizer:

1. Öppna menyn **[!UICONTROL Campaigns]** och klicka sedan på **[!UICONTROL Create campaign]**.

1. Välj kampanjtypen **API utlöst**.

   * Välj **API-utlöst marknadsföring** för målgruppsbaserade kampanjer

   * Välj **API-utlöst Transactional** för enskilda kampanjer.

   >[!IMPORTANT]
   >
   > Observera att alternativet **inte ska aktiveras för** API-utlösta transaktioner **[!UICONTROL High Throughput]**.

   ![](assets/create-live-1.png)

1. I avsnittet **[!UICONTROL Properties]** redigerar du din kampanjs **[!UICONTROL Title]** och **[!UICONTROL Description]**.

1. I avsnittet **[!UICONTROL Actions]** väljer du **[!UICONTROL Live activity]** och väljer eller skapar en ny konfiguration.

   Läs mer om Live-aktivitetskonfigurationen på [den här sidan](mobile-live-configuration.md).

   ![](assets/create-live-2.png)

1. Klicka på **[!UICONTROL Create experiment]** för att börja konfigurera ditt innehållsexperiment och skapa behandlingar för att mäta deras prestanda och identifiera det bästa alternativet för målgruppen. [Läs mer](../content-management/content-experiment.md)

1. Välj **[!UICONTROL Audience]** **[!UICONTROL Identity type]** Läs mer[&#x200B; på fliken &#x200B;](../audience/about-audiences.md).

   >[!NOTE]
   >
   >För **API-utlösta Marketing**-kampanjer kan du välja en befintlig målgrupp som fungerar som den första segmenteringen innan du kontrollerar APNs channelID-prenumerationen från API-nyttolasten.

1. Kampanjer är utformade för att köras ett visst datum eller med en återkommande frekvens. Lär dig hur du konfigurerar **[!UICONTROL Schedule]** för din kampanj i [det här avsnittet](../campaigns/create-campaign.md#schedule).

1. När konfigurationen är klar klickar du på **[!UICONTROL Review to activate]** och sedan på **[!UICONTROL Activate]**.

1. När kampanjen har aktiverats använder du den angivna **cURL-begäran** som en mall för att utlösa Live-aktivitetens start-, uppdaterings- eller sluthändelser. Uppdatera exempelnyttolasten med dina specifika data före körning.

   Kontrollera att du även kopierar identifierarna **[!UICONTROL Campaign ID]** som ska ingå i din nyttolast.

   ➡️ I [API-dokumentationen för utlösta kampanjer](https://developer.adobe.com/journey-optimizer-apis/references/messaging/) finns autentiseringskrav, inklusive OAuth-tokens och API-nycklar.

   ![](assets/create-live-3.png)

   +++ Exempel på en nyttolast för fall av enhetsanvändning (API-utlösta transaktionskampanj)

   Detta exempel på nyttolast är för enskilda kampanjer som använder kampanjtypen **API-utlöst Transactional**. Observera att de flesta fält från följande exempel på nyttolast är obligatoriska, men bara `requestId`, `dismissal-date` och `alert` är valfria.

   ```json
   {
       "requestId": "your-request-id",
       "campaignId": "your-campaign-id",
       "recipients": [
   {
       "type": "aep",
       "userId": "testemail@gmail.com",
       "namespace": "email",
       "context": {
        "requestPayload": {
       "aps": {
       "content-available": 1,
       "timestamp": 1756984054,              // current epoch time
       "dismissal-date": 1756984084,         // optional – auto remove when event="end"
       "event": "update",                    // start | update | end
   
       // Fields from FoodDeliveryLiveActivityAttributes
       "content-state": {
         "orderStatus": "Delivered"
       },
   
       "attributes-type": "FoodDeliveryLiveActivityAttributes",
       "attributes": {
         "restaurantName": "Pizza",
         "liveActivityData": {
           "liveActivityID": "orderId1"       // customer reference ID
         }
       },
   
       "alert": {
         "title": "Order Delivered!",
         "body": "Your pizza has arrived."
       }
     }
   }
   }
   }
   ]
   }
   ```

   +++

   +++ Exempel på en nyttolast för användningsfall för sändning (API-utlösta marknadsföringskampanjer)

   Detta exempel på nyttolast är för målgruppsbaserade kampanjer som använder kampanjtypen **API-utlöst Marketing**.

   ```json
   {
       "requestId": "123400000",
       "campaignId": "d32e6f6c-56df-4a98-a2c0-6db6008f8f32",
       "audience": {
           "id": "508f9416-52d0-4898-ba47-08baaa22e9c7"
       },
       "context": {
           "requestPayload": {
               "aps": {
                   "input-push-channel": "V+8UslywEfAAAOq9SbTrLg==",  //apns-channel-id
                   "content-available": 1,
                   "timestamp": 1770808339,
                   "event": "update",   // start | update | end
   
                   // Fields from GameScoreLiveActivityAttributes
                   "content-state": {
                       "homeTeamScore": 33,
                       "awayTeamScore": 49,
                       "statusText": "Wingdom keeps scoring!"
                   },
                   "attributes-type": "GameScoreLiveActivityAttributes",
                   "attributes": {
                       "liveActivityData": {
                           "channelID": "V+8UslywEfAAAOq9SbTrLg=="   //apns-channel-id, must match the "input-push-channel" value
                       }
                   },
                   "alert": {
                       "title": "This is the title for game",
                       "body": "This is the body for body"
                   }
               }
           }
       }
   }
   ```

   +++

När du har utformat din Live-aktivitet kan du spåra effekten av din Live-aktivitet med [inbyggda rapporter](../reports/campaign-global-report-cja-activity.md).

## Instruktionsvideo

Upptäck hur du konfigurerar iOS Live-aktiviteten med Adobe Journey Optimizer för att leverera omfattande uppdateringar i realtid på iPhone Lock Screen och Dynamic Island.

>[!VIDEO](https://video.tv.adobe.com/v/3479868?captions=swe)
