---
solution: Journey Optimizer
product: journey optimizer
title: API för begränsning
description: Lär dig hur du arbetar med API:t för begränsning
feature: Journeys, API
role: Developer
level: Beginner
keywords: extern, API, optimerare, capping
exl-id: b837145b-1727-43c0-a0e2-bf0e8a35347c
source-git-commit: b495462aed9a67ff25c2563288bb2ca57e9b7db7
workflow-type: tm+mt
source-wordcount: '1024'
ht-degree: 48%

---

# Arbeta med API:t för begränsning

API:t för begränsning hjälper dig att skapa, konfigurera och övervaka dina begränsningskonfigurationer för att begränsa antalet händelser som skickas per sekund.

Det här avsnittet innehåller global information om hur du arbetar med API:t. En detaljerad API-beskrivning finns i [dokumentationen för Adobe Journey Optimizer API](https://developer.adobe.com/journey-optimizer-apis/){target="_blank"}.

## Måste läsas

* **En konfiguration per organisation:** Endast en konfiguration tillåts för närvarande per organisation. En konfiguration måste definieras i en produktionssandlåda (anges via `x-sandbox-name` i rubrikerna).
* **Program på organisationsnivå:** En konfiguration används på organisationsnivå.
* **Hantering av API-begränsning:** När gränsen som anges i API:t nås köas ytterligare händelser i upp till 6 timmar. Detta värde kan inte ändras.
* **`maxHttpConnections`-parameter:** Parametern `maxHttpConnections` är en valfri parameter som bara är tillgänglig i API:t för att du ska kunna begränsa antalet anslutningar som Journey Optimizer öppnar till det externa systemet. [Lär dig hur du arbetar med API:t för tak](../configuration/capping.md)

  Om du vill begränsa antalet anslutningar men även begränsa dessa externa anrop kan du konfigurera två konfigurationer, en begränsning och en begränsning, på samma slutpunkt. Båda konfigurationerna kan finnas samtidigt för en slutpunkt. Om du vill ange maxHttpConnections för en begränsad slutpunkt använder du API:t för begränsning och API:t för begränsning för att ange maxHttpConnections. När du anropar API:t för begränsning kan du ange ett tröskelvärde för begränsning till något högre än tröskelvärdet, så att reglerna för begränsning aldrig kommer att börja gälla.

## Beskrivningar av begränsnings-API och Postman-samling {#description}

I tabellen nedan visas tillgängliga kommandon för begränsnings-API:t. Detaljerad information, inklusive frågeexempel, parametrar och svarsformat, finns i [Adobe Journey Optimizer API:s dokumentation](https://developer.adobe.com/journey-optimizer-apis/references/journeys-throttling/).

| Metod | Sökväg | Beskrivning |
|---|---|---|
| [!DNL POST] | list/throttlingConfigs | Hämta en lista över begränsningskonfigurationer |
| [!DNL POST] | /throttlingConfigs | Skapa en begränsningskonfiguration |
| [!DNL POST] | /throttlingConfigs/`{uid}`/deploy | Driftsätt en begränsningskonfiguration |
| [!DNL POST] | /throttlingConfigs/`{uid}`/undeploy | Avbryta driftsättning för en begränsningskonfiguration |
| [!DNL POST] | /throttlingConfigs/`{uid}`/canDeploy | Kontrollera om en begränsningskonfiguration kan driftsättas eller inte |
| [!DNL PUT] | /throttlingConfigs/`{uid}` | Uppdatera en begränsningskonfiguration |
| [!DNL GET] | /throttlingConfigs/`{uid}` | Hämta en begränsningskonfiguration |
| [!DNL DELETE] | /throttlingConfigs/`{uid}` | Radera en begränsningskonfiguration |

Dessutom finns en Postman-samling [här](https://github.com/AdobeDocs/JourneyAPI/blob/master/postman-collections/Journeys_Throttling-API_postman-collection.json){target="_blank"} som kan hjälpa dig med testkonfigurationen.

Den här samlingen har konfigurerats för att dela Postman Variable-samlingen som genereras via **[Adobe I/O Console’s Integrations](https://console.adobe.io/integrations) > Testa > Hämta för Postman**, som genererar en Postman-miljöfil med de valda integreringsvärdena.

När du hämtat och laddat upp till Postman måste du lägga till tre variabler: `{JO_HOST}`,`{BASE_PATH}` och `{SANDBOX_NAME}`.

* `{JO_HOST}` : [!DNL Journey Optimizer] Gateway-URL.
* `{BASE_PATH}` : startpunkt för API.
* `{SANDBOX_NAME}`: sidhuvudet **x-sandbox-name** (till exempel ”produktion”) som motsvarar namnet på sandlådan där API-åtgärderna utförs. Se [översikten över sandlådor](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=sv){target="_blank"} för mer information.

## Begränsningskonfiguration {#configuration}

Här är strukturen för en begränsningskonfiguration. Attributen **name** och **description** är valfria.

```json
{
    "name": "<given name - free text>",
    "description": "<given description - free text>"
    "urlPattern": "<endpoint URL - wildcards are allowed>",
    "methods": [ "<HTTP method such as GET, POST, PUT>" ],
    "maxThroughput": <max call throughput>
}
```

Exempel:

```json
{
  "name": "throttling-config-external",
  "description": "example of throttling config for an external endpoint",
  "urlPattern": "https://api.example.org/data/2.5/*",
  "methods": ["POST", "PUT"],
  "maxThroughput": 4000
}
```

>[!IMPORTANT]
>
>Konfigurationen är bara aktiv efter anrop av slutpunkten **deploy**.

## Fel

När en konfiguration skapas eller uppdateras validerar processen den angivna konfigurationen och returnerar den valideringsstatus som identifieras av dess unika ID, antingen:

```json
"ok" or "error"
```

>[!IMPORTANT]
>
>Attributen **maxThroughput**, **urlPattern** och **methods** är obligatoriska.
>
>Värdet **maxThroughput** måste vara i intervallet 200–5 000.

Följande fel kan uppstå när du skapar, raderar eller distribuerar en begränsningskonfiguration:

* **ERR_THROTTLING_CONFIG_100**: begränsningskonfiguration: `<mandatory attribute>` obligatoriskt
* **ERR_THROTTLING_CONFIG_101**: begränsningskonfiguration: maxThroughput krävs och måste vara större än eller lika med 200 och mindre än eller lika med 5 000
* **ERR_THROTTLING_CONFIG_104**: begränsningskonfiguration: felformat URL-mönster
* **ERR_THROTTLING_CONFIG_105**: begränsningskonfiguration: jokertecken tillåts inte i värddelen av URL-mönstret
* **ERR_THROTTLING_CONFIG_106**: begränsningskonfiguration: ogiltig nyttolast
* **THROTTLING_CONFIG_DELETE_FORBIDDEN_ERROR: 1456**, ”Det gick inte att radera en driftsatt begränsningskonfiguration. Avbryt driftsättning innan den tas bort”
* **THROTTLING_CONFIG_DELETE_ERROR: 1457**, ”Det gick inte att radera begränsningskonfigurationen: ett oväntat fel inträffade”
* **THROTTLING_CONFIG_DEPLOY_ERROR: 1458**, ”Det gick inte att driftsätta begränsningskonfigurationen: ett oväntat fel inträffade”
* **THROTTLING_CONFIG_UNDEPLOY_ERROR: 1459**, ”Det gick inte att avbryta driftsättningen av begränsningskonfigurationen: ett oväntat fel inträffade”
* **THROTTLING_CONFIG_GET_ERROR: 1460**, ”Det gick inte att hämta begränsningskonfigurationen: ett oväntat fel inträffade”
* **THROTTLING_CONFIG_UPDATE_NOT_ACTIVE_ERROR: 1461**, ”Det gick inte att uppdatera begränsningskonfigurationen: körningsversionen är inte aktiv”
* **THROTTLING_CONFIG_UPDATE_ERROR: 1462**, ”Det gick inte att uppdatera begränsningskonfigurationen: ett oväntat fel inträffade”
* **THROTTLING_CONFIG_NON_PROD_SANDBOX_ERROR: 1463**, ”Åtgärden tillåts inte för begränsningskonfiguration: sandlåda ej för produktion”
* **THROTTLING_CONFIG_CREATE_ERROR: 1464**, ”Det gick inte att skapa begränsningskonfigurationen: ett oväntat fel inträffade”
* **THROTTLING_CONFIG_CREATE_LIMIT_ERROR: 1465**, ”Det gick inte att skapa begränsningskonfigurationen: endast en konfiguration tillåts per organisation”
* **THROTTLING_CONFIG_ALREADY_DEPLOYED_ERROR: 14466**, ”Det gick inte att driftsätta begränsningskonfigurationen: den är redan driftsatt”
* **THROTTLING_CONFIG_NOT_FOUND_ERROR: 14467**, ”begränsningskonfigurationen hittades inte”
* **THROTTLING_CONFIG_NOT_DEPLOYED_ERROR: 14468**, ”Det gick inte att avbryta driftsättningen av begränsningskonfigurationen: den är inte ännu driftsatt”

**Exempel på fel**

När du försöker skapa en konfiguration i en sandlåda som är ej för produktion:

```json
{
    "status": 400,
    "error": "{\"code\":1463,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Operation not allowed on throttling config: non prod sandbox\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:384\",\"schema\":\"throttlingConfigs$ui-tests\"}",
    "requestId": "5sgnAYXs8mpswwjAFEIaAU2faQYbtyHc"
}
```

Om den angivna sandlådan inte finns:

```json
{
    "status": 500,
    "error": "{\"code\":4000,\"family\":\"INTERNAL_ERROR\",\"message\":\"INTERNAL ERROR\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.common.exceptions.ApiErrorException:43\"}",
    "requestId": "04ZJ4e5ki4bYs3lfO17a7hovRGewjvdK"
}
```

När du försöker skapa en annan konfiguration:

```json
{
    "status": 400,
    "error": "{\"code\":1465,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Can't create throttling config: only one config allowed per org\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:108\",\"schema\":\"throttlingConfigs$prod\"}",
    "requestId": "A7ezT8JhOQT4WIAf1Fv7K2wCDA8281qM"
}
```

## Konfigurationens livscykel på körningsnivå {#config}

När en konfiguration inte driftsätts markeras den som inaktiv på körningsnivå och väntande händelser fortsätter bearbetas under 24 timmar. Den raderas sedan i körningstjänsten.

När driftsättningen av en konfiguration har avbrutits är det möjligt att uppdatera och driftsätta konfigurationen igen. Detta skapar en ny körningskonfiguration som beaktas i körandet av kommande åtgärder.

När du uppdaterar en konfiguration som redan har driftsatts beaktas de nya värdena omedelbart. De underliggande systemresurserna anpassas automatiskt. Detta är optimalt jämfört med att avbryta driftsättningen och sedan driftsätta konfigurationen igen.

## Exempel på svar {#responses}

**Skapa – POST**

```json
{
    "canDeploy": {
        "validationStatus": "ok"
    },
    "createdElement": {
        "name": "throttling-config-external",
        "description": "example of throttling config for an external endpoint",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "PUT",
            "POST"
        ],
        "maxThroughput": 4000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T10:48:16.099647Z"
        },
        "state": "created",
        "authoringFormatVersion": "1.0"
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "created"
}
```

**Uppdatera – PUT**

```json
{
    "updatedElement": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "updated",
    "canDeploy": {
        "validationStatus": "ok"
    }
}
```

**Läs (efter uppdatering) – GET**

```json
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    }
}
```

**Läs (efter driftsättning) – GET**

```json
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "authoringFormatVersion": "1.0",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "version": "1.0",
        "state": "deployed",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z",
            "lastDeployedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastDeployedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastDeployedAt": "2023-03-22T11:46:07.532648Z"
        },
        "hasBeenDeployed": true
    }
}
```

## Användningsfall {#uc}

I det här avsnittet visas viktiga användningsfall för hantering av begränsningskonfigurationer i [!DNL Journey Optimizer] och associerade API-kommandon som krävs för att implementera användningsexemplet.

Information om varje API-kommando finns i [API-beskrivningen och Postman-samlingen](#description).

+++Skapa och distribuera en ny begränsningskonfiguration

API-anrop som ska användas:

1. **`list`** - Hämtar befintliga konfigurationer.
1. **`create`** - Skapar en ny konfiguration.
1. **`candeploy`** - Kontrollerar om konfigurationen kan distribueras.
1. **`deploy`** - Distribuerar konfigurationen.

+++

+++Uppdatera och distribuera en begränsningskonfiguration (ännu inte distribuerad)

API-anrop som ska användas:

1. **`list`** - Hämtar befintliga konfigurationer.
1. **`get`** - Hämtar information om en viss konfiguration.
1. **`update`** - Ändrar konfigurationen.
1. **`candeploy`** - Kontrollerar distributionsbehörighet.
1. **`deploy`** - Distribuerar konfigurationen.

+++

+++Avdistribuera och ta bort en distribuerad begränsningskonfiguration

API-anrop som ska användas:

1. **`list`** - Hämtar befintliga konfigurationer.
1. **`undeploy`** - Avdistribuerar konfigurationen.
1. **`delete`** - Tar bort konfigurationen.

+++

+++Ta bort en distribuerad begränsningskonfiguration

I endast ett API-anrop kan du avdistribuera och ta bort konfigurationen med hjälp av parametern `forceDelete`.

API-anrop som ska användas:

1. **`list`** - Hämtar befintliga konfigurationer.
1. **`delete`(med parametern `forceDelete`)** - Tvingar borttagning av en distribuerad konfiguration i ett enda steg.

+++

+++Uppdatera en begränsningskonfiguration som redan har distribuerats

>[!NOTE]
>
>Du behöver inte avbryta driftsättningen av konfigurationen innan du uppdaterar

API-anrop som ska användas:

1. **`list`** - Hämtar befintliga konfigurationer.
1. **`get`** - Hämtar information om en viss konfiguration.
1. **`update`** - Ändrar konfigurationen.

+++
