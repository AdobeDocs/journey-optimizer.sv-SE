---
title: Kodbaserade implementeringsexempel
description: På den här sidan visas exempel på implementeringsmetoden för Journey Optimizer kodbaserade funktion
feature: Offers
topic: Content Management
role: User
level: Experienced
hide: true
hidefromtoc: true
badge: label="Beta"
source-git-commit: f271aa457d2f8b7e66e58692b613d80c6e6b3adb
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 2%

---

# Exempel på kodbaserade implementeringsmetoder {#implementation-samples}

>[!BEGINSHADEBOX]

Vad du hittar i den här handboken:

* [Kom igång med kodbaserad kanal](get-started-code-based.md)
* [Kodbaserade förutsättningar](code-based-prerequisites.md)
* **[Kodbaserade implementeringsexempel](code-based-implementation-samples.md)**
* [Skapa kodbaserade upplevelser](create-code-based.md)

>[!ENDSHADEBOX]

Kodbaserad upplevelse stöder alla typer av kundimplementeringar. På den här sidan hittar du exempel för varje implementeringsmetod:

* [Klientsida](#client-side-implementation)
* [Serversidan](#server-side-implementation)
* [Hybrid](#hybrid-implementation)

Du kan också följa [den här länken](https://github.com/adobe/alloy-samples/tree/main/ajo){target="_blank"} för att hitta exempelimplementeringar för olika användningsfall för personalisering och experiment. Kolla in dem och kör dem för att få en bättre förståelse för vilka implementeringssteg som behövs och hur hela personaliseringsflödet fungerar.

## Implementering på klientsidan {#client-side-implementation}

Om du har en implementering på klientsidan kan du använda någon av AEP-klientens SDK: AEP Web SDK eller AEP Mobile SDK. Stegen nedan beskriver processen att hämta det innehåll som publiceras på kanten av de kodbaserade upplevelsekampanjerna i en exempelimplementering av Web SDK och visa det personaliserade innehållet.

### Så fungerar det

1. [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html){target="_blank"} finns på sidan.

1. Du måste använda `sendEvent` och ange ytans URI för att hämta personaliseringsinnehåll.

   ```javascript
   alloy("sendEvent", {
   renderDecisions: true,
   personalization: {
       surfaces: ["#sample-json-content"],
   },
   }).then(applyPersonalization("#sample-json-content"));
   ```

1. Kodbaserade upplevelseobjekt ska tillämpas manuellt av implementeringskoden (med [`applyPersonalization`](https://github.com/adobe/alloy-samples/blob/ac83b6927d007dc456caad2c6ce0b324c99c26c9/ajo/personalization-client-side/public/script.js){target="_blank"} metod) för att uppdatera DOM baserat på beslutet.

1. För kodbaserade upplevelsekampanjer måste visningshändelser skickas manuellt för att ange när innehållet har visats. Detta görs via `sendEvent` -kommando.

```javascript
function sendDisplayEvent(decision) {
  const { id, scope, scopeDetails = {} } = decision;

  alloy("sendEvent", {

    xdm: {
      eventType: "decisioning.propositionDisplay",
      _experience: {
        decisioning: {
          propositions: [
            {
              id: id,
              scope: scope,
              scopeDetails: scopeDetails,
            },
          ],
        },
      },
    },
  });
}
```

### Viktiga kommentarer

**Cookies**

Cookies används för att bevara användaridentitet och klusterinformation. När du använder en implementering på klientsidan hanterar Web SDK automatiskt lagring och sändning av dessa cookies under begärans livscykel.

| Cookie | Syfte | Lagrad av | Skickat av |
| ------------------------ | -------------------------------------------------------------------------- | --------- | ------- |
| kndctr_AdobeOrg_identity | Innehåller information om användaridentitet | Webb-SDK | Webb-SDK |
| kndctr_AdobeOrg_Cluster | Anger vilket kluster med upplevelsekanter som ska användas för att slutföra begäranden | Webb-SDK | Webb-SDK |

**Begär placering**

Begäranden till Adobe Experience Platform API krävs för att få förslag och skicka ett visningsmeddelande. När en implementering på klientsidan används, kommer Web SDK att göra dessa förfrågningar när `sendEvent` -kommandot används.

| Begäran | Skapad av |
| ---------------------------------------------- | ----------------------------------- |
| interaktionsbegäran för att få förslag | Web SDK med kommandot sendEvent |
| interagera begäran om att skicka visningsmeddelanden | Web SDK med kommandot sendEvent |

**Flödesdiagram**

![](assets/code-based-client-side-implementation.png)

## Implementering på serversidan {#server-side-implementation}

Om du har en implementering på serversidan kan du använda ett API för AEP Edge Network. Stegen nedan beskriver processen att hämta det innehåll som publiceras på kanten av de kodbaserade upplevelsekampanjerna i en exempelimplementering av Edge Network API för en webbsida och visa det personaliserade innehållet.

### Så fungerar det

1. Webbsidan har begärts och alla cookies som tidigare lagrats av webbläsaren har prefixats med `kndctr_` ingår.
1. När sidan begärs från programservern skickas en händelse till [slutpunkt för interaktiv datainsamling](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=en) för att hämta personaliseringsinnehåll. Det här exempelprogrammet använder vissa hjälpmetoder för att förenkla skapandet och skickandet av begäranden till API:t (se [aepEdgeClient.js](https://github.com/adobe/alloy-samples/blob/ac83b6927d007dc456caad2c6ce0b324c99c26c9/common/aepEdgeClient.js){target="_blank"}). Men begäran är bara en `POST` med en nyttolast som innehåller en händelse och fråga. Cookies (om sådana finns) från föregående steg inkluderas i begäran i `meta>state>entries` array.

   ```javascript
   fetch(
     "https://edge.adobedc.net/ee/v2/interact?dataStreamId=abc&requestId=123",
     {
       headers: {
         accept: "*/*",
         "accept-language": "en-US,en;q=0.9",
         "cache-control": "no-cache",
         "content-type": "text/plain; charset=UTF-8",
         pragma: "no-cache",
         "sec-fetch-dest": "empty",
         "sec-fetch-mode": "cors",
         "sec-fetch-site": "cross-site",
         "sec-gpc": "1",
         "Referrer-Policy": "strict-origin-when-cross-origin",
         Referer: "https://localhost/",
       },
       body: JSON.stringify({
         event: {
           xdm: {
             eventType: "decisioning.propositionFetch",
             web: {
               webPageDetails: {
                 URL: "https://localhost/",
               },
               webReferrer: {
                 URL: "",
               },
             },
             identityMap: {
               FPID: [
                 {
                   id: "xyz",
                   authenticatedState: "ambiguous",
                   primary: true,
                 },
               ],
             },
             timestamp: "2022-06-23T22:21:00.878Z",
           },
           data: {},
         },
         query: {
           identity: {
             fetch: ["ECID"],
           },
           personalization: {
             schemas: [
               "https://ns.adobe.com/personalization/default-content-item",
               "https://ns.adobe.com/personalization/html-content-item",
               "https://ns.adobe.com/personalization/json-content-item",
               "https://ns.adobe.com/personalization/redirect-item",
               "https://ns.adobe.com/personalization/dom-action",
             ],
             surfaces: ["web://localhost/","web://localhost/#sample-json-content"],
           },
         },
         meta: {
           state: {
             domain: "localhost",
             cookiesEnabled: true,
             entries: [
               {
                 key: "kndctr_XXX_AdobeOrg_identity",
                 value: "abc123",
               },
               {
                 key: "kndctr_XXX_AdobeOrg_cluster",
                 value: "or2",
               },
             ],
           },
         },
       }),
       method: "POST",
     }
   ).then((res) => res.json());
   ```

1. JSON-upplevelsen från den kodbaserade upplevelsekampanjen läses från svaret och används när svaret från HTML tas fram.
1. För kodbaserade upplevelsekampanjer måste visningshändelser skickas manuellt i implementeringen för att ange när kampanjinnehållet har visats. I det här exemplet skickas meddelandet på serversidan under livscykeln för begäran.

   ```javascript
   function sendDisplayEvent(aepEdgeClient, req, propositions, cookieEntries) {
     const address = getAddress(req);
   
     aepEdgeClient.interact(
       {
         event: {
           xdm: {
             web: {
               webPageDetails: { URL: address },
               webReferrer: { URL: "" },
             },
             timestamp: new Date().toISOString(),
             eventType: "decisioning.propositionDisplay",
             _experience: {
               decisioning: {
                 propositions: propositions.map((proposition) => {
                   const { id, scope, scopeDetails } = proposition;
   
                   return {
                     id,
                     scope,
                     scopeDetails,
                   };
                 }),
               },
             },
           },
         },
         query: { identity: { fetch: ["ECID"] } },
         meta: {
           state: {
             domain: "",
             cookiesEnabled: true,
             entries: [...cookieEntries],
           },
         },
       },
       {
         Referer: address,
       }
     );
   }
   ```

1. När HTML-svaret returneras ställs identitets- och klustercookies in på programserverns svar.

### Viktiga kommentarer

**Cookies**

Cookies används för att bevara användaridentitet och klusterinformation. När en implementering på serversidan används, måste programservern hantera lagringen och sändningen av dessa cookies under begärans livscykel.

| Cookie | Syfte | Lagrad av | Skickat av |
| ------------------------ | -------------------------------------------------------------------------- | ------------------ | ------------------ |
| kndctr_AdobeOrg_identity | Innehåller information om användaridentitet | programserver | programserver |
| kndctr_AdobeOrg_Cluster | Anger vilket kluster med upplevelsekanter som ska användas för att slutföra begäranden | programserver | programserver |

**Begär placering**

Begäranden till Adobe Experience Platform API krävs för att få förslag och skicka ett visningsmeddelande. När en implementering på klientsidan används, kommer Web SDK att göra dessa förfrågningar när `sendEvent` -kommandot används.

| Begäran | Skapad av |
| ---------------------------------------------- | ------------------------------------------------------------ |
| interaktionsbegäran för att få förslag | programserver som anropar Adobe Experience Platform API |
| interagera begäran om att skicka visningsmeddelanden | programserver som anropar Adobe Experience Platform API |

**Flödesdiagram**

![](assets/code-based-server-side-implementation.png)

## Hybrid-implementering {#hybrid-implementation}

Om du har en hybridimplementering kan du kolla in länkarna nedan.

* Adobe Tech Blog: [Hybrid-anpassning i Adobe Experience Platform Web SDK](https://blog.developer.adobe.com/hybrid-personalization-in-the-adobe-experience-platform-web-sdk-6a1bb674bf41){target="_blank"}
* SDK-dokumentation: [Hybrid-personalisering med Web SDK och Edge Network Server API](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/hybrid-personalization.html){target="_blank"}
