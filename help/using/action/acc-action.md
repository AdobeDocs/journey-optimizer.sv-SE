---
solution: Journey Optimizer
product: journey optimizer
title: Integrera med Adobe Campaign v7/v8
description: Lär dig integrera Journey Optimizer med Adobe Campaign v7/v8
feature: Actions
topic: Administration
role: Admin,Developer
level: Intermediate
keywords: kampanj, acc, integration
exl-id: 109ba212-f04b-425f-9447-708c8e0b3f51
source-git-commit: 72bd00dedb943604b2fa85f7173cd967c3cbe5c4
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 0%

---

# Integrera med Adobe Campaign v7/v8 {#integrating-with-adobe-campaign-classic}

>[!CONTEXTUALHELP]
>id="ajo_journey_action_acc"
>title="Adobe Campaign v7/v8-åtgärder"
>abstract="Den här integreringen är tillgänglig för Adobe Campaign Classic v7 och v8. Det gör att du kan skicka e-post, push-meddelanden och SMS med Adobe Campaign Transactional Messaging-funktioner. Anslutningen mellan Journey Optimizer- och Campaign-instanserna konfigureras av Adobe vid etableringstidpunkten."

Den här integreringen är tillgänglig för Adobe Campaign Classic v7 från och med version 7.1 och Adobe Campaign v8. Det gör att du kan skicka e-post, push-meddelanden och SMS med Adobe Campaign Transactional Messaging-funktioner.

Anslutningen mellan Journey Optimizer- och Campaign-instanserna konfigureras av Adobe vid etableringstidpunkten.

Ett heltäckande exempel på användning presenteras i detta [section](../building-journeys/ajo-ac.md).

För varje konfigurerad åtgärd finns en åtgärdsaktivitet tillgänglig på paletten Resursdesigner. Se detta [section](../building-journeys/using-adobe-campaign-classic.md).

## Viktiga anteckningar {#important-notes}

* Det finns ingen begränsning för meddelanden. Systemet begränsar antalet meddelanden som kan skickas till 4 000 per 5 minuter, baserat på aktuellt Campaign-SLA. Därför bör Journey Optimizer endast användas i enstaka fall (enskilda evenemang, inte målgrupper).

* Du måste konfigurera en åtgärd på arbetsytan per mall som du vill använda. Du måste konfigurera en åtgärd i Journey Optimizer för varje mall som du vill använda från Adobe Campaign.

* Vi rekommenderar att du använder en dedikerad Message Center-instans som är värd för den här integreringen för att undvika att påverka andra Campaign-åtgärder som du har påbörjat. Marknadsföringsservern kan vara värd eller lokal. Den version som krävs är 21.1 Release Candidate eller senare.

* Det finns ingen validering av att nyttolasten eller kampanjmeddelandet är korrekt.

* Du kan inte använda en Campaign-åtgärd med en publikkvalificeringshändelse.

## Förutsättningar {#prerequisites}

I Campaign måste du skapa och publicera ett transaktionsmeddelande och tillhörande händelse. Se [Adobe Campaign-dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging){target="_blank"}.

Du kan skapa din JSON-nyttolast som motsvarar varje meddelande enligt mönstret nedan. Du klistrar sedan in den här nyttolasten när du konfigurerar åtgärden i Journey Optimizer (se nedan)

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

* **kanal**: den kanal som är definierad för er transaktionsmall för Campaign
* **eventType**: det interna namnet på Campaign-händelsen
* **ctx**: variabeln baserat på den personalisering du har i ditt meddelande.

## Konfigurera åtgärden {#configure-action}

I Journey Optimizer måste du konfigurera en åtgärd per transaktionsmeddelande. Följ de här stegen:

1. Skapa en ny åtgärd. Se detta [section](../action/action.md).
1. Ange ett namn och en beskrivning.
1. I **Åtgärdstyp** fält, markera **Adobe Campaign Classic**.
1. Klicka på **Nyttolast** och klistra in ett exempel på JSON-nyttolasten som motsvarar Campaign-meddelandet. Kontakta Adobe för att få denna nyttolast.
1. Justera de olika fälten så att de blir statiska eller variabla beroende på om du vill mappa dem på arbetsytan på resan. Vissa fält, till exempel kanalparametrar för e-postadresser och anpassningsfält (ctx), kan behöva definieras som variabler för mappning i samband med resan.
1. Klicka **Spara**.

![](assets/accintegration1.png)
