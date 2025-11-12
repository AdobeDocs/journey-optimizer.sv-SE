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
source-git-commit: ce6bfca78d097588b5958c10c721b29b7013b3e2
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 1%

---

# Skapa en Live-aktivitet {#create-mobile-live}

>[!BEGINSHADEBOX]

* [Kom igång med Live-aktivitet](get-started-mobile-live.md)
* [Konfiguration av aktiv aktivitet](mobile-live-configuration.md)
* [Live Activity-integrering med Adobe Experience Platform Mobile SDK](mobile-live-configuration-sdk.md)
* **[Skapa en Live-aktivitet](create-mobile-live.md)**
* [Vanliga frågor och svar](mobile-live-faq.md)
* [Rapport om aktiv aktivitetskampanj](../reports/campaign-global-report-cja-activity.md)

>[!ENDSHADEBOX]

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

1. Kampanjer är utformade för att köras ett visst datum eller med en återkommande frekvens. Lär dig hur du konfigurerar **[!UICONTROL Schedule]** för din kampanj i [det här avsnittet](../campaigns/create-campaign.md#schedule).

1. När konfigurationen är klar klickar du på **[!UICONTROL Review to activate]** och sedan på **[!UICONTROL Activate]**.

1. När kampanjen har aktiverats använder du den angivna **cURL-begäran** som en mall för att aktivera start-, uppdatering- eller sluthändelser för Live-aktiviteten. Uppdatera exempelnyttolasten med dina specifika data före körning.

   Kontrollera att du även kopierar identifierarna **[!UICONTROL Campaign ID]** som ska ingå i din nyttolast.

   ➡️ I [API-dokumentationen för utlösta kampanjer](https://developer.adobe.com/journey-optimizer-apis/references/messaging/) finns autentiseringskrav, inklusive OAuth-tokens och API-nycklar.

   ![](assets/create-live-3.png)

   +++ Exempel på en enskild nyttolast

   Observera att de flesta fält från följande exempel på nyttolast är obligatoriska, men bara `requestId`, `dismissal-date` och `alert` är valfria.

       &quot;json
       &lbrace;
       &quot;requestId&quot;: &quot;your-request-id&quot;,
       &quot;campaignId&quot;: &quot;your-campaign-id&quot;, 
       &quot;mottagare&quot;: &lbrack;
       &lbrace;
       &quot;type&quot;: &quot;aep&quot;, 
       &quot;userId&quot;: &quot;testemail@gmail.com&quot;,
       &quot;namespace&quot;: &quot;email&quot;, 
       &quot;context&quot;: 
       &quot;requestPayload&quot;: 
       &quot;aps&quot;: 
       &quot;content-available&quot;: 1,
       &quot;timestamp&quot;: 1756984054,              // aktuell epoktid 
       &quot;dismissal-date&quot;: 1756984084,         // valfritt - ta bort automatiskt när event=&quot;end&quot;
       &quot;event&quot;: &quot;update&quot;,                    // start | uppdatera | end
       
       // Fält från FoodDeliveryLiveActivityAttributes 
       &quot;content-state&quot;: 
       &quot;orderStatus&quot;: &quot;Levererad&quot; 
       ,
       
       &quot;attributes-type&quot;: &quot;FoodDeliveryLiveActivityAttributes&quot;,
       &quot;attributes&quot;: 
       &quot;aurangnamn&quot;: &quot;Pizza&quot;, 
       &quot;liveActivityData&quot;: 
       &quot;liveActivityID&quot;: &quot;orderId1&quot;       // kundreferens-ID 
       
       ,
       
       &quot;alert&quot;: 
       &quot;title&quot;: &quot;Order Delived!&quot;,
       &quot;body&quot;: &quot;Your pizza has come.&quot;
        
       
       
       
       
       &rbrack;
       
       &quot;
   +++

När du har utformat din Live-aktivitet kan du spåra effekten av din Live-aktivitet med [inbyggda rapporter](../reports/campaign-global-report-cja-activity.md).
