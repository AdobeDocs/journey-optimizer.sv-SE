---
solution: Journey Optimizer
product: journey optimizer
title: Skapa feedback-webhooks för API-utlösta kampanjer i Journey Optimizer
description: Lär dig hur du skapar feedback-webhooks för API-utlösta kampanjer i Journey Optimizer.
feature: Channel Configuration
topic: Administration
role: Admin
level: Experienced
source-git-commit: be07b0dfec31d23f741bfc2a9f89fe1a7891ef0b
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 1%

---


# Skapa feedback-webhooks för API-utlösta kampanjer {#webhooks}

Med hjälp av webhooks för feedback kan ni ta emot statusuppdateringar i realtid för meddelanden som skickas via kampanjer som triggas av transaktions-API. Genom att konfigurera en webkrok kan ni automatiskt få leveransresultat direkt till era system, vilket möjliggör övervakning, loggning och automatiserad bearbetning.

Du kan hantera webbkrokkonfigurationer på menyn **[!UICONTROL Administration]** / **[!UICONTROL Channels]** / **[!UICONTROL Feedback webhook settings]** .

![](assets/webhook-list.png)

>[!NOTE]
>Endast en webkroskonfiguration per kombination av **Organisation + sandlåda** tillåts.

## Skapa en webkrok för feedback

Så här skapar du en webkrok:

1. Navigera till **[!UICONTROL Administration]** / **[!UICONTROL Channels]** / **[!UICONTROL Feedback webhook settings]**.

1. Klicka på **Skapa webkrok för feedback**.

1. Ange följande information i avsnittet **[!UICONTROL Basic Configuration]**:

   ![](assets/webhook-config.png)

   * **Webkrok-namn** - Ange ett beskrivande namn som identifierar webkroken.
   * **Kanaler** - Välj kanal(er) som den här webkroken ska få feedback för (e-post och/eller SMS).
   * **Webkroks-URL** - Ange HTTPS-slutpunkten där feedback-händelser måste levereras.

1. Välj autentiseringsmetod i avsnittet **[!UICONTROL Authentication]**:

   ![](assets/webhook-authentication.png)

   * **Ingen autentisering** - Inga autentiseringshuvuden läggs till.
   * **JWT-autentisering** - Ange nödvändig information om slutpunkten kräver JWT-autentisering.

1. I avsnittet **[!UICONTROL Header Parameters]** konfigurerar du ytterligare anpassade rubriker som ska skickas med varje webkrok-begäran.

   ![](assets/webhook-header.png)

1. Klicka på **[!UICONTROL Submit]** för att spara konfigurationen.

>[!NOTE]
>
>Du kan redigera en webkrok när du vill. Om du vill göra det öppnar du det från lagret och klickar sedan på knappen **[!UICONTROL Edit]**.

## Webkroks nyttolaststruktur

Efter en meddelandekörning skickar **[!DNL Journey Optimizer]** följande nyttolast till den konfigurerade slutpunkten.

```
{
  "requestId": "8NoByJneShCdCGRnrGS1t1m3CdA73dhR",
  "imsOrg": "myImsOrg",
  "sandbox": {
    "id": "068abf40-575e-11ea-8512-9b1bfdb82603",
    "name": "prod"
  },
  "channel": "email",
  "eventType": "message.feedback",
  "messageExecution": {
    "messageExecutionID": "HUMA-26362805",
    "messageType": "transactional",
    "campaignID": "16f24a15-7e21-477c-848a-d5695ca7f137",
    "campaignVersionID": "2ca10c10-56dd-4505-87cd-fa5da84e7a5d"
  },
  "messageDeliveryFeedback": {
    "feedbackStatus": {
      "value": "bounce"
    },
    "offers": null,
    "messageExclusion": null,
    "messageFailure": {
      "category": "sync",
      "type": "Ignored",
      "code": "25",
      "reason": "Admin Failure"
    },
    "retryCount": 0
  },
  "identityMap": {
    "email": [
      {
        "id": "john.doe@luma.com",
        "primary": true
      }
    ]
  }
}
```

Webbhoven kan fånga följande händelser:

* Skickat
* Levererat
* Studsa (se exemplet ovan)
* Fel

Varje inkommande begäran innehåller också ett unikt requestId som skickas tillbaka till webkroken.

## Nästa steg {#next}

När en webkrok för feedback har skapats kan du aktivera den när du konfigurerar en **transaktionell API-utlöst kampanj**-målgrupp. Läs mer i det här avsnittet: [Aktivera webhooks](../campaigns/api-triggered-campaign-audience.md#webhook)
