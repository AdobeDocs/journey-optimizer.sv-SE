---
solution: Journey Optimizer
product: journey optimizer
title: Integrera med Adobe Campaign v7/v8
description: Lär dig integrera Journey Optimizer med Adobe Campaign v7/v8
feature: Journeys, Actions, Custom Actions
topic: Administration
role: Data Engineer, Data Architect, Admin
level: Intermediate
keywords: kampanj, acc, integration
exl-id: 109ba212-f04b-425f-9447-708c8e0b3f51
source-git-commit: cc4ea97f858a212b82ac3b77328e61f59e3bfc27
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 0%

---

# Integrera med Adobe Campaign v7/v8 {#integrating-with-adobe-campaign-v7-v8}

>[!CONTEXTUALHELP]
>id="ajo_journey_action_acc"
>title="Adobe Campaign v7/v8-åtgärder"
>abstract="Den här integreringen är tillgänglig för Adobe Campaign v7 och v8. Det gör att du kan skicka e-post, push-meddelanden och SMS med Adobe Campaign Transactional Messaging-funktioner. Anslutningen mellan Journey Optimizer- och Campaign-instanserna konfigureras av Adobe vid etableringstidpunkten."

Den här integreringen är tillgänglig för Adobe Campaign v7/v8 från och med version 7.1 och Adobe Campaign v8. Det gör att du kan skicka e-post, push-meddelanden och SMS med Adobe Campaign Transactional Messaging-funktioner.

Ett slutanvändarfall visas i det här [avsnittet](../building-journeys/ajo-ac.md).

För varje konfigurerad åtgärd finns en åtgärdsaktivitet tillgänglig på paletten Resursdesigner. Se det här [avsnittet](../building-journeys/using-adobe-campaign-v7-v8.md).

## Åtkomst {#access}

Anslutningen mellan Journey Optimizer- och Campaign-instanserna konfigureras av Adobe vid etableringstidpunkten om det skulle behövas. Om du inte har begärt anslutningen vid etableringstidpunkten kontaktar du Adobe Journey Optimizer support och lämnar följande information för att begära aktiveringen:

Från Adobe Journey Optimizer:

* Organisations-ID (Adobe OrgID)
* Sandbox

Från Adobe Campaign:

* Kampanj-URL
* RT-URL
* Campaign-version

## Viktiga anteckningar {#important-notes}

* Det finns ingen begränsning för meddelanden. Systemet begränsar antalet meddelanden som kan skickas till 4 000 per 5 minuter, baserat på aktuellt Campaign-SLA. Därför bör Journey Optimizer endast användas i enstaka fall (enskilda evenemang, inte målgrupper).

* Du måste konfigurera en åtgärd på arbetsytan per mall som du vill använda. Du måste konfigurera en åtgärd i Journey Optimizer för varje mall som du vill använda från Adobe Campaign.

* Vi rekommenderar att du använder en dedikerad Message Center-instans som är värd för den här integreringen för att undvika att påverka andra Campaign-åtgärder som du har påbörjat. Marknadsföringsservern kan vara värd eller lokal. Den version som krävs är 21.1 Release Candidate eller senare.

* Det finns ingen validering av att nyttolasten eller kampanjmeddelandet är korrekt.

* Du kan inte använda en Campaign-åtgärd med en publikkvalificeringshändelse.

## Förhandskrav {#prerequisites}

I Campaign måste du skapa och publicera ett transaktionsmeddelande och tillhörande händelse. Se [Adobe Campaign-dokumentationen](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=sv-SE#transactional-messaging){target="_blank"}.

Du kan skapa din JSON-nyttolast som motsvarar varje meddelande enligt mönstret nedan. Du klistrar sedan in nyttolasten när du konfigurerar åtgärden i Journey Optimizer (se nedan)

Här är ett exempel:

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "Email address",
    "ctx": {
        "firstName": "First name"
    }
}
```

* **kanal**: kanalen som är definierad för din transaktionsmall för Campaign
* **eventType**: det interna namnet på Campaign-händelsen
* **ctx**: variabel baserad på den personalisering du har i meddelandet.

## Konfigurera åtgärden {#configure-action}

I Journey Optimizer måste du konfigurera en åtgärd per transaktionsmeddelande. Följ de här stegen:

1. Skapa en ny åtgärd. Se det här [avsnittet](../action/action.md).
1. Ange namn och beskrivning.
1. I fältet **Åtgärdstyp** väljer du **Adobe Campaign Classic**.
1. Klicka i fältet **Nyttolast** och klistra in ett exempel på JSON-nyttolasten som motsvarar Campaign-meddelandet. Kontakta Adobe för att få denna nyttolast.
1. Justera de olika fälten så att de blir statiska eller variabla beroende på om du vill mappa dem på arbetsytan på resan. Vissa fält, till exempel kanalparametrar för e-postadresser och anpassningsfält (ctx), kan behöva definieras som variabler för mappning i samband med resan.
1. Klicka på **Spara**.

![](assets/accintegration1.png)