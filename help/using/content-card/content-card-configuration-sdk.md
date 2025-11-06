---
title: Konfiguration av innehållskort Web SDK
description: Konfigurera stöd för innehållskort i Web SDK
feature: Channel Configuration, Content Cards
topic: Content Management
role: Admin
level: Experienced
exl-id: bb67b55f-2eac-4775-a9f5-78288009477e
source-git-commit: 37862682a25843ce138c076e443f6d9b6229ece3
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 0%

---

# Konfigurera stöd för innehållskort i Web SDK {#content-card-configuration-sdk}

I det här exemplet visas hur du hämtar innehållskort från Adobe Journey Optimizer (AJO) med Adobe Experience Platform. Genom att utnyttja [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/sv/docs/experience-platform/web-sdk/home) hämtas personaliseringsinnehållet och återges helt på klientsidan.

När den första sidan läses in visas sidans standardläge. Om du interagerar med knapparna **Insättningsfonder** eller **Dela på sociala medier** visas ytterligare innehållskort. Dessa kort aktiveras av klientvillkoren, vilket säkerställer att de bara visas när specifika åtgärder vidtas.

![](assets/content-card-web-1.png)

## Köra exemplet {#run-sample}

>[!PREREQUISITES]
>
>Du måste installera nod och npm. [Läs den här dokumentationen](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)


1. Konfigurera lokala SSL-certifikat för HTTPS. Dessa exempel kräver lokalt signerade SSL-certifikat för att leverera innehåll via HTTPS:

   1. Installera `mkcert` på datorn.

   1. Efter installationen kör du `mkcert -install` för att installera `mkcert root`-certifikatet.

1. Klona databasen till din lokala dator.

1. Öppna en terminal och navigera till exempelmappen.

1. Installera nödvändiga beroenden genom att köra `npm install`.

1. Starta programmet med `npm start`.

1. Öppna webbläsaren och gå till `https://localhost`.

## Så fungerar det {#setup}

1. Inkludera och konfigurera [Web SDK](https://experienceleague.adobe.com/sv/docs/experience-platform/web-sdk/home) på sidan med inställningar från filen `.env` i exempelmappen.

   ```
   <script src="https://cdn1.adoberesources.net/alloy/2.18.0/alloy.min.js" async></script>
   alloy("configure", {
       defaultConsent: "in",
       edgeDomain: "{{edgeDomain}}",
       edgeConfigId: "{{edgeConfigId}}",
       orgId:"{{orgId}}",
       debugEnabled: false,
       personalizationStorageEnabled: true,
       thirdPartyCookiesEnabled: false
   });
   ```

1. Använd kommandot `sendEvent` för att hämta anpassat innehåll.

   ```
   alloy("sendEvent", {
       renderDecisions: true,
       personalization: {
           surfaces: ["web://alloy-samples.adobe.com/#content-cards-sample"],
       },
   });
   ```

1. Prenumerera på innehållskort för en viss yta med kommandot `subscribeRulesetItems`. Varje gång regeluppsättningar utvärderas hanterar du resultatobjektet i återanropet, som kommer att innehålla `propositions` med innehållskortsdata.

   ```
   const contentCardManager = createContentCardManager("content-cards");
   
   alloy("subscribeRulesetItems", {
       surfaces: ["web://alloy-samples.adobe.com/#content-cards-sample"],
       schemas: ["https://ns.adobe.com/personalization/message/content-card"],
       callback: (result, collectEvent) => {
           const { propositions = [] } = result;
           contentCardManager.refresh(propositions, collectEvent);
       },
   });
   ```

1. Hantera återgivning av innehållskort och skicka `interact`- och `display`-händelser med objektet `contentCardsManager` som finns i `script.js`. Extrahera, sortera och bearbeta innehållskort från de mottagna förslagen.

   ```
   const createContentCard = (proposition, item) => {
       const { data = {}, id } = item;
       const {
           content = {},
           meta = {},
           publishedDate,
           qualifiedDate,
           displayedDate,
       } = data;
   
       return {
           id,
           ...content,
           meta,
           qualifiedDate,
           displayedDate,
           publishedDate,
           getProposition: () => proposition,
       };
   };
   
   const extractContentCards = (propositions) =>
       propositions
           .reduce((allItems, proposition) => {
           const { items = [] } = proposition;
   
           return [
               ...allItems,
               ...items.map((item) => createContentCard(proposition, item)),
           ];
       }, [])
       .sort(
           (a, b) =>
               b.qualifiedDate - a.qualifiedDate || b.publishedDate - a.publishedDate
       );
   
   const contentCards = extractContentCards(propositions);
   ```

1. Rendera innehållskorten baserat på de detaljer som definierats för varje kampanj. Varje kort innehåller en `title`, `body`, `imageUrl` och andra anpassade datavärden.

   ```
   const renderContentCards = () => {
       const contentCardsContainer = document.getElementById(containerElementId);
       contentCardsContainer.addEventListener("click", handleContentCardClick);
   
       let contents = "";
   
       contentCards.forEach((card) => {
           const { id, title, body, imageUrl, meta = {} } = card;
           const { buttonLabel = "" } = meta;
   
           contents += `
               <div class="col">
                   <div data-id="${id}" class="card h-100">
                       <img src="${imageUrl}" class="card-img-top" alt="...">
                       <div class="card-body d-flex flex-column">
                           <h5 class="card-title">${title}</h5>
                           <p class="card-text">${body}</p>
                           <a href="#" class="mt-auto btn btn-primary">${buttonLabel}</a>
                       </div>
                   </div>
                </div>
            `;
       });
   
       contentCardsContainer.innerHTML = contents;
       collectEvent(
           "display",
           contentCards.map((card) => card.getProposition())
        );
   };
   ```

1. När återanropet `subscribeRulesetItems` anropas finns även en bekvämlighetsfunktion med namnet `collectEvent`. Den här funktionen används för att skicka Experience Edge-händelser för att spåra interaktioner, visningar och andra användaråtgärder. I det här exemplet spårar collectEvent när någon klickar på ett innehållskort. Om du klickar på knappen på innehållskortet dirigeras dessutom webbläsaren till `actionUrl` som anges av kampanjen.

   ```
   const handleContentCardClick = (evt) => {
       const cardEl = evt.target.closest(".card");
   
       if (!cardEl) {
           return;
       }
   
       const isAnchor = evt.target.nodeName === "A";
       const card = contentCards.find((card) => card.id === cardEl.dataset.id);
   
       if (!card) {
           return;
       }
   
       collectEvent("interact", [card.getProposition()]);
   
       if (isAnchor) {
           evt.preventDefault();
           evt.stopImmediatePropagation();
           const { actionUrl } = card;
           if (actionUrl && actionUrl.length > 0) {
               window.location.href = actionUrl;
           }
       }
   };
   ```

## Viktiga kommentarer {#key-observations}

### personalizationStorageEnabled

Alternativet `personalizationStorageEnabled` är inställt på `true` i kommandot `configure`. Detta garanterar att tidigare kvalificerade innehållskort lagras och fortsätter att visas i alla användarsessioner.

### Utlösare

Innehållskort har stöd för anpassade utlösare som utvärderas på klientsidan. När en utlösarregel har uppfyllts visas ytterligare innehållskort. Det här exemplet använder fyra olika kampanjer, en för varje innehållskort, som alla delar samma yta: `web://alloy-samples.adobe.com/#content-cards-sample`. Tabellen nedan visar utlösarreglerna för varje kampanj och hur de kan uppfyllas.

<table>
    <tr>
        <th>Utlösarregel</th>
        <th>Kort</th>
        <th>Så här uppfyller du utlösarregeln</th>
    </tr>
    <tr>
        <td>Ingen</td>
        <td><img src="assets/content-card-web-2.png"></td>
        <td>sendEvent, kommando. Ingen klientsidregel att uppfylla.</td>
    </tr>
    <tr>
        <td>Ingen</td>
        <td><img src="assets/content-card-web-3.png"></td>
        <td>sendEvent, kommando. Ingen klientsidregel att uppfylla.</td>
    </tr>
    <tr>
        <td><img src="assets/content-card-web-4.png"></td>
        <td><img src="assets/content-card-web-5.png"></td>
        <td><img src="assets/content-card-web-6.png"></td>
    </tr>
    <tr>
        <td><img src="assets/content-card-web-7.png"></td>
        <td><img src="assets/content-card-web-8.png"></td>
        <td><img src="assets/content-card-web-9.png"></td>
    </tr>
</table>

Kommandot `evaluateRulesets` aktiveras när du klickar på knapparna Insättningsfonder och Dela på sociala medier. Varje knapp anger den relevanta `decisionContext` för att uppfylla reglerna som definierats för respektive kampanj.

```
document.getElementById("action-button-1").addEventListener("click", () => {
    alloy("evaluateRulesets", {
        renderDecisions: true,
        personalization: {
            decisionContext: {
                action: "deposit-funds",
            },
        },
    });
});

document.getElementById("action-button-2").addEventListener("click", () => {
    alloy("evaluateRulesets", {
        renderDecisions: true,
        personalization: {
            decisionContext: {
                action: "social-media",
            },
        },
    });
});
```
