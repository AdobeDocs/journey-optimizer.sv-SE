---
title: Ytterligare steg för att skicka händelser till en resa
description: Lär dig ytterligare steg för att skicka händelser till en resa
feature: Events
topic: Administration
role: Admin
level: Intermediate
exl-id: e0144151-6c54-4656-9650-b544d8e7be16
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 4%

---

# Ytterligare steg för att skicka händelser {#additional-steps-to-send-events}

Så här konfigurerar du händelser som ska skickas till **[!UICONTROL Streaming Ingestion APIs]** och ska användas i [!DNL Journey Optimizer]måste du följa dessa steg:

1. Hämta URL:en för inlopp från Adobe Experience Platform API:er. Läs mer i [Översikt över API:er för direktuppspelning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=sv){target=&quot;_blank&quot;}.
1. Kopiera nyttolasten från nyttolastförhandsvisningen i **[!UICONTROL Event]** -menyn. Läs mer i [den här sidan](../event/about-creating.md#define-the-payload-fields).

Sedan måste du konfigurera det datasystem som överför händelser till API:er för direktuppspelning av inmatning med den nyttolast som du kopierade:

1. Konfigurera ett POST-API-anrop till API:n för direktuppspelning (kallas för ett inlopp).
1. Använd nyttolasten som du kopierade från [!DNL Journey Optimizer] i brödtexten (&quot;dataavsnittet&quot;) för API-anropet till API:er för Streaming Ingmit. Se nedan för ett exempel
1. Bestäm var alla variabler som finns i nyttolasten ska hämtas. Exempel: om händelsen ska förmedla adressen, kommer nyttolasten som klistras in att visa&quot;adress&quot;: &quot;string&quot;. &quot;string&quot; ska ersättas med variabeln som automatiskt fyller i rätt värde, e-postadressen till den person som meddelandet ska skickas till. Observera att i nyttolastförhandsvisningen i **[!UICONTROL Header]** fyller vi automatiskt i många värden som förväntas underlätta arbetet.
1. Välj &quot;application/json&quot; som en texttyp.
1. Skicka ditt IMS-organisations-ID i huvudet med tangenten &quot;x-gw-ims-org-id&quot;. Använd ditt IMS-organisations-ID (&quot;XXX@AdobeOrg&quot;) för värdet.

Här är ett exempel på en API-händelse för direktuppspelning:

```
{
    "header": {
        "msgType": "xdmEntityCreate",
        "msgId": "c25585b9-252e-431d-b562-e73da70c04e7",
        "msgVersion": "1.0",
        "xactionId": "f5995abe-c49d-4848-9577-a7a4fc2996fb",
        "datasetId": "string - required if you want the data to land in a specific dataset - not mandatory",
        "imsOrgId": "XXX@AdobeOrg",
        "schemaRef": {
            "id": "XXX",
            "contentType": "application/vnd.adobe.xed-full+json;version=1"
        },
        "source": {
            "name": "Journeys"
        }
    },
    "body": {
        "xdmMeta": {
            "schemaRef": {
                "id": "XXX",
                "contentType": "application/vnd.adobe.xed-full+json;version=1"
            }
        },
        "xdmEntity": {
            "_instance_name": {
                "person": {
                    "firstName": "string",
                    "lastName": "string",
                    "gender": "string",
                    "birthYear": 10,
                    "emailAddress": "string"
                }
            },
            "identityMap": {
                "Email": [
                {
                    "id": "string"
                    }
                ]
            },
            "_id": "string",
            "timestamp": "2018-05-29T00:00:00.000Z",
            "_experience": {
                "campaign": {
                    "orchestration": {
                    "eventID": "XXX"
                    }
                }
            }
        }
    }
}
```

För att underlätta identifieringen av den plats där delen&quot;data&quot; ska klistras in kan du använda ett JSON-visualiseringsverktyg som [JSON-format](https://jsonformatter.curiousconcept.com){target=&quot;_blank&quot;}.

Information om hur du felsöker API:er för direktuppspelning finns i [Experience Platform dokumentation](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html){target=&quot;_blank&quot;}.