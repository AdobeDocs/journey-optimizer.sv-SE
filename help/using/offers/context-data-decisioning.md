---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: Kontextdata och beslutsbegäranden
description: Lär dig hur du skickar kontextdata i beslutsbegäranden.
badge: label="Äldre" type="Informative"
feature: Decision Management
role: Developer
level: Experienced
exl-id: 45d060ce-0a12-4a6e-a594-ec10cdff8f38
version: Journey Orchestration
source-git-commit: 8732a73118b807eaa7f57cfdad60355b535282ff
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 1%

---

# Kontextdata och beslutsbegäranden {#context-data-decisioning}

>[!TIP]
>
>Beslutsfattandet, [!DNL Adobe Journey Optimizer]s nya beslutsfunktion, är nu tillgängligt via den kodbaserade upplevelsen och e-postkanalerna! [Läs mer](../experience-decisioning/gs-experience-decisioning.md)

I det här avsnittet får du hjälp med att skicka kontextdata i beslutsbegäranden och använda dem i reglerna för behörighet.

>[!BEGINSHADEBOX]

Om du vill gå vidare kan du även utnyttja sammanhanget i **rankningsformler** för att lyfta fram dina erbjudanden. Detaljerade exempel på rankningsformler som utnyttjar kontextdata finns i [det här avsnittet](../offers/ranking/create-ranking-formulas.md#context-data).

>[!ENDSHADEBOX]

## Skicka kontextdata i beslutsbegäranden

Kontextdata i beslutsbegäranden definieras med nyckeln: `xdm:ContextData`.

Kontextdataattribut styrs inte av XDM-schema. Du kan skicka alla kontextdata i JSON som en del av nyttolasten för beslutsbegäran.

Här är ett exempel på en beslutsbegäran med kontextdata (se `xdm:ContextData`):

```
curl --location 'https://platform-stage.adobe.io/data/core/ods/decisions' \
--header 'Accept: application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-response;version=1.0"' \
--header 'Content-Type: application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-request;version=1.0"' \
--header 'Authorization: Bearer eyJhbGciOi....' \
--header 'x-api-key: {{api_key}}' \
--header 'x-gw-ims-org-id: {{ims_org}}' \
--header 'x-sandbox-name: {{sandbox_name}}' \
--header 'x-request-id: {{$guid}}' \
--data-raw '{
    "xdm:propositionRequests": [
        {
            "xdm:activityId": "dps:offer-activity:19978bf95ebfc8fb",
            "xdm:placementId": "dps:offer-placement:199772e1c90d50ac"
        }
    ],
    "xdm:profiles": [
        {
            "xdm:identityMap": {
                "Email": [
                    {
                        "xdm:id": "test@test.com",
                        "primary": true
                    }
                ]
            },
            "xdm:contextData": [
                {
                    "@type": "_xdm.context.additionalParameters;version=1",
                    "xdm:data": {
                        "xdm:channel": "mobile",
                        "xdm:language": "en",
                        "xdm:isThirdParty": true,
                        "xdm:mobileVersion": "3.0.5106",
                        "xdm:mobileVersionMajor": "3",
                        "xdm:mobileVersionMinor": "0",
                        "xdm:mobileVersionPatch": "125",
                        "xdm:deviceType": "iOS",
                        "xdm:features": [
                            "p1000",
                            "p1001"
                        ]
                    }
                }
            ]
        }
    ],
    "xdm:allowDuplicatePropositions": {
        "xdm:acrossActivities": true,
        "xdm:acrossPlacements": true
    },
    "xdm:responseFormat": {
        "xdm:includeContent": true,
        "xdm:includeMetadata": {
            "xdm:activity": [
                "name"
            ],
            "xdm:option": [
                "name"
            ],
            "xdm:placement": [
                "name"
            ]
        }
    }
}'
```

## Använd kontextdata i berättiganderegler

Här följer exempel som illustrerar hur man använder kontextdata som skickats i beslutsbegäranden i regler för behörighet.

* Kan användas om kontextdatafunktionerna innehåller ett visst värde:

  ```
  select contextData from @{_xdm.context.additionalParameters;version=1} where contextData.features AND (select personetic from contextData.features where personetic.contains("123"))
  ```

* Berättigad om kanalen inte är tom och lika med mobilen:

  ```
  select contextData from @{_xdm.context.additionalParameters;version=1} where !contextData.channel.isNull() AND contextData.channel!="" AND contextData.channel="mobile"
  ```
