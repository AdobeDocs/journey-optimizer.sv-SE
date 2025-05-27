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
source-git-commit: bf4044bc23b0e7c0ef74e5b612d93cb45ec20242
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 1%

---

# Integrera med Adobe Campaign v7/v8 {#integrating-with-adobe-campaign-v7-v8}

>[!CONTEXTUALHELP]
>id="ajo_journey_action_acc"
>title="Adobe Campaign v7/v8-åtgärder"
>abstract="Den här integreringen är tillgänglig för Adobe Campaign v7 och v8. Det gör att du kan skicka e-post, push-meddelanden och SMS med Adobe Campaign Transactional Messaging-funktioner. Anslutningen mellan Journey Optimizer- och Campaign-instanserna konfigureras av Adobe vid etableringstidpunkten."

Om du har Adobe Campaign Classic v7 eller Campaign v8 finns det en specifik anpassad åtgärd att utföra på dina resor för att integrera Adobe Journey Optimizer och Adobe Campaign. Tack vare den här integreringen kan du skicka e-post, push-meddelanden och SMS med Adobe Campaign Transactional Messaging-funktioner. Läs mer i det här [heltäckande användningsexemplet](../building-journeys/ajo-ac.md).

För varje konfigurerad åtgärd finns en [kampanjåtgärdsaktivitet](../building-journeys/using-adobe-campaign-v7-v8.md) tillgänglig på paletten Resursdesigner.

## Aktivering {#access}

På begäran konfigureras anslutningen mellan Journey Optimizer- och Adobe Campaign-miljöerna av Adobe vid etableringstidpunkten. Om du inte har begärt att få ansluta vid etableringstidpunkten kontaktar du Adobe Journey Optimizer support för att begära aktiveringen. Du måste ange följande information:

>[!BEGINTABS]

>[!TAB För Adobe Journey Optimizer]

* Organisations-ID (Adobe OrgID)

* Namn på sandlåda

>[!TAB För Adobe Campaign]

* URL för kampanjserver

* URL för realtidsserver

* Campaign-version

>[!ENDTABS]


## Viktiga anteckningar {#important-notes}

* Det finns ingen begränsning för meddelanden. Systemet begränsar antalet meddelanden som kan skickas till 4 000 per 5 minuter, baserat på den aktuella Campaign SLA. Därför bör Journey Optimizer endast användas i enstaka fall (enskilda evenemang, inte målgrupper).

* Du måste konfigurera en åtgärd på arbetsytan per mall som du vill använda. Du måste konfigurera en åtgärd i Journey Optimizer för varje mall som du vill använda från Adobe Campaign.

* Vi rekommenderar att du använder en dedikerad Message Center-instans som är värd för den här integreringen för att undvika att påverka andra Campaign-åtgärder som du har påbörjat. Marknadsföringsservern kan vara värd eller lokal. Den version som krävs är 21.1 Release Candidate eller senare.

* Det finns ingen validering av att nyttolasten eller kampanjmeddelandet är korrekt.

* Du kan inte använda en Campaign-åtgärd med en publikkvalificeringshändelse.

## Förhandskrav {#prerequisites}

I Adobe Campaign måste du skapa och publicera ett transaktionsmeddelande och tillhörande händelse. Mer information finns i [Adobe Campaign-dokumentationen](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/real-time/transactional){target="_blank"}.

Du kan skapa din JSON-nyttolast som motsvarar varje meddelande enligt mönstret nedan. Du klistrar sedan in denna nyttolast när du konfigurerar åtgärden i Journey Optimizer (se nedan).

Här är ett exempel:

```JSON
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
* **ctx**: variabel baserad på den personalisering du har i meddelandet

## Konfigurera åtgärden {#configure-action}

I Journey Optimizer måste du konfigurera en åtgärd per transaktionsmeddelande. Följ de här stegen:

1. Skapa en ny åtgärd. [Läs mer om anpassade åtgärder](../action/action.md).
1. Ange namn och beskrivning.
1. I fältet **Åtgärdstyp** väljer du **Adobe Campaign Classic**.
1. Klicka i fältet **Nyttolast** och klistra in ett exempel på JSON-nyttolasten som motsvarar Campaign-meddelandet. Kontakta Adobe för att få denna nyttolast.
1. Justera de olika fälten så att de blir statiska eller variabla beroende på om du vill mappa dem på arbetsytan på resan. Vissa fält, till exempel kanalparametrar för e-postadresser och anpassningsfält (ctx), kan behöva definieras som variabler för mappning i samband med resan.
1. Klicka på **Spara**.

![](assets/accintegration1.png)