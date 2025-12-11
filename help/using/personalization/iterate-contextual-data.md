---
solution: Journey Optimizer
product: journey optimizer
title: Iterera över kontextuella data
description: Lär dig iterera över arrayer från olika sammanhangskällor med hjälp av Handlebars-syntax
feature: Personalization
topic: Personalization
role: Developer
level: Intermediate
keywords: uttryck, redigerare, handtag, iteration, matriser, kontext, personalisering
source-git-commit: a0e8ca1b45818014993c37ac41f25e30ee1d1bb5
workflow-type: tm+mt
source-wordcount: '3008'
ht-degree: 0%

---

# Iterera över kontextuella data {#personalization-contexts}

Lär dig hur du använder itereringssyntax för Handlebars för att visa dynamiska listor med data från olika källor i dina meddelanden, inklusive händelser, anpassade åtgärdssvar och andra sammanhangsbaserade data.

## Översikt {#overview}

Journey Optimizer ger åtkomst till kontextuella data från flera källor under [meddelandepersonalisering](personalize.md). Du kan iterera över arrayer från dessa källor med hjälp av Handlebars-syntax i inbyggda kanaler ([email](../email/get-started-email-design.md), [push](../push/create-push.md), [SMS](../sms/create-sms.md)) för att visa dynamiskt innehåll som produktlistor, rekommendationer eller andra upprepade element.

**Tillgängliga sammanhangskällor:**

* **[Händelser](#event-data)**: Data från resehändelser (affärshändelser, enhetshändelser)
* **[Anpassade åtgärdssvar](#custom-action-responses)**: Data som returnerats från externa API-anrop via anpassade åtgärder
* **[Datauppsättningssökning](#dataset-lookup)**: Förbättrade data har hämtats från Adobe Experience Platform datauppsättningar
* **[Tekniska egenskaper](#technical-properties)**: Resemetadata som resa-ID och extra identifierare
* **[Resekontext](#other-contexts)**: Andra reserelaterade data som är tillgängliga under körningen

Den här guiden visar hur du itererar över arrayer från var och en av dessa källor i dina meddelanden och hur du arbetar med arrayer när du konfigurerar reseaktiviteter. Börja med [Hantera fält-itereringssyntax](#syntax) om du vill förstå grunderna för meddelandeanpassning, eller gå till [Arbeta med arrayer i Journey-uttryck](#arrays-in-journeys) om du vill lära dig hur du skickar arraydata till anpassade åtgärder och datasetsökningar.

## Syntax för iterering av Handlebars {#syntax}

Hanteringsfält ger `{{#each}}` [hjälpen](functions/helpers.md) som kan itereras över arrayer. Grundsyntaxen är:

```handlebars
{{#each arrayPath as |item|}}
  <!-- Access item properties here -->
  {{item.property}}
{{/each}}
```

**Nyckelpunkter:**

* Ersätt `arrayPath` med sökvägen till matrisdata
* Ersätt `item` med valfritt variabelnamn (t.ex. `product`, `response`, `element`)
* Åtkomst till egenskaper för varje objekt med `{{item.propertyName}}`
* Du kan kapsla in flera `{{#each}}`-block för flernivåarrayer

## Iterera över händelsedata {#event-data}

Händelsedata är tillgängliga när din resa aktiveras av en [händelse](../event/about-events.md). Detta är användbart för att visa data som hämtades när resan påbörjades, till exempel kundvagnsinnehåll, orderartiklar eller formulärinskickningar.

>[!TIP]
>
>Du kan kombinera händelsedata med andra källor. Se [Kombinera flera sammanhangskällor](#combine-sources) för exempel.

### Kontextsökväg för händelser

```handlebars
context.journey.events.<event_ID>.<fieldPath>
```

* `<event_ID>`: Det unika ID:t för din händelse som konfigurerats under resan
* `<fieldPath>`: Sökvägen till fältet eller arrayen i ditt händelseschema

### Exempel: Skapa kundvagnsobjekt från en händelse

Om ditt [händelseschema](../event/experience-event-schema.md) innehåller en `productListItems`-matris (standardformat [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/product-list-item.html?lang=sv-SE){target="_blank"}) kan du visa kundvagnens innehåll enligt exemplet nedan.

+++ Visa exempelkod

```handlebars
{{#each context.journey.events.event_ID.productListItems as |product|}}
  <div class="product">
    <h3>{{product.name}}</h3>
    <p>Quantity: {{product.quantity}}</p>
    <p>Price: ${{product.priceTotal}}</p>
  </div>
{{/each}}
```

+++

### Exempel: Kapslade arrayer i händelser

Använd kapslade `{{#each}}`-block för kapslade strukturer.

+++ Visa exempelkod

```handlebars
{{#each context.journey.events.event_ID.categories as |category|}}
  <h2>{{category.name}}</h2>
  <ul>
    {{#each category.items as |item|}}
      <li>{{item.title}}</li>
    {{/each}}
  </ul>
{{/each}}
```

+++

Läs mer om kapsling i [Bästa tillvägagångssätt](#best-practices).

## Iterera över anpassade åtgärdssvar {#custom-action-responses}

[Anpassade åtgärder](../action/about-custom-action-configuration.md)-svar innehåller data som returnerats från externa API-anrop. Detta är användbart när du vill visa realtidsinformation från dina system, t.ex. förmånspoäng, produktrekommendationer, lagerstatus eller personaliserade erbjudanden.

>[!NOTE]
>
>Anpassade åtgärder måste konfigureras med en svarsnyttolast för att den här funktionen ska kunna användas. Läs mer i [det här avsnittet](../action/action-response.md#config-response). Du kan också kombinera anpassade åtgärdssvar med händelsedata eller datasökningar - se [Kombinera flera sammanhangskällor](#combine-sources) för exempel.

### Kontextsökväg för anpassade åtgärder

```handlebars
context.journey.actions.<actionName>.<fieldPath>
```

* `<actionName>`: Namnet på din [anpassade åtgärd](../action/about-custom-action-configuration.md) som konfigurerats under resan
* `<fieldPath>`: Sökvägen till fältet eller arrayen i svarsnyttolasten

### Exempel: Produktrekommendationer från ett API

Om du vill iterera över en array med produktrekommendationer som returneras från en anpassad åtgärd och visa dem som enskilda kort i ditt meddelande, se exemplet nedan.

+++ Visa exempelkod

**API-svar:**

```json
{
  "recommendations": [
    {
      "productId": "12345",
      "productName": "Summer Jacket",
      "price": 89.99,
      "imageUrl": "https://example.com/jacket.jpg"
    },
    {
      "productId": "67890",
      "productName": "Running Shoes",
      "price": 129.99,
      "imageUrl": "https://example.com/shoes.jpg"
    }
  ]
}
```

**Meddelandepersonalisering:**

```handlebars
<h2>Recommended for You</h2>
<div class="recommendations">
  {{#each context.journey.actions.GetRecommendations.recommendations as |item|}}
    <div class="product-card">
      <img src="{{item.imageUrl}}" alt="{{item.productName}}" />
      <h3>{{item.productName}}</h3>
      <p class="price">${{item.price}}</p>
    </div>
  {{/each}}
</div>
```

+++

### Exempel: Kapslade arrayer från anpassade åtgärder

Om du vill iterera över ett anpassat åtgärdssvar som innehåller kapslade arrayer (en array med objekt där varje objekt innehåller en annan array), se exemplet nedan. Detta visar hur kapslade `{{#each}}`-slingor används för att få åtkomst till flera datanivåer.

+++ Visa exempelkod

**API-svar:**

```json
{    
  "id": "84632848268632",    
  "responses": [
    { "productIDs": [1111, 2222, 3333] },
    { "productIDs": [4444, 5555, 6666] },
    { "productIDs": [7777, 8888, 9999] }
  ]
}
```

**Meddelandepersonalisering:**

```handlebars
<h2>Product Groups</h2>
{{#each context.journey.actions.GetProducts.responses as |response|}}
  <div class="product-group">
    <ul>
      {{#each response.productIDs as |productID|}}
        <li>Product ID: {{productID}}</li>
      {{/each}}
    </ul>
  </div>
{{/each}}
```

+++

Mer komplexa kapslingsmönster finns i [Bästa tillvägagångssätt](#best-practices).

### Exempel: Förmåner i bonusskiktet

Om du vill visa dynamiska fördelar baserat på lojalitetsstatus, se exemplet nedan.

+++ Visa exempelkod

**API-svar:**

```json
{
  "loyaltyTier": "gold",
  "benefits": [
    { "name": "Free shipping", "icon": "truck" },
    { "name": "20% discount", "icon": "percent" },
    { "name": "Priority support", "icon": "headset" }
  ]
}
```

**Meddelandepersonalisering:**

```handlebars
<h2>Your {{context.journey.actions.GetLoyaltyInfo.loyaltyTier}} Member Benefits</h2>
<ul class="benefits">
  {{#each context.journey.actions.GetLoyaltyInfo.benefits as |benefit|}}
    <li>
      <span class="icon-{{benefit.icon}}"></span>
      {{benefit.name}}
    </li>
  {{/each}}
</ul>
```

+++

## Iterera sökresultat för datauppsättningar {#dataset-lookup}

[Uppslagsaktiviteten för datauppsättningar](../building-journeys/dataset-lookup.md) gör att du kan hämta data från [Adobe Experience Platform-datauppsättningar](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=sv-SE){target="_blank"} under körning. De inkapslade data lagras som en array och kan itereras över i dina meddelanden.

>[!AVAILABILITY]
>
>Uppslagsaktiviteten för datauppsättningar är bara tillgänglig för en begränsad uppsättning organisationer. Kontakta din Adobe-representant för att få åtkomst.

Läs mer om hur du konfigurerar uppslagsaktiviteten för datauppsättningar i [det här avsnittet](../building-journeys/dataset-lookup.md). Datauppsättningssökningen är särskilt kraftfull när den kombineras med händelsedata - se [Exempel: Händelsedata som har berikats med datauppsättningssökning](#combine-sources) för ett praktiskt användningsexempel.

### Kontextsökväg för datasökningar

```handlebars
context.journey.datasetLookup.<activityID>.entities
```

* `<activityID>`: Det unika ID:t för datauppsättningsaktiviteten
* `entities`: Arrayen med anrikade data som hämtats från datauppsättningen

### Exempel: Produktinformation från en datauppsättning

Om du använder en datauppslagsaktivitet för att hämta produktinformation baserat på SKU:er, se exemplet nedan.

+++ Visa exempelkod

**Uppslagskonfiguration för datauppsättning:**

* Uppslagstangenter: `list(@event{purchase_event.products.sku})`
* Fält som ska returneras: `["SKU", "category", "price", "name"]`

**Meddelandepersonalisering:**

```handlebars
<h2>Product Details</h2>
<table>
  <thead>
    <tr>
      <th>Product Name</th>
      <th>Category</th>
      <th>Price</th>
    </tr>
  </thead>
  <tbody>
    {{#each context.journey.datasetLookup.3709000.entities as |product|}}
      <tr>
        <td>{{product.name}}</td>
        <td>{{product.category}}</td>
        <td>${{product.price}}</td>
      </tr>
    {{/each}}
  </tbody>
</table>
```

+++

### Exempel: Filtrerad iteration med datauppsättningsdata

Om du vill filtrera sökresultat för datauppsättningar under upprepning och bara visa objekt som matchar specifika villkor (t.ex. produkter från en viss kategori) använder du villkorliga `{{#if}}`-satser i `{{#each}}` -slingan. Se exemplet nedan.

+++ Visa exempelkod

```handlebars
<h2>Household Products</h2>
{{#each context.journey.datasetLookup.3709000.entities as |product|}}
  {{#if product.category = "household"}}
    <div class="product">
      <h3>{{product.name}}</h3>
      <p>Price: ${{product.price}}</p>
    </div>
  {{/if}}
{{/each}}
```

+++

Läs mer om villkorsstyrd filtrering i [Bästa praxis](#best-practices).

### Exempel: Beräkna summor från datauppsättningssökning

Om du vill beräkna och visa summor medan du itererar över datasetsökningsresultat, se exemplet nedan.

+++ Visa exempelkod

```handlebars
{% let householdTotal = 0 %}
{{#each context.journey.datasetLookup.3709000.entities as |product|}}
  {%#if product.category = "household"%}
    {% let householdTotal = householdTotal + product.price %}
  {%/if%}
{{/each}}

<p>Your household products total: ${{householdTotal}}</p>
```

+++

## Använd resans tekniska egenskaper {#technical-properties}

Resetekniska egenskaper ger åtkomst till metadata om körningen av resan, som rese-ID och kompletterande identifierare. Dessa kan vara användbara när de kombineras med iterationsmönster, särskilt för att filtrera arrayer baserat på specifika resinstanser.

### Tillgängliga tekniska egenskaper

```handlebars
context.journey.technicalProperties.journeyUID
context.journey.technicalProperties.supplementalId
```

### Exempel: Filtrera arrayobjekt med hjälp av tilläggsidentifierare

När du använder tilläggsidentifierare i händelseutlösta resor med matriser kan du filtrera så att bara den relevanta artikeln för den aktuella resinstansen visas. Läs mer om ytterligare identifierare i [den här handboken](../building-journeys/supplemental-identifier.md).

**Scenario**: En resa aktiveras med flera bokningar, men du vill bara visa information för den specifika bokningen (identifieras med ett extra ID) som utlöste den här reseinstansen.

+++ Visa exempelkod

```handlebars
{{#each context.journey.events.event_ID.bookingList as |booking|}}
  {%#if booking.bookingInfo.bookingNum = context.journey.technicalProperties.supplementalId%}
    <div class="booking-details">
      <h3>Your Booking: {{booking.bookingInfo.bookingNum}}</h3>
      <p>Destination: {{booking.bookingInfo.bookingCountry}}</p>
      <p>Date: {{booking.bookingInfo.bookingDate}}</p>
    </div>
  {%/if%}
{{/each}}
```

+++

### Exempel: Inkludera rese-ID för spårning

Se exemplet nedan om du vill inkludera rese-ID:t i ditt meddelande för spårningsändamål.

+++ Visa exempelkod

```handlebars
<footer>
  <p>Journey Reference: {{context.journey.technicalProperties.journeyUID}}</p>
</footer>
```

+++

## Kombinera flera sammanhangskällor {#combine-sources}

Ni kan kombinera data från olika källor i samma budskap för att skapa innehållsrika, personaliserade upplevelser. I det här avsnittet visas praktiska exempel på hur du använder flera sammanhangskällor tillsammans.

**Kontextkällor som du kan kombinera:**

* [Händelsedata](#event-data) + [Anpassade åtgärdssvar](#custom-action-responses)
* [Händelsedata](#event-data) + [Datauppsättningssökning](#dataset-lookup)
* [Flera källor](#combine-sources) + [Tekniska egenskaper](#technical-properties)

### Exempel: Kundvagnsartiklar med realtidslager

Se exemplet nedan om du vill kombinera händelsedata (kundvagnens innehåll) med anpassade åtgärdsdata (lagerstatus).

+++ Visa exempelkod

```handlebars
<h2>Your Cart</h2>
{{#each context.journey.events.cartEvent.productListItems as |product|}}
  <div class="cart-item">
    <h3>{{product.name}}</h3>
    <p>Quantity: {{product.quantity}}</p>
    <p>Price: ${{product.priceTotal}}</p>
  </div>
{{/each}}

<h2>We Also Recommend</h2>
{{#each context.journey.actions.GetRecommendations.items as |recommendation|}}
  <div class="recommendation">
    <h4>{{recommendation.name}}</h4>
    <p>${{recommendation.price}}</p>
    {{#if recommendation.inStock}}
      <span class="badge">In Stock</span>
    {{else}}
      <span class="badge out-of-stock">Out of Stock</span>
    {{/if}}
  </div>
{{/each}}
```

+++

### Exempel: Händelsedata som har berikats med datasökning

Visa exemplet nedan om du vill kombinera [händelse-SKU:er](#event-data) med detaljerad produktinformation från en [dataset-sökning](#dataset-lookup).

+++ Visa exempelkod

```handlebars
<h2>Your Order Details</h2>
{{#each context.journey.events.orderEvent.productListItems as |item|}}
  <div class="order-item">
    <p><strong>SKU:</strong> {{item.SKU}}</p>
    <p><strong>Quantity:</strong> {{item.quantity}}</p>
    
    <!-- Enrich with dataset lookup data -->
    {{#each context.journey.datasetLookup.1234567.entities as |enrichedProduct|}}
      {{#if enrichedProduct.SKU = item.SKU}}
        <p><strong>Product Name:</strong> {{enrichedProduct.name}}</p>
        <p><strong>Category:</strong> {{enrichedProduct.category}}</p>
        <img src="{{enrichedProduct.imageUrl}}" alt="{{enrichedProduct.name}}" />
      {{/if}}
    {{/each}}
  </div>
{{/each}}
```

+++

### Exempel: Kombinera flera källor med tekniska egenskaper

Se exemplet nedan om du vill kombinera flera sammanhangskällor (profildata, händelsedata, anpassade åtgärder och tekniska egenskaper) i ett enda meddelande.

+++ Visa exempelkod

```handlebars
<div class="personalized-content">
  <!-- Profile data -->
  <h1>Hello {{profile.person.name.firstName}},</h1>
  
  <!-- Event data iteration -->
  <h2>Your Recent Purchases</h2>
  {{#each context.journey.events.purchaseEvent.items as |purchase|}}
    <div class="purchase">
      <p>{{purchase.productName}} - ${{purchase.price}}</p>
    </div>
  {{/each}}
  
  <!-- Custom action response iteration -->
  <h2>Recommended for You</h2>
  {{#each context.journey.actions.GetPersonalizedRecs.recommendations as |rec|}}
    <div class="recommendation">
      <h3>{{rec.title}}</h3>
      <p>{{rec.description}}</p>
    </div>
  {{/each}}
  
  <!-- Technical properties -->
  <footer>
    <p class="fine-print">Journey ID: {{context.journey.technicalProperties.journeyUID}}</p>
  </footer>
</div>
```

+++

## Andra sammanhangstyper {#other-contexts}

Den här guiden fokuserar på upprepning över arrayer, men det finns andra sammanhangstyper tillgängliga för personalisering som vanligtvis inte kräver upprepning. De här nås direkt i stället för att upprepas:

* **[Profilattribut](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv){target="_blank"}** (`profile.*`): Individuella profilfält från Adobe Experience Platform
* **[Publiker](../audience/about-audiences.md)** (`inAudience()`): Kontroller av målgruppsmedlemskap
* **[Erbjud beslut](../offers/get-started/starting-offer-decisioning.md)**: Beslutshantering erbjuder
* **[Målattribut](../orchestrated/activities/channels.md#add-personalization)** (endast orkestrerade kampanjer): Attribut som beräknas på kampanjarbetsytan
* **Token** (`context.token`): Sessions- eller autentiseringstoken

Fullständig personaliseringssyntax och exempel på hur du använder dessa källor finns i:

* [Lägg till personalisering](personalization-build-expressions.md)
* [Personalization syntax](personalization-syntax.md)

## Arbeta med arrayer i Journey-uttryck {#arrays-in-journeys}

I de föregående avsnitten fokuseras på att iterera över arrayer i meddelandepersonalisering med hjälp av Handlebars, men du arbetar också med arrayer när du konfigurerar reseaktiviteter. I det här avsnittet beskrivs hur du använder arraydata från händelser i Journey-uttryck, särskilt när du skickar data till anpassade åtgärder eller använder arrayer med datasetuppslag.

>[!IMPORTANT]
>
>Reseuttryck har en annan syntax än Handlebars personalisering. I konfigurationen av resan (till exempel anpassade åtgärdsparametrar eller villkor) använder du [redigeraren för reseuttryck](../building-journeys/expression/expressionadvanced.md) med funktioner som `first`, `all` och `serializeList`. I meddelandeinnehåll använder du Handlebars syntax med `{{#each}}` -slingor.

### Skicka arrayvärden till anpassade åtgärdsparametrar {#arrays-to-custom-actions}

När du konfigurerar [anpassade åtgärder](../action/about-custom-action-configuration.md) måste du ofta extrahera värden från händelsearrayer och skicka dem som parametrar. I det här avsnittet beskrivs vanliga mönster.

Läs mer om hur du skickar samlingar i [Överför samlingar till anpassade åtgärdsparametrar](../building-journeys/collections.md#passing-collection).

#### Extrahera ett enskilt värde från en array

**Använd fall**: Hämta ett specifikt fält från en händelsearray som ska skickas som en frågeparameter i en GET-begäran.

+++ Visa exempelkod

**Exempelscenario**: Extrahera den första SKU:n med ett pris som är större än 0 från en produktlista.

**Exempel på händelseschema**:

```json
{
  "commerce": {
    "productListItems": [
      { "SKU": "SKU-1", "priceTotal": 10.0 },
      { "SKU": "SKU-2", "priceTotal": 0.0 },
      { "SKU": "SKU-3", "priceTotal": 20.0 }
    ]
  }
}
```

**Anpassad åtgärdskonfiguration**:

1. Konfigurera en frågeparameter (t.ex. `sku`) med typen `string` i den anpassade åtgärden
2. Markera det som `Variable` om du vill tillåta dynamiska värden

**Reseuttryck i åtgärdsparameter**:

```javascript
@event{YourEventName.commerce.productListItems.first(currentEventField.priceTotal > 0).SKU}
```

**Förklaring**:

* `@event{YourEventName}`: Refererar till din resehändelse
* `.first(currentEventField.condition)`: Returnerar det första arrayobjektet som matchar villkoret
* `currentEventField`: Representerar varje objekt i händelsearrayen när du gör en slinga genom den
* `.SKU`: Extraherar SKU-fältet från det matchade objektet
* Resultat: `"SKU-1"` (en sträng som är lämplig för åtgärdsparametern)

Läs mer om funktionen `first` i [Samlingshanteringsfunktioner](../building-journeys/expression/collection-management-functions.md).

+++

#### Skapa en lista med värden från en array

**Använd skiftläge**: Skapa en kommaavgränsad lista med ID:n som ska skickas som en frågeparameter (t.ex. `/products?ids=sku1,sku2,sku3`).

+++ Visa exempelkod

**Anpassad åtgärdskonfiguration**:

1. Konfigurera en frågeparameter (till exempel `ids`) med typen `string`
2. Markera den som `Variable`

**Reseuttryck**:

```javascript
serializeList(
  @event{YourEventName.commerce.productListItems.all(currentEventField.priceTotal > 0).SKU},
  ",",
  true
)
```

**Förklaring**:

* `.all(currentEventField.condition)`: Returnerar alla matrisobjekt som matchar villkoret (returnerar en lista)
* `currentEventField`: Representerar varje objekt i händelsearrayen när du gör en slinga genom den
* `.SKU`: Projicerar listan så att den bara innehåller SKU-värden
* `serializeList(list, delimiter, addQuotes)`: Kopplar listan till en sträng
   * `","`: Använd komma som avgränsare
   * `true`: Lägg till citattecken runt varje strängelement
* Resultat: `"SKU-1,SKU-3"` (lämpligt för en frågeparameter)

Läs mer om:

* [&quot;all&quot;](../building-journeys/expression/collection-management-functions.md)
* [`serializeList`](../building-journeys/functions/list-functions.md#serializeList)

Samlingshantering för anpassade åtgärder beskrivs i [Överför samlingar till anpassade åtgärdsparametrar](../building-journeys/collections.md#passing-collection).

+++

#### Överföra en array med objekt till en anpassad åtgärd

**Använd skiftläge**: Skicka en fullständig array med objekt i en begärandebrödtext (för POST eller GET med brödtext).

+++ Visa exempelkod

**Exempel på begärandetext**:

```json
{
  "ctxt": {
    "products": [
      {
        "id": "productA",
        "name": "Product A",
        "price": 20.1,
        "color": "blue"
      }
    ]
  }
}
```

**Anpassad åtgärdskonfiguration**:

1. Definiera `products` som typ `listObject` i begärandetexten
2. Markera den som `Variable`
3. Definiera objektfälten: `id`, `name`, `price`, `color` (varje blir mappningsbart)

**Resans arbetsytekonfiguration**:

1. I avancerat läge anger du mängduttrycket:

   ```javascript
   @event{YourEventName.commerce.productListItems.all(currentEventField.priceTotal > 0)}
   ```

1. I samlingsmappningens användargränssnitt:
   * Karta `id` → `productListItems.SKU`
   * Karta `name` → `productListItems.name`
   * Karta `price` → `productListItems.priceTotal`
   * Karta `color` → `productListItems.color`

Journey Optimizer konstruerar en array med objekt som matchar din åtgärdsnyttolaststruktur.

>[!NOTE]
>
>När du arbetar med händelsearrayer använder du `currentEventField` för att referera till varje objekt. Använd `currentDataPackField` för datakällsamlingar (Adobe Experience Platform). Använd `currentActionField` för anpassade åtgärdssvarssamlingar.

Läs mer i [Överför samlingar till anpassade åtgärdsparametrar](../building-journeys/collections.md#passing-collection).

+++

### Använda arrayer med datasetsökningar {#arrays-with-dataset-lookup}

När du använder [uppslagsaktiviteten för datauppsättningar](../building-journeys/dataset-lookup.md) kan du skicka en array med värden som uppslagsnycklar för att hämta inkapslade data.

**Exempel**: Sök efter produktinformation för alla SKU:er i en händelsearray.

+++ Visa exempelkod

**Uppslagskonfiguration för datauppsättning**:

Använd `list()` i fältet för söknycklar för att konvertera en arraysökväg till en lista:

```javascript
list(@event{purchaseEvent.productListItems.SKU})
```

Då skapas en lista med alla SKU-värden som ska slås upp i datauppsättningen. Resultaten är tillgängliga som en array på `context.journey.datasetLookup.<activityID>.entities` som du kan iterera igenom i meddelandet (se [Upprepa sökresultat för datauppsättningar](#dataset-lookup)).

+++

### Begränsningar och mönster {#array-limitations}

Tänk på dessa begränsningar när du arbetar med matriser under resor:

#### Ingen dynamisk slinga över matriser i reseflödet

Det går inte att skapa dynamiska slingor där en åtgärdsnod körs flera gånger för varje objekt i en array. Detta är avsiktligt för att förhindra prestandaproblem vid körning.

**Vad du inte kan göra**:

* Kör en anpassad åtgärd dynamiskt en gång per arrayobjekt
* Skapa flera resegrenar baserat på matrislängd

**Rekommenderade mönster i stället**:

1. **Skicka alla objekt samtidigt**: Skicka hela arrayen eller en serialiserad lista till en anpassad åtgärd som bearbetar alla objekt. Se [Skapa en lista med värden från en array](#arrays-to-custom-actions).

2. **Använd extern aggregering**: Låt ditt externa API acceptera flera ID:n och returnera kombinerade resultat i ett enda anrop.

3. **Förberäkning i AEP**: Använd [beräknade attribut](../audience/computed-attributes.md) för att förberäkna värden från arrayer på profilnivå.

4. **Extrahering av enstaka värden**: Om du bara behöver ett värde extraherar du det med `first` eller `head`. Se [Extrahera ett enskilt värde från en array](#arrays-to-custom-actions).

Läs mer i [Guardrutor och begränsningar](../start/guardrails.md).

#### Överväganden om matrisstorlek

Stora disksystem kan påverka resprestanda:

* **Händelsematriser**: Behåll händelsens nyttolaster under 50 kB totalt
* **Anpassade åtgärdssvar**: Svarsnyttolasterna ska vara under 100 kB
* **Uppslagsresultat för datauppsättning**: Begränsa antalet uppslagsnycklar och returnerade entiteter

### Fullständigt exempel: händelsematris till anpassad åtgärd {#complete-example}

Här är ett komplett arbetsflöde som visar hur du använder en händelsearray med en anpassad åtgärd.

**Scenario**: När en användare överger sin kundvagn skickar du kundvagnsdata till ett externt rekommendations-API för att få anpassade förslag och visar dem sedan i ett e-postmeddelande.

+++ Visa exempelkod

**Steg 1: Konfigurera den anpassade åtgärden**

Skapa en anpassad åtgärd &quot;GetCartRecommendations&quot;:

* **Metod**: POST
* **URL**: `https://api.example.com/recommendations`
* **Begärandetext**:

```json
{
  "cartItems": [
    {
      "sku": "string",
      "price": 0,
      "quantity": 0
    }
  ]
}
```

* Markera `cartItems` som typ `listObject` och `Variable`
* Definiera fält: `sku` (sträng), `price` (tal), `quantity` (heltal)

Läs mer i [Konfigurera en anpassad åtgärd](../action/about-custom-action-configuration.md).

**Steg 2: Konfigurera svarsnyttolast**

Konfigurera svaret i den anpassade åtgärden:

```json
{
  "recommendations": [
    {
      "productId": "string",
      "productName": "string",
      "price": 0,
      "imageUrl": "string"
    }
  ]
}
```

Läs mer i [Använd API-anropssvar](../action/action-response.md).

**Steg 3: Vidga åtgärden i resan**

1. Lägg till den anpassade åtgärden efter kundvagnsöverhoppningen
1. I avancerat läge för samlingen `cartItems`:

   ```javascript
   @event{cartAbandonment.commerce.productListItems.all(currentEventField.quantity > 0)}
   ```

1. Mappa samlingsfälten:
   * `sku` → `productListItems.SKU`
   * `price` → `productListItems.priceTotal`
   * `quantity` → `productListItems.quantity`

**Steg 4: Använd svaret i ditt e-postmeddelande**

Upprepa rekommendationerna i ditt e-postinnehåll:

```handlebars
<h2>We noticed you left these items in your cart</h2>
{{#each context.journey.events.cartAbandonment.productListItems as |item|}}
  <div class="cart-item">
    <p>{{item.name}} - Quantity: {{item.quantity}}</p>
  </div>
{{/each}}

<h2>You might also like</h2>
{{#each context.journey.actions.GetCartRecommendations.recommendations as |rec|}}
  <div class="recommendation">
    <img src="{{rec.imageUrl}}" alt="{{rec.productName}}" />
    <h3>{{rec.productName}}</h3>
    <p>${{rec.price}}</p>
  </div>
{{/each}}
```

**Steg 5: Testa konfigurationen**

Innan du kör en direktresa testar du den anpassade åtgärden med funktionen&quot;Skicka testbegäran&quot; i åtgärdskonfigurationen för att verifiera den inbyggda begäran och värdena.

1. Använd [provningsläget för resan](../building-journeys/testing-the-journey.md)
2. Utlös med exempelhändelsedata som innehåller en `productListItems`-array
3. Verifiera att den anpassade åtgärden tar emot rätt matrisstruktur
4. Kontrollera [åtgärdstestloggarna](../action/action-response.md#test-mode-logs)
5. Förhandsgranska e-postmeddelandet för att bekräfta att båda arrayerna visas korrekt

Läs mer i [Felsöka anpassade åtgärder](../action/troubleshoot-custom-action.md).

+++

## Bästa praxis {#best-practices}

Följ dessa metodtips när du itererar över kontextuella data för att skapa underhållande, högpresterande personalisering.

### Använd beskrivande variabelnamn

Välj variabelnamn som tydligt anger vad du itererar över. Detta gör koden mer läsbar och enklare att underhålla. Läs mer om [personaliseringssyntax](personalization-syntax.md):

+++ Visa exempelkod

```handlebars
<!-- Good -->
{{#each products as |product|}}
{{#each users as |user|}}
{{#each recommendations as |recommendation|}}

<!-- Less clear -->
{{#each items as |item|}}
{{#each array as |element|}}
```

+++

### Uttrycksfragment i slingor

När du använder [uttrycksfragment](use-expression-fragments.md) i `{{#each}}` -slingor bör du vara medveten om att du inte kan skicka loopomfattade variabler som fragmentparametrar. Fragment kan dock komma åt globala variabler som är definierade i meddelandeinnehållet utanför fragmentet.

+++ Visa exempelkod

**Mönster som stöds - Använd globala variabler:**

```handlebars
{% let globalDiscount = 15 %}

{{#each context.journey.actions.GetProducts.items as |product|}}
  <div class="product">
    <h3>{{product.name}}</h3>
    {{fragment id='ajo:fragment123/variant456' mode='inline'}}
  </div>
{{/each}}
```

Fragmentet kan referera till `globalDiscount` eftersom det har definierats globalt i meddelandet.

**Stöds inte - skicka loopvariabler:**

```handlebars
{{#each products as |product|}}
  <!-- This will NOT work as expected -->
  {{fragment id='ajo:fragment123/variant456' currentProduct=product}}
{{/each}}
```

**Tillfällig lösning**: Inkludera personaliseringslogiken direkt i slingan i stället för att använda ett fragment, eller anropa fragmentet utanför slingan.

+++

Läs mer om [att använda uttrycksfragment i slingor](use-expression-fragments.md#fragments-in-loops), inklusive detaljerade exempel och ytterligare tillfälliga lösningar.



### Hantera tomma arrayer

Använd `{{else}}`-satsen för att tillhandahålla reservinnehåll när en matris är tom. Läs mer om [hjälpfunktioner](functions/helpers.md):

+++ Visa exempelkod

```handlebars
{{#each context.journey.actions.GetRecommendations.items as |item|}}
  <div>{{item.name}}</div>
{{else}}
  <p>No recommendations available at this time.</p>
{{/each}}
```

+++

### Kombinera med villkorliga hjälpmedel

Använd `{{#if}}` i slingor för villkorligt innehåll. Läs mer om [villkorliga regler](create-conditions.md) och se exempel i avsnitten [Anpassade åtgärder](#custom-action-responses) och [Datauppsättningssökning](#dataset-lookup).

+++ Visa exempelkod

```handlebars
{{#each context.journey.actions.GetProducts.items as |product|}}
  <div class="product">
    <h3>{{product.name}}</h3>
    {{#if product.onSale}}
      <span class="badge">On Sale!</span>
    {{/if}}
    {{#if product.newArrival}}
      <span class="badge">New</span>
    {{/if}}
  </div>
{{/each}}
```

+++

### Begränsa iteration för prestanda

För stora arrayer bör du överväga att begränsa antalet iterationer:

+++ Visa exempelkod

```handlebars
<!-- Display only first 5 items -->
{{#each context.journey.actions.GetProducts.items as |product|}}
  {{#if @index < 5}}
    <div>{{product.name}}</div>
  {{/if}}
{{/each}}
```

+++

### Åtkomst till arraymetadata

Handlebars innehåller speciella variabler i slingor som hjälper till med avancerade iterationsmönster:

* `@index`: Aktuellt upprepningsindex (0-baserat)
* `@first`: Sant för den första iterationen
* `@last`: Sant för den senaste upprepningen

+++ Visa exempelkod

```handlebars
{{#each products as |product|}}
  <div class="product {{#if @first}}featured{{/if}}">
    {{@index}}. {{product.name}}
  </div>
{{/each}}
```

+++

>[!NOTE]
>
>Dessa hanterarfältsvariabler (`@index`, `@first`, `@last`) är bara tillgängliga i `{{#each}}` -slingor i meddelandepersonalisering. Om du arbetar med arrayer i Journey-uttryck (till exempel hämtar det första objektet från en array innan det skickas till en anpassad åtgärd) använder du arrayfunktioner som [`head`](../personalization/functions/arrays-list.md#head), [`first`](../building-journeys/expression/collection-management-functions.md) eller [`all`](../building-journeys/expression/collection-management-functions.md). Mer information finns i [Arbeta med arrayer i Journey-uttryck](#arrays-in-journeys).

## Felsökning {#troubleshooting}

Har du problem med upprepningen? I det här avsnittet beskrivs vanliga problem och lösningar.

### Matrisen visas inte

**Problem**: Din arrayiteration visar inget innehåll.

+++ Visa möjliga orsaker och lösningar

**Möjliga orsaker och lösningar**:

1. **Felaktig sökväg**: Verifiera den exakta sökvägen till arrayen baserat på kontextkällan:
   * För [händelser](#event-data): `context.journey.events.<event_ID>.<fieldPath>`
   * För [anpassade åtgärder](#custom-action-responses): `context.journey.actions.<actionName>.<fieldPath>`
   * För [datasökningar](#dataset-lookup): `context.journey.datasetLookup.<activityID>.entities`

2. **Arrayen är tom**: Lägg till en `{{else}}`-sats för att kontrollera om arrayen saknar data. Exempel finns i [Bästa tillvägagångssätt](#best-practices).

3. **Data är inte tillgängliga än**: Kontrollera att aktiviteten för anpassad åtgärd, händelse eller sökning efter datauppsättningar har körts innan meddelandeaktiviteten i ditt kundflöde.

+++

### Syntaxfel

**Problem**: Uttrycksvalideringen misslyckas eller meddelandet återges inte.

+++ Visa vanliga misstag

**Vanliga misstag**:

* Avslutande taggar saknas: Varje `{{#each}}` måste ha en `{{/each}}`. Granska [Interaktionssyntaxen &#x200B;](#syntax) för att se om strukturen är korrekt.
* Felaktigt variabelnamn: Kontrollera att variabelnamnet används konsekvent genom hela blocket. Mer information om namnkonventioner finns i [Bästa tillvägagångssätt](#best-practices).
* Felaktiga sökvägsavgränsare: Använd punkter (`.`), inte snedstreck eller andra tecken

+++

### Uttrycksfragment fungerar inte i slingor

**Problem**: Ett uttrycksfragment visar inte förväntat innehåll när det används i en `{{#each}}`-slinga eller visar tomma/oväntade utdata.

+++ Visa möjliga orsaker och lösningar

**Möjliga orsaker och lösningar**:

1. **Försöker skicka loopvariabler som parametrar**: Uttrycksfragment kan inte ta emot loopomfångsvariabler (som det aktuella upprepningsobjektet) som parametrar. Detta är en känd begränsning.

   **Lösning**: Använd något av följande tillfälliga lösningar:

   * Definiera globala variabler i meddelandet som fragmentet kan komma åt
   * Inkludera personaliseringslogiken direkt i slingan i stället för att använda ett fragment
   * Anropa fragmentet utanför slingan om det inte behöver loopspecifika data

2. **Fragment förväntar sig en parameter som inte är tillgänglig**: Om fragmentet har utformats för att ta emot specifika indataparametrar fungerar det inte korrekt när dessa parametrar inte kan skickas från en slinga.

   **Lösning**: Strukturera om ditt tillvägagångssätt så att du kan använda globala variabler som fragmentet har åtkomst till. Se [God praxis - Uttrycksfragment i slingor](#best-practices) för exempel.

3. **Felaktigt variabelomfång**: Fragmentet kanske försöker referera till en variabel som bara finns inom slingomfånget.

   **Lösning**: Definiera alla variabler som fragmentet behöver på meddelandenivå (utanför slingan) så att de är globalt tillgängliga.

Läs mer om [att använda uttrycksfragment i slingor](use-expression-fragments.md#fragments-in-loops), inklusive detaljerade förklaringar, exempel och rekommenderade mönster.

+++

### Testa dina iterationer

Använd [testläget &#x200B;](../building-journeys/testing-the-journey.md) för resan för att verifiera dina iterationer. Detta är särskilt viktigt när du använder [anpassade åtgärder](#custom-action-responses) eller [datauppsättningssökningar](#dataset-lookup):

+++ Visa teststeg

1. Starta din resa i [testläge](../building-journeys/testing-the-journey.md)
2. Utlös händelsen eller den anpassade åtgärden med exempeldata
3. Kontrollera [förhandsgranskningen av meddelandet](../content-management/preview.md) för att verifiera att iterationen visas korrekt
4. Granska testlägesloggar för eventuella fel (se [Loggar för testläge för anpassade åtgärder](../action/action-response.md#test-mode-logs))

+++

## Relaterade ämnen {#related-topics}

**Grundläggande om Personalization:** [Kom igång med personalisering](personalize.md) | [Lägg till personalisering](personalization-build-expressions.md) | [Personalization-syntax &#x200B;](personalization-syntax.md) | [Hjälpfunktioner](functions/helpers.md) | [Skapa villkorliga regler](create-conditions.md)

**Resekonfiguration:** [Om händelser](../event/about-events.md) | [Konfigurera anpassade åtgärder](../action/about-custom-action-configuration.md) | [Skicka samlingar till anpassade åtgärdsparametrar](../building-journeys/collections.md#passing-collection) | [Använd API-anropssvar i anpassade åtgärder](../action/action-response.md) | [Felsöka anpassade åtgärder](../action/troubleshoot-custom-action.md) | [Använd Adobe Experience Platform-data på resor](../building-journeys/dataset-lookup.md) | [Använd extra identifierare på resor](../building-journeys/supplemental-identifier.md) | [Skyddsritningar och begränsningar &#x200B;](../start/guardrails.md) | [Testa din resa](../building-journeys/testing-the-journey.md)

**Reseuttrycksfunktioner:** [Avancerad uttrycksredigerare](../building-journeys/expression/expressionadvanced.md) | [Funktioner för samlingshantering](../building-journeys/expression/collection-management-functions.md) (först, alla, sist) | [Listfunktioner](../building-journeys/functions/list-functions.md) (serializeList, filter, sort) | [Arrayfunktioner](../personalization/functions/arrays-list.md) (head, tail)

**Användningsexempel för Personalization:** [E-post om att kunden har lämnat en kundvagn](personalization-use-case-helper-functions.md) | [Meddelande om orderstatus](personalization-use-case.md)

**Meddelandedesign:** [Kom igång med e-postdesign](../email/get-started-email-design.md) | [Skapa push-meddelanden](../push/create-push.md) | [Skapa SMS-meddelanden](../sms/create-sms.md) | [Förhandsgranska och testa ditt innehåll](../content-management/preview-test.md)

