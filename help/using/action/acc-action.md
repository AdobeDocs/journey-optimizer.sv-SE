---
title: Integrera med Adobe Campaign v7/v8
description: Lär dig integrera med Adobe Campaign v7/v8
feature: Instruktioner
topic: Administrering
role: Administrator
level: Intermediate
source-git-commit: b07970ff11f1ba7c4e6db30dc2eca1252a579ca4
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 1%

---

# Integrera med Adobe Campaign v7/v8 {#integrating-with-adobe-campaign-classic}

Den här integreringen är tillgänglig för Adobe Campaign Classic v7 från och med version 21.1 och Adobe Campaign v8. Det gör att du kan skicka e-post, push-meddelanden och SMS med Adobe Campaign Transactional Messaging-funktioner.

Anslutningen mellan Journey Optimizer- och Campaign-instanserna konfigureras av Adobe vid etableringstidpunkten.

Det finns ett användningsexempel från början till slut i det här [avsnittet](../building-journeys/campaign-classic-use-case.md).

För varje konfigurerad åtgärd finns en åtgärdsaktivitet tillgänglig på paletten Resursdesigner. Se det här [avsnittet](../building-journeys/using-adobe-campaign-classic.md).

## Viktiga anteckningar

* Det finns ingen begränsning för meddelanden. Vi har som gräns antalet meddelanden som kan skickas till 50 000/timme baserat på vårt aktuella Campaign-SLA. Därför bör Journey Optimizer endast användas i enstaka fall (enskilda händelser, inte segment).

* Du måste konfigurera en åtgärd på arbetsytan per mall som du vill använda. Du måste konfigurera en åtgärd i Journey Optimizer för varje mall som du vill använda från Adobe Campaign.

* Vi rekommenderar att du använder en dedikerad Message Center-instans som är värd för den här integreringen för att undvika att påverka andra Campaign-åtgärder som du har påbörjat. Marknadsföringsservern kan vara värd eller lokal. Den version som krävs är 21.1 Release Candidate eller senare.

* Det finns ingen validering av att nyttolasten eller kampanjmeddelandet är korrekt.

* Du kan inte använda en Campaign-åtgärd med en segmentkvalificeringshändelse.

## Förutsättningar

I Campaign måste du skapa och publicera ett transaktionsmeddelande och tillhörande händelse. Läs [Adobe Campaign-dokumentationen](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging){target=&quot;_blank&quot;}.

Du kan skapa din JSON-nyttolast som motsvarar varje meddelande enligt mönstret nedan. Du klistrar sedan in den här nyttolasten när du konfigurerar åtgärden i Journey Orchestration (se nedan)

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

## Konfigurera åtgärden

I Journey Optimizer måste du konfigurera en åtgärd per transaktionsmeddelande. Följ de här stegen:

1. Skapa en ny åtgärd. Se det här [avsnittet](../action/action.md).
1. Ange ett namn och en beskrivning.
1. I fältet **Åtgärdstyp** väljer du **Adobe Campaign Classic**.
1. Klicka i fältet **Nyttolast** och klistra in ett exempel på JSON-nyttolasten som motsvarar Campaign-meddelandet. Kontakta Adobe för att få denna nyttolast.
1. Justera de olika fälten så att de blir statiska eller variabla beroende på om du vill mappa dem på arbetsytan på resan. Vissa fält, till exempel kanalparametrar för e-postadresser och anpassningsfält (ctx), kan behöva definieras som variabler för mappning i samband med resan.
1. Klicka på **Spara**.

![](../assets/accintegration1.png)


