---
solution: Journey Optimizer
product: journey optimizer
title: API för reglering
description: Lär dig hur du arbetar med API:t för att hämta innehåll
feature: Journeys, API
role: Developer
level: Beginner
keywords: extern, API, optimerare, capping
exl-id: 377b2659-d26a-47c2-8967-28870bddf5c5
source-git-commit: 0b0badfa09a24d451671f5bae9ddc437c6db2911
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 6%

---

# Arbeta med API:t för tak {#work}

Med API:t för att hämta innehåll kan du skapa, konfigurera och övervaka dina appkonfigurationer.

Det här avsnittet innehåller global information om hur du arbetar med API:t. En detaljerad API-beskrivning finns i [dokumentationen för Adobe Journey Optimizer API](https://developer.adobe.com/journey-optimizer-apis/){target="_blank"}.

## Beskrivning av API-begränsning och Postman-samling {#description}

Tabellen nedan visar tillgängliga kommandon för API:t för appning. Detaljerad information, inklusive frågeexempel, parametrar och svarsformat, finns i [Adobe Journey Optimizer API:s dokumentation](https://developer.adobe.com/journey-optimizer-apis/references/journeys-throttling/){target="_blank"}.

| Metod | Sökväg | Beskrivning |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | Hämta en lista över konfigurationer för slutpunktsbegränsning |
| [!DNL POST] | /endpointConfigs | Skapa en konfiguration för begränsning av slutpunkter |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | Distribuera en slutpunktskonfiguration |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy | Avdistribuera en slutpunktskonfiguration |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | Kontrollera om en slutpunktskonfiguration kan distribueras eller inte |
| [!DNL PUT] | /endpointConfigs/`{uid}` | Uppdatera en konfiguration för begränsning av slutpunkter |
| [!DNL GET] | /endpointConfigs/`{uid}` | Hämta en konfiguration för slutpunktsbegränsning |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | Ta bort en ändpunktskonfiguration |

När en konfiguration skapas eller uppdateras utförs en kontroll automatiskt för att garantera nyttolastens syntax och integritet.
Om det uppstår problem returneras en varning eller felmeddelanden som hjälper dig att korrigera konfigurationen.

Dessutom finns en Postman-samling [här](https://github.com/AdobeDocs/JourneyAPI/blob/master/postman-collections/Journeys_Capping-API_postman-collection.json) som kan hjälpa dig med testkonfigurationen.

Den här samlingen har konfigurerats för att dela Postman Variable-samlingen som genereras via __[Adobe I/O Console’s Integrations](https://console.adobe.io/integrations) > Testa > Hämta för Postman__, som genererar en Postman-miljöfil med de valda integreringsvärdena.

När du hämtat och laddat upp till Postman måste du lägga till tre variabler: `{JO_HOST}`,`{BASE_PATH}` och `{SANDBOX_NAME}`.

* `{JO_HOST}` : [!DNL Journey Optimizer] Gateway-URL.
* `{BASE_PATH}` : startpunkt för API.
* `{SANDBOX_NAME}`: sidhuvudet **x-sandbox-name** (till exempel ”produktion”) som motsvarar namnet på sandlådan där API-åtgärderna utförs. Se [översikten över sandlådor](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=sv){target="_blank"} för mer information.

## Konfiguration av slutpunkt

Här är den grundläggande strukturen för en slutpunktskonfiguration:

```json
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint (optional)>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

>[!IMPORTANT]
>
>Parametern **maxHttpConnections** är valfri. Du kan begränsa antalet anslutningar som Journey Optimizer öppnar till det externa systemet.
>
>Det högsta värdet som kan anges är 400. Om inget anges kan systemet öppna upp till flera tusen anslutningar beroende på systemets dynamiska skalning.
>
>Om inget `maxHttpConnections`-värde har angetts när takkonfigurationen distribueras läggs `maxHttpConnections = -1` till i den distribuerade konfigurationen och Journey Optimizer använder standardsystemvärdet.

Exempel:

```json
{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "rating": {
        "maxCallsCount": 500,
        "periodInMs": 1000
      }
    }
  }
}
```

>[!IMPORTANT]
>
>Konfigurationen är bara aktiv efter anrop av slutpunkten **deploy**.

## Varningar och fel

När en **canDeploy** -metod anropas validerar processen konfigurationen och returnerar den verifieringsstatus som identifieras av dess unika ID, antingen:

```json
"ok" or "error"
```

Möjliga fel är:

* **ERR_ENDPOINTCONFIG_100**: Konfiguration för begränsning: URL saknas eller är ogiltig
* **ERR_ENDPOINTCONFIG_101**: capping-konfiguration: felaktig URL
* **ERR_ENDPOINTCONFIG_102**: capping config: felaktig url: jokertecken i url tillåts inte i värd:port
* **ERR_ENDPOINTCONFIG_103**: capping config: HTTP-metoder saknas
* **ERR_ENDPOINTCONFIG_104**: konfiguration för begränsning: ingen anropsklassificering har definierats
* **ERR_ENDPOINTCONFIG_107**: capping-konfig: ogiltigt max antal anrop (maxCallCount)
* **ERR_ENDPOINTCONFIG_108**: capping config: ogiltigt antal anrop (periodInms)
* **ERR_ENDPOINTCONFIG_111**: det går inte att skapa slutpunktskonfigurationen: nyttolasten är ogiltig
* **ERR_ENDPOINTCONFIG_112**: Det går inte att skapa slutpunktskonfigurationen: en JSON-nyttolast förväntas
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: ogiltigt tjänstnamn `<!--<given value>-->`: måste vara dataSource eller action

Den potentiella varningen är:

**ERR_ENDPOINTCONFIG_106**: capping config: max HTTP connections not defined: no limitation as default

## Användningsfall

I det här avsnittet visas viktiga användningsfall för hantering av appningskonfigurationer i [!DNL Journey Optimizer] och associerade API-kommandon som krävs för att implementera användningsfallet.

Information om varje API-kommando finns i [API-beskrivningen och Postman-samlingen](#description).

+++Skapa och distribuera en ny takkonfiguration

API-anrop som ska användas:

1. **`list`** - Hämtar befintliga konfigurationer.
1. **`create`** - Skapar en ny konfiguration.
1. **`candeploy`** - Kontrollerar om konfigurationen kan distribueras.
1. **`deploy`** - Distribuerar konfigurationen.

+++

+++Uppdatera och distribuera en capping-konfiguration (inte distribuerad än)

API-anrop som ska användas:

1. **`list`** - Hämtar befintliga konfigurationer.
1. **`get`** - Hämtar information om en viss konfiguration.
1. **`update`** - Ändrar konfigurationen.
1. **`candeploy`** - Kontrollerar distributionsbehörighet.
1. **`deploy`** - Distribuerar konfigurationen.

+++

+++Avdistribuera och ta bort en distribuerad capping-konfiguration

API-anrop som ska användas:

1. **`list`** - Hämtar befintliga konfigurationer.
1. **`undeploy`** - Avdistribuerar konfigurationen.
1. **`delete`** - Tar bort konfigurationen.

+++

+++Ta bort en distribuerad capping-konfiguration i ett enda steg

I endast ett API-anrop kan du avdistribuera och ta bort konfigurationen med hjälp av parametern `forceDelete`.

API-anrop som ska användas:

1. **`list`** - Hämtar befintliga konfigurationer.
1. **`delete`(med parametern `forceDelete`)** - Tvingar borttagning av en distribuerad konfiguration i ett enda steg.

+++

+++Uppdatera en takkonfiguration som redan distribuerats

>[!NOTE]
>
>En omdistribution krävs efter uppdatering av en redan distribuerad konfiguration.

API-anrop som ska användas:

1. **`list`** - Hämtar befintliga konfigurationer.
1. **`get`** - Hämtar information om en viss konfiguration.
1. **`update`** - Ändrar konfigurationen.
1. **`undeploy`** - Avdistribuerar konfigurationen innan ändringarna tillämpas.
1. **`candeploy`** - Kontrollerar distributionsbehörighet.
1. **`deploy`** - Distribuerar den uppdaterade konfigurationen.

+++
