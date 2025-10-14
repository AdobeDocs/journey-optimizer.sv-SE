---
title: Kodbaserade implementeringsexempel
description: På den här sidan visas exempel på implementeringsmetoden för Journey Optimizer kodbaserade funktion
feature: Code-based Experiences
topic: Content Management
role: Developer
level: Experienced
exl-id: e5ae8b4e-7cd2-4a1d-b2c0-8dafd5c4cdfd
source-git-commit: bf0a6fa496a08348be16896a7f2313882eb97c06
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 1%

---

# Exempel på kodbaserade implementeringsmetoder {#implementation-samples}

Kodbaserad upplevelse stöder alla typer av kundimplementeringar. På den här sidan hittar du exempel för varje implementeringsmetod:

* [Klientsidan](#client-side-implementation)
* [Serversidan](#server-side-implementation)
* [Hybrid](#hybrid-implementation)

>[!IMPORTANT]
>
>Följ [den här länken](https://github.com/adobe/alloy-samples/tree/main/ajo){target="_blank"} för att hitta exempelimplementeringar för olika användningsfall för personalisering och experimenterande. Kolla in dem och kör dem för att få en bättre förståelse för vilka implementeringssteg som behövs och hur hela personaliseringsflödet fungerar.

## Implementering på klientsidan {#client-side-implementation}

Om du har en implementering på klientsidan kan du använda någon av AEP-klientens SDK: AEP Web SDK eller AEP Mobile SDK.

* Stegen [&#x200B; nedan](#client-side-how) beskriver processen att hämta det innehåll som publiceras på kanten av de kodbaserade upplevelsegångarna och kampanjerna i en exempelimplementering av **Web SDK** och visa det personaliserade innehållet.

* Stegen för att implementera kodbaserad kanal med **Mobile SDK** beskrivs i [den här självstudiekursen](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer/code-based/tutorial/){target="_blank"}.

  >[!NOTE]
  >
  >Exempel på implementeringar för mobilanvändning finns för [iOS-appen](https://github.com/adobe/aepsdk-messaging-ios/tree/main/TestApps/MessagingDemoAppSwiftUI){target="_blank"} och [Android-appen](https://github.com/adobe/aepsdk-messaging-android/tree/main/code/testapp){target="_blank"}.

### Så här fungerar det - Web SDK {#client-side-how}

1. [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=sv-SE){target="_blank"} ingår på sidan.

1. Du måste använda kommandot `sendEvent` och ange [yt-URI](code-based-surface.md)<!--( or location/path)--> för att hämta personaliseringsinnehåll.

   ```javascript
   alloy("sendEvent", {
   renderDecisions: true,
   personalization: {
       surfaces: ["#sample-json-content"],
   },
   }).then(applyPersonalization("#sample-json-content"));
   ```

1. Kodbaserade upplevelseobjekt ska tillämpas manuellt av implementeringskoden (med metoden [`applyPersonalization`](https://github.com/adobe/alloy-samples/blob/ac83b6927d007dc456caad2c6ce0b324c99c26c9/ajo/personalization-client-side/public/script.js){target="_blank"}) för att uppdatera DOM baserat på beslutet.

1. För kodbaserade upplevelseresor och kampanjer måste visningshändelser skickas manuellt för att ange när innehållet har visats. Detta görs via kommandot `sendEvent`.

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

1. För kodbaserade upplevelseresor och kampanjer måste interaktionshändelser skickas manuellt för att ange när en användare har interagerat med innehållet. Detta görs via kommandot `sendEvent`.

   ```javascript
   function sendInteractEvent(label, proposition) {
     const { id, scope, scopeDetails = {} } = proposition;
   
     alloy("sendEvent", {
   
       xdm: {
         eventType: "decisioning.propositionInteract",
         _experience: {
           decisioning: {
             propositions: [
               {
                 id: id,
                 scope: scope,
                 scopeDetails: scopeDetails,
               },
             ],
             propositionEventType: {
               interact: 1
             },
             propositionAction: {
               label: label
             },
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
| kndctr_AdobeOrg_identity | Innehåller information om användaridentitet | Web SDK | Web SDK |
| kndctr_AdobeOrg_Cluster | Anger vilket kluster med upplevelsekanter som ska användas för att slutföra begäranden | Web SDK | Web SDK |

**Begär placering**

Begäranden till Adobe Experience Platform API krävs för att få förslag och skicka ett visningsmeddelande. När du använder en implementering på klientsidan gör Web SDK dessa begäranden när kommandot `sendEvent` används.

| Begäran | Skapad av |
| ---------------------------------------------- | ----------------------------------- |
| interaktionsbegäran för att få förslag | Web SDK med kommandot sendEvent |
| interagera begäran om att skicka visningsmeddelanden | Web SDK med kommandot sendEvent |

**Flödesdiagram**

![](assets/code-based-client-side-implementation.png)

## Implementering på serversidan {#server-side-implementation}

Om du har en implementering på serversidan kan du använda ett API för AEP Edge Network.

Stegen nedan beskriver processen att hämta det innehåll som publiceras på kanten av de kodbaserade upplevelseflödena och kampanjerna i en exempelimplementering av Edge Network-API för en webbsida och visa det personaliserade innehållet.

### Så fungerar det

1. Webbsidan har begärts och alla cookies som tidigare lagrats av webbläsaren som har prefixet `kndctr_` ingår.
1. När sidan begärs från programservern skickas en händelse till [slutpunkten för interaktiv datainsamling](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=sv-SE) för att hämta personaliseringsinnehåll. I det här exempelprogrammet används vissa hjälpmetoder för att förenkla generering och sändning av begäranden till API (se [aepEdgeClient.js](https://github.com/adobe/alloy-samples/blob/ac83b6927d007dc456caad2c6ce0b324c99c26c9/common/aepEdgeClient.js){target="_blank"}). Men begäran är bara en `POST` med en nyttolast som innehåller en händelse och fråga. Cookies (om de är tillgängliga) från föregående steg inkluderas i begäran i arrayen `meta>state>entries`.

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

1. JSON-upplevelsen från de kodbaserade upplevelseresorna och kampanjen läses från svaret och används när svaret från HTML tas fram.

1. För kodbaserade upplevelseresor och kampanjer måste displayhändelser skickas manuellt i implementeringen för att ange när resan eller kampanjinnehållet har visats. I det här exemplet skickas meddelandet på serversidan under livscykeln för begäran.

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

Begäranden till Adobe Experience Platform API krävs för att få förslag och skicka ett visningsmeddelande. När du använder en implementering på klientsidan gör Web SDK dessa begäranden när kommandot `sendEvent` används.

| Begäran | Skapad av |
| ---------------------------------------------- | ------------------------------------------------------------ |
| interaktionsbegäran för att få förslag | programserver som anropar Adobe Experience Platform API |
| interagera begäran om att skicka visningsmeddelanden | programserver som anropar Adobe Experience Platform API |

**Flödesdiagram**

![](assets/code-based-server-side-implementation.png)

## Hybrid-implementering {#hybrid-implementation}

Om du har en hybridimplementering kan du kolla in länkarna nedan.

* Adobe Tech Blog: [Hybrid Personalization i Adobe Experience Platform Web SDK](https://blog.developer.adobe.com/hybrid-personalization-in-the-adobe-experience-platform-web-sdk-6a1bb674bf41){target="_blank"}
* SDK-dokumentation: [Hybrid-anpassning med API:t för Web SDK och Edge Network Server &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/hybrid-personalization.html?lang=sv-SE){target="_blank"}
